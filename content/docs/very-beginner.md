---
title: A beginner's introduction
weight: 2
---

This doc is for readers who don't have too much exposure hacking their devices, but want to personalize their ereader. 

If you're someone who already had a Github account before your ereader, then go ahead and [start here](/docs/install-Koreader). If you're still wondering what the hell GitHub is and what people mean when they refer to a root directory, then you're in a good spot.

## Create a new folder in `.kobo`

We're going to introduce a bunch of concepts by first working on a task: creating a screensaver folder in your `.kobo` directory. This task should give you a firmer grasp on the kinds of actions we'll take everywhere else in these docs, like adding resources to folders and creating new folders inside your Kobo. It should prime you to install Koreader, too, which is famously a pain in the ass. 

### Step 1: Plug in your Kobo via USB to your PC

First thing's first: at the end of the day every piece of technology is just a bunch of folders and files that you can view and edit from your File Explorer. Your Kobo is no different. So let's plug her in:

![Image that shows directory for plugged-in Kobo](images/beginners-directory.png)

The screenshot shows a plugged in Kobo (`KOBOeReader(D:)`) and all the folders that make up my Kobo's **root directory**. The difference between a root directory and regular directory is that **root** indicates the top-most level in a file structure. Sometimes people will call something root when it's not, so clarify what they mean if you're uncertain.

My device already has a bunch of directories (or folders, but we'll use the term directories throughout these docs). You you may or may not recognize some of these. `.adds` is where NickelMenu and Koreader will eventually live; `Books` is where I keep all my epubs, which live in subdirectories by genre; `.fonts` is where I've added my own fonts; and so on. 

But let's ignore all that for now and move on to the second step.

### Step 2: Create a folder in `.kobo`

1. Select `.kobo` to open the main Kobo directory. A bunch of stuff appears. Take a look, then ignore all of it for now:

    ![Image that shows an uncollapsed .kobo directory](./images/kobo-directory.png)

2. Create a new folder called `screensaver`. This is where you'll add new images so when your Kobo is asleep or powered off, you'll have something custom on display. Your directory should look like this:

    ![Image that shows an uncollapsed .kobo directory, but with a new folder called `screensaver`](./images/screensaver-dotkobo.png)

    Re: `.kobo`: This is one of two directories you might use often. 

    * Generally speaking, making changes to the `.kobo` directory introduces new behaviors and outcomes for your default Kobo software. 
    * For example, images in the `.kobo` screensaver folder will appear when your device goes asleep from the default launcher. 
    * You may need to add something to `.kobo` even if you're modifying something in Koreader. Be cognizant of what folder you're adding shit to in future procedures, and clarify if you're uncertain.

### Step 3. Add an image

Find an image and add it to screensavers. Copy any old downloaded image from your PC and paste it into the new folder. Should look something like this:

![Image of screensaver folder with some images](./images/screensaver-folder.png)

I use a Kobo Libra Color, and the resolution size that gets the full screen effect is 926x1200. Don't know what aspect ratio that is, so can't help anyone there. As far as I can tell image titles and file extensions (that is the `.png` and `.jpg`) aren't super important, though IIRC my Kobo didn't load any  `.webp` images.

### Step 4. Safely eject

Any time you want to test if some modification worked, you need to safely eject. To safely eject, right click on `KOBOeReader (D:)` and choose **Eject**. Don't just unplug your device. 

![Image of menu options with Eject highlighted](./images/safely-eject.png)

Your Kobo will update, then turn on. Put your Kobo in sleep mode and the image you added should appear. :)

### Let's review really quick

Earlier I said that tinkering with devices is just playing with files and folders. Everything you do here on out will follow this broad procedure:

1. Plug in your Kobo.
2. Either create a new folder and add some files to it, or add a folder to an existing folder, or even just edit some text in an existing file... or add a new file. You get the picture, lol. 
3. Eject your Kobo safely.
4. Wait for an update, then see the results.

There is a diabolical fifth step that involves troubleshooting and repeating all of these steps until you get the results you want. You will get a crash page sometimes... But the good news is Kobo is super forgiving with the DIY hacker spirit, so worry not. :)
 
## What's next?

You have two options for the next part of your journey. You can either:

* [Get an introduction to tools](/docs/the-tools) like VS Code, GitHub, and some suggested best practices. Some might see this doc as overkill, but I don't.
* Jump right into [getting started with installing Koreader](/docs/install-Koreader). 