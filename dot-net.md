# .NET 

## Definitions
- **Global Assembly Cache (GAC)**
  - A folder in Windows where all shared .NET assemblies reside. These assemblies can be shared by all applications executed on a system. A place to store code libraries so they're accessible to all applications running on the machine.
  - A way to keep DLLs globally accessible without worrying about conflicts (No more DLL hell)
  - Each architecture and version gets it's own place to live. 
  - Also gets its own way to browse it in Explorer, i.e. can go to C:\Windows\assembly which lists all the DLLs.

