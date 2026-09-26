# Quizploit - Binary Exploitation



## Approach
(how you started, what you tried)
First i used cat on both the source code and binary. I found out we have to answer 0xD(13) questions to get the answer. Then i ran the instance
command nc chatelaine.cylabacademy.net 24625.

## Solution
It basically defined some stuff and then told me to run the code and also to do file and checksec on the binary.

<img width="870" height="924" alt="image" src="https://github.com/user-attachments/assets/fd03d84d-e260-45e0-ba3a-3fa285572699" />
It gave me some of the info required to answer the questions.
<img width="889" height="369" alt="image" src="https://github.com/user-attachments/assets/2d7dba51-e7ab-4197-adc8-d71f98bea7eb" />
I also had to look at the source code to answer some of the questions like the one about the size of the buffer.
When it asked for the buffer overflow vulnerability, there was one because the size of the input was larger than the size of the buffer.
Then I used this command to get the adress of win()
objdump -d vuln.2 | grep 'win'
It basically converted the binary into assembly and found the line on which win was written, which was its adress.





## Flag
academy{my_bIn@4y_3xpl0it_fL@g_5f0a9d30}

## Takeaway
I learnt how to properly use objdump and to always run a file and checksec.
