---
Note Type: "Permanent"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "Software Architecture"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Unprocessed"
Created time: "August 12, 2023 2:53 PM"
---

# Data Access: A Forgotten Cornern In Front-End Code

**Note**: *This article is an opinion, which means nothing I am writing here have any intention to insult the way you write software or that you should or shouldn't do something. There are multiple ways of organizing code, this is just one I have come to benefit from.*

**Note 2**: *Examples will be written in React.js as it is the most popular tool for building user interfaces however the ideas of this article could be extrapolated to be used with other tools.*

## Everyday Work

I have been a software development for a few years. During the first years of working in the industry, most of my conversation topics revolved around the different tools we could use in our project (I started in front-end, could you blame me?). With time I grew to appreciate that front-end development seems to be more oriented towards tooling. Most discussions on internet always talk about the new trendy tool in the space, however I consider this only makes us forget about an important aspect of our work, software design, which is something I believe we could learn from our fellow back-end developers.

Let's start with an example. Our employer needs us to create a component that should display a list of books by their title.

```jsx

const books = [
	{
		id: "Building a Second Brain: A Proven Method to Organize Your Digital Life and Unlock Your Creative Potential",
		authorName: "Thiago Forte"
	},
	/* Imagine there are more books listed on this array. */
];

const Books = () => {
	return (
		<div>
			<h2>Books List</h2>
		  <div>
	      {books.map(book => (
	        <div key={book.id}>
						<div>
							{book.title} by {book.authorName}
						</div>
					</div>
	      ))}
	    </div>
		</div>
	);
}
```

Up next, our employer comments we need to update our code to match what the design team has thought the app should look like. For this reason we meet them and are given the following changes:

- We need to make our code semantic and use proper elements for what is displayed.
- We need to have a color theme they created for our employer.
- We need to provide an empty state for our users in case they don't have books.

After implementing those changes, we end up with the following:

```jsx

/* ... */

const Books = () => {
  if (books.length === 0) {
		return (
			<section class="px-4 py-5 bg-gray-100">
				<h2 class="text-white">
					You don't have any books
				</h2>
			</section>
		);
	}

	return (
		<section class="px-4 py-5 bg-gray-100">
			<h2>Books List</h2>
		  <ul className="p-4">
	      {books.map(book => (
	        <li key={book.id}>
						<h3 className="text-white">
							{book.title} by {book.authorName}
						</h3>
					</li>
	      ))}
	    </ul>
		</section>
	);
}
```

After seeing our latest changes, the design team mentions that future features will need to make use of the same design, “*Better make it reusable somehow so we are consistent about our styles.*” which is a fair point. We update our code again and end up with:

```jsx

/* ... */

const UiSection = () => {
	/* ... */
}

const UiList = () => {
	/* ... */
}

const UiListItem = () => {
	/* ... */
}

const UiText = ({ as, color }) => {
	/* ... */
}

const Books = () => {
  if (books.length === 0) {
		return (
			<UiSection>
				<UiText as="h2" color="white">
					You don't have any books
				</UiText>
			</UiSection>
		);
	}

	return (
		<UiSection>
			<UiText as="h2" color="black">Books List</UiText>
		  <UiList>
	      {books.map(book => (
	        <UiListItem key={book.id}>
						<UiText as="h3" color="white">
							{book.title} by {book.authorName}
						</UiText>
					</UiListItem>
	      ))}
	    </UiList>
		</UiSection>
	);
}
```

So far, so good. Some time later our employer comes up to us and mentions they decided to store the books list in a database for reasons. They requests us to reach the back-end developer as they have provided us an enpoint to consume. A meeting later with the backend, we have a list of changes to apply:

- Drop the books array we have on the app.
- Use the `/api/books` to retrieve a list of books from their API.
- Make sure the UI doesn't crash completly if the endpoint fails for an unknown reason.

Those changes are clear enough, we make use of `swr` to handle this remote data and adjust our code accordingly:

```jsx
import useSWR from 'swr';
import axios from 'axios';

/* ... */

const Books = () => {
	const { data, error, isLoading } = useSwr("books-list", async () => {
		const axiosResponse = await axios.get("/api/books");

		return axiosResponse.data.books;
	});

	if (error) {
		return (
			<UiSection>
				<UiText as="h2" color="black">Books List</UiText>
				<UiText as="h3">Failed to load.</UiText>
			</UiSection>
		);
	}

  if (isLoading) {
		return (
			<UiSection>
				<UiText as="h2" color="black">Books List</UiText>
				<UiText as="h3">Loading...</UiText>
			</UiSection>
		);
	}

  /* ... */
}
```

For the last set of requirements, our employer mentioned they want to be able to edit the title of each book, the user should see an input when they click the title of a book and it will transform the element into an input which will submit the changes when pressing enter. They also mentioned the back-end developer will be in charge of providing another endpoint for this.

Another meeting later with the back-end developer, we have a new list of changes to apply:

- Add a different state for the UI, the edition mode.
- Convert the text into an input and submit the new name of the book.
- Use `/api/books/:bookId` to update an existing book.
- We are only allowed to send the title.
- Make sure the UI doesn't crash completly if the endpoint fails for an unknown reason.

This is a more complex feature however we work it out and came up with the following:

```jsx
/* ... */
import useSWRMutation from 'swr/mutation';
import { useForm }  from 'react-hooks-form';
import { useState } from 'react';

/* ... */

const BookItem = ({ book, onBookUpdated }) => {
	const [isEditing, setIsEditing] = useState

	const { register, handleSubmit } = useForm({
		defaultValues: {
			title: book.title,
		}
	});

	const { trigger, isMutating } = useSWRMutation('update-book', async (key, { arg }) => {
		const response = await axios.put(`/api/books/${book.id}`);
		
		return response.data.book;
	},
	{
		onSuccess: onBookUpdated
	});

	const onSubmit = handleSubmit(trigger);

	if(isEditing) {
		return (
			<UiListItem key={book.id}>
				<form onSubmit={onSubmit}>
					<input {...register('title')} disabled={isMutating} />
				</form>
			</UiListItem>
		);
	}

	return (
		 <UiListItem key={book.id}>
			<UiText as="h3" color="white">
				{book.title} by {book.authorName}
			</UiText>
		</UiListItem>
	);
};

const Books = () => {
	const { data, /* ... */, mutate } = useSwr(/* ... */);

	/* ... */

	const onBookUpdated = async (book) => {
		await mutate([ ...data, book ]);
	};

	/* ... */

	return (
		<UiSection>
			<UiText as="h2" color="black">Books List</UiText>
		  <UiList>
	      {books.map(book => <BookItem book={book} onBookUpdated={onBookUpdated} />)}
	    </UiList>
		</UiSection>
	);
}
```

Now, let's recapitulate all the code we have written so far:

```jsx
import useSWR from "swr";
import axios from "axios";
import useSWRMutation from "swr/mutation";
import { useForm } from "react-hooks-form";
import { useState } from "react";

const UiSection = () => {
  /* ... */
};

const UiList = () => {
  /* ... */
};

const UiListItem = () => {
  /* ... */
};

const UiText = ({ as, color }) => {
  /* ... */
};

const BookItem = ({ book, onBookUpdated }) => {
  const [isEditing, setIsEditing] = useState;

  const { register, handleSubmit } = useForm({
    defaultValues: {
      title: book.title,
    },
  });

  const { trigger, isMutating } = useSWRMutation(
    "update-book",
    async (key, { arg }) => {
      const response = await axios.put(`/api/books/${book.id}`);

      return response.data.book;
    },
    {
      onSuccess: onBookUpdated,
    }
  );

  const onSubmit = handleSubmit(trigger);

  if (isEditing) {
    return (
      <UiListItem key={book.id}>
        <form onSubmit={onSubmit}>
          <input {...register("title")} disabled={isMutating} />
        </form>
      </UiListItem>
    );
  }

  return (
    <UiListItem key={book.id}>
      <UiText as="h3" color="white">
        {book.title} by {book.authorName}
      </UiText>
    </UiListItem>
  );
};

const Books = () => {
  const { data, error, isLoading } = useSwr("books-list", async () => {
    const axiosResponse = await axios.get("/api/books");

    return axiosResponse.data.books;
  });

  if (error) {
    return (
      <UiSection>
        <UiText as="h2" color="black">
          Books List
        </UiText>
        <UiText as="h3">Failed to load.</UiText>
      </UiSection>
    );
  }

  if (isLoading) {
    return (
      <UiSection>
        <UiText as="h2" color="black">
          Books List
        </UiText>
        <UiText as="h3">Loading...</UiText>
      </UiSection>
    );
  }

  if (books.length === 0) {
    return (
      <UiSection>
        <UiText as="h2" color="white">
          You don't have any books
        </UiText>
      </UiSection>
    );
  }

  const onBookUpdated = (book) => {
	  mutate([...data, book]);
  };

  return (
    <UiSection>
      <UiText as="h2" color="black">
        Books List
      </UiText>
      <UiList>
        {books.map((book) => (
          <BookItem book={book} onBookUpdated={onBookUpdated} />
        ))}
      </UiList>
    </UiSection>
  );
};
```

If we were to enter a new React codebase today, this is somthing similar to what we'd probably find.

## Front-End Development Responsibilities

As software developers, our way of describing how our application should behave is by writing code (obviously). The code written represents logic, this is why we use using conditional statements, loops, logical operators, comparison operators, switch statements, and other primitives provided your programming language of choice. The written logic has a mix of “*concerns*” in it. Different parts of the logic are used for different purposes. If I tried to come up with a name for each of these concerns, I'd identify the following:

- Visual concerns: Code responsible visual output of the user interface.
- Infrastructure concerns: Code responsible for interacting with external systems.
- UX concerns: Code responsible for the behavior and user experience, including accessibility rules, business rules, and permission logic.

**Note**: *Notice that I am referring to “concerns” rather than “technologies” or “file type”.*

Interestingly, these concerns I identify somewhat of align to the responsibilities listed in a job offer for a front-end developer:

- “*Creating, mantain and test UI components that reflect what the design teams invisions for the app*”.
- “*Make use of the the different service(s) the back-end team provides via an HTTP API*”.
- “*Work with the product and UX team to implement new features*”.

**Note:** *There are obviously more responsibilities associated however we can come to an agreement that if we tried to summarize what a front-end developer does at its core, this pretty much describe its role.*

Let's proceed to identify those concerns in what we have done so far:

```jsx
import useSWR from "swr";
import axios from "axios";
import useSWRMutation from "swr/mutation";
import { useForm } from "react-hooks-form";
import { useState } from "react";

/* Visual Concern */
const UiSection = () => {
  /* ... */
};

/* Visual Concern */
const UiList = () => {
  /* ... */
};

/* Visual Concern */
const UiListItem = () => {
  /* ... */
};

/* Visual Concern */
const UiText = ({ as, color }) => {
  /* ... */
};

const BookItem = ({ book, onBookUpdated }) => {
  const [isEditing, setIsEditing] = useState;

	/* UX Concern */
  const { register, handleSubmit } = useForm({
    defaultValues: {
      title: book.title,
    },
  });

  const { trigger, isMutating } = useSWRMutation(
    "update-book",
    async (key, { arg }) => {
			/* Infrastructure Concern */
      const response = await axios.put(`/api/books/${book.id}`);

      return response.data.book;
    },
    {
			/* UX Concern */
      onSuccess: onBookUpdated,
    }
  );

  const onSubmit = handleSubmit(trigger);

	/* UX Concern */
  if (isEditing) {
    return (
      <UiListItem key={book.id}>
        <form onSubmit={onSubmit}>
          <input {...register("title")} disabled={isMutating} />
        </form>
      </UiListItem>
    );
  }

	/* Visual Concern */
  return (
    <UiListItem key={book.id}>
      <UiText as="h3" color="white">
        {book.title} by {book.authorName}
      </UiText>
    </UiListItem>
  );
};

const Books = () => {
  const { data, error, isLoading } = useSwr("books-list", async () => {
		/* Infrastructure Concern */
    const axiosResponse = await axios.get("/api/books");

    return axiosResponse.data.books;
  });

	/* UX Concern */
  if (error) {
    return (
      <UiSection>
        <UiText as="h2" color="black">
          Books List
        </UiText>
        <UiText as="h3">Failed to load.</UiText>
      </UiSection>
    );
  }

	/* UX Concern */
  if (isLoading) {
    return (
      <UiSection>
        <UiText as="h2" color="black">
          Books List
        </UiText>
        <UiText as="h3">Loading...</UiText>
      </UiSection>
    );
  }

	/* UX Concern */
  if (books.length === 0) {
    return (
      <UiSection>
        <UiText as="h2" color="white">
          You don't have any books
        </UiText>
      </UiSection>
    );
  }

	/* UX Concern */
  const onBookUpdated = (book) => {
	  mutate([...data, book]);
  };

	/* Visual Concern */
  return (
    <UiSection>
      <UiText as="h2" color="black">
        Books List
      </UiText>
      <UiList>
        {books.map((book) => (
          <BookItem book={book} onBookUpdated={onBookUpdated} />
        ))}
      </UiList>
    </UiSection>
  );
};
```

## A Back-End Perspective

I would say we have made a decent job in fulfilling our responsibilities as we have:

- Made our components reusable while following the design and semantic guidelines.
- Made proper consumption of the data provided by the backend team.
- Made proper interpretation of what our employer wants for the application.

However that is mainly from our perspective, If a developer with more back-end development experience saw our code, I can somewhat imagine them pointing out a few aspects we could improve upon:

- They would probably mention we should move the endpoint calls to a “*service*”.
- They would probably mention we lack of “*a clean way*” of accesing data as we would need to perform `filter` operations everytime they wanted to iterate over the books or that data is not located in a central place but rather spread through the component tree.
- They would probably mention we don't have an agreement in what our objects should look like and what operations we can do with them.

Trying not to come up with retaliation it's hard sometimes, as we think our code is simple enough for others to understand and here is a fellow developer stating our work is a mess. If we try to see between lines, they all are talking about a lack of boundaries between our concerns. They feel we have too many concerns at plain sight, and given their background it makes sense to point these things out. But which concerns are they referring to?

“[*For real world apps, it is generally impossible by construction for a client to create and maintain an accurate replica of the data they are supposed to be able to query and share ownership of.*](https://acko.net/blog/apis-are-about-policy/)”

In React-land, people use to mention the term "*server state*”. If we were to google "*server state react*” we would find multiple articles talking about replacing redux stores ,`useState` and `useEffect`  with technologies such as SWR and TanStackQuery. The term “*server state*” could be used as a broad definition to refer to refer to:

- The mechanisms we use to perform queries
- The mechanisms we use to perform mutations.
- The mechanisms we use to perform cache and cache invalidation.
- Reacting to these operations (`isLoading`, `isError`, etc.).

By these definitions, this server state problem feels solved as we just need to leverage SWR or TanStackQuery and call it a day. However I feel this is the part where we focus too much on the tooling instead of the theory. It didn't feel our code reviewer was trying to say SWR and friends are a bad choice. They commented in terms of “*data access*” and “*data shape*”.

/ Continue here

In back-end development, there is a much clearer notion about the different boundaries of each concern. The terms “Model”, “View” and “Controller” may feel familiar, when googling these terms we find they are usually referred as “*layers*” in the way they organize certain portions of code, each one of those concepts handle different concerns for the back-end code.

 (I *think* these are referred as “*layers*”). If we wereIs

I would answer “*data access***”**

 having **boundaries** between these concerns. 

 to refer to the aspects of retreiving data from the server, caching responses, performing mutations and providing the proper boolean flags like . for the UI to react (pun intented) accordingly.  

But what about the objects resulting from performing queries and mutations?

Going back to what our fellow code reviewer commented, in back-end development there is the notion of separating the way data is accessed from performing operations. This is usually referred as a “*data access layer*”.

---

---

---

---

This is where the popular term for “*server state*” enters the picture. Server state is somewhat understood to be data whose nature is born from the communication with the server and this is bounded to libraries such as SWR and TanStackQuery as they provided different utilities such as caching and retrying.

As caching is done by SWR (or other libraries), it is up to us how we manage that data and this is a forgotten piece in most cases. Data retrieval.

The other part of the my point is object management, sometimes confused for “*server state*”.

- Having a canonical shape for our data is good.
- Objects computed from the server should have an id.
- Having a single and standard way of accesing our objects make it easier to abstract upon.

I think one of the tricky things about Front-End development is that 

Libraries such as swr and react-query do really help in this regard however

More often than note I end up with business requirements that are too much of a headache for me to do, even simple things.

An Additional Concern.

In one of my jobs, I had a coworker, he was a back-end developer who used Ruby on Rails.  My coworker at the time, a back-end developer who used Ruby On Rails, always answered my questions however he always mentioned that it is not about the amount of tools but their purpose. It was thanks to him I read about Ruby On Rails and the way they structured apps. 

During one of our conversations, he mentioned Sandy Metz

I don't consider the place where your code runs to be an excuse to ignore the knowledge you can obtain from the other side.

Then I played a round some for Ember.js in some side projects.

When I shared some of my interests in learning

Is there any way of applying such concepts in Front-End?.

One of the things that have always made me grind my reels is the fact most front-end apps I have worked in do not have a clear distintion in the responsibilities of the code. Let me elllaborate:

## Visual Concerns

## Business Concerns

## Infrastructure Concerns

I think we can identify three things:

- Application logic: Is all about how the user interacts with the app. [https://www.apisec.ai/blog/business-logic-vs-application-logic#:~:text=Business logic refers to the,rules within a specific application](https://www.apisec.ai/blog/business-logic-vs-application-logic#:~:text=Business%20logic%20refers%20to%20the,rules%20within%20a%20specific%20application).
    - Business logic: This
- Application / Presentation logic: Logic that allows the user to comply with the business logic.
    - Event handlers: They are the bridge between the user intention and the logic that needs to be performed.
    - Rendering: A more specific version of application logic. Controls what the users ends up seeing on their screen.
- Infrastructure logic:
    - Lookup and cache management of domain objects.
    - Adapter
- Business logic:
    - Invokking
    - If you are on front-end this usually involves talking to an API).
- Your specific domain logic (). → This is a common practice. Encapsulating functions that send something to the api.
- 

## Consequences

- 

## Possible Use Cases

-