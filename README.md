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
> How to fix situation Error ERESOLVE could not resolve [duplicate](09/10/2022)
== npm install ==

After running ==npm install==  I'm getting this error:

npm ERR! code ERESOLVE
npm ERR! ERESOLVE could not resolve
npm ERR! 
npm ERR! While resolving: client@0.0.0
npm ERR! Found: @angular/compiler@11.0.9
npm ERR! node_modules/@angular/compiler
npm ERR!   @angular/compiler@"^11.0.7" from the root project
npm ERR!   peer @angular/compiler@"11.0.9" from @angular/compiler-cli@11.0.9
npm ERR!   node_modules/@angular/compiler-cli
npm ERR!     dev @angular/compiler-cli@"~11.0.7" from the root project
npm ERR!     peer @angular/compiler-cli@"^11.0.0" from @angular-devkit/build-angular@0.1100.7
npm ERR!     node_modules/@angular-devkit/build-angular
npm ERR!       dev @angular-devkit/build-angular@"^0.1100.6" from the root project
npm ERR! 
npm ERR! Could not resolve dependency:
npm ERR! @angular/platform-browser-dynamic@"^11.0.7" from the root project
npm ERR! 
npm ERR! Conflicting peer dependency: @angular/compiler@11.2.14
npm ERR! node_modules/@angular/compiler
npm ERR!   peer @angular/compiler@"11.2.14" from @angular/platform-browser-dynamic@11.2.14
npm ERR!   node_modules/@angular/platform-browser-dynamic
npm ERR!     @angular/platform-browser-dynamic@"^11.0.7" from the root project
npm ERR! 
npm ERR! Fix the upstream dependency conflict, or retry
npm ERR! this command with --force, or --legacy-peer-deps
npm ERR! to accept an incorrect (and potentially broken) dependency resolution.
npm ERR! 
npm ERR! See /home/salami/.npm/eresolve-report.txt for a full report.

npm ERR! A complete log of this run can be found in:
npm ERR!     /home/salami/.npm/_logs/2021-09-25T09_49_52_657Z-debug.log

So you can try this

```python
npm config set legacy-peer-deps true
```

```python
npm install --save --legacy-peer-deps
```
