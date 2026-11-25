# Sort Sol

Flying inside a murmuration of starlings at dusk over the marsh at Ribe, Denmark.

**Live:** https://www.attabird.com/sortsol

Sort sol means "black sun". It's what we call it in Denmark when hundreds of thousands of starlings gather over the marshes at dusk and darken the sky. I grew up in Ribe, Denmark's oldest town, on the west coast, where you can see it every spring and autumn. My father used to play the organ in Ribe Cathedral, and the cathedral is on the horizon behind you.

You start on the dike and watch the flock. Then you fly into it and become one of the birds. After about three minutes the evening ends and the flock pours into the reeds.

## How it's built

One self-contained HTML file. WebGL 2, Web Audio and plain JavaScript, no libraries and no build step.

- **The flock.** 7,000 birds are simulated on the CPU (4,000 on phones). Each is drawn 20 times (12 on phones) with instancing, so about 140,000 birds on screen. The number of copies drops if the screen can't keep up.
- **Neighbours.** Every bird follows its seven nearest neighbours, like measured starlings do.
- **Flying with you.** Around the camera, 500 free birds (250 on phones) fly as one group with you inside a 7.5 m bubble, so your neighbours stay close and steady. They cross-fade with the rest of the flock at the edge.
- **Waves and the falcon.** Turns sweep through the flock as waves at 20 m/s. The falcon flies at 15 m/s and strikes the edge of the flock, like real peregrine attacks. When it strikes, an escape wave rolls through in three pulses, each weaker than the last.
- **Light.** Dark birds on a bright sky blend without sorting, and far birds keep their true coverage so they don't flicker. Dusk haze gives the flock depth.
- **One bird's flight.** Wing strokes with glides and bounds, a nose-up body and a level horizon.
- **Sound.** All of it is generated live with Web Audio: wind by airspeed, the rush of the flock, the wings of the nearest birds, music that swells when the flock wheels, and chatter in the roost. No audio files.

Click or tap the flock to startle it: the birds burst away from the spot, as when a falcon strikes, and the hole closes again over a couple of seconds. The view follows your mouse a little, and scrolling speeds up the evening. With reduced motion turned on, the flight is calmer.

## Running it

Open `index.html` in a browser, or serve the folder:

```
npx serve .
```

The page uses Fraunces italic for its title from `assets/fonts/fraunces-italic.woff2`. That file isn't in this repo, so locally the title falls back to your system serif.

## The research behind it

The numbers in the code come from studies of real starling flocks. The main ones:

- Ballerini et al. 2008, *Interaction ruling animal collective behavior depends on topological rather than metric distance*. Seven neighbours, not a fixed radius.
- Ballerini et al. 2008, *Empirical investigation of starling flocks*. Shape, density and spacing of real flocks.
- Attanasi et al. 2014 and Cavagna et al. 2015. How turns travel through a flock as waves.
- Attanasi et al. 2015. Every bird flies the same arc in a turn.
- Storms et al. 2019, *Complex patterns of collective escape in starling flocks under predation*. The dark bands that roll through a flock when a falcon attacks.
- Goodenough et al. 2017. How murmurations end.

The comments in the code say where each number comes from.

## Credit

Created by Henrik Pultz Melbye, [attabird](https://www.attabird.com).

## License

MIT. See [LICENSE](LICENSE).
