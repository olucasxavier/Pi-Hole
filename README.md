# Pi-Hole

Welcome to my Pi-hole exploration project! In this repository, I'll take you on a journey through the realm of DNS security as I deploy Pi-hole in my homelab environment.

<h3>WHAT IS PI-HOLE?</h3>

Pi-hole is a powerful, open-source network-wide ad blocker and DNS sinkhole that runs on a variety of platforms, including Raspberry Pi. However, it's not just about ad-blocking; Pi-hole is an excellent tool for enhancing DNS security and privacy. It works by intercepting DNS requests and filtering out known malicious domains, thereby protecting your network from various online threats.

<h3>WHY PI-HOLE?</h3>

DNS security is a critical aspect of network defense. Pi-hole offers an elegant solution to DNS-level security and privacy challenges. With Pi-hole, I can:

**Block Malicious Domains:** Pi-hole can block DNS requests to known malicious domains, protecting devices on my network from accessing harmful content.

**Enhance Privacy:** By blocking tracking domains, Pi-hole enhances the privacy of network users, preventing data leakage to third-party advertisers.

**Customize Filters:** I have the flexibility to customize blocklists and allowlists, tailoring Pi-hole's filtering to my specific needs.

<h3>HANDS ON, TIME TO INSTALL PI-HOLE</h3>

**Prerequisites:**

If you want to install Pi-hole on an Ubuntu container in Proxmox as I'm running mine, you can follow these steps:

**Step 1: Create an Ubuntu LXC Container**

1. Log in to the Proxmox web interface.
2. Select the node where you want to create the LXC container.
3. Click on "Create CT" (Container).
4. In the "General" tab, provide a unique ID for the container (e.g., 100) and set a hostname.
5. Under "Template," select "ubuntu-20.04" or the Ubuntu version of your choice.
6. Set the "Root Password" and any other necessary options.
7. Click "Next" and review your settings. Then, click "Finish" to create the container.
8. Start the container by selecting it in the Proxmox web interface and clicking "Start."

**Step 2: Access the Ubuntu Container**

1. Once the Ubuntu container is running, you can access it via SSH or the Proxmox web terminal.
2. Open a terminal or SSH client and connect to the IP address of the LXC container. You'll need the root username and password you set during container creation.

**Step 3: Install Pi-hole**

1. Inside the Ubuntu container, update the package list:
````
sudo apt update
sudo apt upgrade
````
2. Install Pi-hole by cloning the official Pi-hole repository from GitHub:
````
git clone --depth 1 https://github.com/pi-hole/pi-hole.git Pi-hole
cd Pi-hole/automated\ install/
sudo bash basic-install.sh
````

3. Follow the on-screen prompts to configure Pi-hole. You'll be asked to set your timezone, select an upstream DNS provider, and set a strong password for the Pi-hole web interface.

4. Once the installation is complete, change your DNS to the IP you set on your Ubuntu container, this can be done manually per machine, or on your router/DHCP server, so all machines will be protected in your network.

5. Access the Pi-hole web interface by opening a web browser and entering the IP address of the Ubuntu container. The web interface allows you to manage Pi-hole's settings, including whitelisting and blacklisting domains and monitoring network activity.

That's it! You've now installed Pi-hole on an Ubuntu container in Proxmox. Pi-hole will serve as a network-wide ad blocker and DNS server, helping to improve your internet experience by blocking unwanted ads.

</p>
<img src="https://i.imgur.com/ZEY9i0S.png" alt="Pi-Hole Web Interface - Dashboard"/>
<i>Pi-Hole Web Interface - Dashboard</i>
</p>

This is a basic overview of the installation process. Please refer to the official Pi-Hole documentation for more detailed instructions and troubleshooting if needed.

**Contributions are more than Welcome**

I encourage contributions, feedback, and collaboration from the community. If you have suggestions, improvements, or questions, please feel free to open issues or submit pull requests.

Thank you,</br>
Lucas
