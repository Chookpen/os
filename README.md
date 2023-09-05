# Chookpen OS

A minimal GNOME desktop based on Arch Linux.

## Install

Don't install it yet, there's better versions coming!

If you want to install it in a virtual machine, install as if you were installing Arch Linux manually.

The live ISO's desktop can be found by running:

```
useradd (username)
passwd (username)
systemctl start gdm.service
```

Log in with your new username and password.

## Build it yourself

You'll need access to an Arch-based computer or virtual machine.

Clone the repository.

Install archiso: 
```
sudo pacman -S archiso
```
Find the folder contaning archlive and run:
```
sudo mkarchiso -v -w work -o output archive
```
Wait for a bit (maybe go feed your chickens).

Your ISO will be ready in the directory output.
