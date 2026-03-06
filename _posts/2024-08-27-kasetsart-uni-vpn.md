---
title: Guide for connecting to the Kasetsart University VPN on Fedora
author: Atirut Wattanamongkol
fediverse_creator: "@Atirut@toot.community"
tags: kasetsart-university vpn fedora
---

Hi! Been a while, eh? Oh, that's... almost three months without updates... well, let's set you up for connecting to Kasetsart University's VPN on Fedora, the easy way!

I am writing this guide partially out of spite for the lackluster docs provided by the university, for Linux users. Here are a few crimes its author committed:

- **Zero** mention of the fact that the auth credentials are your Nontri username and password.
- Assuming that everyone uses the terminal to connect to the VPN.

Well, screw that, because GNOME has integrations for all sorts of VPNs, and it's all GUI! Let's get started.

## Step 1: Acquire the VPN configuration file
This should be easy enough. Head to their [VPN page](https://vpn.ku.ac.th/) and log in with your Nontri credentials. Once you're in, download the configuration file for Fedora. It should be a `.ovpn` file.

## Step 2: Setting up the VPN connection
Now, open up your GNOME settings and navigate to the Network section. Under the VPN section, click the add button (you know what it looks like) and pick "Import from file...". Select the `.ovpn` file you downloaded earlier.

Now, this is where you'll likely make a mistake. If you just click "Add" and try to connect, you'll be repeatedly asked for your password. This is because you also have to fill out the username, which GNOME doesn't ask for. The username is the same as your Nontri username.

If you did everything correctly, it should connect without a fuss. If it does, congrats! Now you can access the university's intranet from the comfort of your Fedora desktop.

## Final thoughts
Well, that's a lot easier than manually downloading a VPN client n stuff on Windows. And now you can (hopefully) also use it to do stuff as if on LAN, like remoting into the gaming computer you definitely have at home as long as you note down the IP. Have fun!
