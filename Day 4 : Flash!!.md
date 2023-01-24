now it's time to make our SBC to fire up. SBC???? Never mentioned it before... okok so SBC is an acronym for Single Board Computer. now you can understand why this is called so.
today we will install Raspbian in the pi.

<h3>Prerequisites</h3>

so what do we need? let's make a list--

1. A computer to download raspbian. but you can flash any os that is iot compatible.
2. A minuimum of 8 gb SD card to flash the os (raspbian here)
3. SD card reader for your pc
4. ypur pi (obiously)
5. a mouse and keyboard. p.s. if you are going to do it hackerman style from your laptop only then i have the tips for that also
6. A screen, probably monitor via HDMI. p.s. if you are a hackerman or a hackergirl you won't probably need it.

this is all you need for now. mouse keyboard and a screen can be excluded by you if you want to learn sommething extra today. we will go over every steps.

<h3>Raspbian</h3>
To be more precise, it’s a Linux distribution.
You can find it in three versions:
1. Raspbian Lite: with a terminal interface only, no graphics at all
2. Raspbian Desktop: same base with an intuitive graphic interface
3. Raspbian Full: similar to Raspbian Desktop, but with more software directly installed
In the next few chapters, we’ll use Raspbian Desktop.

<h3>Downloading the OS</h3>
so you have chosen your os. you can either download it from the website or there is a good shortcut and stable way if you have a good internet connection.
lets download it from https://www.raspberrypi.com/software/operating-systems/ if your chosen os is from pi community.
if not good you are going for an out of the box approach. i absolutely encourage your discision. so in that case move to the etcher portion otherwise the next.

<h3>Raspberry Pi Imager</h3>
so you have a stable internet connection and you want to do the work clean and saft. okk we have proper things for you in our arsenal.
download raspberry pi imager from https://www.raspberrypi.com/software/ as preferable for your system.
it comes with all os included in raspberry pi commununity and with a bonus of -
1. ubuntu : desktop, server or core images.
2. manjaro ARM linux : semi-rolling distro for desktop and server use.
3. Apertis : debian based distro aimed at embedded system.
4. RISC os pi : fast and customizable for pi

now you have downloaded your imager. installed it in your system. now plug in the sd card and choose os from the imager. 
then select the storage device.
then go to settings. set username and passwd.
(HACKERMAN Tips) : to all hackerman and hackergirls who dont want to use screen or keyboard mouse but only laptop. enable ssh and wireless lan. this will come handy next.

now flash and sit back for a few minutes depending on your internet speed and et ready for the next steps.

<h3>Etcher</h3>
So you have chosen another os or want to do it another way. no problem we got you. lets download and install balena etcher for windows from https://www.balena.io/etcher
after dwonloading the steps are pretty straightforward. choose your storage device. then choose your iso then flash. boom your sd card is ready to be mounted.

<h3>booting the raspbian for the first time</h3>
1. Ensure that the power cable is not plugged in
2. Insert the SD card into your Raspberry Pi
3. Plug in the power input cable again and wait a few seconds
4. Raspbian will expand the main partition and start up
5. The system automatically logs in and introduces you to a welcome wizard: press next
6. Here, you can configure the basic options for your Pi:
7. Select your country and language from the lists 
8. Change the password
9. Connect to the Wi-Fi network, if you have one
10. Start system updates

Wait for the update to finish and restart the Raspberry Pi.
It may take a few times depending on your Internet connection speed.
After this, the Raspberry Pi is ready for your next day :)


<h3>the Hackerman team</h3>
so you would like to go for some extra challenge and boot your of without any scrren or keyboard or mouse or screen?
i absolutely love your madness and i am ready to help you in every possible way to achieve it.
remember it told you to srt up username and passwd and enable ssh prior in time of flashing the image.

now you have to plug in your sd card into pi and the lan cable and fire your pi up. now we have to locate our pi's ip address. we can do it in a few ways..

1. let's fire up our linux console and type 'ifconfig' . that will give us our ip addr. then use nmap. Nmap is a network scanner used to discover computers on a network.That’s precisely what we want to do! to install type in terminal 'sudo apt-get install nmap' assuming you are using debian. if you are using arch wtf are you doing in here? this place is below your standards you the great arch user! if lets say our ip is 192.168.0.xx, then scan with nmap typing 'sudo nmap -sP -sV -sC 192.168.0.0/24' if your ip is 192.168.1.xx then replace the 0 with 1 like 192.168.1.0 in nmap scan. thus you can find your raspberry pi's ip address.
2. looks tough? okk no issue. got an easier way. go to your router admin portal. how to go? type in the same ip local address you used in your nmap search in your browser and you will be greeted with the admin page. go to router network status and find the linked devices. the ip of ypur pi will be there.
3. A quick way to find it is to display the arp cache of your machine. The arp cache is a list of associations IP ⇆ MAC address for your network. On Linux or Mac you can display it by doing : 'arp -a'

now y'all know your pi's ip addr. so ssh into it using your pi's username@ip of your pi. like ' ssh raspberry@192.168.0.101 '
now type 'sudo raspi-console'    don't know command line? don't worry there will be a cheasheet for you soon.
go to interfacing option and enable vnc.

then get bac and from screen set screen resolution 1920x1080. this is for preventing a future vnc problems.

now to see the pi desktop in our computer, we will use vnc viewer. because i found it very useful in this case.
download vncviewer. it will be downloaded as a .deb file and to install .deb files in linux in the best way possible is to use gdebi.
install gdebi by the command 'sudo apt-get install gdebi' and then install vncviewer with it. now sign in to vnvviewer account. it will be somewhat of a tedious job but it will be worth it.

now all you need is the ip of the pi which you knew previously and connect to your pi using the ip. 
congrats you did the hard part!! you configured ans booted a pi withhout a screen or a keyboard or a mouse. true hackerman/hackergirl you are!!

