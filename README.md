# Website to Gradio Flight Assistant Chatbot With Tools

Example of a [Gradio](https://www.gradio.app/) Chatbot with Tools integration.

Credit LLM Engineering week 2 / day 4 project [here](https://github.com/ed-donner/llm_engineering/blob/main/week2/day4.ipynb).

This project is an example of a chat interface using Gradio UI and it will call the `chat` function as defined in [main.py](/main.py). 

When the message is sent to the OpenAI SDK, a list of available tools is passed into the API call. These tools are defined using a specific dictionary structure which is in the [tools.py](/tools.py) file. When the response comes back from the OpenAI SDK there is a `while` loop implemented that checks if there are tool calls and a `while` loop is used so that multiple tool calls in the same response can be made and it will call the `handle_tool_calls` function which then calls the specific function, essentially, based on the function name sent back by the LLM payload (`message.tool_calls.tool_call.function.name`). All the ticket price data is stored in an Sqlite DB but this can be a PostgresDB, an external API or any data source.

## Install and Run

```bash
uv run main.py
```
