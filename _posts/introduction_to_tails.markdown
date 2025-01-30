---
layout: post
title:  "Introduction to Tails"
date:   2025-01-30 00:00:00 -0500
tags: technology
---

# Introduction to Tails

## Table of Contents
- [What is Tails?](#what-is-tails)
  - [How good is this really?](#how-good-is-this-really)
  - [Advantages](#advantages)
  - [What disappears?](#what-disappears)
  - [Tails is safe, but not magic](#tails-is-safe-but-not-magic)
- [Using Tails](#using-tails)
- [Additional Digital Security Resources](#additional-digital-security-resources)
- [Sources](#sources)

## What is Tails?
Tails is designed to help you use the Internet anonymously and get around censorship. It lets you connect to the Internet using virtually any computer while leaving no trace of your activities after you have finished. Tails connects to the hardware of a computer but doesn’t use the operating system or disk drives. That means there is no permanent record of your activities on that computer. Once you remove the Tails USB Stick or DVD and restart the computer, there will be no way to tell Tails was used there. Tails is far safer than the typical operating system, but it is not foolproof. [3]

### How good is this really?
Tails and the Tor project were developed by the US Government for secure espionage. They realized that if they only used it themselves, everyone would be able to tell who was government and who wasn't. In order to keep it secure for their own use, they were forced to release it publicly and keep it secure for everyone to use. The US Goverment is still the primary financial backer of Tails and the Tor project.

If you follow the instructions provided by Tails, people will know that someone is using it, but they won't be able to tell who.

### Advantages
- Use almost any computer, including those owned by other people. [1]
- Leave no trace on the computer when you are done. [1]
- Save important files, emails, and bookmarks to persistent storage on the Tails drive. [1]

### What disappears?
- Websites that you visited. [1]
- Passwords that you typed. [1]
- Networks and WiFi that you connected to. [1]

### Tails is safe, but not magic
- Files you share may still have date, time, location, and device information. [2]
- Using Tails for more than one purpose at a time may reveal your identity. [2]
- Tails cannot hide that you are using Tails and Tor from sites you connect to. [2]
- Tails may not hide your communications from skilled, determined attackers. [2]
- If you use a computer which is compromised, your security may be as well. [2]

## Starting Tails
This document assumes that you have been provided with a copy of Tails on a USB Drive.  

For the best security, do not plug in your Tails USB stick while another operating system is running on the computer. [5]  
Use your Tails USB stick only to run Tails. Do not use your Tails USB stick to transfer files to or from another operating system. [5]  

Getting into Tails can be tricky. The two primary methods are from inside Windows, or using the computer's Boot Menu key.

### Booting the Tails USB from Windows
https://tails.net/install/windows/index.en.html#restart  

1. Log into Windows normally.
2. Insert the Tails USB.
3. Click on the Start Button.
4. Press and hold the Shift key while you choose Power > Restart.
5. In the Choose an option screen, choose Use a device.
6. In the Use a device screen, choose Boot Menu.

Windows will shut down, reboot, and you should have options of possible boot devices. 

7. In the Boot Menu, select your USB stick and press Enter.
8. If the computer starts on Tails, the Boot Loader appears and Tails starts automatically after 4 seconds.

- The Troubleshooting Mode entry disables some features and might work better on some computers.
- The External Hard Disk entry makes it possible to start from some problematic USB sticks.

### Booting the Tails USB without access to Windows.
https://tails.net/doc/first_steps/start/pc/index.en.html#boot-menu-key  

1. Shut down the computer and plug in the Tails USB stick.
2. Identify the possible Boot Menu keys for the computer depending on the computer manufacturer in the following list:

| Manufacturer | Key              |
|--------------|------------------|
| Acer         | F12, F9, F2, Esc |
| Apple        | Option           |
| Asus         | Esc              |
| Clevo        | F7               |
| Dell         | F12              |
| Fujitsu      | F12, Esc         |
| HP           | F9               |
| Huawei       | F12              |
| Intel        | F10              |
| Lenovo       | F12, Novo        |
| MSI          | F11              |
| Samsung      | Esc, F12, F2     |
| Sony         | F11, Esc, F10    |
| Toshiba      | F12              |
| Others…      | F12, Esc         |

3. Switch on the computer. Immediately press several times the first possible Boot Menu key identified in step 2.  
  3a. If the computer starts on another operating system or returns an error message, shut down the computer again and repeat step 3 for all the possible Boot Menu keys identified in step 2.  
4. If a Boot Menu with a list of devices appears, select your USB stick and press Enter.
5. If the computer starts on Tails, the Boot Loader appears and Tails starts automatically after 4 seconds.

### Troubleshooting Tails not starting at all
https://tails.net/doc/first_steps/start/pc/index.en.html#not-entirely  

- Try all other USB ports on the computer. Some USB ports cannot be used to start from.
- Try to use the same USB stick to start on a different computer.
- In the Boot Loader, choose the Troubleshooting Mode entry, which works better on some computers.
- In the Boot Loader, choose the External Hard Disk entry, if it is available. Some USB sticks need this entry in order to start Tails.
- If you get the following error message in Windows: `The disc image file is corrupted.` your USB stick is incompatible and needs to be recreated.

## Using Tails
- It's best not to label the drive in any way. If you think someone could take it off you, destroy it.
- It's recommended that you use Tails on public WiFi or in a Public Space, like a Library or Internet Cafe.
- You may also be able to use the Library's computers instead of your own computer, which provides an additional layer of security.
- Leave your phone at home if it's safe to do so. See "Turn off your phone!" in the Additional Resources for more advice.
- Use Tails sessions for only one purpose at a time. [4]
- Use a password manager to paste saved passwords. This way, you don't have to type passwords that might be visible to people or cameras near you. [5]
- Use the screen keyboard, if you are using a public computer or worry that the computer might have a keylogger. [5]

### Accessibility
You can activate several assistive technologies, like a screen reader or large text, from the accessibility menu in the top bar, the icon that looks like a person. [6]
- To hear screen elements spoken to you, turn on the Screen Reader from the accessibility menu.
- If you prefer a pointing device over the keyboard, turn on the Screen Keyboard from the accessibility menu.

Some Keyboard shortcuts are available by Default. More can be found in the Settings menu.  

| Action                       | Shortcut  |
|------------------------------|---------- |
| Turn screen reader on or off | Alt+Win+S |
| Turn zoom on or off          | Alt+Win+8 |
| Zoom in                      | Alt+Win+= |
| Zoom out                     | Alt+Win+- |
| Window resize menu           | Alt+Space |

### Welcome Screen
When Tails first starts, the welcome screen allows you to select:
- The Language
- The Keyboard Format
- Whether Persistent storage is enabled

As well as other optional settings. For Users in the US, the default Language and format options will suffice. Click Start Tails to move to the next section.

- Create Persistent Storage only if you need to save files to the flash drive. If someone gets hold of the drive, they could reverse the enryption and access the files.
- Create Set an Administration Password to be able to perform administrative tasks like installing additional software or accessing the internal hard disks of the computer. [7]
- Turn on the Offline Mode if you want to work completely offline for increased security. [7]

### Desktop Environment
When Tails Loads, you will be presented with a Desktop Computer environment that you can do your work in. Familiarize yourself with the location of the following:
- Activities: Your Windows and Applications. You can search here as well.
- Applications: All of the included and installed software.
- Places: Shortcuts to commonly used folders and applications.
- System Menu: In the Top Right. Allows you to manage your settings, connect to a Wi-Fi network, and restart your computer.

### Included Software
- Tor Browser: Along with the "Tor Connection" application, creates the heart of the Tails experience. Allows you to browse the web anonymously and uncensored.
- Tor Connection: Allows you to connect to the Tor network.
- Persistent Storage: Allows you to save some of your files and configuration in an encrypted Persistent Storage on your Tails USB stick.
- Tails Documentation: Opens an offline version of the Tails website and documentation.
- Thunderbird: Allows you to write emails and read RSS and Atom feeds.
- KeePassXC: Allows you to store and manage secure passwords.
- Kleopatra: Allows you to encrypt text and files using GnuPG.

As well as other applications for specific purposes. The Tails Documentation contains more details on how to use each of these applications to best secure your online experience.

### Using the Tor Browser

## Additional Digital Security Resources
Turn off your phone! And other basic digital security strategies.  
https://ia802707.us.archive.org/12/items/zines-security/Turn_Off_Your_Phone.pdf  

Surveillance Self-Defense  
Electronic Frontier Foundation  
https://ssd.eff.org/  

What do you need to protect?  
security in-a-box  
https://securityinabox.org/en/  

## Sources
This document is compiled from the following sources. Due to the technical nature of the subject, some information may be paraphrased or copied verbatim. Efforts have been made to provide direct attribution where appropriate. To request removal of any content, please contact DSchaedler on Github or email deeschaedler@gmail.com.

### [1]  
"How Tails works"  
https://tails.net/about/index.en.html  

### [2]  
"Warnings: Tails is safe but not magic!"  
https://tails.net/doc/about/warnings/index.en.html

### [3]  
"Tails OS – An Actionable Guide for Regular Folks"  
Bill Mann, blokt.com  
https://blokt.com/guides/tails-os  

### [4]  
"Protecting your identity when using Tails"  
https://tails.net/doc/about/warnings/identity/index.en.html  

### [5]  
"Reducing risks when using untrusted computers"  
https://tails.net/doc/about/warnings/computer/index.en.html  

### [6]  
"Accessibility"  
https://tails.net/doc/first_steps/accessibility/index.en.html

### [7]  
"Welcome Screen"  
https://tails.net/doc/first_steps/welcome_screen/index.en.html
