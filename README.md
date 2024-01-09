# chatGPT TERMINAL CLIENT

A simple script to query ***one direct question / task*** to chatGPT via terminal.<br>
It doesn't remember questions made previously like the normal web chat.<br> 
Interaction is not the main focus of this script.<br>
Its main porpuse is to use chatGPT as a ***powerful search-engine / terminal-tool*** directly via terminal.<br>
<br>
Remember that chatGPT is also capable to answer in multiple/alternative ways.<br>
Play with its "***temperature***" to have the ***most common answer or a variety of different creative answers***.
<br>

Usage: 
```
chatGTP [Options] 'Question in single quotes'
```

Examples: 
```
chatGPT 'Write a oneliner in powershell to get a reverse shell'
```
```
chatGPT -t 0.5 'Write a script in python to open a socket'
or
chatGPT -t 1,3 'Write a script in python to open a socket'
```
Help:
```
chatGPT -h

Options:
-t or --temperature <0.0-1.0>: set the temperature used.

     If not specified default value is 1.0.
     Lower temperature (e.g. 0.0 / 1.0):
     chatGPT will choose words with a higher probability of occurrence.
     Useful when we want to complete something with the most probable value/phrase/word.
     Higher temperature (e.g. 1.0 / max 2.0):
     Very creative but inconsistent answers.
     Above 1.5 very inconsistent.

-m or --max-tokens <NUMBER>: the maximum number of tokens to generate in completion.

     If not specified default value is 4000.
     1000 tokens =~ 750 words.
     Your prompt + max_tokens can't exceed the context lenght of the model.
     Normal models have a context lenght of 2048. New ones accept up to 4096.

-h or --help: print this help.

*** Attention ***
You have to escape double quotes in questions: e.g. \"
For single quote ' do NOT try to escape them.
Use backtick ` instead!
```
## SETUP
It's a common script made for Linux system. It uses ```curl``` to query chatGPT, ```jq``` to process the JSON and ```eval``` to execute the curl query. On Kali Linux and other Linux systems these tools are installed by default. You just have to give to it the execution permission:
```
chmod +x ./chatGPT
```
If you want to implement it directly in your system you just have to copy it in your user local bin folder. For example in Kali use the following command:
```
sudo cp chatGPT /usr/local/bin
```
If you are going to use it in a real working enviroment ***PLEASE*** pay attention to permissions you will give to this script.

## REMEMBER TO ADD YOUR API KEY

To add it modify the script with a text editor.
You can find the variable "TOKEN" at the beginning of the code.
If you do not have an API key go to:
```
https://beta.openai.com/account/api-keys
```
Subscribe and require it!

## DESCRIPTION:

chatGPT use 2 parameters: max_token and temperature.

- max_tokens = the maximum number of tokens to generate in completion of your question.
               Default script value is = 4000.
               To understand what does it mean think that 1000 tokens =~ 750 words.
               Your prompt + max_tokens can't exceed the context lenght of the model.
               Normal models have a context lenght of 2048.
               New ones accept 4096.

- temperature = defines the type ("creativity") of processing applied to answer.
                Default script value is = 1.0. 
                Lower values (e.g. 0.0 / 1.0) mean that chatGPT will choose words with a higher probability of occurrence.
                Useful when we want to complete something with the most probable value/phrase/word. 
                Higher values (e.g. 1.0 / max 2.0) instead could create very creative but inconsistent answers.
                Above 1.5 very inconsistent.
                
## ATTENTION
You have to escape double quotes in questions: ``` e.g. \" ```.<br>
For single quote ``` ' ``` in questions do ***NOT*** try to escape them.<br>
Use backtick ``` ` ``` instead!
