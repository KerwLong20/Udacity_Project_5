# Write-up Template
### Analyze, choose, and justify the appropriate resource option for deploying the app.

I chose Azure App Service because it provides everything developers need to create websites, mobile backends, and web APIs for any platform or device. It features built-in infrastructure maintenance, security patching, and automatic scaling, ensuring a seamless experience. Azure App Service supports multiple programming languages, including .NET, .NET Core, Java, Ruby, Node.js, PHP, and Python. My application is developed using Python, one of the supported languages. With Azure App Service, I can quickly build, deploy, and scale my web app efficiently.

The reason I opted not to use a Virtual Machine (VM) is that I prefer not to manage the underlying operating system or install software on the server. With Azure App Service, I can quickly deploy my web application without the need to set up a programming environment. In contrast, virtual machines function like fully independent computers, for which I would be responsible for all aspects, including maintenance, security, and updates.

# Analyze costs, scalability, availability, and workflow*
Cost: Azure App Service is more cost-effective than Virtual Machines. It offers various pricing plans, including Free and Shared (preview) options, which are ideal for testing or deploying applications. Additionally, App Services come with built-in load balancers that help reduce infrastructure costs.

Scalability: Azure enables developers to easily scale their applications both horizontally and vertically. Vertical scaling automatically adjusts the resources allocated to your App Service, such as vCPUs or RAM, by changing the pricing tier. Horizontal scaling, on the other hand, increases or decreases the number of Virtual Machine instances running your App Service. With auto-scaling, App Service can automatically adjust the number of instances based on a schedule or metrics like CPU usage, memory consumption, or HTTP queue length.

Availability: Azure App Service provides global scalability with high availability. You can host your application anywhere within Microsoft’s extensive global data center infrastructure, and the App Service SLA guarantees high availability.

Workflow: Azure App Service supports automated deployments from GitHub, Azure DevOps, or any Git repository. With GitHub Actions for Azure Web Apps, developers can create workflows in their GitHub repositories to build, test, package, release, and deploy applications to Azure seamlessly.

*Detail how the app and any other needs would have to change for you to change your decision in the last section.* 

Azure App Service does have hardware limitations and may not be the best choice for applications that are expected to expand in the future. In such cases, Virtual Machines (VMs) are often preferred. If this application scales significantly—whether due to a substantial increase in users or the addition of new features—I would opt for a Virtual Machine.

For advanced scaling and traffic management capabilities, VMs are the better option, especially when utilizing Azure Virtual Machine Scale Sets, which simplify the process.

If the application is later developed using a programming language not supported by Azure App Service, I would choose a VM to create the necessary environment for that language.

Additionally, using App Service provides limited access to the host server. If I need to control the underlying operating system or install specific software, a Virtual Machine would be the appropriate choice.

