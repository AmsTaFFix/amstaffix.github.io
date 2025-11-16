---
title: 'External app for combat rotation for WoW pre-Midnight'
date: 2025-11-16
permalink: /posts/2025/11/wow-combat-rotation-external-app-prototype-archived/
tags:
  - wow
  - combat rotation
  - prototype
  - pixel analysis
---

Today I want to talk about [a little prototype](https://github.com/WoW-U/pixel-rotation) I made for WoW, which I have to archive. 

This is a [discontinued experimental project](https://github.com/WoW-U/pixel-rotation): a part of a combat rotation 
engine for WoW that worked without an unlocker by encoding decisions into on-screen pixels and reading them externally.

It was primarily tuned for melee classes, which fit my playstyle well, but the project became obsolete with [the
Midnight expansion](https://worldofwarcraft.blizzard.com/en-gb/midnight), which removed the features it depended on.

Today this repository is only kept as an educational/technical reference.

## How it worked

A Lua-based rotation engine decided which actions to perform (casts, target changes, etc.) and encoded those
decisions into compact [msgpack](https://msgpack.org/index.html) data, rendered as pixels in the top-left corner of the screen.  
[This application](https://github.com/WoW-U/pixel-rotation) then read and decoded those pixels to perform the 
corresponding actions, validating a hash to avoid artifacts corrupting the data.

## Conclusion

Building this was a fun journey, even if it has now ended. I’ve since created a new, Rust-based solution that relies solely on pixel analysis. It’s not as effective as this approach was, but it works.