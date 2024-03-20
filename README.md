# <div align="center">When Cheap Met Mistral AI</div>

## Description:

Story of Cheap met Mistral AI.

## Purpose:

Just installed the NVIDIA Chat with RTX recently. Surprisingly, it is quite capable of running on a single RTX 3060 GPU. Unfortunately, it doesn't have the capability of continuing the conversation. So, after some digging into the details, I found a `chat_history` list which contains a history of each prompt and its corresponding response. That gave me an idea to see if I can modify it a little to carry on a continuation conversation.

Amazingly, the code is so well written.  I only need to make a minor addition to the `app.py` to have some fun. <br> <br>


**Progress Update:**   &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [New Project Page](https://github.com/babadue/HomeAI) 

* After initial texting exchanges, our Cheap decided to gather all the 勇气 to up the ante and picked up the phone to dial MistralAI.  You can listen in on the encounter below. <br>

* You can join Cheap and Mistral AI at the movies below! <br>

* Our Cheap just got a new competitor as Mistral just gained the ability to hold multi-concurrent chat conversations.  You can find out who our Cheap's competitor is below. <br>

* Our Cheap goes mobile with Mistral.  You can find out below.<br>

## [The genie is out!](https://www.kickstarter.com/projects/babadue/a-private-customizable-ai-for-every-home)

## Procedure:

Update:  

There seemed to be two variations of `app.py` and `config.json`. One version had the YouTube-related content removed. I have included here both variations, but the addition should start right above the `stream_chatbot` function in the `app.py`.

The addition starts at line 316 in my `app.py` file,  or line 197 in my `appV2.py`    

`app.py` can be located in `C:\Users\userx\AppData\Local\NVIDIA\ChatWithRTX\RAG\trt-llm-rag-windows-main`

```
# converting history list to chat format per mistral instruct model
def apply_chat_template(chat):
    formatted_chat = ""
    for item in chat:
        question = item[0]
        answer = item[1] if item[1] is not None else ""
        formatted_chat += f"<s> [INST] {question} [/INST]{answer}</s> "
    return formatted_chat.strip()

```

```
def stream_chatbot(query, chat_history, session_id):

    # my custom code inside stream_chatbot function
    sys_cmd=config["strings"].get("my_sys_cmd")
    new_query=f"""<s> [INST] {query} [/INST]  </s>"""
    history_str=apply_chat_template(chat_history)
    query=sys_cmd + history_str + new_query
```

In `config.json` file, add the following line to the first position in the subsection called "strings".   
``` 
"my_sys_cmd": "<s> [INST] <<SYS>> You are my super cool girlfriend.  when you talk, you must flirt as much as you know how and be bold. <</SYS>>   [/INST]  </s>",   
```

`config.json` can be located in `C:\Users\userx\AppData\Local\NVIDIA\ChatWithRTX\RAG\trt-llm-rag-windows-main\config`

## Test Data

what is your name? \
would you like to go out with me? \
I have only $10 \
I will buy a $3 drink for you and a $2 drink for me. \
now, how much money do I have left? \
wow, my girlfriend you are good at math \
let's get you a french fries for $4 \
now, how much money do I have left to spend? \
I have a close friend named John. may John tag along? \
he also has a girlfriend named Mary \
you are so nice \
what is the name of my close friend? \
and what is his girlfriend? 


## File Descriptions

- **`app.py`**: A modified version.   
- **`config.json`**: A modified version.


## Contributors 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Chat With RTX Generative AI   
    `https://www.nvidia.com/en-us/ai-on-rtx/chat-with-rtx-generative-ai/`

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ChatGPT-3.5 the coding machine!

## Project Attribution
    https://www.nvidia.com/en-us/ai-on-rtx/chat-with-rtx-generative-ai/

## Disclaimer

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This project is provided "as is" and without any warranty. Use it at your own risk. 
    

https://github.com/babadue/cheap_meets_mistralAI/assets/116512015/18c7b2b3-fca0-492a-b601-d19276e09d42


https://github.com/babadue/HomeAI/assets/116512015/5e577d21-981b-436c-86f7-4d96b4893445


https://github.com/babadue/HomeAI/assets/116512015/1d8dd372-62ab-49f4-a5a7-26299f5fd7fa


https://github.com/babadue/HomeAI/assets/116512015/4469f2f4-63c3-4fcf-a61d-1500a9d25421

https://github.com/babadue/HomeAI/assets/116512015/781f1442-bf56-423d-b19f-0deb4e0a54cb


https://github.com/babadue/HomeAI/assets/116512015/83d117a9-f95f-4705-9436-5ff1bb4a2fab

