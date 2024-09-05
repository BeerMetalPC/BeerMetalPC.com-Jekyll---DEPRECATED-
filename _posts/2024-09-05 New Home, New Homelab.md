---
layout: post
title: New Home, New Homelab
tags:
  - Projects
  - Ramble
caption: What better way to celebrate achieving homeownership than by immediately putting holes in the walls?
description: We bought a house this year, so I got to build out a network and homelab for the first time. This post repackages some of my notes and thought process from that effort.
date: 5 September 2024
image:
  path: "\assets\img\blog\Rack-20240905-[608]-min.JPG"
  srcset:
    1920w: "\assets\img\blog\Rack-20240905-[608]-min.JPG"
    960w: "\assets\img\blog\Rack-20240905-[304]-min.JPG"
    480w: "\assets\img\blog\Rack-20240905-[152]-min.JPG"
sitemap: false
---

* this unordered seed list will be replaced by the toc
{:toc}

So as to not bury the lede, we bought a house this past April! 🎉 

This is the realization of a long time dream for the wife and I. It has resulted in a lot of work that has distracted me from other side projects, writing, and just mere day to day routine for a time. The montage scene includes the closing, a full sewer line replacement, AC replacement, dishwasher and disposal installs, some minor structural and insulation repairs in a crawlspace under an addition, painting, the move, the unpacking, and *many* trips to Hammerbarn. 

What's relevant here is I was able to get an electrician in recently to pull some Cat6, staging drops for APs, cameras, and a couple wall jacks around the place. I've done a lot of reading and note-taking in the past couple months as I plan for the network and equipment. Since half of this written already, and I've done a shit job of writing anything personally of late, I figure it's good fodder for a post. 

## Why the upgrades? 

Our network that's made the jump over from our old apartment to the house already had some prosumer kit. A [Firewalla Gold ](https://firewalla.com/products/firewalla-gold) was already running the show with VLANs for trusted, semi-trusted, and a couple different flavors of untrusted (work, IoT, and guest) devices, and a set of Eero 5's in bridge mode formed a mesh WiFi network. I admit this was perfectly good for our needs, even if the Eeros are starting to fall behind on their 802.11 letter. 

I've had some conversations with my boss and skip level recently about professional development. One of the items I self identified was that because I came up through the risk side of IT and security, I feel that while I can understand and speak to some of the more technical aspects of security I've never actually been "hands on keyboard" with more modern tooling. Professionally we're addressing that by getting me more involved in operations and infrastructure projects. While this home networking project doesn't mesh neatly with my day job's responsibilities, I do think it is an opportunity both to future-proof the home network and for me to get hands on time in an ops-y sysadmin-y way, even if it is just as a homelab. 

## To Lack Rack, or not to Lack Rack?

For those unfamiliar, IKEA offers a low cost side table called the [Lack](https://www.ikea.com/us/en/p/lack-side-table-black-brown-80104268/) which just so happens to be wide enough between the legs to fit standard 19" rack mount equipment, up to 8U worth per table. I found no shortage of inspiration and guidance on the art of the Lack Rack, some of the most helpful links are below with a special nod to Baker Street Forensics for their excellent posts. 

- [A relatively low profile Lack Rack seen on r/Ubiquiti](https://www.reddit.com/r/Ubiquiti/comments/vvzhym/799_ikea_lack_rack/)
- [DIY Home Network Rack – the Lack Rack – Baker Street Forensics](https://bakerstreetforensics.com/2022/02/28/diy-home-network-rack-the-lack-rack/)
- [Lack Rack Updates – Baker Street Forensics](https://bakerstreetforensics.com/2022/09/03/lack-rack-updates/)
- [Lack Rack part III: the Final chapter – Baker Street Forensics](https://bakerstreetforensics.com/2022/09/08/lack-rack-part-iii-the-final-chapter/)
- [Steampunk or Cyberpunk ? – Baker Street Forensics](https://bakerstreetforensics.com/2023/06/05/steampunk-or-cyberpunk/)
- [LackRack - Eth0Wiki](https://wiki.eth0.nl/index.php/LackRack)
- [List of IkeaRacks - Eth0Wiki](https://wiki.eth0.nl/index.php/List_of_IkeaRacks)

There's just a couple problems. The legs are honeycomb / semi-hollow and the max weight rating on the table top is only 55lbs. If I load one of these down with 8U worth of kit, how long can I reasonably expect the legs to hold up? If I rearrange things and make upgrades, will I be further weakening the legs with every removed and reapplied screw? 

This sent me down a path of planning to reinforce a Lack. You can follow the lead of u/[RepresentativeAsk798](https://www.reddit.com/user/RepresentativeAsk798/) and make a "[Lack Rack Pro](https://www.reddit.com/r/lackrack/comments/19fiqxu/lack_rack_pro/)". But lacking (har har) my own 3D printer to make the bracket, and facing the need to purchase two Lacks, bolts, some 18U rails, buy a couple beers for someone to print me the brackets, and then take the time to assemble it all, wouldn't it just be cheaper to buy a purpose built rack? 

....
.... .... 

So anyway I bought a [15U Navepoint rack](https://navepoint.com/navepoint-15u-450mm-depth-wallmount-networking-cabinet-consumer-series/). 

## What's in the rack?

Without going into the details of the home and camera placements (not a great idea to share those in public), our plan for cameras and WiFi coalesced around two APs, some camera drops, and a doorbell, with potential to add cameras later if/where/as needed. These would all be run off of PoE wherever possible. I waffled a fair bit on how to deliver the PoE, flip flopping between maintaining the current Firewalla Gold and adding a PoE switch, or springing for a [Ubiquiti Dream Machine SE](https://store.ui.com/us/en/collections/unifi-dream-machine/products/udm-se).  

I initially considered [Reolink](https://reolink.com/) as the frontrunner for the cameras and doorbell between hardware, cost, and their app. But, I was not pleased with Reolink's relatively basic NVR offerings and was instead considering a Synology NAS and their [Surveillance Station](https://www.synology.com/en-us/surveillance) application. Between cost of the NAS, drives, and licenses, this would quickly balloon in cost and I felt may overtake Ubiquiti. Plus the strong reviews that Ubiquiti kit "just works" (at least for the most part) compared to bodging together products from multiple vendors, Ubiquiti won me over. 

What has actually wound up in the rack at the time of this writing are the modem, a Ubiquiti Dream Machine SE, a Tripp-Lite ISOBAR PDU, a Cyberpower UPS, 2x 24 port patch panels (overkill but in case of future expansion), a Dell 9020M which runs Proxmox VE, a 2U drawer unit for cable and fittings storage, and a shelf. A Ubiquiti 24 port PoE switch is the most recent addition, facilitating the addition of another AP to provide better coverage in the basement and front of house, and provide more PoE ports for the remaining cameras. 

Yes, yes, I know. I'm literally the meme of the selfhoster / homelab guy who's picked all the easiest, high brand awareness stuff. But the fact it's easy to work with is perfect for my immediate needs and it's a platform to grow and learn on. I've got kids and work after all, at the end I need it all to play nice and not be a constant maintenance project. 

### Rack Layout

I threw this table together early in the planning process to help me understand the rack layout. Initial plan looked something like this.  

| Zone | Contents                | Notes                                                 |
| ---- | ----------------------- | ----------------------------------------------------- |
| TOP  |                         |                                                       |
| 1-15 | Patch Panel 24 port -1  | Primary drops                                         |
| 1-14 | Patch Panel 24 port -2  | Redundant drops & special (e.g. doorbell chime on 3*) |
| 1-13 | Firewalla Gold          | Work network - 1gbps off modem                        |
| 1-12 | Dream Machine Pro       | Home Network - 2.5gbps off modem                      |
| 1-11 | Reserved for PoE Switch | Future upgrade when more cameras are added            |
| 1-10 | Modem                   |                                                       |
| 1-9  | Philips Hue             |                                                       |
| 1-8  | Shelf                   | Swap out for NVR at future time                       |
| 1-7  | Dell 9020M              | Runs Proxmox and Home Assistant                       |
| 1-6  | ISOBAR PDU              |                                                       |
| 1-5  | BLANK BLANK BLANK       | Save space for oversized bricks                       |
| 1-4  | Drawer 2U               |                                                       |
| 1-3  | Drawer 2U               |                                                       |
| 1-2  | UPS                     |                                                       |
| 1-1  | UPS                     |                                                       |
| Base | Base                    |                                                       |

But we all know no plan survives contact with reality. Thankfully these realizations didn't have a  dollar value associated. 

First, I had planned to have ISP drop into the Modem, then the 2.5gbps out to the Dream Machine and the 1gbps out to the Firewalla. In theory this would let me connect my work devices to the Firewalla, segregating them off via hardware completely from our personal, lab, and IOT devices. 
Unfortunately, Comcast and/or Arris don't play nice with this approach, only one of those outputs from the modem can be in use at a time. So the Firewalla is now sitting in a box, waiting for use in another project.

Second, I found some of the Cat6 drops which come up from below the rack were just a touch short. They could still plug into the patch panels at the top of the rack, but I had concerns that if e.g. a Dream Machine slotted below them it would put too much strain on the cables. I decided not to risk it and moved the patch panels towards the bottom of the rack, above the UPS. 

Current state of the rack: 

| Zone | Contents               | Notes                                                 |
| ---- | ---------------------- | ----------------------------------------------------- |
| TOP  | Access Point           | Ubiquiti Swiss Army Knife                             |
| 1-15 | ISOBAR PDU             |                                                       |
| 1-14 | BLANK PLATE            | Save space for oversized wall worts down off the PDU  |
| 1-13 |                        |                                                       |
| 1-12 | Shelf                  | To be swapped out for an NVR at a future date.        |
| 1-11 | Drawer 2U              |                                                       |
| 1-10 | Drawer 2U              |                                                       |
| 1-9  | Philips Hue            |                                                       |
| 1-8  | Modem                  |                                                       |
| 1-7  | Dell 9020M             | Proxmox VE.                                           |
| 1-6  | Dream Machine SE       |                                                       |
| 1-5  | Patch Panel 24 port -1 | Primary drops for APs and Cameras                     |
| 1-4  | PoE Switch             | Ubiquiti Standard 24 PoE                              |
| 1-3  | Patch Panel 24 port -2 | Redundant drops & special (e.g. doorbell chime on 3*) |
| 1-2  | UPS                    |                                                       |
| 1-1  | UPS                    |                                                       |
| BASE | Base                   |                                                       |

## What are you *doing* with this setup? 

Best to think of this question in three components: network, surveillance, and the homelab. 

### Network

The household network centers on the UDM which handles routing, firewall, etc. It enforces VLANs similarly to how I had the Firewalla configured. Devices are assigned to VLANs based on whether they are Trusted, Semi-trusted, or Untrusted. E.g. work and guest devices are untrusted and their VLANs are isolated from all other VLANs. Some types of IOT devices are presently in a semi-trust VLAN while I tinker with firewall rules to make them easier to interact with. Our personal devices and the household infrastructure such as VMs, cameras, etc. are in Trusted VLANs. 

By current calculation, the UPS will run everything in the rack for 1 hour in a power loss scenario. More than enough time to gracefully shutdown, and with the relative rarity of blackouts and brownouts here well up to the task of keeping us online. 

WiFi is presently provided by 2x Ubiquiti AP7s and a Ubiquiti Swiss Army Knife, one AP per floor of the home with one of the AP7 biased rearward in the home to provide coverage into the back deck and yard. Granted there's like three devices on the market that support WiFi 7 at this point, but it's good future proofing. The Swiss Army Knife will eventually move to the garage and be replaced by a third AP7. 

### Surveillance

Camera drops and junction boxes are all in place and gradually having cameras put in as funds are available. The UDM is acting as the NVR, and I'll eventually offload that to a dedicated NVR for both capacity and RAID support as a future upgrade. Ubiquiti's [G4 Doorbell Pro](https://store.ui.com/us/en/products/uvc-g4-doorbell) was the first Protect family device I installed once the Cat6 was in place and it's a really, really sweet piece of kit. Showing gifs on the screen is icing on an already great product cake. I would say that if, like me, you have an install location without a large hole behind the unit to accommodate the rj45 connector / rubber housing, you may want to obtain an aftermarket mount. ([Here's what I used](https://www.etsy.com/listing/1270278038/angled-mount-for-ubiquiti-unifi-protect)) 

### Homelab

The Homelab is modest at the moment. A [Dell Optiplex 9020 Micro ](https://i.dell.com/sites/doccontent/shared-content/data-sheets/en/documents/optiplex-9020-micro-technical-spec-sheet.pdf) runs [Proxmox VE](https://www.proxmox.com/en/proxmox-virtual-environment/overview), which in turn is hosting [HomeAssistant](https://www.home-assistant.io/), [Dashy](https://dashy.to/), [CommaFeed](https://www.commafeed.com/#/welcome), [Uptime Kuma](https://uptime.kuma.pet/), and [Watch Your LAN](https://github.com/aceberg/WatchYourLAN) Because this box only takes up half of a 1U slot, I plan to add another of these Micro form factor PCs beside it in the near future to tinker with [PiHole](https://pi-hole.net/), [Searxng](https://github.com/searxng/searxng), [Crowdsec](https://www.crowdsec.net/), and [PaperlessNGX](https://docs.paperless-ngx.com/). I eventually intend to add a NAS (likely TrueNAS) and a Plex or Jellyfin server. 

Of note, [tteck's Proxmox VE Helper-Scripts ](https://tteck.github.io/Proxmox/)have been a HUGE help in getting this all started, providing me a platform to work from to see results quickly so that my ADHD brain wouldn't abandon the project too soon, while also finding what I still have to learn and do manually. 

HomeAssistant is the main tool I wanted to start selfhosting for, as this is allowing us to tie multiple home automation products together under one app (The wife really likes this). Without it, we'd be using nine different apps in different contexts around the home. Maybe half of that was able to integrate into Google Home or Homekit, but not both. I'm in the midst of adding automations when/as the wife and I find uses for them, e.g. turning the living room lights on in the morning right before the wife heads downstairs, tying the downstairs hallway lights to motion sensors and the side door open/close sensor, and setting the exterior lights to come on at sunset. The immediate next use case I want to add are tilt sensors on the mailbox and garage door so that HA can fire notifications when they are opened. 

As to upcoming projects, because I'm in relatively close proximity to O'Hare International Airport, I'm also eyeing a redundant Cat6 drop in the attic for use as a [PiAware]([PiAware - ADS-B and MLAT Receiver - FlightAware](https://www.flightaware.com/adsb/piaware/)). That'll likely be a start of the new year project. Longer term when we renovate the first floor of our home, I want to add a digital signage display that can operate in a kiosk mode showing a full screen browser page serving HomeAssistant's dashboard(s) for controlling rooms and viewing the outside cameras. 

## Miscellany

A couple parting items that didn't fit elsewhere: 

Given the amount of reorganizing and shifting stuff around in the rack I did, a set of [RackStuds](https://www.rackstuds.com/) were an absolute lifesaver. This is not sponsored, I have no relationship with RackStuds, I just know I would've been hating my choices if I was futzing with cage nuts at points in this project and these things were a huge timesaver. 

If you've got the disposable income to throw at it and no access to a 3D printer yourself, Etsy was a surprisingly great source for 3D rack mount kits for various devices that would otherwise have had to sit on a shelf unit. I snagged one for the [modem](https://www.etsy.com/listing/1604798414/1u-rack-mount-for-arris-surfboard-s33) and another for the [Philips Hue](https://www.etsy.com/listing/891257372/philips-hue-smart-hub-1u-rack-mount?) bridge. 

If, like me, the rack is going to be in the same room as your workspace, spend the money on some variable speed fans to replace whatever ships stock with your rack. Your ears will thank you. Doubly so considering my office doubles as the guest room. 🙃