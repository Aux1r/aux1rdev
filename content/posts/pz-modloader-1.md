+++
date = '2026-06-18T21:06:05+01:00'
draft = true
title = 'Project Zomboid Modloader (Part 1)'
tags = ['gaming', 'python', 'hosting']
+++

## What's Project Zomboid, and why a modloader?
Project Zomboid is an isometric zombie survival game that I get into every now and then and during that time it's the only thing I can think about. I've been wanting to get into it again, but I've remembered the struggles / nuisances of setting up mods for the dedicated server host machine. For example, I'd often run into mysterious errors where the steam workshop would struggle with downloading a particular mod, resulting in an infinite loading loop that would never resolve. Furthermore, SteamCMD would usually tell me what mod it's complaining about by referring to its Steam Workshop ID, which without knowing the IDs off the top of my head was a real headache.

So why don't I try to write a mod loader? Sounds like fun and there'll probably be some challenges along the way - but if everything goes to plan, I'll be able to set up and play Project Zomboid Multiplayer again without wanting to die in the set-up process.

## The Plan

Three words: Python and GUI. I want to run my dedicated server on my main machine this time around (instead of a remote server) and as that runs Windows and is a desktop PC, I'd like to have a GUI for the whole modloading process. I'll use Python (mostly for ease of programming) for the code part of this project and pair it with something like PyQt for the GUI. I'll also create a command line version of the modloader for machines without a dedicated desktop, in the event that at some point I want to move the server onto a linux machine (maybe when I finally get into homelabbing...)

But what should the modloader do? Well, for starters, I'd like for it to take a Steam workshop collection link as an input from the user. The modloader will then do the rest; access the workshop collection, download all the mods, move them into the right folders and run the server. The modloader should (metaphorically) hold the user's hand throughout the entire process - providing logs, messages and anything else necessary to help the user with a clean installation.

In fact, with what I have in mind, this modloader is more like a 'modded server running utility' - that probably has some kind of name in the hosting world, but I don't know it so I'll stick with 'MSRU' because that makes me sound smart.

