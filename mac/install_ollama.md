# Ollama
 - [Ollama Installation](https://ollama.com/download/mac)

### Ollama Commands

```
# Run a model in local
ollama run <model_name>
# ollama run llama2
```

#### Run a model from huggingface
 - Install huggingface package and download the desired model
```
# Install huggingface package
pip install huggingface-hub

# download the desired model
huggingface-cli download \
  TheBloke/MistralLite-7B-GGUF \
  mistrallite.Q4_K_M.gguf \
  --local-dir downloads \
  --local-dir-use-symlinks False
```

 - Create a model file using the following content
```
# ./downloads/Mistrallite
FROM ./downloads/mistrallite.Q4_K_M.gguf
```

 - Create the model from Modelfile
 ```
 !ollama create mistrallite -f Mistrallite
 ```

 - Run the model in your local
```
!ollama run mistrallite
```

Also follows the steps from here to import from pytorch & safetensors - [Importing (PyTorch & Safetensors)](https://github.com/ollama/ollama/blob/main/docs/import.md#importing-pytorch--safetensors)


### OpenAI Compatibility
 - [Ollama doc](https://ollama.com/blog/openai-compatibility)

 - Install OpenAI

```
!pip install openai
```

```
from openai import OpenAI

client = OpenAI(
  base_url = 'http://localhost:11434/v1',
  api_key='ollama', # required, but unused
)

chat_completion = client.chat.completions.create(
  model="llama2",
  messages=[{"role": "user", "content": "Hello world"}]
)

print(chat_completion.choices[0].message.content)
```
