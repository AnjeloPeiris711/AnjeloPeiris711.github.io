# AnjeloPeiris711.github.io
## Hi there <picture><source srcset="https://fonts.gstatic.com/s/e/notoemoji/latest/1f44b/512.webp" type="image/webp"><img src="https://fonts.gstatic.com/s/e/notoemoji/latest/1f44b/512.gif" alt="👋" width="32" height="32"></picture> , You can call me Anjelo Peiris
#### I am undergraduate Students of Plymouth University 
<img align="left" alt="nick" width="325" src="https://images6.fanpop.com/image/photos/41200000/IMG-1970-PNG-nick-wilde-41239315-702-970.png">
<p align ="right" style="color:green; writing-mode: vertical-rl;">I made this project just for fun,it allows me to create nice and simple blog</p>

> Install the USBIP tools and hardware database in Kali-Linux(02/08/2022)

```python
~/root💀junior# apt install linux-tools-5.4.0-77-generic hwdata
~/root💀junior# update-alternatives --install /usr/local/bin/usbip usbip /usr/lib/linux-tools/5.4.0-77-generic/usbip 20
```
----

> How to Install Nessus in wsl(26/09/2022)

if you  trying to install nessus for a vulnerability study in Kali linux. Kali is running as a Win-Kex instance from WSL2 on windows 11. I have downloaded Nessus and trying to install with:

```python
~/root💀junior# sudo dpkg -i Nessus-10.3.0-debian6_amd64.deb
```

But you are getting error as ...

```python
~/root💀junior# System has not been booted with systemd as init system (PID 1). Can't operate
```
I guess this is because WSL2 doesn't actually "boot up" Linux, instead Linux behaves like a docker container without any kind of init system.The easiest way to install is as a docker image.

So you can try this

```python
~/root💀junior# docker pull tenableofficial/nessus
```

After that

```python
~/root💀junior# docker run -d --name tenableofficial_nessus -p 8834:8834 tenableofficial/nessus
```
And that’s it! Now the container should be running and we can open https://localhost:8834/ and activate our new shiny Nessus instance.

----
