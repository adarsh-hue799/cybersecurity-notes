Here, we turned off real-time protection on our target device (here
windows)\
\
We will run**vulnserver** and **immunity debugger** as administrator.\
\
After that, on imunity debugger go the file and attach vulnserver.\
\
After that on the kali machine we will use netcat to connect to the port
9999 (since vulnserver runs on 9999 default).\
\
\
![](image.png)\
\
![](image%202.png)\
\
We will use different comands mentioned below the overfow the buffer, we
are gonna do this by throwing bunch of characters and overflow it :\
\
![](image%203.png)\
\
EXAMPLE:\
Lets try using STATS command to overflow.\
\
We use generic_send \_tcp and the syntax is shown below.\
It requires the **host \| port \| spike_script\
\**
The spike_script is replacing the string with a random character and
trying to overflow.For other commands mentioned above we have to replace
the \"STATS\" with them.\
\
![](image%207.png)\
\
\
\
![](image%206.png)\
\
\
This is the vulnserver shell output:\
\
![](image%204.png)\
\
This is the immunity debugger output:\
\
![](image%205.png)\
\
WE CAN INFER FROM ABOVE THAT THERE IS NOTHING HAPPENING FROM
**STATS**AND HENCE WE CANNOT OVERFLOW THE BUFFER FROM IT.\
\
\
Next we triedfor **TRUN** because it can overfow the buffer.\
\
![](image%208.png)\
\
Vulnserver Output:\
\
![](image%209.png)\
\
**\*\*Immunity debugger output\*\*:**\
\
![](image%2010.png)\
\
Here we can clearly see **ESP EBP**and**EIP**were**overflowed by bunch
of A\'s.\
There is also an error message displayed \"Access violation when
executing \[41414141\]\"\**
We clearly overflowed the registors we wanted to and now can point this
registor to our malicious code.\
