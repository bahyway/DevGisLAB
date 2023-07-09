---
description: Memory Error
---

# Error Code 137

{% hint style="danger" %}
If you encountered theis Error , then this means that there is no sufficient Memory for the Container
{% endhint %}

### Solutions

1. Change the  `.wslconfig` file and add the following to it:

{% hint style="success" %}
Check this Link: [**Advanced settings configuration in WSL**](https://learn.microsoft.com/en-us/windows/wsl/wsl-config#configure-global-options-with-wslconfig)
{% endhint %}

```
# Settings apply across all Linux distros running on WSL 2
[wsl2]

# Limits VM memory to use no more than 4 GB, this can be set as whole numbers using GB or MB
memory=10GB 

# Sets the VM to use two virtual processors
processors=4
# Specify a custom Linux kernel to use with your installed distros. The default kernel used can be found at https://github.com/microsoft/WSL2-Linux-Kernel
kernel=C:\\temp\\myCustomKernel

# Sets additional kernel parameters, in this case enabling older Linux base images such as Centos 6
kernelCommandLine = vsyscall=emulate

# Sets amount of swap storage space to 8GB, default is 25% of available RAM
swap=8GB

# Sets swapfile path location, default is %USERPROFILE%\AppData\Local\Temp\swap.vhdx
swapfile=C:\\temp\\wsl-swap.vhdx

# Disable page reporting so WSL retains all allocated memory claimed from Windows and releases none back when free
pageReporting=false

# Turn off default connection to bind WSL 2 localhost to Windows localhost
localhostforwarding=true

# Disables nested virtualization
nestedVirtualization=false

# Turns on output console showing contents of dmesg when opening a WSL 2 distro for debugging
debugConsole=true
```

2. <mark style="background-color:green;">**Do This**</mark> : If the first solution does not work , do the second solution and this is by removing all related images , container connected to this Dev Container, and restart the process from the beginning.&#x20;
