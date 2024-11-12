I chose the web app over the virtual machine for several reasons: accessibility, maintenance, scalability, cost, security, and user experience.

Accessibility: The web app can be accessed from any device with an internet connection and a web browser, making it ideal for this project, which aims to enable quick and easy posting. Users need seamless access to the application, and the web app provides that.

Maintenance: Debugging and updating the Azure web app is more straightforward because updates and bug fixes can be deployed centrally on the server. This eliminates the need for users to download and install updates. Additionally, addressing security errors, such as updating invalid login messages, is faster and more efficient, benefiting both programmers and end users.

Cost: The web app is significantly more cost-effective, with monthly costs at $54.75 compared to the VM’s $134.75(Screenshots attached to powerPoint). Neither option has upfront costs, but the web app’s pay-as-you-go model is more economical, especially for applications with fluctuating workloads. Using multiple VMs and configurations only increases costs.

Scalability: Azure Virtual Machines can automatically scale using virtual machine scale sets, providing control over scaling. However, this requires more manual setup and management. In contrast, the Azure web app handles infrastructure, scaling, and maintenance automatically, allowing me to focus on application code rather than server management.

Availability: While VMs offer high availability, it requires configuration. The web app, on the other hand, has built-in availability, reducing the need for manual setup.

Ease of Use: As a part-time developer, the web app was the more practical choice. Its management and seamless operation were easier for me to handle. Given the straightforward nature of this project, deploying a virtual machine didn’t make sense. For larger projects or full-time developers, a VM might be necessary, but for this project, the web app was more cost-effective and efficient
