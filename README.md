# simple_openai

`simple_openai.py` defines two classes, `SimplePrompt` and `SimpleOpenAI`, that are used to interact with the OpenAI API for generating text. 

The `SimplePrompt` class is used to create prompts for the OpenAI API. It has methods for setting and adding prompts, clearing the prompt list, and getting the prompt list. The `SimpleOpenAI` class is used to make requests to the OpenAI API using the prompts created by the `SimplePrompt` class. 

The `SimpleOpenAI` class has several attributes that are used to configure the API request, such as the model to use, the temperature and top_p values for text generation, and the maximum number of tokens to generate. It also has a method for adding the generated text to a history list. 

Overall, this code provides a simple interface for generating text using the OpenAI API.

## Use

```python
import simpleopenai
from simpleopenai import SimpleOpenAI

openai_key = 'your openai api key'
simp_ai = SimpleOpenAI(openai_key)

# set a prompt
simp_ai.prompts.set_prompt('user','What is the airspeed velocity of an unladen swallow?')
# request a completion
response = simp_ai.request()
```

This code defines two classes: `SimplePrompt` and `SimpleOpenAI`.

`SimplePrompt` is a class that helps build prompts for the `SimpleOpenAI` class. It has the following methods:

- `__init__(self, system_role)`: Initializes the class with a system role and an empty message list. The `system_role` parameter sets the role of the system, which is used to identify the prompts that are not user-generated.
- `clear(self)`: Clears the message list.
- `set_prompt(self, role, msg)`: Sets a prompt with the given `role` and `msg`. If the role is "system", it updates the system prompt.
- `add_prompt(self, role, msg)`: Adds a prompt with the given `role` and `msg` to the message list. If the role is "system", it updates the system prompt.
- `add_prompts(self, prompt_array)`: Clears the message list and adds prompts from the `prompt_array`. Each prompt in `prompt_array` is a list with two elements: the `role` and the `msg`.
- `get_prompt_list(self)`: Returns the list of prompts, which includes the system prompt and the message list.

`SimpleOpenAI` is a class that uses the OpenAI API to generate responses to prompts. It has the following attributes:

- `MODEL`: The name of the OpenAI model to use.
- `prompts`: A `SimplePrompt` object that contains the prompts to send to the OpenAI API.
- `temperature`: The sampling temperature to use when generating responses.
- `top_p`: The top_p value to use when generating responses.
- `n`: The number of responses to generate.
- `stop`: The token to use to stop generating responses.
- `max_tokens`: The maximum number of tokens to generate.
- `presence_penalty`: The presence penalty to use when generating responses.
- `logit_bias`: The logit bias to use when generating responses.
- `user`: The name of the user sending the prompts.
- `history`: A list of dictionaries representing the history of queries and responses.

`SimpleOpenAI` also has the following methods:

- `__init__(self, api_key)`: Initializes the class with the OpenAI API key, sets the default prompts, and initializes the history.
- `add_to_hist(self,messages,responses)`: Adds the `messages` and `responses` to the history.
- `request(self)`: Sends the prompts to the OpenAI API and returns the responses. The prompts are obtained from the `prompts` attribute, and the other parameters are set using the attributes of the class. The responses are added to the history before they are returned.