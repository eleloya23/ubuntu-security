# ubuntu-security
Practical security & privacy guide for Ubuntu Desktop users.

The document is not a guide yet. Currently it's just a draft with links, snippets & code in no particular order. Whatever I find relevant, I will put below.

------------------

echo "Updating Packages..."
apt-get -qq -y update

*Checar que onda con bugs y version actualizada de OpenSSl
echo "Installing OpenSSL..."
	rvm package install openssl


execute "gsettings set com.canonical.Unity.Lenses remote-content-search 'none'" \
    "Turn off 'Remote Search' so that search terms in Dash do not get sent over the internet"

execute "gsettings set com.canonical.Unity.ApplicationsLens display-available-apps false" \
"Disable Dash 'More suggestions' section"

`
    # Install tools for compiling/building software from source.

    install_package "Build Essential" "build-essential"

    # - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

    # GnuPG archive keys of the Debian archive.

    install_package "GnuPG archive keys" "debian-archive-keyring"

    install_package "Chromium" "chromium-browser"

    # - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

    install_package "cURL" "curl"
`

keep your packages upgraded. with apt-get update & upgrade. I believe there is also a tool that send periodic mail with vulnerable software versions.

Check shellsheck for bash vulnerable software

Investigate into disposable-vms or sandbox technology for linux desktop users.

Apparently its possible to dockerize GUI apps in ubuntu. Great way to add a layer of security.
https://blog.jessfraz.com/post/docker-containers-on-the-desktop/
http://fabiorehm.com/blog/2014/09/11/running-gui-apps-with-docker/

General Tips

* use monitoring tools. snort?
* disable unnecesary network services
* use chrooting / jails for some system services. They are not in jails by default.
* use log analysis software
* limit ssh to certain commands
* web browsers security
* crypto on local system
* vpns section
* use automatic binary integrity checking
* use BIOS password, boot sequence.
* Picking a safe password
* Disabling inetd.d or it's services
* Remove unnecesary packages
* subscribe to Debian/Ubuntu security mailing list
* enable Automatic Security Updates
* Remove root prompt on the kernel
* Restricting the use of the Magic SysRq key _advanced topic_
* User login actions: edit /etc/login.defs. You can set password policy expiration here. Althought I think this is only for people with good discipline. Change DEFAULT_HOME to no. Change SHA_CRYPT_MIN_ROUNDS to 10000 to make bruteforce more difficult. Start loggin succesfull logins with LOG_OK_LOGINS yes
* Be carefull with Log files permissions.
* Check interesting kernel patches. lids, trustees, selinux, exec-shield, grsecurity
* Check ext3 specific file attributes. i, a, etc.
* automatic setuid checks
* protect against ARP attacks
* system snapshot? Deepfreeze style?
* Check into X11 protection
* Check into using pf for a firewall
* Check into Bastile Linux for hardening. Is an automated tool used in RedHat apparently.
* How to protect against rootkits
* Using chattr +i to make certain binaries unmodifiable / inmmutable. The problem is with system upgrades.. Maybe a script that locks them and unlocks them.
* Removing banners for services. Avoid fingerprinting.
* Blacklisting, whitelisting kernel modules
* On security limits, prevent coredumps. Only useful for developers
* On backups.
* On disk encription ubuntu
* AppArmor. Kind of sandbox?



SSH TIPS

* If  you run local servers for testing & developing. You should attach them to specific interface. Loopback
* Disable rootlogin on ssh
* Obscure sshd port?
* Allow only certain users to access the machine via ssh.  AllowUsers alex ref me@somewhere. Whitelist
* You should disable Password Authentication in favor of public-key authentification
* Add a warning for legal protection. /etc/some_file
* Investigate about changing openssl for libressl
* Limiting file transfers to specific enviroment.
* Fail2Ban

* Restricting DMESG
* Look into DNSCrypt
* Using checksec http://www.trapkit.de/tools/checksec.html
* Mount /tmp With noexec,nodev,nosuid in RAM..
* GrSecurity, PAX for improved ADSLR https://micahflee.com/2016/01/debian-grsecurity/
* Talk about sending documents anonymously using OnionShare.
* Follow the steps on https://fixubuntu.com/
* Ubuntu hardening script. Interesting to take a look. https://github.com/micahflee/linux_harden
* torbrowser-launcher
* Set a Private HOME 700
* Check security with tiger

SOURCES
* download the harden-doc repo
http://www.insanitybit.com/2012/06/02/the-definitive-guide-for-securing-chrome/
