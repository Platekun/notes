---
Note Type: "Fleeting"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "Work"
Last edited time: "February 29, 2024 1:31 PM"
Status: "Unprocessed"
Created time: "February 29, 2024 5:50 AM"
---

# Work Day (@February 29, 2024)

## Today's Tasks

[Untitled](Work%20Day%20(@February%2029,%202024)/Untitled%2079de342260024b96bf24dc3c71bf94e8.csv)

## Today's Thoughts

- I'm pending to add these rules:

```json
		// Reason: When components reach too far to the right of the editor, it is a good time to split it into smaller ones.
		"react/jsx-max-depth": ["error", { "max": 5 }],		
		"react/hook-use-state": ["error", { "allowDestructuredState": true }],
		// Reason: Avoid stylish comments. Force a single common style of writing component event handlers.
		"react/jsx-handler-names": [
			2,
			{
				eventHandlerPrefix: 'handle',
				eventHandlerPropPrefix: 'on',
				checkLocalVariables: true,
				checkInlineFunction: true
			}
		],
```