# Introduction

In this practice, I'll try to make a streaming API call directly to Bedrock.

Streaming responses are useful when you want to start returning content immediately to the end user. You can display the output a few words at a time, instead of waiting for the entire response to be created.

-----------

Define the function: `get_streaming_response(prompt, streaming_callback)` to call the Bedrock streaming API.

We use Bedrock's `invoke_model_with_response_stream` function to make the call to the streaming API endpoint.
As response chunks are returned, this code extracts the chunk's text from the returned JSON and passes it to the provided callback method.