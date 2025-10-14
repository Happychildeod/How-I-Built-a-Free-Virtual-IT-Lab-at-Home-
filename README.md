# Setting Up a Free Virtual Home Lab
### Built and Written by Emmanuel Oladeinde — Cybersecurity Analyst

---

## Index
- [Virtualization Overview](#virtualization-overview)
- [Free Virtualization Software](#free-virtualization-software)
- [Downloading and Installing VirtualBox](#downloading-and-installing-virtualbox)
- [Creating a Virtual Network](#creating-a-virtual-network-with-virtualbox)
- [Creating a Virtual Machine](#creating-a-virtual-machine)
- [Downloading Your Operating System ISO(s)](#downloading-your-operating-system-isos)
- [Installing an OS on Your Lab VMs](#installing-an-os-on-your-lab-vms)
- [Conclusion](#wrapping-it-up)

---

## Virtualization Overview
Virtualization is the process of emulating a computer system.  
Instead of using multiple physical machines, you can create several virtual machines (VMs) that run as software on your main computer.

Your main computer is the **host**, and the virtual machines are the **guests** — each acting like its own separate computer with its own operating system, storage, and settings.

Think of it as running a full computer inside your computer, like opening a new digital world on your desktop.

---

### Virtual Machines — Computers Within a Computer
Virtual machines (VMs) behave just like real computers, but they run as software inside your main system. You can:
- Start, restart, and shut down them just like real PCs  
- Install operating systems and applications  
- Experiment safely without affecting your main system  

Because of this flexibility, virtual machines are ideal for IT labs, giving you a **safe environment** to learn, test, and explore without needing expensive hardware.

---

## Free Virtualization Software
There are many virtualization platforms available, and the best choice depends on your operating system and needs.  

For this project, we’ll use **Oracle VM VirtualBox**, which is:
- Free and open-source  
- Works on Windows, Linux, and macOS  
- Beginner-friendly  

Other options include VMware Workstation Player and KVM, but the steps below focus on VirtualBox.

---

## Downloading and Installing VirtualBox
1. Download **Oracle VM VirtualBox** from the [official VirtualBox website](https://www.virtualbox.org/).  
2. Run the installer and choose the **default options** during setup.  
3. When prompted with yes/no questions, select **“Yes”** to continue.  
4. Once installation finishes, click **Finish** to launch VirtualBox.

---

## Creating a Virtual Machine
Now that VirtualBox is installed, let’s create our first **Virtual Machine (VM)**.

1. Click **New** in the VirtualBox Manager.  
2. Switch to **Expert Mode**.  
3. Name your VM (e.g., `Windows 8 Sales Department 1`)  
4. Allocate **2048 MB (2 GB)** of RAM  
5. Set the **virtual hard disk** to **40 GB** and make it **dynamically allocated**  
6. Click **Finish**

Tip: If you have an SSD, store your VM files on it for faster performance.

You can also modify your VM’s settings later to:
- Assign more CPU cores  
- Adjust network adapters  
- Mount an operating system ISO  

---

## Creating a Virtual Network with VirtualBox
Virtual networks let your VMs connect to each other, your host, or the internet.

Here’s an overview of the main **network types** in VirtualBox:

| Network Type | Description | Use Case |
|---------------|--------------|-----------|
| NAT | VM uses host’s internet but cannot talk to other VMs | Simple setups needing internet |
| NAT Network | Internet + VM-to-VM communication | Multi-VM labs |
| Bridged Adapter | VM appears as a physical device on your network | Access VM from other devices |
| Internal Network | Fully isolated lab network | Malware analysis / sandboxing |
| Host-only Adapter | Isolated but accessible from host | Local web servers / testing |

Recommended: Create a **NAT Network** for flexibility — it allows internet access and VM-to-VM communication.

Steps:
1. Go to **File → Preferences → Network**  
2. Click **+** to create a new NAT Network  
3. Assign your VM(s) to it under **Settings → Network → Attached to: NAT Network**

---

## Downloading Your Operating System ISO(s)
Next, download the operating system you want to install.  
An ISO file is a digital copy of an installation disc.

Download only from **official sources** to stay safe. Examples:

- [Windows Server (Evaluation)](https://www.microsoft.com/en-us/evalcenter)  
- [Windows 10](https://www.microsoft.com/software-download/windows10)  
- [Ubuntu](https://ubuntu.com/download)  
- [Kali Linux](https://www.kali.org/get-kali)  

Avoid third-party or “free license key” sites. Always verify file authenticity.

---

## Installing an OS on Your Lab VMs
Once you’ve downloaded your ISO:

1. Right-click your VM → **Settings**  
2. Go to **Storage**  
3. Select the empty disc icon  
4. Click the small **disc icon** under *Attributes → Choose a disk file...*  
5. Browse and select your ISO file  
6. Click **OK**

Now start the VM — your OS installation should begin automatically.  
Follow the prompts as you would on a real PC.

---

## Wrapping It Up
Congratulations — your virtual IT lab is ready!

### What You’ve Accomplished
- Created a Virtual Machine  
- Set up a Virtual Network  
- Downloaded an OS ISO  
- Installed your operating system  

You now have a fully functional **virtual lab environment** for hands-on IT, networking, and cybersecurity practice — all from your home computer.

---

## Final Thoughts
With your virtual environment in place, you can:
- Experiment with network configurations  
- Practice ethical hacking and forensics  
- Build Windows or Linux server setups  
- Prepare for certifications (CompTIA, Cisco, etc.)  

Keep exploring — your only limit is your curiosity.  
**— Emmanuel Oladeinde, Cybersecurity Analyst**
