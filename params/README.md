# Introduction

Create the helper function: `get_inference_parameters(model)` to get inference parameters based on the model.

- Each model provider has its own set of inference parameters. This function returns a set of custom parameters based on the first portion of each model's id.

- You can experiment with different inference parameters using the Text playground in the Bedrock console. You can use the View API request button in the playground to get the parameters to use in your code.

Build the function: `get_text_response(model, input_content)` to call Bedrock with the appropriate inference parameters for the model.

- Here we are instantiating the LangChain Bedrock client, setting the model, and getting the inference parameters for the model.

# Run the script

Run the script from the terminal.

`python params.py "ai21.j2-ultra-v1" "Write a haiku:"
`