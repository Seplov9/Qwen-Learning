# 百炼API Key
- 阿里云网址：https://www.aliyun.com
- 搜索：“大模型服务云平台百炼”
- 百炼网址：https://bailian.console.aliyun.com
- 百炼网址：https://bailian.console.aliyun.com/cn-beijing
- 手册：https://bailian.console.aliyun.com/cn-beijing?tab=api#/api
- 国外阿里云网址：https://www.alibabacloud.com
- 国外百炼网址：https://modelstudio.console.alibabacloud.com

# 配置
- 网址：https://huggingface.co/Qwen/Qwen3.5-2B

- 当前Shell  
`$ export OPENAI_BASE_URL="[http://localhost:8000/v1](https://dashscope.aliyuncs.com/compatible-mode/v1)"`  
`$ export OPENAI_API_KEY="sk-xxx"`

- 全局配置  
`$ echo 'export OPENAI_BASE_URL="https://dashscope.aliyuncs.com/compatible-mode/v1"' >> ~/.bashrc`  
`$ echo 'export OPENAI_API_KEY="sk-xxx"' >> ~/.bashrc`

# 代码
```python
from openai import OpenAI
# Configured by environment variables
client = OpenAI()

messages = [
    {"role": "user", "content": "Give me a short introduction to large language models."},
]

chat_response = client.chat.completions.create(
    model="qwen3.5-plus",
    messages=messages,
    max_tokens=32768,
    temperature=1.0,
    top_p=1.0,
    presence_penalty=2.0,
    extra_body={
        "top_k": 20,
    }, 
)
print("Chat response:", chat_response.choices[0].message.content)

```
