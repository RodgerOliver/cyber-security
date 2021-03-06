#  Cyber Security Course Volume 1
## Know Yourself - The Threat and Vulnerability Landscape

**Security** = way to protect your assets.

**Assets** = what is important and have to be secured.

* What is most confidential?
* What can't you afford to lose?
* What is irreplaceable?
* What would cause the most damage?
* What might impact your reputation?

**Privacy** = no one knows what you do, but can know who you are. Privacy is about content, secret content.

**Anonymity** = no one knows who you are, but can know what you do. Anonymity keeps your actions separate from your true identity.

**Pseudonymity** = you get a reputation from what you do, but it's has nothing to do with the real you.

![The Cyber Security Landscape Diagram](https://raw.githubusercontent.com/RodgerOliver/cyber-security/master/The-Cyber-Security-Landscape-Diagram.jpg)

Apply security controls to your assets to protect them from threats planned and executed by attackers. The threats try to exploit vulnerabilities in the security to get access to the assets.

**Risk** = Vulnerability X Threats X Consequences

**Threat Landscape or Model** = attackers and threats that are faced.

**Risk Assessments** = select the right security for specific assets.

Select, implement, assess and monitor the security controls for assets.

### CIA Triad

**Confidentiality, Integrity, Availability**

The security controls need to enable the security attributes (CIA Triad).

### Defense In Depth

**Prevent**: encryption.
**Detect**: setup a canary.
**Recover**: backup.

### ZERO Trust Model

Evaluate instead of trust. Mitigate the risk. Trust nothing.

Crypton and Encryptr are Zero Knowledge systems, they don't know what the clients are hosting.

## Know Your Enemy  - The Current Threat and Vulnerability Landscape

![Things to Stay Safe Online](https://raw.githubusercontent.com/RodgerOliver/cyber-security/master/Things-to-Stay-Safe-Online.jpg)

**Vulnerability or Bugs** = error in the software that creates a potential for a hacker to exploit it.

**Known bugs** have patches. Unknown bugs or **Zero Days** don't.

### Hackers

**Malware** = all programs written with malicious intent

Virus, worms, rootkits, trojans, ransomware, RATs, spywares, adware, scareware, browser hijacking are types of malware.

**Phishing** = attack that tricks the victim into clicking on a link, filling a form with personal details or executing something unwanted.

**Doxing** = research on an individual, organization or company top find personal or private information. It can be done by searching on the internet.

**Scams or Social Engineering Attacks** = attacks that central weaknesses in the human. Ex: fake emails saying that your bank account needs your documents; buying something and don't receive it; 

**CPU Hijackers** = malware that hijacks your CPU cycles to mine cryptocurrency.

**Darkweb** = any encrypted overlay network that can only be accessed with specific types of software, authorization, protocols or ports.

To protect against known vulnerabilities and bugs is to use **formal methods**. The software is fundamentally a mathematical system, therefore you can prove the correctness of a system by testing the properties of that system. This way you can provide complete evidence of correctness.

**Back Door** = weakness of a system.

## Encryption Crash Course

Encryption is a method of transforming readable data, called **plain text**, into a form that is unreadable that is called **cipher text**. And decryption is a method to transform cipher text into plain text.

### Symmetric Encryption Algorithm

There are to main components of symmetric encryption. There is the **algorithm (public, padlock)**, and the **key (secret)**.

This combination determines how the plain text will be jumbled up.

Examples: AES, DES, 3DES, Blowfish, RC4, RC5, RC6.

**AES** = Advanced Encryption Standard (Symmetric Algorithm, uses one key).

**256-bit** AES = bit length & keyspace (2 ^ bit-rate are the possible keys with this algorithm). The higher the number, the stronger the algorithm and the slower the encryption and decryption.

### Asymmetric Encryption Algorithm

Also known as Public & Private Key.

Examples: RSA, ECC, DH, El Gamal.

The **public key** is designed to be known by anybody, and the **private key** is secret. These key are mathematically related and have to be generated at the same time.

If you encrypt with the **public**, you need the **private** to decrypt.
If you encrypt with the **private**, you need the **public** to decrypt.

![Asymmetric Encryption](https://raw.githubusercontent.com/RodgerOliver/cyber-security/master/Asymmetric-Encryption.png)

The sender encrypts the message with the receiver's public key, so you want privacy or confidentiality, and the message is decrypted with the receiver's private key, but there is no authentication, cause anyone can use the receiver's public key to send a message to encrypt.

But if the message is encrypted with the sender's private key, it means that authenticating is what he is interested in, the receiver will know who sent it, but anyone can decrypt it with the sender's public key, so it is not private.

### Conclusion

Asymmetric: better key distribution, scalability, authentication and non-repudiation, slow, mathematically intense.

Symmetric: fast and strong.

### Hashes

A hash function takes as input data of any size and converts it into a fixed length string of characters. This is a one-way function, so it cannot be converted back to its original state, and no keys are required for this.

![Hash Functions](https://raw.githubusercontent.com/RodgerOliver/cyber-security/master/Hash-Functions.jpg)

### Digital Signatures

A Digital Signature is a hashed value that is encrypted with the sender's private key. When this is done, it provides authentication, non-repudiation and integrity.

To verify that the data is what it claims to be, the Digital Signature is decrypted with the sender's public key returning a hash, this hash compared to the hash of the data, if they match, that data is original and verified.

![Digital Signatures](https://raw.githubusercontent.com/RodgerOliver/cyber-security/master/Digital-Signatures.jpg)

### SSL and TLS

**SSL** = Secure Sockets Layer (older).

**TLS** = Transport Layer Security (newer but also called SSL).

SSL and TLS are cryptographic protocols designed to provide communication security over a network or the Internet.

When you access a website, the browser communicates with the server, and this is encrypted from end to end using TLS.

The data is encrypted with a symmetric algorithm, then to exchange this key an asymmetric algorithm is used, and a hash algorithm is used to ensure integrity.

**Cipher Suite** = the combination of algorithms used to encrypt and transmit the data.

[Click here](https://wiki.mozilla.org/Security/Server_Side_TLS) to see the best cipher suites to use.

### HTTPS

When you request a website with the `http://` the response is sent in plain text, but when it's requested with `https://` the response is over SSL or TLS.

![HTTPS](https://raw.githubusercontent.com/RodgerOliver/cyber-security/master/HTTPS.jpg)

The client generates a symmetric session key by using AES, for example, and encrypts it with the server's public key. This encrypted key is sent to the web server and they both use this symmetric key to encrypt the data they send back and forth. This is how a secure channel is established.

[Click here](https://www.ssllabs.com) to see what encryption options your website is using.

### Digital Certificates

**Digital Certificates** = a digital document containing information about the website signed by a authority. The authority is saying that all the information on that certificate is legitimate.

![Digital Certificates](https://raw.githubusercontent.com/RodgerOliver/cyber-security/master/Digital-Certificates.jpg)

### Steganography

**Steganography** = the practice of concealing information or files within other non-secret text or data. It's called "hiding data in plain sight". For example: a image (carrier) can look like normal, but there is a secret message inside it.

[OpenPuff](https://embeddedsw.net/OpenPuff_Steganography_Home.html) is a Stegranography tool that you can use on Windows.

## Setting up a Testing Environment Using Virtual Machines (Lab)

In order to learn and remember the content of the course it’s good to practically try things out. And one way to do this is to use a virtual environment or hypervisors, which emulates a physical computer.

![Hypervisor](https://raw.githubusercontent.com/RodgerOliver/cyber-security/master/Hypervisor.jpg)

To use VirtualBox, a type of hypervisor, you have to enable virtualization in the BIOS. After that, install a machine via an ISO file or a CD. Ounce the machine is readdy you can install Virtualbox Guest Additions to have a better experience.


## Sections 6 to 9 (tips)

Disable everything that can compromise you, such as privacy and tracking settings. Be aware of the security bugs of your OS.

Always patch your OS. This is so much important for privacy and security concerns. Always update.

Never use an admin or root account on daily usage. If you use and your computer is compromised, the attacker would be able to do a lot more damage.

Be aware of social engineering attacks. They can be everywhere. Pay attention to everything before you click on something or execute a program.

## Secutiry Domains

### Physical Security Domain

**Physical Security Domain (ie)** = a computer that has full disk encryption, protect with a good password, and a OS with a high level of security, and other computer for general use.

Physical isolation provides the highest level of security and privacy, and protects against attackers that have physical access to your computer.

### Virtual Security Domain

**Virtual Security Domain or Isolation (ie)** = a computer with a hypervisor, and the Host OS is Windows, for general use, and Debian in Virtualbox is used for high security.

Technology used to creat virtual isolation can be attacked, so you have to be aware of it. To create a separate domains you can do things like dualbooting, use hypervisors with VirtualBox or VMware, have hidden operating systems with VeraCrypt and TrueCrypt provide that, encrypted or hidden drive partitions, sandboxes, portable apps, bootable USBs, non-persistent OSs like Tails, OSs dedicated to isolation like Qubes.

## Security Through Isolation and Compartmentalization

**Tip 1** : CHANGE YOUR MAC ADDRESS. Check if other hardware hava a serial number or something like that.

**Tip 2** : SEPARATE YOUR ASSETS BY THEIR LEVEL OF IMPORTANCE. Do this and encrypt each volume with a different key.

**Tip 3** : USE PORTABLE APPS TO CONTROL THE FILES. This way every change made in the app, or history will be in one folder.

**Tip 4** : USE SANDBOXES TO BE ISOLATED. It is an isolated environment for running applications or code. It’s a virtual container that keeps the contents confined to it. All sandboxes are based on the core principle of not allowing the contents of the sandbox to spill out of the container.

![Sandbox](https://raw.githubusercontent.com/RodgerOliver/cyber-security/master/Sandboxes.gif)

**Tip 4** : VIRTUAL MACHINES ARE GOOD FOR ISOLATION AND COMPARTMENTALIZATION. When configured correctly they are a good way to stay safe in other environment.

You can use specific OSs to have a better result. Some of them are **Whonix**, **Knoppix**, **Qubes** and **Tails**.
