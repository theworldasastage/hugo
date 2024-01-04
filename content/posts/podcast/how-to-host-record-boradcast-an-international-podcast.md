---
title: "Tutorial : How to host, record and broadcast a podcast with distributed members"
date: 2018-09-14
image: img/podcast.jpg
categories: ["podcast"]
type: "post"
tags: ["podcast", "dev", "tutorial"]
draft: true
---

With [Podcast Science](http://podcastscience.fm), I host, record and broadcast a popular science podcast in French every week since 2010. We had a lot of trial and error to establish a setup that allowed us to :

- Host and record a podcast with participants in different places (we have people every week from France, Switzerland, Spain and US)
- Broadcast it live
- Play sounds and jingles

Here is a fully detailed step-by-step tutorial with animated gif on how to setup your computer to make it a real live podcast studio!

## Configuration

To use our setup you must use a **Mac** since we couldn't find any equivalents of the main softwares we need. You need to get the following softwares (they all have a trial version) :

- [Audio Hijack](https://rogueamoeba.com/audiohijack/) (59$) to do about everything, this is _THE_ mandatory element of our setup. This software is awesome.
- [Loopback](https://rogueamoeba.com/loopback/) ( 99$ ) to be able to connect audio as you want, this is also mandatory and I don't know any free equivalent ([Soundflower](https://rogueamoeba.com/freebies/soundflower/) was doing the job for free but seems dead).
- [Skype](https://skype.com) (0$ ) or any other audio communication tool like [Discord](https://discordapp.com/) (0$ ) , [Appear](https://appear.in) (0$ ), etc.
- [Farrago](https://rogueamoeba.com/farrago/) (39$ ) to play jingles. You can also use any other software that can play a sound like [iTunes](https://itunes.apple.com/) (0$ ) or [Spotify](http://spotify.com) (0$ )

As you may have noticed, all the paid applications we use come from Rogue Amoeba, in our experience these app are the most reliable we've found (and you'll hate to have a technical problem when you start your live podcast...).

so if you want several of them you can buy bundles :

- Audio Hijack and Loopback bundle for 130$
- The Ultimate Podcast Bundle for 170$ (with another app called Fission which is perfect to edit the meta data of a MP3 before posting it on your feed).

You also need a Mic. For one person, [Zoom H2N](https://www.amazon.com/Zoom-H2N-H2n-Handy-Recorder/dp/B005CQ2ZY6?keywords=zoom+H2&qid=1536820944&s=Musical+Instruments&sr=1-4&ref=sr_1_4) (170$ ) or [Blue Yeti](https://www.amazon.com/Blue-Yeti-USB-Microphone-Blackout/dp/B00N1YPXW2?keywords=yeti+blue&qid=1536820897&sr=8-5&ref=sr_1_5) (130$, often discounted on Amazon) are very good options.

## Hosting and recording

The first step is to make the podcast happen : to be able to talk to other folks and to record the conversation.

If you are alone in your podcast, there are a lot of easier configurations but the one I'm presenting here will allow you to do much more :

- You will be able to host a podcast with several people (at your home or online)
- You will be able to play jingles (next part)
- You will be able to broadcast (last part)

We'll use Audio Hijack and our objective is to create a configuration similar to the one below.

<img src="/img/podcast/tutorial-1.jpg" width="50%"/>

We'll have one or several mics (1) that we will record in different files (2). All these voices will be sent in Skype (3) so that the other podcast member online we hear us. We'll get the voice of the other people through Skype to record it (4) and finally make us able to hear them (5).

Audio Hijack allows you to do all that almost as easily as the figure. First open the software and go to `Session > New Session` (Cmd+N). You will have a new window asking for the kind of Session you want to create, pick "New Blank Session".

![](/img/podcast/tutorial-2.jpg)

First we'll add the mics (1 in the figure). To do that click open the source library (by clicking on "show library" if it's closed). Pick the source "Input device", click and drag it anywhere in the main window as in the gif below.

![](/img/podcast/tutorial-3.gif)

Now you have to configure your source to connect it to your mic. Click on the mic you just added to make the menu "Audio Source" appear. If you use the internal mic of your Mac, no more configuration to do. But if you use a more complex mic you should open the "Advanced" part on the menu to select which sources you exactly want.

![](/img/podcast/tutorial-4.png)

Use the same method to add as many inputs as you need for each mic you have. In this example I have two inputs.

![](/img/podcast/tutorial-5.png)

Now we need a recorder to record our audio. As for the input, click and drag on the recorder to add it on the main window and connect the "Recorders" to the inputs as presented in the gif.

![](/img/podcast/tutorial-6.gif)

Be very careful that, as in the example, your recorders are connected to only **one** input. The connexion is the little "tube" between the square elements.

<img src="/img/podcast/tutorial-7.png" width="50%">

Now you need to configure your recorder. As for the input device, click on each recorder element to configure it. If you plan on editing your podcast, don't pick MP3 for the format as it's compressed. At PodcastScience, our recorders have the following configuration :

- Quality : custom
- Format : Wav
- Type : 24bits
- Sample Rate : Auto
- Channels : Mono (our mics are mono, if yours are stereo, pick stereo)

The configuration process is illustrated by the gif below.

![](/img/podcast/tutorial-8.gif)

So now we have mics that we record (yay!), we still have to send this voices to skype so your friends can hear you. In an ideal world, we should be able to open Skype and pick "Audio Hijack" as a source but this is impossible... Here come the need of Loopback.

As soon as you installed Loopback, you should have a new window open, **you have nothing to configure here**, close it and go back to Audio Hijack. Loopback is like a virtual cable, so instead of connecting directly Audio Hijack to Skype you do it through Loopback : You first connect Audio Hijack to Loopback and then Loopback to Skype.

In Audio Hijack, add an "Output Device" to the main window. Move it so that it's connected to all your inputs' recorders. Then click on it to configure it and pick "Loopback Audio". All this is presented in the gif below.

![](/img/podcast/tutorial-9.gif)

No you need to be sure that Skype uses this new input. You have to go in the preference panel of Skype and pick "Loopback audio" as the input. I don't put any capture of Skype interface in this post since Skype loves to change its interface every other month.

**First Test!** Your configuration is not finished but you can start testing it : Talk with our mic and check if someone you call on Skype can hear you and that you get a record (and if you are alone you can call the Skype test call). To do that, click on the red button (**As long as you don't click the red button, nothing will be recorded and you won't be heard**) and then call your friend on Skype. You should see the "tubes" on Audio Hijack become orange as you speak.

![](/img/podcast/tutorial-10.gif)

If your friend can hear you, this is good news (be sure he hear you from the mic you want to test).

Now let's check the recorded files. To find them, click on "Recordings," then
"Actions" and finally "Reveal in Finder" to open a Finder window on the folder of your recordings. You should have one file per recorder. If you can find the find and hear your voice, that's a win!

![](/img/podcast/tutorial-11.gif)

We still need to record the voice of the people on Skype. To do that we'll build a parallel configuration on the same Audio Hijack window.

In the source library, pick "Application" and drag it to the main window **without connecting it to anything**. Click on it and pick "Skype." In "Advanced," uncheck "Include Audio Input" (You already record the audio input so you don't need it a second time).

![](/img/podcast/tutorial-12.gif)

You need now to add a "Recorder" (with the same config as before) to record what comes from Skype.

If you stop here, you won't hear anything anymore on Skype because Audio Hijack captures the sound of Skype. You have to add a new "Output Device" with your headset to get the output again.

![](/img/podcast/tutorial-13.gif)

Your setup is complete! You can test it by pushing the red button and calling someone. All the "tubes" should become orange as people speak and you should find all the recorded files at the end of the call.

![](/img/podcast/tutorial-14.gif)

Here are the link between the initial figure and your configuration.

<img src="/img/podcast/tutorial-1.jpg" width="50%"/>

![](/img/podcast/tutorial-15.png)

## Jingles!

To be able to play sounds in a configuration like Podcast Science (several people in different places) with only one computer is way more complicated than it seems. However, hopefully, Audio Hijack makes this smooth.

The main issue is that we want the sounds to be heard by us _and_ the other people on Skype. Moreover, we don't want to hear our own voice in the mic (which is also a Skype input). So we'll have to add the sounds in our setup twice: once for us, and once for the people remote.

You can play your jingles from any app; I'll use Farrago because it's a very convenient tool to play quick sounds when you need them.

So, in Audio Hijack, you'll create two "Application" sources :

- the first one connects to Loopback (to go in Skype)
- the second one connects to our headset

Note that I don't connect Farrago to the recorders since I don't want to record them, I'll add them directly in the editing for better sound quality.

![](/img/podcast/tutorial-16.gif)

You have two "Farrago" boxes, but they represent the same application, this is where the magic of Audio Hijack occurs. If you play a sound and start recording, you should see the tubes become orange again.

![](/img/podcast/tutorial-17.gif)

**Note:** You may have one of the two blocs that stop working when you start Audio Hijack. Just delete it (right click and delete) and create a new one.

So now you can play sounds during your podcast! You can use the same methods to add sources that only you and/or other people can hear. For example, at Podcast Science, I can monitor our live broadcast when I need by connecting Google Chrome as an input of my headset.

This is our final configuration (without broadcast) for Podcast Science.

![](/img/podcast/tutorial-18.png)

## Live broadcast

Last and easiest step: Live Broadcast. Audio Hijack (still him) can also manage the broadcast as soon as you use a [Icecast](http://icecast.org/) (We rent ours on [Infomaniak](https://www.infomaniak.com/fr)).

To add a broadcast to your configuration, you need to add a new "Skype Application" block and a "Broadcast" block.

![](/img/podcast/tutorial-19.gif)

You then have to configure these two blocks. For Skype, no configuration should be required (be sure that "include audio input" is checked under the advanced panel). On the broadcast block, your configuration depends on your Icecast server, only the setup part is very important, the metadata part is for display only.

Some options will still be similar :

- Port : 8000
- Encoding format : Custom
  - Format : MP3
  - Bit rate : 96kbps
  - Bit rate mode : constant bitrate
  - Sample rate : 44100 Hz
  - Channels : Stereo

This is it! You know how to host, record and broadcast a podcast. If you have any comments on this procedure, feel free to share them on the comments below!

{{< partial "mailing-with-tag" "Subscribe to my newsletter to receive my next articles!" "podcast">}}
