---
Note Type: "Fleeting"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "Work"
Last edited time: "January 26, 2024 12:19 PM"
Status: "Unprocessed"
Created time: "January 26, 2024 6:56 AM"
---

# Work Day (@January 26, 2024)

## Today's Tasks

[Untitled](Work%20Day%20(@January%2026,%202024)/Untitled%20789c2849e7664a9db9ac9786d9285f98.csv)

## Today's Thoughts

```json
import { logger } from '@onesafe/shared/logger';
import type { ClientInstance } from '@onesafe/shared/types';
import { resolveHttpError } from '@onesafe/ui-http';

type CreateAdapterOptions<TInput, TOutput, TDeserializedOutput = TOutput> = {
	name: string;
	requester: (options: { input: TInput; httpClient: ClientInstance }) => Promise<TOutput>;
	deserializer?: (response: TOutput) => TDeserializedOutput;
};

export const createAdapter = <TInput, TOutput, TDeserializedOutput = TOutput>(
	options: CreateAdapterOptions<TInput, TOutput, TDeserializedOutput>
) => {
	const { requester, deserializer } = options;

	logger.info({ ...options }, 'Creating adapter...');

	const adapter = async (adapterOptions: {
		input: TInput;
		httpClient: ClientInstance;
	}): Promise<TDeserializedOutput> => {
		const { input, httpClient } = adapterOptions;

		logger.info({ ...options }, 'Executing adapter...');

		try {
			const response = await requester({ input, httpClient });

			logger.info({ ...options, response }, 'Adapter execution completed.');

			if (deserializer) {
				logger.info({ ...options, response }, 'Deserializing adapter response...');

				const deserialized = deserializer(response);

				logger.info({ ...options, response }, 'Adapter response deserialization completed...');

				return deserialized;
			}

			return response as TDeserializedOutput;
		} catch (error) {
			logger.error({ ...options, error }, 'Adapter execution failed.');

			throw resolveHttpError({ error });
		}
	};

	logger.info({ ...options }, 'Adapter creation completed.');

	return adapter;
};
```