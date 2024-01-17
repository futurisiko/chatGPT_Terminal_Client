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
chatGTP -m <MODEL> -t <NUMBER> -mt <NUMBER> 'Question in single quotes'
```

Examples: 
```
chatGPT 'Write a powershell oneliner to send a command to a server list'
```
```
chatGPT -t 0.5 'Write a script in python to open a socket'
or
chatGPT -t 1,3 'Write a script in python to open a socket'
```
Help:
```
chatGPT -h

Options

-m or --model <MODEL>: select the model to use.
     If not specified default value is 'gpt-3.5-turbo'.
     You can try 'gpt-4' to ask more complex questions/tasks.

-t or --temperature <0.0-2.0>: set the temperature used.

     If not specified default value is 0.5.
     Lower temperature (e.g. 0.0 / 1.0):
     chatGPT will choose words with a higher probability of occurrence.
     Useful when we want to complete something with the most probable value/phrase/word.
     Higher temperature (e.g. 1.0 / max 2.0):
     Very creative but inconsistent answers.
     Above 1.5 very inconsistent.

-mt or --max-tokens <NUMBER>: the maximum number of tokens to generate in completion.

     If not specified default value is 4000.
     Your prompt + max_tokens can't exceed the context lenght of the model.

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

 chatGPT use 3 parameters: model, max_token and temperature.

 - model =     select which model to use. 
               If not specified default is gpt-3.5-turbo. 
               You can try gpt-4 to ask more complex question/tasks.

 - max_tokens = the maximum number of tokens to generate in completion. 
                Default is 4000. 
                Your prompt + max_tokens can't exceed the context lenght of the model.

 - temperature = defines the type of processing applied to answer. 
                 Default is 0.5 .
                
## ATTENTION
You have to escape double quotes in questions: ``` e.g. \" ```.<br>
For single quote ``` ' ``` in questions do ***NOT*** try to escape them.<br>
Use backtick ``` ` ``` instead!
