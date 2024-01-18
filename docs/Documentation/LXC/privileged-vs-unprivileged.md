# Differentiating both

## My understanding 


|                        | Privileged Containers                                        | Unprivileged Containers                                    |
|------------------------|--------------------------------------------------------------|--------------------------------------------------------------|
| **Container Type**      | Elevated privileges, shares host kernel.                     | Restricted access, runs with separate user namespace.        |
| **UID Allocation**      | uid 0 is mapped to the host's uid 0                          | uid 0 is mapped to an unprivileged user on the host
| **Full System Access**  | Yes                                                          | No                                                           |
| **Kernel Capabilities** | Inherits host kernel capabilities.                            | Reduced capabilities for certain privileged operations.     |
| **Security Implications**| May pose security risks if not configured properly.          | Considered more secure; limited impact on host if compromised.|
| **User Namespace**      | No                                                           | Yes (isolated user namespace).                                |



## According to LXC Official Docs


| Type of Container   | Definition                                                                                                   | Security Measures                                                                                                                                   | Security Considerations                                                                                                                     |
|----------------------|--------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| Privileged Containers| Containers where container uid 0 is mapped to the host's uid 0.                                               | - Mandatory Access Control (AppArmor, SELinux) <br> - Seccomp filters <br> - Dropping of capabilities and namespaces                                   | - Not considered root-safe by LXC upstream <br> - Valuable for trusted workloads or environments without untrusted tasks running as root    |
| Unprivileged Containers | Containers designed to be safe by mapping container uid 0 to an unprivileged user outside of the container. | - Use of SELinux, AppArmor, Seccomp, and capabilities is optional for security <br> - Additional layer of security provided by LXC for kernel issues | - Security model not enforced by these technologies <br> - Relies on setuid code (lxc-user-nic, newuidmap, newgidmap)                        |


**Choosing Between Privileged and Unprivileged Containers:**
- Consider specific application requirements and desired security levels.
- Recommended to use unprivileged containers for enhanced security and isolation.
