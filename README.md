<p align="center">
<a href=https://www.bountysource.com/trackers/3011939-pi-hole-pi-hole?utm_source=3011939&utm_medium=shield&utm_campaign=TRACKER_BADGE><img src="https://www.bountysource.com/badge/tracker?tracker_id=3011939"></a>
<a href="https://www.codacy.com/app/Pi-hole/pi-hole?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=pi-hole/pi-hole&amp;utm_campaign=Badge_Grade"><img src="https://api.codacy.com/project/badge/Grade/c558a0f8d7124c99b02b84f0f5564238"/></a>
<a href=https://travis-ci.org/pi-hole/pi-hole><img src="https://travis-ci.org/pi-hole/pi-hole.svg?branch=development"></a>
</p>

<p align="center">
<a href=https://discourse.pi-hole.net><img src="https://assets.pi-hole.net/static/Vortex_with_text_and_TM.png" width=210></a>
</p>

## Pi-hole®: The multi-platform, network-wide ad blocker

Block ads for **all** your devices _without_ the need to install client-side software.

<p align="center">
<a href=http://www.digitalocean.com/?refcode=344d234950e1><img src="https://assets.pi-hole.net/static/DOHostingSlug.png"></a>
</p>

## Executive Summary
The Pi-hole blocks ads at the DNS-level, so all your devices are protected.

- **Easy-to-install** - our intelligent installer walks you through the process with no additional software needed on client devices
- **Universal** - ads are blocked in _non-browser locations_ such as ad-supported mobile apps and smart TVs
- **Quick** - installation takes less than ten minutes and it [_really_ is _that easy_](https://discourse.pi-hole.net/t/new-pi-hole-questions/3971/5?u=jacob.salmela)
- **Informative** - an administrative Web interface shows ad-blocking statistics
- **Lightweight** - designed to run on [minimal resources](https://discourse.pi-hole.net/t/hardware-software-requirements/273)
- **Scalable** - even in large environments, [Pi-hole can handle hundreds of millions of queries](https://pi-hole.net/2017/05/24/how-much-traffic-can-pi-hole-handle/) (with the right hardware specs)
- **Powerful** - advertisements are blocked over IPv4 _and_ IPv6
- **Fast** - it speeds up high-cost, high-latency networks by caching DNS queries and saves bandwidth by not downloading advertisement elements
- **Versatile** -  Pi-hole can function also function as a DHCP server


## Your Support Still Matters

Digital Ocean helps with our infrastructure, but our developers are all volunteers so *your donations help keep us innovating*. Sending a donation using our links below helps us offset a portion of our monthly costs.

-   ![Paypal](https://assets.pi-hole.net/static/paypal.png) [Donate via PayPal](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=3J2L3Z4DHW9UY)
-   ![Bitcoin](https://assets.pi-hole.net/static/Bitcoin.png) Bitcoin Address: 1GKnevUnVaQM2pQieMyeHkpr8DXfkpfAtL

### Other Ways To Support Us
If you're not the type to give away money, there are [other ways support us](https://pi-hole.net/donate): you can sign up for services through our affiliate links, which will also help us offset some of the costs associated with keeping Pi-hole operational.

### One-Step Automated Install
1.  Install a [supported operating system](https://discourse.pi-hole.net/t/hardware-software-requirements/273/1)
2.  Run the command below (it downloads [this script](https://github.com/pi-hole/pi-hole/blob/master/automated%20install/basic-install.sh) in case you want to read over it first!)

### `curl -sSL https://install.pi-hole.net | bash`

#### Alternative Semi-Automated Install Methods
_If you wish to read over the script before running it, run `nano basic-install.sh` to open the file in a text viewer._

##### Clone our repository and run the automated installer from your device.

```
git clone --depth 1 https://github.com/pi-hole/pi-hole.git Pi-hole
cd Pi-hole/automated\ install/
bash basic-install.sh
```

##### Or

```bash
wget -O basic-install.sh https://install.pi-hole.net
bash basic-install.sh
```

Once installed, [configure your router to have **DHCP clients use the Pi-hole as their DNS server**](https://discourse.pi-hole.net/t/how-do-i-configure-my-devices-to-use-pi-hole-as-their-dns-server/245) and then any device that connects to your network will have ads blocked without any further configuration.

If your router does not support setting the DNS server, you can [use Pi-hole's built in DHCP server](https://discourse.pi-hole.net/t/how-do-i-use-pi-holes-built-in-dhcp-server-and-why-would-i-want-to/3026); just be sure to disable DHCP on your router first.

Alternatively, you can manually set each device to use Pi-hole as their DNS server.

## What is Pi-hole and how do I install it?
<p align="center">
<a href=https://www.youtube.com/watch?v=vKWjx1AQYgs><img src="https://assets.pi-hole.net/static/video-explainer.png"></a>
</p>


## Get Help Or Connect With Us On The Web

-   [Users Forum](https://discourse.pi-hole.net/)
-   [FAQs](https://discourse.pi-hole.net/c/faqs)
-   [Feature requests](https://discourse.pi-hole.net/c/feature-requests?order=votes)
-   [Wiki](https://github.com/pi-hole/pi-hole/wiki)
-   ![Twitter](https://assets.pi-hole.net/static/twitter.png) [Tweet @The_Pi_Hole](https://twitter.com/The_Pi_Hole)
-   ![Reddit](https://assets.pi-hole.net/static/reddit.png) [Reddit /r/pihole](https://www.reddit.com/r/pihole/)
-   ![YouTube](https://assets.pi-hole.net/static/youtube.png)  [Pi-hole channel](https://www.youtube.com/channel/UCT5kq9w0wSjogzJb81C9U0w)
-   [![Join the chat at https://gitter.im/pi-hole/pi-hole](https://badges.gitter.im/pi-hole/pi-hole.svg)](https://gitter.im/pi-hole/pi-hole?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

## Technical Details

The Pi-hole is an **advertising-aware DNS/Web server**. If an ad domain is queried, a small Web page or GIF is delivered in place of the advertisement.

### Gravity: Finding Ads To Block

The [gravity.sh](https://github.com/pi-hole/pi-hole/blob/master/gravity.sh) script does most of the magic. The script pulls in over 100,000 known ad-serving domains from many sources and aggregates them into a single list.

#### Additional Blocklists
You can also use Pi-hole to block additional domains beyond the defaults.  It can even be used to block malware or phising domains.  [The Big Blocklist Collection](https://wally3k.github.io/) is a good resource for finding additional domains to block.



#### Other Operating Systems

The automated install is only for a clean install of a Debian family or Fedora based system, such as the Raspberry Pi. However, this script will work for most UNIX-like systems, some with some slight **modifications** that we can help you work through. If you can install `dnsmasq` and a web server, it should work OK. If there are other platforms you'd like supported, let us know.

### Web Interface

The [Web interface](https://github.com/pi-hole/AdminLTE#pi-hole-admin-dashboard) will be installed automatically so you can view stats and change settings. You can find it at:

`http://192.168.1.x/admin/index.php` or `http://pi.hole/admin`

![Pi-hole Advanced Stats Dashboard](https://assets.pi-hole.net/static/dashboard212.png)

### Whitelist and blacklist

Domains can be whitelisted and blacklisted using either the web interface or the command line. See [the wiki page](https://github.com/pi-hole/pi-hole/wiki/Whitelisting-and-Blacklisting) for more details
<p align="center">
<a href=https://github.com/pi-hole/pi-hole/wiki/Whitelisting-and-Blacklisting><img src="https://assets.pi-hole.net/static/whitelist212.png"></a>
</p>

### Settings

The settings page lets you control and configure your Pi-hole.  You can do things like:

- enable Pi-hole's built-in DHCP server
- exclude domains from the graphs
- configure upstream DNS servers
- and more!

![Settings page](https://assets.pi-hole.net/static/settings212.png)

#### Built-in DHCP Server

Pi-hole ships with a built-in DHCP server.  This allows you to let your network devices use Pi-hole as their DNS server if your router does not let you adjust the DHCP options.
<p align="center">
<a href=hhttps://discourse.pi-hole.net/t/how-do-i-configure-my-devices-to-use-pi-hole-as-their-dns-server/245><img src="https://assets.pi-hole.net/static/piholedhcpserver.png"></a>
</p>

## API

A basic read-only API can be accessed at `/admin/api.php`. It returns the following JSON:

``` json
{
    "domains_being_blocked": "136708",
    "dns_queries_today": "18108",
    "ads_blocked_today": "14648",
    "ads_percentage_today": "80.89"
}
```

The same output can be achieved on the CLI by running `chronometer.sh -j`

## Real-time Statistics

You can view [real-time stats](https://discourse.pi-hole.net/t/how-do-i-view-my-pi-holes-stats-over-ssh-or-on-an-lcd-using-chronometer/240) via `ssh` or on an [2.8" LCD screen](http://amzn.to/1P0q1Fj). This is accomplished via [`chronometer.sh`](https://github.com/pi-hole/pi-hole/blob/master/advanced/Scripts/chronometer.sh). ![Pi-hole LCD](http://i.imgur.com/nBEqycp.jpg)

## Pi-hole Projects

-   [An ad blocking Magic Mirror](https://zonksec.com/blog/magic-mirror-dns-filtering/#dnssoftware)
-   [Pi-hole stats in your Mac's menu bar](https://getbitbar.com/plugins/Network/pi-hole.1m.py)
-   [Get LED alerts for each blocked ad](http://thetimmy.silvernight.org/pages/endisbutton/)
-   [Pi-hole on Ubuntu 14.04 on VirtualBox](http://hbalagtas.blogspot.com/2016/02/adblocking-with-pi-hole-and-ubuntu-1404.html)
-   [Docker Pi-hole container (x86 and ARM)](https://hub.docker.com/r/diginc/pi-hole/)
-   [Splunk: Pi-hole Visualiser](https://splunkbase.splunk.com/app/3023/)
-   [Pi-hole Chrome extension](https://chrome.google.com/webstore/detail/pi-hole-list-editor/hlnoeoejkllgkjbnnnhfolapllcnaglh) ([open source](https://github.com/packtloss/pihole-extension))
-   [Go Bananas for CHiP-hole ad blocking](https://www.hackster.io/jacobsalmela/chip-hole-network-wide-ad-blocker-98e037)
-   [Sky-Hole](http://dlaa.me/blog/post/skyhole)
-   [Pi-hole in the Cloud!](http://blog.codybunch.com/2015/07/28/Pi-Hole-in-the-cloud/)
-   [unRaid-hole](https://github.com/spants/unraidtemplates/blob/master/Spants/unRaid-hole.xml#L13)--[Repo and more info](http://lime-technology.com/forum/index.php?PHPSESSID=c0eae3e5ef7e521f7866034a3336489d&topic=38486.0)
-   [Pi-hole on/off button](http://thetimmy.silvernight.org/pages/endisbutton/)
-   [Minibian Pi-hole](http://munkjensen.net/wiki/index.php/See_my_Pi-Hole#Minibian_Pi-hole)
-   [Windows Tray Stat Application](https://github.com/goldbattle/copernicus)
-   [Let your blink1 device blink when Pi-hole filters ads](https://gist.github.com/elpatron68/ec0b4c582e5abf604885ac1e068d233f)
-   [Pi-hole Prometheus exporter](https://github.com/nlamirault/pihole_exporter): a [Prometheus](https://prometheus.io/) exporter for Pi-hole
-   [Pi-hole Droid - open source Android client](https://github.com/friimaind/pi-hole-droid)
-   [Windows DNS Swapper](https://github.com/roots84/DNS-Swapper), see [#1400](https://github.com/pi-hole/pi-hole/issues/1400)

## Coverage

-   [Adafruit livestream install](https://www.youtube.com/watch?v=eg4u2j1HYlI)
-   [TekThing: 5 fun, easy projects for a Raspberry Pi](https://youtu.be/QwrKlyC2kdM?t=1m42s)
-   [Pi-hole on Adafruit's blog](https://blog.adafruit.com/2016/03/04/pi-hole-is-a-black-hole-for-internet-ads-piday-raspberrypi-raspberry_pi/)
-   [The Defrag Show - MSDN/Channel 9](https://channel9.msdn.com/Shows/The-Defrag-Show/Defrag-Endoscope-USB-Camera-The-Final-HoloLens-Vote-Adblock-Pi-and-more?WT.mc_id=dlvr_twitter_ch9#time=20m39s)
-   [MacObserver Podcast 585](http://www.macobserver.com/tmo/podcast/macgeekgab-585)
-   [Medium: Block All Ads For $53](https://medium.com/@robleathern/block-ads-on-all-home-devices-for-53-18-a5f1ec139693#.gj1xpgr5d)
-   [MakeUseOf: Adblock Everywhere, The Pi-hole Way](http://www.makeuseof.com/tag/adblock-everywhere-raspberry-pi-hole-way/)
-   [Lifehacker: Turn Your Pi Into An Ad Blocker With A Single Command](http://lifehacker.com/turn-a-raspberry-pi-into-an-ad-blocker-with-a-single-co-1686093533)!
-   [Pi-hole on TekThing](https://youtu.be/8Co59HU2gY0?t=2m)
-   [Pi-hole on Security Now! Podcast](http://www.youtube.com/watch?v=p7-osq_y8i8&t=100m26s)
-   [Foolish Tech Show](https://youtu.be/bYyena0I9yc?t=2m4s)
-   [Pi-hole on Ubuntu](http://www.boyter.org/2015/12/pi-hole-ubuntu-14-04/)
-   [Catchpoint: iOS 9 Ad Blocking](http://blog.catchpoint.com/2015/09/14/ad-blocking-apple/)
-   [Build an Ad-Blocker for less than 10$ with Orange-Pi](http://www.devacron.com/orangepi-zero-as-an-ad-block-server-with-pi-hole/)
