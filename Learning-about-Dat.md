---
title: "Learning about Dat"
date: 2017-12-07T10:04:00+01:00
author: npscience
---

## What is Dat?

Dat is a protocol for sharing data over the internet.
Specifically, it is the protocol for finding and retrieving data files via the metadata about the datafile. The protocol itself is about finding and retrieving data, not about storing it. However, you can store data files in a Dat repository, and then others can stream from the repository or clone it.

## Why has Dat been made?

Access to data stored in online repositories is currently via HTTP (over the web). However, this protocol is insufficient for supporting version control and content addressing.

### What does this mean?

#### Content addressable storage
"Content-addressable storage, also referred to as associative storage or abbreviated CAS, is a mechanism for storing information that can be retrieved based on its content, not its storage location" - [Wikipedia](https://en.wikipedia.org/wiki/Content-addressable_storage)

HTTP retrieves by location (go to a server, ask for a file). What if the data is moved from that location? That's 'link rot'. It's like when you move house. If you don't tell people you've moved, they may try to visit you at your old address, only to find you not there. If you don't set up a postal redirect, your post will continue to go to your old house, but you'll never see it to respond to it. This is what can happen to files accessed by HTTP.

So storing data for access via a location reference only is problematic, as it doesn't help you find the data if it's moved. Aha - but we have search too. Search queries look for content in the data file itself, and are location-agnostic. So you could search for something about the file you're looking for and find it that way (think about searching for something in your folder system without knowing exactly where you put it). Well this search query is similar to content addressing. Instead of finding something via its location (path), you find it via something that identifies the file.

In content addressable storage, the data file has a unique identifier attached to it, and that is what you use to find and retrieve the file. But there's a drawback — with this system, every time a file changes, it needs a new identifier so that each identifier points to a defined version of the file. So it's less useful when files are constantly changing (overload of administration required). That's why using a location-based system can be really useful: you can continue to edit the file behind the address without needing to do anything about changing the address. so you can renovate your house, change its inside, without needing to update your address to receive visitors to appreciate your renovations.

#### Data files need something other than HTTP

When it comes to data, e.g. a research dataset, it's vital that this data isn't ever lost (e.g. by link rot) and it's also really important to keep a track of the version record. Once prepared and shared, datasets aren't likely to change that much. New data can be appended, maybe some errors need resolving, but other than that, data is not as much in flux as say the contents of a webpage.

So Dat brings the benefits of content-addressable storage protocol (retrieval by unique identifier not location; and version control since the ID changes whenever the data is changed) to data shared over the internet.

*Share webpages with HTTP. Share data with CAS protocols.*

Examples (from [Wikipedia](https://en.wikipedia.org/wiki/Content-addressable_storage)):
* "**Git** is a userspace CAS filesystem. However it is primarily used as a source code control system."
* "**[InterPlanetary File System (IPFS)](https://en.wikipedia.org/wiki/InterPlanetary_File_System)**, is a content-addressable, peer-to-peer hypermedia distribution protocol."
* "**[Arvados Keep](https://doc.arvados.org/user/topics/keep.html)** is an open source content-addressable distributed storage system.[11] It is designed for large-scale, computationally intensive data science work such as storing and processing genomic data.""

#### Data defined storage

Source: [Wikipedia](https://en.wikipedia.org/wiki/Data_defined_storage)

"Data defined storage focuses on metadata with an emphasis on the content, meaning and value of information over the media, type and location of data. Data centric management enables organizations to take a single, unified approach to managing data across large, distributed locations which includes the use of content and metadata indexing."

"Distributed Metadata Repository: Data defined storage enables organizations to virtualize aggregate file systems into a single global namespace. At ingestion; file, full text index and custom metadata is collected and stored in a distributed metadata repository. This repository is leveraged to enable speed and accuracy of search and discovery, and to extract value leading to informed business decisions and analytics."

Dat uses data defined storage:
* Data is distributed across systems, but aggregated under the Dat namespace
* Access to data is fast and accurate

### Dat whitepaper

Source: https://github.com/datproject/docs/blob/master/papers/dat-paper.md

* Hub-and-spoke (centralised) storage solutions have limited bandwidth (because all traffic has to go through the hub) so sharing popular files becomes expensive.
* Cloud storage solutions with version control and syncing do exist, but they rely on proprietary code and lock-in services.
* Distributed file sharing tools can improve access to popular files (the files are then stored in many places, because many people have been interested in them, and so become faster to access as you avoid the bandwidth limitation of a central hub). they include link resolution systems, so help avoid link rot. BUT they are not supported by Web browsers, lack good privacy guarantees (they access data storage on your machine) and do not have a suitable easy sync-update mechanism.

Some definitions:
* Bandwidth [Source: Wikipedia](https://en.wikipedia.org/wiki/Bandwidth_(computing)) - this is the speed at which data (in bits) is served to you across your internet connection. This affects how quickly you can download resources to view a website (so how quickly a site loads), download a file, etc. Your bandwidth is the maximum capacity you can use, but you don't necessarily use this all the time. It is measured in bits per second. A high bandwidth = faster access / loading.
* Traffic [Source: Wikipedia](https://en.wikipedia.org/wiki/Web_traffic) -  "Web traffic is the amount of data sent and received by visitors to a web site." This is demand placed on a resource on the internet by users, e.g. people visiting a website. It's a measure of users visiting a site, but each user may request more than one file for that site (be that a page, image, or other). High levels of traffic can overwhelm the server with requests and lead to site downtime (this is the basis for a denial-of-service attack). The majority of traffic over the internet is web traffic (i.e. accessing content on the WWW).

Content integrity...




# Beaker Browser

Paul Frazee, co-creator
[YouTube Video](https://www.youtube.com/watch?v=6yhlMReH1PE&feature=youtu.be&t=2100)

OS fork of Chrome
To decentralise web (original vision)
Currently we depend on central servers, and communicate from our individual nodes to centralised servers and we depend on these centralised servers to publish information on the web. What if we no longer trust the organisations running these servers? What if they don't meet our needs? e.g. we want to share like we do on Facebook but not under their terms? We don't currently have the control over our data to make it truly possible to switch platforms as we need. So the market is closed, and we end up with dominant third-party services.

Problems:
* Closed source applications
* Lose ownership of our own data
* We pay with our privacy right now

What if we kept control of our data? What if we could shape the applications we use to share information, to make them work for us? What if we could do this without handing over personal data to people we do not trust?

Dat is the one protocol integrated into Beaker. Like BitTorrent but can change data files with version control.

Beaker has one-click publishing - add a new site from the browser. Dat gives you a global address. Good for sharing files (static content, media, etc).

Relies on bandwidth sharing. If you download a file. you rehost it for a short period. You can also donate some of your own resources to the network (e.g. some bandwidth). This is critical. Popular files need to be distributed across many peers, a single peer could not cope with the demand otherwise. Dat allows this scalable infrastructure.

You own the website. No internet connection required to update the files. you can connect via LAN to share files as well as via Internet.

Live reloading feature - can see page change as it is live updated.
Versioning - native package manager for the web.

You can fork sites! Just like on GitHub. Copy the files and then customise it how you like. This makes the web easily editable (a vision to TBL).

So this works for static webpages, sharing files. Next? How to create web applications based on this? Requires all backend replaced with p2p web APIs.

* Dat Web API - create your own Dat repo, create and read files, watch activity stream.
Photos app, RSS feeder.
Rotonde (twitter based on p2p). Every user has their own site with a single JSON (profile, who they follow, etc). Users follow each other's websites. Fork a site, change your name, customise etc. Vibrant indie community.

* WebDB - filesystem API is powerful but hard to run queries (e.g. last ten status updates). So created indexing crawler that will scan sites for JSON files, index them, and allow you to query them. Feels like you are using a database.


More about what you can do with Beaker at [Video](https://youtu.be/U2B9mwRFE8U)
**You can write in markdown!!**

Index.md is homepage
Nav.md gives you a navigation bar on the left.


### Sharing my website persistently and beyond Beaker

Via Dat, your site can be shared with anyone you wish to share it with, and no more. You send them the dat link and they can access your files. That's kind of the point. Making a site on Beaker, well that limits who can see the files to the people who are viewing through Beaker too.

The drawbacks? If your computer isn't online, and you've no friends (peer) who are hosting your files, then your files won't be accessible. This is what a server does for the web — it holds the files so anyone can see them without the file author actively serving them. (See above for concerns re: relying on centralised servers.) So how do I keep my site live even when my computer isn't switched on? Well, I need a friendly server. Enter hashbase.io. This is doing the job of normal web servers, by acting as a peer on the network that is always on. If I share my files with hashbase, then anyone can view my p2p site regardless of whether my machine is on or not. Of course, this comes back round to the trust problem. Do I trust hashbase to be a central storer of my files? Hashbase is a super-peer created by the creators of Beaker: Tara Vancil and Paul Frazee. It's open source and Tara is a nice person (I've not met Paul). Better the devil you know!

Now there's another reason you may not be able to see my blogsite. You have to download Beaker Browser to get involved (that's the point of p2p sharing). What if I want all the personal benefits of creating a blogsite using Beaker, but also want it to be visible on the normal web? Handily, hashbase also mirrors the files on the web, so people can see my site via HTTPS too. That makes it accessible to anyone.

So in the end, me and my Beaker friends can read-write content in our decentralised web, I can share my files with hashbase as a friendly super-peer to keep my content online via Beaker plus they provide the service of pushing to the WWW for everyone else not on Beaker. Tara and Paul really are making this easy...
