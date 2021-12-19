---
id: C6v9ci4JyeBqYQClQKHfK
title: DOM
desc: ''
updated: 1639886928554
created: 1639835415479
---

## [IME event(CompositionEvent)](https://stackoverflow.com/questions/35876470/react-composition-events)

## For a tag to open a new tab, attribute `rel="noopener noreferer"` needs to be added

## [Camera and microphone access in cross origin iframes](https://blog.addpipe.com/camera-and-microphone-access-in-cross-oirigin-iframes-with-feature-policy/)

## [HTML text overflow ellipsis detection](https://stackoverflow.com/questions/7738117/html-text-overflow-ellipsis-detection)

## Caustions of video autoplay in DOM

Create a video tag with JS, if not added into DOM, it can't autoplay. Usually, modern browsers also try to avoid autoplay muted videos. If autoplay is necessary anyway, `crossorigin` attribute is required on the video tag. `video.setAttribute('crossorigin', 'anonymous') This was found on a [stackoverflow post](https://stackoverflow.com/questions/64065651/html5-video-autoplay-is-not-always-triggered/64067330#64067330)
[MDN HTML CORS attribute](https://developers.google.com/web/updates/2017/09/autoplay-policy-changes)
