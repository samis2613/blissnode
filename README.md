# blissnode

A **work-in-progress** reimplementation in Rust of the long gone servers for the old P2P versions of Skype.

# Status

**Main Supernode**
- [ ] UDP RC4 Key Exchange
- [ ] UDP Probe Packet
- [ ] HTTPS Handshake
- [ ] TCP Key Exchange
- [ ] Client Accept Packet

**Login Server**
- [ ] Login Server Handshake
- [ ] RSA-1536 Key Exchange
- [ ] AES-256 Key Exchange
- [ ] Login Packet

**Event Server**
- [ ] Broadcast Packet
- [ ] Contacts Packet

**Supported versions**

Standard clients:

- [x] Skype 1.4.0.84
- [x] Skype 2.5.0.151
- [x] Skype 3.8.0.188
- [x] Skype 4.2.0.187
- [x] Skype 5.5.0.124
- [x] Skype 5.9.66.114

While Skype did switch to MSNP24 with Skype 6, versions before 6.22 still fully supported the old P2P protocol, so version 6.16.0.105 is supported as well for those who want to use it. Versions 6.22+ only use the MSNP24 protocol and this will **not** be supported for my server.

Beta clients:
- [x] Skype 4.1.0.130 Beta

I am hoping to support Skype 0.x versions from when Skype was in beta but I cannot track down any deobfuscated versions to patch at the moment.


# Backstory and Goal

**Screenshot from May 2024 of Skype 2.5 with debug logs successfully signing in to my server:**

<a href="https://ibb.co/WWGqYBH"><img src="https://i.ibb.co/cckM72y/image.png" alt="image" border="0" /></a>

Back in July 2020, I began my journey on studying/reverse engineering the old Skype protocol and trying to make sense of its heavily obfuscated nature so that I can try to get the old clients working again. After much analysis, I finally got to work on writing my server in Rust during September 2023 and on May 2024, I finally made a breakthrough and got the actual clients to login since I was able to implement everything regarding the main supernode and login server in a messy proof-of-concept version of my server. Before starting work on implementing the Event Server, I want to do a whole rewrite of my server since it was pretty messy backend wise and it is missing stuff for public use such as proper account registration instead of hard-coded public key and username. So here we are, this is what the Blissnode project is all about, providing an open source reimplementation of the old servers so people can experience the good old peer-to-peer versions of Skype once again! :)

NOTE:
Please keep in mind I am only one person and I have many things going on in my life like anyone else. There are many times where periods of inactivity/lack of constant updates regarding the project will occur, please understand that life goes first before anything else. I am only human after all, not a robot! I thank you all for understanding. :)

# Skype protocol resources

Please visit the [Wiki](https://github.com/samis2613/blissnode/wiki) for all resources regarding the old Skype protocol.
