<div align="center">
  <h1>Black Angel Rootkit</h1>
  <br/>

  <p>Black Angel is a Windows 11/10 x64 kernel mode rootkit. Rootkit can be loaded with enabled DSE while maintaining its full functionality.</p>
  <p>Designed for Red Teams.</p>
  <br />
</div>


## Rootkit Features
Rootkit can be loaded with Black Angel Loader which is modified [kdmapper](https://github.com/TheCruZ/kdmapper) bypassing DSE. Project [driver-hijack](https://github.com/not-wlan/driver-hijack) is used to maintain full driver functionality such as callback support.
- DSE Bypass
- KPP Bypass
- Hide processes
- Hide ports (TCP/UDP)
- Process permission elevation
- Process protection
- Shellcode injector (Unkillable shellcode. Even if process dies, shellcode can still run)
- (TODO) Hide files/directories
- (TODO) Hide registry keys

## Angel Support
Functions that you can implement into your program to be able to do direct kernel calls. More functions will be added in a future.
- ZwProtectVirtualMemory
- MmCopyVirtualMemory
- ZwQueryInformationProcess
- ZwUnmapViewOfSection

## Additional Info
- Remember to change [ACTIVE_PROCESS_LINKS](https://github.com/XaFF-XaFF/Black-Angel-Rootkit/blob/f4a5c762ae864b7395a6a03b8d46fdeda6a8bb25/Black%20Angel%20Rootkit/rootkit.hpp#L7) offset corresponding to your Windows versions. Current offset has been tested on Windows 10/11 Pro 21H2.
- There may still be stability issues!
- KM shellcode injector is OP. If you inject shellcode into protected process, no antivirus will remove it >:D Simple shellcodes such as Metasploit shell_reverse_tcp are able to work even if process is terminated.

## Resources:
- [kdmapper](https://github.com/TheCruZ/kdmapper)
- [driver-hijack](https://github.com/not-wlan/driver-hijack)
- [Cronos-Rootkit](https://github.com/XaFF-XaFF/Cronos-Rootkit)
