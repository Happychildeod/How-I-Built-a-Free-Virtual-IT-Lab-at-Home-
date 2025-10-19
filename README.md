SETTING UP A VIRTUAL HOME LAB 

STEP BY STEP GUIDE 

BY EMMANUEL OLADEINDE – CYBERSECURITY ANALYST 

 

 

Setting up a virtual home lab 

I Built a Free Virtual IT Lab at Home. Here's How 

Back in the early 2000s, setting up an IT lab meant buying expensive physical servers or digging up old computers to repurpose. It was a hands-on and valuable experience, but not the easiest or fastest route. 

Today, with the power of open-source tools and virtualisation, anyone can build a fully functional IT lab right from their own computer and that is exactly what I did. 

I built a completely free virtual IT lab from scratch on my home machine using open-source software. It’s fast, flexible, and a great way to gain hands-on IT and cybersecurity skills without needing a stack of hardware. 

Let me walk you through how I did it and how you can, too. 

 

Index 

Virtualization Overview 

Free Virtualization Software 

Downloading and Installing VirtualBox 

Creating a Virtual Network 

Creating a Virtual Machine 

Downloading Your operating systems ISO(s) 

Installing an OS on Your Lab VMs 

Conclusion 

 

 

Virtualization Overview 

So, what exactly is virtualization? 
In simple terms, virtualization is the process of emulating a computer system. Instead of needing multiple physical machines, you can create several virtual machines (VMs) that run as software on your main computer. 

Imagine your main computer is the host, the one doing all the work. On this host, you can run one or more guest virtual machines, each acting like its own separate computer with its own operating system and settings. 

Think of it as running a full computer inside your existing one, like opening up a new world on your desktop! 

 

Virtual Machines — Your Own Computers Within a Computer 

Virtual machines (VMs) behave just like real computers, but they run as software inside your main system. That means you can start, restart, shut down, and even install operating systems and applications, just like you would on a physical machine. 

Because of this flexibility, virtual machines are ideal for creating your own IT lab, giving you a safe space to test, learn, and build without needing extra hardware. 

 

Free Virtualisation Software 

There’s a wide range of virtualisation software out there, and it can get a bit overwhelming trying to choose the “best” one. 

Here’s the truth: there is no single “best” virtualisation software, it really depends on your operating system and your specific needs. 

For this project, I’m using Oracle VM VirtualBox, mainly because it works seamlessly on both Windows and Linux systems. However, feel free to use any other virtualisation tool you prefer most of the setup steps will be very similar across platforms. 

 

  

 

Downloading and Installing VirtualBox 

 

Download Oracle VM VirtualBox by clicking here. Once the download is completed, I launched the  

 

 

A screenshot of a computer

AI-generated content may be incorrect. 

 

 

 

 

 

 

 

 

 

 

installation  

I went through the installation using all the default options. 
Whenever you're prompted with a yes/no question, simply choose "Yes" to continue. 

 

 

 

 

Click Finish and launch VirtualBox. 

 

 

Creating a Virtual Machine 

Now that we've decided on the type of virtual network to use, it's time to create a Virtual Machine (VM). You can do this by clicking the "New" button in the VirtualBox Manager. 

 

Ink 2, ShapeInk 3, ShapeInk 1, ShapeA screenshot of a computer

AI-generated content may be incorrect. 

 

This will launch the new VM window. Click the Expert Mode button to proceed. Don’t worry, it doesn’t make the process harder. It simply streamlines the setup by reducing the number of steps. 

 

 

 

 

I am going to specify a name of "Windows 8 Sales Department 1" and 2048 MB (2gb) of RAM then I will click Finish. 

 

 

 

 

This will open another window for creating the Virtual Hard Disk. The default options here are all fine except for the File Size. I am going to set my new HDD to 40GB and then choose Finish. 

Ink 10, Shape 

Ink 14, ShapeInk 13, ShapeInk 11, ShapeInk 9, ShapeInk 6, Shape 

 

 

Since this hard disk drive (HDD) is set to be dynamically allocated (see the option on the middle-right of the screenshot below), the HDD file will only take up as much space as the data stored on it—up to a maximum of 40GB. 

Now, you’ll see Windows 8 Sales Department 1 listed on the VirtualBox dashboard. Before starting the virtual machine (VM), you can modify its settings if needed. Typically, you might want to: 

Assign more processors 

Change the networking adapter 

Mount an ISO image 

  

 

Increasing the number of CPU cores can significantly enhance your virtual machine’s (VM) performance. If possible, set the number of CPUs to 2. 

Pro tip: Storing the VM’s virtual hard disk on a solid-state drive (SSD) can further improve performance, especially when running disk-intensive tasks. 

 

 

Ink 28, Shape 

And that’s all we need to do to create the virtual machine (VM). Of course, we can’t start it just yet — we still need to download and attach an operating system ISO. But don’t worry, we’ll cover that in the next section. 

Shape 

Creating a Virtual Network with VirtualBox 

Virtual networks allow your VMs to connect to each other, your host machine, or the internet depending on how you configure them. VirtualBox supports several types of virtual network configurations, and the one you choose will depend on your specific use case. 

Note: Some network types can only be configured after a VM has been created, as they're managed within the VM’s settings. 

 

 

 

Network Types in VirtualBox 

1. NAT (Network Address Translation) 

This network type allows your VM to access the internet using the host computer’s connection. However, it does not allow communication between the VM and the host or between multiple VMs. 

Use this if: Your lab setup only includes one VM and it just needs internet access. 

To enable NAT: 

Right-click your VM 

Select Settings 

Go to the Network tab 

Choose Attached to: NAT (see image above) 

Shape 

2. NAT Network 

This option is similar to NAT but also allows VMs connected to the same NAT Network to communicate with each other, while still maintaining internet access. 

Use this if: Your lab setup includes multiple VMs that need to talk to each other and access the internet. 

To create a NAT Network: 

Go to File > Preferences 

Select the Network tab 

Click the plus (+) button to create a new NAT Network 

Then, in your VM's settings, attach it to the NAT Network you just created 

 

 

 

  

More Network Types in VirtualBox 

3. Bridged Adapter 

This network type makes your VM appear as a separate physical device on your local network. Your router will assign it an IP address, just like it would with any other device. 

Use this if: You need your VM to be accessible from other devices on your local network (e.g., your host, other VMs, or even other physical computers). 

To enable a Bridged Adapter: 

Right-click your VM 

Select Settings 

Go to the Network tab 

Choose Attached to: Bridged Adapter 

Shape 

4. Internal Network 

This creates a completely isolated network shared only between VMs attached to the same internal network. There’s no internet access, and your host computer cannot communicate with these VMs. 

Use this if: You want a fully isolated lab environment for testing, malware analysis, or network simulation. 

To use an Internal Network: 

Right-click your VM 

Select Settings 

Go to the Network tab 

Choose Attached to: Internal Network 

Shape 

5. Host-only Adapter 

This setup is similar to an internal network but also gives the host computer a direct IP connection to the VM. The VM still doesn’t have internet access unless combined with another adapter (e.g., NAT). 

Use this if: You need to access the VM directly from your host (e.g., using RDP, SSH, ping, or file transfer). This is ideal for web development labs or local server testing. 

To set up a Host-only Adapter: 

Right-click your VM 

Select Settings 

Go to the Network tab 

Choose Attached to: Host-only Adapter 

You can create a host-only network by select File > Host Network Manager 

 

 

 

Generic Driver 

According to Oracle’s documentation: 

“The generic driver attachment is special and cannot be considered as an alternative to other attachment types.” 

In most use cases, the Generic Driver is not commonly used and is intended for advanced or specialized networking scenarios. You typically won’t need this unless you're working with custom or experimental networking configurations. 

 

 

 

I'm going to leave all the NAT Network settings at their defaults so that is it! The Virtual Network is now set up and ready to use. 

Now, go ahead and configure the Networking tab of your VM to match your chosen network type. As mentioned earlier, the easiest and most flexible option is to create and use a NAT Network, especially for multi-VM labs that require internet access. 

 

  

 

 

Downloading Your Operating System ISO(s) 

Now that your virtual network is ready, the next step is to download an operating system (OS) to install on your virtual machine. 

While it's technically possible to install from a physical disc, the most common and convenient method is to use an ISO file a digital copy of the OS installation media. 

To find an ISO file, the easiest approach is to search online. For example, if you’re looking to install Window Server, simply search: 

"Window Server ISO Download" 

Make sure to download ISOs from official or trusted sources to avoid corrupted or unsafe files. Some operating systems like Ubuntu, Fedora, or Windows Evaluation Editions provide free, official ISOs on their websites. 

You should ONLY download ISOs from official websites. This means you shouldn't download Windows Server from a website like "sneakyfreecdkeys.com"... 

 

I will still provide links to the most common operating systems that people want to install below. Keep in mind if the link is dead you can just run a quick google search and easily find the download. 

Windows Server  

Windows 10 (requires a valid Windows 10 license to download) 

Windows XP 

Ubuntu 

Kali Linux 

 

Installing an OS on Your Lab VMs 

Once you have downloaded your ISO file, it's time to mount it to your VM in VirtualBox. Mounting a VM is essentially like virtually inserting a disc into a DVD drive of a computer. 

  

Right click on your VM and select settings then open the Storage tab. From there click the Empty disc icon, then again, the disc icon under Attributes on the right-hand side of the window. Click the Choose Virtual Optical Disk File... and browse to and open your desired ISO. 

 

 

 

Click OK and now when we launch the VM you will be able to begin your OS installation. 

I mounted a Window Server ISO so when I launch the VM I will see the installation screen for this OSA computer screen shot of a computer

AI-generated content may be incorrect. 

Wrapping It Up... 

That’s it! You’re now ready to run through your OS installation and complete your lab setup. 

With your virtual machine, virtual network, and operating system in place, you have everything you need to start building hands-on IT labs and gaining real-world experience — right from your own machine. 

Shape 

What You’ve Accomplished: 

Created a virtual machine 

Set up a virtual network 

Chosen and downloaded an operating system ISO 

Prepared everything for your OS installation 

Shape 

Now go ahead and create something awesome. Whether you're studying for certifications, testing software, or building your own virtual network lab, you're well on your way to sharpening your IT skills. 

 
