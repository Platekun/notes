---
Note Type: "Fleeting"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "Work"
Last edited time: "February 29, 2024 12:52 PM"
Status: "Unprocessed"
Created time: "January 11, 2024 5:17 AM"
---

# Work Day (@January 11, 2024)

## Today's Tasks

[Untitled](Work%20Day%20(@January%2011,%202024)/Untitled%2087fd1259254244b28f0768dbd0bd94e7.csv)

## Today's Thoughts

```
Rules

{
	"extends": [
		"next/core-web-vitals",
		"plugin:react/recommended",
		"plugin:tailwindcss/recommended",
		"plugin:prettier/recommended",
		"plugin:boundaries/recommended"
	],
	"parser": "@typescript-eslint/parser",
	"plugins": ["@typescript-eslint", "boundaries"],
	"root": true,
	"parserOptions": {
		"project": "./tsconfig.eslint.json"
	},
	"ignorePatterns": ["./node_modules/", "./packages/**/node_modules/", "./public/", "./.tmp/", "./.next/"],
	"rules": {
		// Reason: prevent private env variables in front-end context
		"no-process-env": "error",
		"prettier/prettier": "warn",
		// Reason: Makes codebase feels clase as everything written is used.
		"no-unused-vars": "off",
		// Reason: Makes codebase feels clase as everything written is used.
		"@typescript-eslint/no-unused-vars": [
			"error",
			{
				"argsIgnorePattern": "^_"
			}
		],
		// Reason: Avoid stylish comments. Force a single common style of declaring functions to devs.
		"func-style": ["error", "expression"],
		// Reason: Avoid stylish comments. Force a single common style of declaring variables to devs.
		// This allows for camelCase components however we are aiming for PascalCase components.
		// Read More: https://github.com/typescript-eslint/typescript-eslint/issues/2607
		"@typescript-eslint/naming-convention": [
			"error",
			{
				"selector": "variable",
				"format": ["camelCase", "UPPER_CASE", "PascalCase"]
			},
			{
				"selector": ["function", "objectLiteralProperty", "objectLiteralMethod"],
				"format": ["PascalCase", "camelCase"],
				// Reason: https://stackoverflow.com/questions/71976394/ignore-classname-in-naming-convention
				"filter": {
					"regex": "[- ]",
					"match": false
				}
			}
		],
		// Reason: Avoid stylish comments. Force a single common style of declaring statements to devs.
		"curly": "error",
		// Reason: Enforce consistent usage of type exports.
		"@typescript-eslint/consistent-type-exports": "error",
		// Reason: Enforce consistent usage of array types. Verbosity over simplicity
		"@typescript-eslint/array-type": ["error", { "default": "generic" }],
		// Reason: Remove cognitive load. No need to add extra keywords.
		"@typescript-eslint/await-thenable": "error",
		// Reason: Remove cognitive load. Can be confusing when having multiple primitive types for the same value.
		"@typescript-eslint/ban-types": "error",
		// Reason: Remove cognitive load. Can be confusing to understand what is a type and what is not.
		"@typescript-eslint/consistent-type-imports": [
			"error",
			{
				"prefer": "type-imports"
			}
		],
		// Reason: Avoid misuse of promises.
		"require-await": "error",
		// Reason: Avoid stylish comments. Force a single common style of declaring functions to devs.
		"arrow-body-style": ["error", "always"],
		// Reason: Avoid stylish comments. Force a single common style of declaring strings to devs. Favor modern ES standards.
		"@typescript-eslint/restrict-plus-operands": "error",
		// Reason: Keep template expressions simple.
		"@typescript-eslint/restrict-template-expressions": "error",
		// Reason: Class method functions don't preserve the class scope when passed as standalone variables.
		"@typescript-eslint/unbound-method": "error",
		// Reason: A "floating" Promise is one that is created without any code set up to handle any errors it might throw.
		"@typescript-eslint/no-floating-promises": "error",
		// Reason: Avoid stylish comments. Force a single common style of declaring exports to devs.
		"import/no-default-export": "error",
		// Reason: Avoid stylish comments. Force a single common style of declaring methods to devs.
		"@typescript-eslint/method-signature-style": "error",
		// Reason: Avoid stylish comments. Force a single common style of returning async.
		// Reason: Let @typescript-eslint/return-await handle awaiting.
		"no-return-await": "off",
		"@typescript-eslint/return-await": ["error", "always"],
		"boundaries/element-types": [
			2,
			{
				"default": "disallow",
				"rules": [
					{
						"from": ["ui", "backend", "pages", "shared"],
						"allow": ["shared"]
					},
					{
						"from": ["ui", ["pages", { "family": "!api" }]],
						"allow": ["ui"]
					},
					{
						"from": ["backend", ["pages", { "family": "api" }]],
						"allow": ["backend"]
					},
					{
						"from": ["shared"],
						"allow": ["shared"]
					}
				]
			}
		],
		// Reason: It is often too easy to declare needless conditionals.
		"@typescript-eslint/no-unnecessary-condition": "error",
		// Reason: Avoid plain img for better performance
		"@next/next/no-img-element": "error",
		"no-restricted-imports": [
			"error",
			{
				"paths": [
					{
						"name": "next/router",
						"message": "Please import this from `@onesafe/hooks` instead."
					},
					{
						"name": "next/link",
						"message": "Please use our `Link` component from `@onesafe/design-system` instead."
					},
					{
						"name": "swr",
						"importNames": ["default"],
						"message": "Please use our `useRemoteData` hook from `@onesafe/ui-http` instead."
					},
					{
						"name": "swr/infinite",
						"importNames": ["default"],
						"message": "Please use our `usePaginatedData` hook from `@onesafe/ui-http` instead."
					},
					{
						"name": "swr/mutation",
						"message": "Please use our `useMutation` hook from `@onesafe/ui-http` instead."
					},
					{
						"name": "react-hook-form",
						"importNames": ["useForm"],
						"message": "Please use our `useForm` hook from `@onesafe/ui-hooks` instead."
					},
					{
						"name": "axios",
						"importNames": ["default"],
						"message": "Please a use a client instance returned by our `useHttp` hook from `@onesafe/ui-http` instead. Even better you can create a proper adapter for this resource if it doesn't exist already."
					}
				]
			}
		],
		// Reason: Makes use of React hooks easier
		"react-hooks/rules-of-hooks": "error",
		// Reason: Prevent useEffect shenanigans
		"react-hooks/exhaustive-deps": [
			"warn",
			{
				"additionalHooks": "(useRecoilCallback|useRecoilTransaction_UNSTABLE)"
			}
		],
		// Reason: Avoid stylish comments. Force a single common style of writing component props.
		"react/destructuring-assignment": ["error", "always", { "destructureInSignature": "always" }],
		// Reason: Promote usage of our built-in component.
		"react/forbid-elements": [
			"warn",
			{
				"forbid": [
					{ "element": "div", "message": "please use our `Stack` component from `onesafe/design-system` instead." },
					{ "element": "HStack", "message": "please use our `Stack` component from `onesafe/design-system` instead." },
					{ "element": "VStack", "message": "please use our `Stack` component from `onesafe/design-system` instead." }
				]
			}
		],
		// Reason: Avoid stylish comments. Force a single commo nstyle of declaring state.
		"react/hook-use-state": ["error", { "allowDestructuredState": true }],
		// Reason: Avoid stylish comments. Force a single common style of writing component props.
		"react/jsx-boolean-value": ["error", "always"],
		// Reason: Avoid stylish comments. Force a single common style of writing react fragments.
		"react/jsx-fragments": ["error", "element"],
		// Reason: Avoid stylish comments. Force a single common style of writing component event handlers.
		"react/jsx-handler-names": [
			2,
			{
				"checkLocalVariables": true,
				"checkInlineFunction": true
			}
		],
		// Reason: When components reach too far to the right of the editor, it is a good time to split it into smaller ones.
		"react/jsx-max-depth": ["error", { "max": 5 }],
		// Reason: Using the && operator to render some element conditionally in JSX can cause unexpected values being rendered, or even crashing the rendering.
		"react/jsx-no-leaked-render": ["error", { "validStrategies": ["ternary"] }],
		// Reason: Enforce consistent use of react fragments.
		"react/jsx-no-useless-fragment": ["error"],
		// Reason: Enforces coding style that user-defined JSX components are defined and referenced in PascalCase.
		"react/jsx-pascal-case": ["error"],
		// Reason: Avoid stylish comments. Force a single common style of writing component props.
		"react/jsx-sort-props": ["error", { "callbacksLast": true }],
		"react/no-array-index-key": ["error"],
		// Reason: Children should always be actual children, not passed in as a prop.
		"react/no-children-prop": "error",
		// Reason: Prevent component files from growing too large.
		"react/no-multi-comp": ["error"],
		// Reason: Creating components inside components (nested components) will cause React to throw away the state of those nested components on each re-render of their parent.
		"react/no-unstable-nested-components": ["error", { "allowAsProps": true }],
		// Reason: Avoid stylish comments. Force a single common style of declaring components.
		"react/function-component-definition": ["warn", { "namedComponents": "arrow-function" }]
	},
	"overrides": [
		// Reason: Next.js needs default exports for pages and API points
		{
			"files": ["src/pages/**/*", "src/pages/api/*"],
			"rules": {
				"import/no-default-export": "off"
			}
		},
		{
			"files": ["test/**/*", "next.config.js", "sentry.*.config.ts"],
			"rules": {
				"no-process-env": "off"
			}
		},
		{
			"files": ["**/*.cjs"],
			"parserOptions": {
				"sourceType": "script"
			},
			"parser": "esprima"
		},
		{
			"files": ["tailwind.config.js"],
			"rules": {
				"arrow-body-style": "off",
				"@typescript-eslint/naming-convention": "off"
			}
		},
		{
			"files": ["lambdas/**/*"],
			"rules": {
				"max-lines-per-function": "off"
			}
		},
		{
			"files": ["packages/**/*.tsx"],
			"rules": {
				"max-lines-per-function": ["error", { "max": 250 }]
			}
		},
		{
			"files": ["packages/**/*.ts"],
			"rules": {
				"max-lines-per-function": ["error", { "max": 100 }]
			}
		}
	],
	"settings": {
		"boundaries/elements": [
			{
				"type": "backend",
				"pattern": "backend/*"
			},
			{
				"type": "pages",
				"pattern": ["pages/*"],
				"capture": ["family"]
			},
			{
				"type": "ui",
				"pattern": "ui/*"
			},
			{
				"type": "shared",
				"pattern": "shared/*"
			}
		]
	}
}
```