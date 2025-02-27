.. _faq-basic-use:

=============
Basic Use FAQ
=============

.. contents::
  :depth: 2 
  :local:

Is it easy to use?
------------------
Yes!  A Start9 server is designed to be plugged into power and internet, and after a short setup, is immediately ready to use.  Getting services is as easy as getting apps for a smartphone.
As with anything new, you should expect to spend a little time learning the functions and features, and keep in mind that some services may be more complex to understand and use than others.

So I can run my own cloud?
--------------------------
Yes! No special skills or knowledge are required to host all your own services and replace those previously thought "necessary" for modern digital life.

Can I run multiple Start9 servers?
----------------------------------
Yes, but there is currently no way to synchronize or federate them.  We are working on ways to make this possible in the future.

Can I still use my VPN?
-----------------------
The short answer is yes, but they can cause some conflicts when accessing your server.  If you need to troubleshoot, turning off your VPN is a good place to start.  The following VPNs are known to not interfere with the proper settings enabled:

- Mullvad - Go to "Settings -> VPN Settings -> Local Network Sharing" - enable this option to be able to access your server's ``.local`` addresses.
- ProtonVPN - Go to "Preferences -> Connection -> Allow LAN Connections" - enable this option to be able to access your server's ``.local`` addresses.
- iVPN - Go to "Settings -> IVPN Firewall -> LAN settings -> Allow LAN traffic when IVPN firewall is enabled" - enable this option to be able to access your server's ``.local`` addresses.

What if I forget my StartOS password?
-------------------------------------
Please follow the :ref:`password reset guide<reset-password>`.

Can I move my server to another location?  What happens when I do this?
------------------------------------------------------------------------
Yes, you can move your server to another network.  Your service tor addresses will remain the same.  Remember that you can only access via LAN if you are accessing with a device on the same network as your server.

What's the advantage of using the .local address over the .onion address?
-------------------------------------------------------------------------
If you are in your home/office network with your server, it is both faster and more private since the connection never leaves your household/office.  The downside is that it won't work if you're on the go.

Can I use the .local addresses over the Tor Browser?
----------------------------------------------------
No. The Tor Browser requires all web visits to first enter the Tor network. Once you have entered the Tor network there is no way to exit the Tor network in such a way that .local/mDNS addresses resolve.

Can I use .local addresses on Android?
--------------------------------------
Yes.  Support was added in version 12 of Android.  For custom ROMs, such as Calyx and Graphene, version 13 is required.

Can I have multiple users on StartOS?
-------------------------------------
Currently, StartOS itself is designed for a single user. There is no way to grant others access to your server without sharing your personal, master password, which is not recommended. There are certain services, however, such as Vaultwarden, File Browser, and Nextcloud, that do support multiple users (aka the "Uncle Jim" model) where people who trust you (and vice versa) can create their own, personal accounts for these services. Just remind them that they are trusting you with their data, and that it might be preferable for them to take the final leap of sovereignty and get a server of their own.

Multi-tenancy is a desired future OS feature.  Stay tuned.

What can I do if I am having issues connecting to a mobile app over Tor?
------------------------------------------------------------------------
The best solution to connection issues is normally to restart Orbot, or to reboot the phone.  This will solve most common problems.

If I uninstall a service, then re-install it, does my data remain?
------------------------------------------------------------------
No.  When uninstalling a service, you completely destroy everything associated with it.  This is because each service runs in it's own 'container', which includes all the required software and operating system environment that it needs to function.  When uninstalling, this container is wiped from StartOS, and with it, any associated service data that you have not backed up.

This can be useful, as you may want to wipe a service and start anew. For example, you might want to receive a fresh Tor .onion address, or to spin up a new Lightning node.  However, if you do this, YOU MUST BE 100% CERTAIN THAT YOU ARE PREPARED TO LOSE ALL DATA for this service.  Also, keep in mind that other services may depend on the service you are uninstalling.

Do I need to delete existing backups before doing a new backup? Or does a new backup override the old backup?
-------------------------------------------------------------------------------------------------------------
No, you don't need to delete the old backups. The technology we use updates the existing backup.  This is known as a "diff-based" model, where the "difference" in backups is what is recorded.

Can I clone my SSD for backup purposes?
---------------------------------------
.. warning:: **DO NOT do this if you are running LND or CLN**. If you clone the SSD, then go back to running LND or CLN, and you *ever* try to restore the SSD, there is a good chance you will lose *all your channel funds*. Also, if you try to use the SSD for a 2nd server, that will also result in loss of funds. This has nothing to do with Start9 or StartOS; it is inherent to the architecture of Lightning.

It is neither necessary, nor recommended to do this.  If you need to copy all data to a new drive because you are migrating or upgrading hardware, check out the :ref:`"Transfer" option explained here<backup-restore>`.

Why would I even buy this when I can just build it for free?
------------------------------------------------------------
(1) You will get white glove support in your preferred format, from text chat to screen sharing conference calls.

(2) Supporting the project. Buying a server from Start9 is your way of supporting the development of the project. And it's not just out of gratitude, but rather, a recognition that if the project isn't funded, the cool software stops coming.

(3) Convenience. This is the big one. It's true, some people will choose to use the software without buying a server, but most will not. Very few people on Earth are comfortable using the command line, compiling code, and configuring an OS. Furthermore, hardware is necessary. Sure, some people already have a Raspberry Pi, and others may try to re-purpose an old laptop, but many people would be choosing between buying the hardware components themselves and assembling vs buying pre-assembled at a reasonable markup.

Bottom line...We are charging a marginal rate for something incredibly powerful, and we think the convenience of a plug-and-play device, free service marketplace, and white glove support is where the money is. Anyone could build their own couches too, but here is a reason furniture stores exist. How much is your time worth?

My server came with a 'product key,' or similar unique code - what is that?
---------------------------------------------------------------------------
This will entitle you to white glove support as well as future benefits yet to be announced.
