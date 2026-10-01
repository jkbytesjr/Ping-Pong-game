[README.md](https://github.com/user-attachments/files/32898111/README.md)
# Ping Pong

A browser Pong game in a single `index.html` file. It has no build step and nothing to install.

**Play it:** https://YOUR-USERNAME.github.io/pong

## Game modes

- **vs CPU:** play against the computer on Easy, Medium or Hard. The CPU reacts late and aims a little off, so it can be beaten.
- **2 Players:** two people on one keyboard, or one tablet.
- **Online:** play a friend on another device. One player hosts and sends an invite link. Opening the link joins the game.

The first player to 7 points wins.

## Controls

| Action | Keys |
| --- | --- |
| Move paddle | W / S, Arrow Up / Down, mouse, or drag on the court |
| Start / pause | Space, or tap the court |
| Restart | R |
| CPU difficulty | 1 Easy, 2 Medium, 3 Hard |

In 2-player mode, the left player uses W/S and the right player uses the arrow keys. On a touch screen, each player drags on their own half of the court.

## How it plays

- The ball bounces off the top and bottom walls and off both paddles.
- Where the ball hits the paddle sets the bounce angle, up to 45°. A hit near the middle goes straight, and a hit near an edge goes steep.
- The ball gets faster with every paddle hit, up to a maximum speed.
- The sound effects are beeps made with the browser's Web Audio API. There are no audio files.

## Run it locally

Download `index.html` and double-click it, or open it in any modern browser. Every mode except online works offline.

## How online play works

The host's browser runs the game, and the friend's browser sends its paddle position and draws what the host reports.

To find each other, the two browsers use the free public [PeerJS](https://peerjs.com/) matchmaking server. After that, they connect directly. If the matchmaking server can't be reached, the game falls back to swapping connection codes by copy and paste.

Some office, school or mobile networks block direct browser-to-browser connections. If online play won't connect, try having both players on the same Wi-Fi.

## Tech

- Plain HTML, CSS and JavaScript in one file
- HTML5 `<canvas>` for drawing, and `requestAnimationFrame` for the game loop
- Web Audio API for sound
- WebRTC through [PeerJS](https://peerjs.com/) for online play. This is the only external script, and it loads only when someone plays online.
