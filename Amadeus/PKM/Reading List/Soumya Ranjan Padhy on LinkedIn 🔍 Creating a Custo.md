---
URL: "https://www.linkedin.com/posts/soumya-ranjan-padhy-70aaa814a_creating-a-custom-screen-size-hook-with-activity-7257926825870262273-XscR?utm_source=share&utm_medium=member_ios"
---

# Soumya Ranjan Padhy on LinkedIn: 🔍 Creating a Custom Screen Size Hook with Tailwind…

🔍 Creating a Custom Screen Size Hook with Tailwind Breakpoints Sometimes, we need to get the screen size programmatically to conditionally render components in React. I recently built a custom React hook using Tailwind CSS breakpoints for exactly this purpose, and I’ll tell you why it works for me. Instead of juggling a dozen boolean values, I wanted simplicity. This hook returns a single value – no fuss, just the current screen size based on Tailwind’s sm, md, lg, xl, and 2xl breakpoints. Now, I get precise control over which breakpoints are active, directly within my components, and it’s as close to real-time as you can get with JavaScript resizing. And yes, I know the resize event gets a lot of attention, but in my opinion, "matchMedia" isn’t always the most straightforward approach. Sometimes, clean simplicity (without too many listeners) makes life easier for me and, honestly, for my code. Responsive design doesn’t have to be complex. If you need a screen size detection hook that’s easy to read, returns just one value, and aligns with Tailwind’s framework, here’s one way to do it. Would you use this approach in your projects? Let’s hear your thoughts! 👇 Gist: [https://lnkd.in/g-EVPQuQ](https://www.linkedin.com/redir/redirect?url=https%3A%2F%2Flnkd%2Ein%2Fg-EVPQuQ&urlhash=46yz&trk=public_post-text)

- 
    
    [](https://media.licdn.com/dms/image/v2/D5622AQF5ZOTaCFGszw/feedshare-shrink_800/feedshare-shrink_800/0/1730357035264?e=2147483647&v=beta&t=KERCLJm8yr9l0VWhfxf0uH-uJ6vE5ilpndWA4fvVgcE)
    
    useScreenSize Hook
    

To view or add a comment, [sign in](https://www.linkedin.com/signup/cold-join?session_redirect=https%3A%2F%2Fwww%2Elinkedin%2Ecom%2Fposts%2Fsoumya-ranjan-padhy-70aaa814a_creating-a-custom-screen-size-hook-with-activity-7257926825870262273-XscR&trk=public_post_feed-cta-banner-cta)