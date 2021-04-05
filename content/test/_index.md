---
title: "Test"
date: Sun, 01 Nov 2020 16:00:46 +0000
draft: false
layout: "page"
---

<style>
.player-wrapper {
  position: relative;
  padding-bottom: 56.4%;
  height: 0;
  width: 100%;
}

.player-wrapper iframe {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
}
</style>
## Player tests

### Player Prod
<a href="https://player.pbs.org/experimental/features/svp_redirect?enable=true&redirect_to=https://player.pbs.org/partnerplayer/5czL0C0cle1vmic6A2Du5A==/?callsign=weta&duration=31536000" target="_blank">Toggle On Feature in Production</a>

<a href="https://player.pbs.org/experimental/features/svp_redirect?enable=false&redirect_to=https://player.pbs.org/partnerplayer/5czL0C0cle1vmic6A2Du5A==/?callsign=weta&duration=31536000" target="_blank">Toggle Off Feature in Production</a>

<div class="player-wrapper">
<iframe id="partnerPlayer" marginwidth="0" marginheight="0" scrolling="no" src="https://player.pbs.org/partnerplayer/5czL0C0cle1vmic6A2Du5A==/?topbar=false&amp;end=0&amp;endscreen=true&amp;start=0&amp;autoplay=false&amp;callsign=weta" allowfullscreen="" sandbox="allow-same-origin allow-scripts allow-top-navigation-by-user-activation allow-storage-access-by-user-activation allow-top-navigation" width="100%" height="100%" frameborder="0" referrerpolicy="no-referrer-when-downgrade"></iframe>
</div>

```html
<iframe id="partnerPlayer" marginwidth="0" marginheight="0" scrolling="no" src="https://player.pbs.org/partnerplayer/5czL0C0cle1vmic6A2Du5A==/?topbar=false&amp;end=0&amp;endscreen=true&amp;start=0&amp;autoplay=false&amp;callsign=weta" allowfullscreen="" sandbox="allow-same-origin allow-scripts allow-top-navigation-by-user-activation allow-storage-access-by-user-activation allow-top-navigation" width="100%" height="100%" frameborder="0"  referrerpolicy="no-referrer-when-downgrade"></iframe>
```

### Player staging

<a href="https://player-staging.pbs.org/experimental/features/svp_redirect?enable=true&redirect_to=https://player-staging.pbs.org/partnerplayer/5czL0C0cle1vmic6A2Du5A==/?callsign=weta&duration=31536000" target="_blank">Toggle On Feature in Staging</a>

<a href="https://player-staging.pbs.org/experimental/features/svp_redirect?enable=false&redirect_to=https://player-staging.pbs.org/partnerplayer/5czL0C0cle1vmic6A2Du5A==/?callsign=weta&duration=31536000" target="_blank">Toggle Off Feature in Staging</a>

<div class="player-wrapper">
<iframe id="partnerPlayer" marginwidth="0" marginheight="0" scrolling="no" src="https://player-staging.pbs.org/partnerplayer/5czL0C0cle1vmic6A2Du5A==/?topbar=false&amp;end=0&amp;endscreen=true&amp;start=0&amp;autoplay=false&amp;callsign=weta" allowfullscreen="" sandbox="allow-same-origin allow-scripts allow-top-navigation-by-user-activation allow-storage-access-by-user-activation allow-top-navigation" width="100%" height="100%" frameborder="0" referrerpolicy="no-referrer-when-downgrade"></iframe>
</div>

```html
<iframe id="partnerPlayer" marginwidth="0" marginheight="0" scrolling="no" src="https://player-staging.pbs.org/partnerplayer/5czL0C0cle1vmic6A2Du5A==/?topbar=false&amp;end=0&amp;endscreen=true&amp;start=0&amp;autoplay=false&amp;callsign=weta" allowfullscreen="" sandbox="allow-same-origin allow-scripts allow-top-navigation-by-user-activation allow-storage-access-by-user-activation allow-top-navigation" width="100%" height="100%" frameborder="0"  referrerpolicy="no-referrer-when-downgrade"></iframe>
```



<iframe id="" marginwidth="0" marginheight="0" scrolling="no" src="https://chipcullen.com/iframe/" allowfullscreen="" sandbox="allow-same-origin allow-scripts allow-top-navigation-by-user-activation allow-storage-access-by-user-activation allow-top-navigation" width="100%" height="100%" frameborder="0" referrerpolicy="no-referrer-when-downgrade"></iframe>

