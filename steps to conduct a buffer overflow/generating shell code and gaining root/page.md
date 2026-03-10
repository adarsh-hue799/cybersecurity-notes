Now, using msfvenom:\
\
-p is for payload type\
EXITFUNC=thread is for stability of the payload\
-f is for filetype (here c)\
-a is for architecture (x86)\
-b is for badchars\
\
![](image.png)\
\
In the python script:\
\
Here, we have added some padding \[ b\"\\x90\" \* 32 \]\
\
![](image%202.png)\
\
After this we listen on port 4444 and keep vulnserver running as admin ,
this time no immunity:\
\
![](image%203.png)\
\
Executing 1.py:\
\
![](image%204.png)\
\
Vulnserver output:\
\
![](image%205.png)\
\
On port 4444 we have gained a windows shell:\
\
![](image%206.png)\
\
\
\
\
