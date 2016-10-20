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


    # Install tools for compiling/building software from source.

    install_package "Build Essential" "build-essential"

    # - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

    # GnuPG archive keys of the Debian archive.

    install_package "GnuPG archive keys" "debian-archive-keyring"

    install_package "Chromium" "chromium-browser"

    # - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

    install_package "cURL" "curl"

keep your packages upgraded. with apt-get update & upgrade. I believe there is also a tool that send periodic mail with vulnerable software versions.

Check shellsheck for bash vulnerable software

Investigate into disposable-vms or sandbox technology for linux desktop users.

Apparently its possible to dockerize GUI apps in ubuntu. Great way to add a layer of security.
https://blog.jessfraz.com/post/docker-containers-on-the-desktop/
http://fabiorehm.com/blog/2014/09/11/running-gui-apps-with-docker/

nmap reference. Is it really neccesary for defense?

monitoring tools

download the harden-doc repo

unnecesary network services
tcpwrappers
host.equiv and other security holes
chrooting / jails
log analysis software
limit ssh to certain commands
web browsers security
crypto on local system
snort?
vpns
integrity checking
BIOS password, boot sequence.
Pick a safe password
Disabling inetd.d or it's services
Remove unnecesary packages
Debian/Ubuntu security mailing list
Automatic Security Updates
Remove root prompt on the kernel
Restricting the use of the Magic SysRq key *advanced topic
User login actions: edit /etc/login.defs
Default permissions for new files * umask
Log files permissions. Log checkers
Check interesting kernel patches. lids, trustees, selinux, exec-shield, grsecurity
ext3 specific file attributes. i, a, etc.
binaries integrity checking automatization
automatic setuid checks
protect against ARP attacks
system snapshot?
