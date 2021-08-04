---
context:
  - login
---

# Graphical User Interfaces (GUI)

The {{ site.cluster.name }} environment supports running a graphical user interface (GUI) on {{ site.cluster.name }} while viewing and interacting with it on your local computer.  More specifically, and in more technical terms, {{ site.cluster.name }} supports NX and X11 Forwarding protocols


## X2Go (NX protocol)

### Requirements

Due to limitation in X2Go Client, it is _not_ possible to connect to {{ site.cluster.name }}  _when using SSH password_(\*).  Instead, in order to connect to {{ site.cluster.nickname }} using the X2Go Client, you have to have a working [SSH key pair] set up and configured the X2Go client. 

If you are connecting to {{ site.cluster.nickname }} from off campus, you will also have to have 2 Factor Authentication setup.

### Setup of the X2Go Client (once)

First, you will need to install the X2Go Client on your local computer.  For instructions on how to do this, see [Installing X2Go Client](https://wiki.x2go.org/doku.php/doc:installation:x2goclient). When you first run x2goclient:

 1. Use the menus to create a **New Session ...**
 2. Pick a **Session name**, e.g. `{{ site.cluster.name }}`
 3. Set the **Host** to a [development node]. Currently one of: `dev1`, `dev2`, `dev3`, or `gpudev1`
 4. Set the **Login** to _your_ {{ site.cluster.name }} username, e.g. `alice`
 5. In the **Use RSA/DSA key for ssh connection**, enter the path to the your private SSH Key.
 6. Select **Try auto login (via SSH Agent or default SSH key)**
 7. Check **Use Proxy server for SSH connection**
 8. Then in the **Proxy server** section:
    - Check **Same login as on X2Go Server**
    - Check **Same password as on X2Go Server**
    - Set **Host** to a {{ site.cluster.name }} [login node]. Currently one of: `{{ site.login1.hostname }}` or `{{ site.login2.hostname }}`
    - In the **RSA/DSA key:** field enter the path to your private SSH Key.
    - Select **SSH Agent or default SSH key**
 7. In the **Session type** section, choose `MATE`


### Logging in

Launch x2go client.

Double Click configured session (above).

Dialog: **Enter Passphrase to decrypt a key**

_Enter ssh key passphrase (if set)_

Dialog: **Choose DUO Authentication Method** (Only if connecting from off campus.)

_Perform Duo Authentication as prompted_

Dialog: **Remember connection authentication for 12 hours? [y/N]**

_Input y (This is important, it does NOT work if you choose "N")_

Dialog: **MATE on dev2** (This may happen with some configurations, even if you are using SSH Keys. We are investigating.)

_Enter Wynton Password_

Dialog: **Enter passphrase to decrypt a key.**

_Enter ssh key passphrase (if set)_

Dialog: **Enter passphrase to decrypt a key.**

_Enter ssh key passphrase (if set)_

Wait, Wait, MATE launches.



### 3D Graphics with X2Go (in alpha testing)

The X2Go client provides basic support for 3D applications with a software implementation of an ancient version of OpenGL.  On the GPU development nodes (*i.e.*, `gpudev1`), [VirtualGL](https://virtualgl.org/) is installed so you can use hardware accelerated 3D graphics.  All you need to do is:

 1. Opt-in by sending email to [{{ site.cluster.email_support }}](mailto:{{ site.cluster.email_support }}?subject=vglusers) with the subject `vglusers`
 2. Wait for confirmation that you have added to the `vglusers` group
 3. Use the `vglrun` program to run your program on a development node, either
    - by starting the application from a terminal (example below), or
    - by using a Wynton desktop shortcut, after editing it in your Wynton `~/Desktop` to have `vglrun` inserted before the program name on the **Exec=** line

For example:

```sh
[alice@{{ site.devel.name }} ~]$ vglrun your-program
```

You have to opt-in because there is a slight security risk.  See <https://virtualgl-users.narkive.com/KHab71sF/security-issues-for-virtualgl> case (2) for details.  Case (1) does not apply because all of the development nodes are headless.



## X11 Forwarding over SSH

You can also use X11 forwarding over the SSH connection used to connect to {{ site.cluster.name }}.

### Verify that you have a working X11 server (once)

Note that, to do this, you will need to be running an X server on your local machine.  You can check this by verifying that environment variable `DISPLAY` is set on your local computer, e.g.

```sh
{local}$ echo "DISPLAY='$DISPLAY'"
DISPLAY=':0'
```

If `DISPLAY` is empty, that is, you get:

```sh
{local}$ echo "DISPLAY='$DISPLAY'"
DISPLAY=''
```

then you don't have a local X server set up and the below will _not_ work.



### Log into the cluster with X11 forwarding

To setup the X11 forwarding when connecting to the cluster, just add option `-X` to your SSH call.  For performance reasons, we will also add option `-C` to enable SSH compression.  By using compression, the responsiveness and latency in GUIs will be much smaller - our benchmarks show a 5-7 times improvement when connected via the UCSF VPN (~60 Mbps download and ~5 Mbps upload).  To login with X11 forwarding and compression enabled, do:

```sh
{local}$ ssh -X -C alice@{{ site.login.hostname }}
alice1@{{ site.login.hostname }}:s password: XXXXXXXXXXXXXXXXXXX
[alice@{{ site.login.name }} ~]$ echo "DISPLAY='$DISPLAY'"
DISPLAY='localhost:20.0'
[alice@{{ site.login.name }} ~]$
```

By checking that `DISPLAY` is set, we know that X11 forwarding is in place.  If `DISPLAY` is empty, then make sure you have specified `-X`.


### Log into a development node with X11 forwarding

Now, since we should not run anything on the login nodes, the next step is to head over to one of the development nodes.  When doing so, we have remember to keep using X11 forward, that is, we need to use `-X` also here;

```sh
[alice@{{ site.login.name }} ~]$ ssh -X {{ site.devel.hostname }}
alice1@{{ site.devel.name }}:s password: XXXXXXXXXXXXXXXXXXX
[alice@{{ site.login.name }} ~]$ echo "DISPLAY='$DISPLAY'"
DISPLAY='localhost:14.0'
[alice@{{ site.devel.name }} ~]$
```

_Comment:_ There is no need to use SSH compression in this second step.  If used, it might even have a negative effect on the X11 latency.

Now, we have an X11 forward setup that runs all the way back to our local computer.  This will allow us to open, for instance, an XTerm window that runs on {{ site.devel.hostname }} but can be interacted with on the local computer;

```sh
[alice@{{ site.devel.name }} ~]$ xterm
[ ... an XTerm window is opened up ... ]
```

If you get an error here, make sure that `DISPLAY` is set and non-empty.


_Tips:_ You can login into a development node via a login node in a single call, e.g.

```sh
{local}$ ssh -X -C alice@{{ site.login.hostname }} ssh -X {{ site.devel.hostname }}
[alice@{{ site.devel.name }} ~]$
```




[development node]: {{ '/about/specs.html' | relative_url }}#development-nodes
[login node]: {{ '/about/specs.html' | relative_url }}#login-nodes
[SSH key pair]: {{ '/howto/log-in-without-pwd.html' | relative_url }}
