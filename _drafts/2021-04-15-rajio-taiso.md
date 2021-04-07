---
layout: post
title: "Rajio Taiso ラジオ体操"
subtitle: "Automate stretch-breaks while working from home"
background: /assets/img/posts/Rajio_Taiso/4S0A0496.jpg
---

## Background
I never thought my love of Studio Ghibli would make working from home better... 

I first learned of Rajio Taiso (Radio Calisthenics) from watching the 2013 documentary 'The Kingdom of Dreams and Madness.' The documentary gives viewers a behind the scenes look into the Japanese offices of Studio Ghibli as they work on the films 'The Wind Rises' and 'The Tale of the Princess Kaguya'.

## Home Automation
There are two ways to implement this automation: The Easy Way (local file) and The Hard Way (streaming). I will cover The Hard Way in a future post.

### My Setup
1. Raspberry Pi 4
2. Home Assistant software
3. Google Home Mini

```
alias: Rajio Taiso
description: ''
trigger:
  - platform: time
    at: '11:00'
  - platform: time
    at: '13:00'
  - platform: time
    at: '15:00'
  - platform: time
    at: '17:00'
condition:
  - condition: time
    weekday:
      - mon
      - tue
      - wed
      - thu
      - fri
action:
  - service: media_player.volume_set
    target:
      entity_id: media_player.living_room_speaker
    data:
      volume_level: 0.26
  - service: media_player.play_media
    data:
      media_content_type: music
      media_content_id: 'https://nathansprojects.duckdns.org:8123/local/rajio.mp3'
    target:
      entity_id: media_player.living_room_speaker
  - delay:
      hours: 0
      minutes: 3
      seconds: 19
      milliseconds: 0
  - service: media_player.turn_off
    target:
      entity_id: media_player.living_room_speaker
mode: single


* Studio Gibli
* Working from home
* Home assistant
    * Google home mini
```

<div style="padding:56.25% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/113410334?title=0&byline=0&portrait=0" style="position:absolute;top:0;left:0;width:100%;height:100%;" frameborder="0" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>
*Hayao Miyazaki and Studio Ghibli employees performing Rajio Taiso during work.*
