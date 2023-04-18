# simple_openai

`simple_openai.py` defines two classes, `SimplePrompt` and `SimpleOpenAI`, that are used to interact with the OpenAI API for generating text. 

The `SimplePrompt` class is used to create prompts for the OpenAI API. It has methods for setting and adding prompts, clearing the prompt list, and getting the prompt list. The `SimpleOpenAI` class is used to make requests to the OpenAI API using the prompts created by the `SimplePrompt` class. 

The `SimpleOpenAI` class has several attributes that are used to configure the API request, such as the model to use, the temperature and top_p values for text generation, and the maximum number of tokens to generate. It also has a method for adding the generated text to a history list. 

Overall, this code provides a simple interface for generating text using the OpenAI API.
