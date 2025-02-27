.. _faq-startos:

===========
StartOS FAQ
===========

.. contents::
  :depth: 2 
  :local:

How is StartOS different from Umbrel?
-------------------------------------
Please see this :ref:`comparison page <umbrel-compare>` for a breakdown.

Can I run StartOS on a VPS or VM?
---------------------------------
Yes! The :ref:`DIY Guide <diy>` has some details.  Also check out our `Community Hub <https://community.start9.com>`_ to see guides and tips from Community members.

Is it possible to use StartOS on my own hardware?
-------------------------------------------------
Yes! The :ref:`DIY Guide <diy>` will take you through our guidelines. This option is great for people who already own some hardware or who live outside the US and want to save on shipping and customs fees.

Additionally, StartOS is available for you to download or build from source under the Start9 Personal Use `License <https://start9.com/license>`_, for free.  The caveat is that you will miss out on the perks that come along with purchasing from us, such as white-glove support, and others, which will grow over time.

Do I plug my Start9 server into my computer?
--------------------------------------------
No. Your Start9 server only needs to be plugged into power and internet, just like your router.  You can set it up right by your router and, similar to a router, generally forget about it - as all access is via your other devices.

Do I plug in a monitor, keyboard, and mouse?
--------------------------------------------
Typically, no.  It is not necessary or recommended to do this as StartOS runs in "headless" mode by default - meaning that you will access it from your computer or mobile device.  However, we have recently added "Kiosk" mode, which allows the installation (and use) of StartOS with a monitor/keyboard/mouse.

How much storage does a Start9 server have?
-------------------------------------------
Currently, Start9 servers ship with 128/256GB SD cards (Server Lite) and  1/2/4TB SSDs (Server One & Pure), but you may use a larger drive if you prefer.  We advise **against** HDDs at this time for perfomance reasons.

Are my Internet requests anonymous and secure?
----------------------------------------------
StartOS and every service on our Marketplace serve their own Tor Hidden Services with unique Tor addresses. The private keys used to create these addresses are generated on your phone or computer when you first set up StartOS. No one, not even Start9, has any idea what your Tor addresses are, let alone the password(s) you choose to authenticate with them.

Does Start9 have access to my personal Start9 server's encryption keys?
-----------------------------------------------------------------------
No.  Your keys are generated on your device using the password you create so we CAN NOT, nor would we like to, see your private keys.

Can multiple Start9 servers be setup to run redundantly in physically separate locations?
-----------------------------------------------------------------------------------------
Currently no, but we have plans for a feature that will enable StartOS to provide encrypted, automated backups across multiple servers.  You can however, run as many servers as you'd like, copying data manually to each.

How does StartOS compare to other Bitcoin nodes or personal servers?
--------------------------------------------------------------------
The cheapest way to run a Bitcoin/Lightning node is to buy a Raspberry Pi (or equivalent), download or compile Bitcoin, LND/CLN, etc, and host everything on Tor.  This takes even technical people significant time to accomplish. On the other end of the spectrum is something like StartOS, which "just works". In between is stuff like MyNode, Nodl, RoninDojo, Umbrel, and Raspiblitz, which all require some degree of command line effort and manual configuration. The biggest benefit of StartOS is that it is infinitely extensible to all of open-source, self-hosted software. The service listing will expand enormously over time in ways the other platforms may choose not to, or have difficulty implementing.

Would you consider (Umbrel, Nodl, RoninDojo, etc) a competitor to StartOS, or are they different enough to be compatible?
--------------------------------------------------------------------------------------------------------------------------
Other node devices are competitors, and there are distinct trade-offs to each platform, but we are definitely moving toward the same future, which is a win for everyone!

One difference with Start9 is that we began with a plan to create an OS for general-purpose sovereign hosting of server-side software.  No other project in this space (that we know of) started this way.  There's also no reason you can't use more than one device.  As an example, some users prefer StartOS for their data and RoninDojo for their Bitcoin stack.

Some other things that StartOS offers that others do not:

- Graphical configuration of services (instead of command line)
- System backups (pretty important)
- Encrypted connection over the home network (https)
- Health Checks for quick-glance understanding of the status of your services
- Unique user experiences created by service-packagers, including "Actions" (custom commands at the click of a button!)

From an architectural perspective, StartOS is a true operating system (of the Linux flavor), giving you the ability to understand and control what is going on.  Many other systems are black boxes offering little insight or agency to you. If something goes wrong, you'll have to put in your engineer hat and go command line diving. Lastly, our team is very responsive and helpful. We pride ourselves on providing incredible customer support and education.

How can I migrate from MyNode/Raspiblitz/Umbrel to StartOS and keep my lightning channels intact?
-------------------------------------------------------------------------------------------------
We've created a guide to help you `transform your Umbrel's bitcoin stack into a Start9 server <https://community.start9.com/t/howto-migrate-from-umbrel-0-5-x-to-embassy/56>`_.

Alternatively, if you have an Umbrel and a Start9 server and they're on the same network, you can just select *Services > Lightning Network Daemon > Actions > Import from Umbrel* in your Start9 server's web interface and your LND settings and channels will be automatically migrated.

As of LND v0.16.4, similar Actions are available for MyNode and Raspiblitz.

Can I mine Bitcoin with this?
-----------------------------
You do **not** want to do that.  Mining equipment is highly specialized, and this is not that.

Does StartOS only work over Tor?  No http or VPN?
-------------------------------------------------
Your server's services are currently primarily accessible over Tor. In many cases we use HTTP over Tor (they are not mutually exclusive), you can see this by navigating to the Tor address in a browser and see the “http” in front of it.  Further networking options (and massive flexibility) are coming with StartOS v040.  You can also connect directly via LAN if you are on the same network as your device.

Which network traffic travels over tor and which does not?
----------------------------------------------------------
In StartOS versions previous to v040, inbound connections can only be **initiated** over tor.  Clearnet (IP) connections can be initiated outbound by the OS (in the case of OS updates or accessing the Start9 Marketplace), or by services (such as by Bitcoin when connecting to the Bitcoin p2p network).  In many cases, it is possible to operate **only** via tor by configuring a particular service to do so.  For example, in the Bitcoin config, you can "Disable Clearnet" connections, or remove your node from the public network entirely.

Following StartOS v040, powerful and flexible networking configs will be possible across the system.

What if someone gets physical access to my device, can they read the contents? Is it encrypted?
-----------------------------------------------------------------------------------------------
The data is currently encrypted at rest, but not in a way that would prevent a sophisticated attacker from accessing it.  This is a step towards better security in the near future.  At-rest encryption on servers is a serious challenge, because of the need for remote availability.  For example, you may not be at home to enter an encryption password following a power outage, leaving you without access to your server.

Services like Vaultwarden, however, encrypt all user data, so your passwords will not be compromised unless they know your master password.

Why http and not https for .onion websites?
-------------------------------------------
When visiting a Tor V3 URL (.onion website), your communications are end-to-end encrypted and onion-routed by default. There is no added benefit to using https.  See this `article <https://community.torproject.org/onion-services/advanced/https/>`_ from the Tor Project for more details.  You will notice that some services implement ``https`` for client compatibility reasons, however.
