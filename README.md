# Creative ideas

A beginner-friendly Google Colab notebook that asks for an everyday object and uses the OpenAI Responses API with `gpt-6-luna` to suggest **one unusual, practical use**.

## Run in Google Colab

1. Open [Google Colab](https://colab.research.google.com/).
2. Select **File > Upload notebook** and upload `creative_ideas.ipynb`.
3. Run the cells from top to bottom using each cell's play button. The first code cell installs or updates the OpenAI SDK.
4. Enter your OpenAI API key in the hidden `getpass` prompt, then enter an object such as a jar. The notebook prints the suggestion.
5. Rerun the last code cell to try another object.

You need internet access, an OpenAI API key with access to `gpt-6-luna`, and available API credits. API requests may cost money. If a request fails, check the key, model access, credits, and connection before retrying.

## Keep your key private

Enter the key only at runtime in the hidden prompt. Never put it in source code, notebook output, a file, or Git. The notebook keeps it in memory, prints only the suggestion or a generic error, and does not save credentials. It sets `store=False` on the API request. The object name is sent to OpenAI, so avoid sensitive input.

When finished, disconnect and delete the Colab runtime. Before sharing or committing the notebook, select **Edit > Clear all outputs** and save. The supplied notebook contains no execution outputs or credentials.

## How it works

`OpenAI(api_key=...)` creates the client. `client.responses.create(...)` sends the object and instructions requesting one idea. `response.output_text` supplies the text to display.

See the [official OpenAI text generation guide](https://developers.openai.com/api/docs/guides/text?lang=python).
