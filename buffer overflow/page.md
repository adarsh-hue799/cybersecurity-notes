Consider this anatomy of memory :\
\
![](image.png)\
\
Stack is the layer we are most interested in.\
Stack structure is shown below:\
\
![](image%202.png)\
\
Now, the flow happens in the downward direction (from ESP to EIP)\
\
For efficiently sanitizing the stack, for example various characters are
flooded in the buffer space till it reaches the boundry.\
\
![](image%203.png)\
\
When a buffer overflow attack is launched, this space is overflowed by
more such characters reaching the EBP and EIP.\
\
![](image%204.png)\
\
\
Now since we have reached EIP, we can use the pointer register to point
toward the instruction we want.\
This instruction is basically malicious code, malware which will be used
to pop a shell.\
