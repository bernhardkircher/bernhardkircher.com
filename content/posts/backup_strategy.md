+++
date = "2017-01-03"
draft = false
title = "My family photo sharing and backup strategy"
tags = [ "Backup", "Family" ]
categories = [ "Backup", "Family" ]
+++

---
# My Backup Strategy

There is one thing you never want to happen, if you are in charge of your family's computers:
**loose data**.

I already do some backups (notice, that "some" is not a term that I use if I am very happy/confident in the context of my current backups), but since I am on holidays and have a little time, I decided to take a look at how I could improve my backups.

## Requirements

My family's most important data are pictures. We have two children and we take a lot of photos.
My wife takes most of the photos with her camera, whereas I use mostly my mobile phone to take photos.
Ideally these devices get backed up automatically (as much as possible).
In addition to that we have a lot of existing photos on our harddrives.

Another thing we would like, is to be able to share/organize the photos easily.

#### Backup requirements:

1. Automate as much as possible

    If you have to remember to do something, it usually gets forgotten, therefore the backups should be as automatic as possible.


2. Multiple copies of the data

    Have at least two Copies of the data around, ideally three copies. Harddisks fail, and if a lightning strikes and a backup disk is attached to the computer, it will be lost too.


3. Offsite backups

    Keep one backup offsite, in case of a disaster (like the house burns down, or something like a like a water damage...).


#### Sharing/organization requirements:

1. Easy accessible

    My wife does not want to enter a password or something all the time to access the photos - it should feel as if they were stored locally.


2. Central organization of photos

    It does not matter who took the photos, my wife and I sometimes take photos at the same time, and afterwards we would like to make an album or something of the event where the photos have been taken. Both of us are allowed to organize/move photos.    


## How to do backups

I started searching for a good existing backup plan or similar resources, but as it turns out, everyone has different needs (and budget), and thus seems to do it differently.

A lot of resources I found give detailed information on how to backup, but do not mention how they share and organize their data (especially photos). The backup strategies I found:

* (mis-) interpreting RAID as a backup
* manually copying files every now and then to an external disk
* automatic backup of PC to an external disk, using backup software (or something like Windows File History)
* automatic backup of PC to a NAS, using backup software (or something like Windows File History)
* central storage of data on a NAS/Server which gets backed up to an external disk or second NAS/Server
* Using online services like Dropbox, OneDrive, etc.
* combinations of the above

Since I want to share all my photos, all options that backup data from a PC to an external disk is not what I want (and it would mean that I need to go to every PC and add). With this decision, I will need some central shared storage that gets backed up.


## Result

Since I already have a NAS (which I used for my existing backups), I decided to set it up to be my **central storage for all of my images, music and documents**. Our PC's music/images location has been changed to point to the same folder on the NAS. Everyone has it's own documents folder (so this one is not shared right now).

Our phone's images are backed up to the NAS automatically, using an app by my NAS' vendor (a QNAP 212P). Since we manually organize our images, these are stored in a special folder and get sorted/categorized later manually (but also backed up) - somtimes we group our images by events (like "birthday party",...) and sometimes just per date - this gives us the flexibility that all photos get backed up, but make sure we can find them again :).

Our camera does not have this feature, so it needs to get attached to one of our PC's manually and the photos need to get uploaded manually to the NAS (in the same folder that our mobile phones get backed up to).

Our PC's might still contain **other data**, that is **not stored on the NAS** directly - these get **backed up** using a simple backup software on a **daily** base (like my programming projects etc, which are also stored on external repository, like github).

In addition to that, **every month** an **image backup** is made of our PC's and stored on the NAS. This is not a backup per se, just to be able to restore the PC's faster.


Now the NAS contains a mix of backup data and photos/music/documents that have not been backed up. The NAS' data is backed up daily via a Job that is running daily on the NAS and copies data to an external USB drive that is attached to the NAS.
Currently we have **three USB disks**, where **one is stored off site** (my wife takes it to her parents' house approximately every month), and the remaining **two disks are rotated daily** (only one is attached to the NAS).

The backup verification happens manually (since I do not know how to automate it) - since this is manual and time consuming, I check the backup disks every quarter.

## Shortcommings/Improvements

If our house would burn down, we would loose all the data since the external disk has been taken to my wife's parents house (which is max. 1 month). This is not great. It's also a manual process, which I cannot automate.

We also have to remember to manually change the USB disks on the NAS. If we forget to do this, I get an Email from the NAS, since after a Backup the USB Disk gets ejected from the NAS and thus the following backup will fail if a new disk does not get attached again.
So here we have at least some kind of notification (although I never trust a notification system).

I also do not like the fact, that the backup verification happens manually, but since I do not know how to automate it, it's my only solution to that right now.

I plan to add an online backup (Crashplan, OneDrive, DropBox,...) to be really save - but I am not keen on restoring a TB of data over the internet - it's more of a safetynet.
