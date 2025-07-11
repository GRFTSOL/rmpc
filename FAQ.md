## Table of contents

- [Mopidy does not work with rmpc](#mopidy-does-not-work-with-rmpc)
- [I want to edit (or otherwise interact directly with) my files from rmpc](#i-want-to-edit-or-directly-interact-with-my-files-from-rmpc)
- [Album art is not working in Zellij](#album-art-is-not-working-in-zellij)
- [Scrobbling and mpris](#scrobbling-and-mpris)

### Mopidy does not work with rmpc

Unfortunately Mopidy only supports a very old version of MPD's protocol. Many features are missing
or behave a bit differently than they should. Mopidy's implementation does not have support for
album art and thus they would simply not work even if rmpc was otherwise usable with Mopidy.

See https://github.com/mopidy/mopidy-mpd/issues/68 for more information.

Mopidy-mpd is looking for help with maintaining the project, maybe you can help out if you want to
use rmpc with Mopidy!

### I want to edit (or directly interact with) my files from rmpc

Rmpc is an MPD client and as such it is not guaranteed to have direct access to the files. Rmpc is
not the right tool for the job here.

See comment from MPD's author https://github.com/mierak/rmpc/issues/287#issuecomment-2902083413.

If you still want some convenience in this matter, you can try scripting your way around this by
integrating rmpc with other tools via `ExternalCommand` keybind or some other means.

### Album art is not working in Zellij

You can force rmpc to use the sixel backend via config. It should somewhat work but will not be a
good experience and is thus not recommended. Zellij's sixel support is spotty and while there
certainly are improvements that could be made on rmpc's side I do not believe this to be a worthwhile
time investment as the album arts are very tricky to get right and a lot of time went into them
already. You are still welcome to submit pull requests with improvements though!

https://github.com/zellij-org/zellij/issues/2576

There is also a feature request to support kitty's image protocol in Zellij which I am keeping an eye
on. If/when it gets merged (assuming full protocol implementation with unicode placeholders), rmpc
will support Zellij.

### Scrobbling and mpris

Scrobbling and mpris are not supported and do not really belong in rmpc. These tools are better suited
for a daemon and not a frontend. There already are tools to do just that and you can use them alongside
rmpc!

- https://github.com/MusicPlayerDaemon/mpdscribble by MPD's author
- https://github.com/eonpatapon/mpDris2
- https://github.com/natsukagami/mpd-mpris

There is also a very useful article on [Arch wiki](https://wiki.archlinux.org/title/Music_Player_Daemon/Tips_and_tricks)

