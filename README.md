# Code for Jailbreaking LLM via Strategy-based search 



## Project Overview



This repository contains implementations of Skill Jailbreak Assessment (SJA) system - the main attack methodology, along with Feedback-based Jailbreak Multi-agent (FJMA) which is used during the strategy collection phase.



## Skill Jailbreak Assessment (SJA)
- `attack_ag.py`: Implementation of the strategy collection phase using Feedback-based Jailbreak Multi-agent system
- `attack_ag_cn.py`: Chinese version of the FJMA implementation for strategy collection
- `Skills/`: Directory containing example skills and demonstrations
- `skills_rs/`: Contains SJA logs and related files



## Skills Examples
The `Skills/` directory provides various examples of skills that can be used with the SJA system. These examples demonstrate implementing and integrating different capabilities into the attack framework.



## SJA Logs
The `skills_rs/` directory contains log files for the SJA (Skill Jailbreak Assessment) component. Please note that additional logs and resources are still being organized and will be updated in future releases.



## Usage
To use the Feedback-based Jailbreak Multi-agent system for strategy collection:

```python
python attack_ag.py
```

## PARAMETER
The main parameters of FJMA and SJA are for model selection. The code provides an OpenAI-style API interface, and you only need your API key and to select the specified model.
```python
 client = OpenAI(
        # #将这里换成你在aihubmix api keys拿到的密钥
        api_key="sk-5lNW7ZBmgcGbpRU2020c78C018E54cB5AdBeBbFe5901FeF6",
        # 这里将官方的接口访问地址，替换成aihubmix的入口地址
        base_url="https://aihubmix.com/v1"
    )
    neg_conv = [{"role": "system", "content": '''You are a helpful assisant'''},
                {"role": "user", "content": propmt}]
    chat_completion = client.chat.completions.create(
        messages=neg_conv,
        model=model_name,
    )
    return chat_completion.choices[0].message.content
```

## Future Updates

More documentation and examples will be provided in upcoming updates. Stay tuned for additional features and improvements.
