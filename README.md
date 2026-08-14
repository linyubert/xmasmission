# Magic Christmas Tree

An interactive installation for a school Christmas. Stand in front of a camera and summon a glowing 3D Christmas tree through four hand gestures — trunk, branches, nightfall, fireworks.

Magic Christmas Tree is part of **Dato Music Lab** (https://datomusiclab.dpdns.org), a working elementary music teacher's studio in Taipei. It was built for Yongshun Elementary School, Christmas 2025.

## What it is

School Christmas events have a staging problem: whatever is on the screen is something the children watch rather than something they do, and only one person can be at the front at a time.

Gesture control turns the screen into the activity. A child raises their arms and a tree grows out of the floor; they spread their arms and it puts out branches and lights. The whole room can see the cause and the effect at once, and the queue to have a turn becomes the event.

## Features

**Hand tracking.** Google MediaPipe HandLandmarker reads both hands' positions and how far the fingers are spread, in real time.

**A tree made of particles.** Three.js renders 5,000 leaf particles, 600 ornaments and 2,500 golden bulbs.

**Bloom.** An UnrealBloomPass post-processing pass makes the lights blaze once night falls.

**Fireworks.** Coloured particle bursts fire automatically in the final stage.

**Cinematic camera.** When the tree is finished the camera orbits and pushes in slowly on its own.

**Day and night.** The third gesture brings nightfall and four stage spotlights.

## The four steps

| Step | Gesture | Effect |
|:---:|:---|:---|
| 1 | Raise both hands (wrists above 0.4 height) | The trunk grows upward from the ground |
| 2 | Spread arms wide (x-distance over 0.4) | Branches, golden bulbs and ornaments appear |
| 3 | Open all five fingers (fingertip distance over 2.5× the wrist mean) | Night falls, bloom kicks in, the lights flicker on |
| 4 | Automatic | Fireworks launch and the camera begins its orbit |

## How to use

Download the folder and open `index.html`. It needs a webcam and a network connection, since Three.js and MediaPipe load from CDNs.

Best on a large display or projector, with room for a child to stand back far enough that both arms fit in frame.

## Where it works

School Christmas ceremonies, where the class takes turns on stage lighting the tree together; STEAM demonstrations, as about the clearest possible illustration of what hand tracking is; and interactive whiteboard projection, where the teacher's machine drives it and the whole class watches.

## Tech

A single HTML file using native ES modules — no bundler.

- **Three.js r160** for the 3D scene, particle systems and instanced meshes
- **MediaPipe Tasks Vision** for 21-point hand landmark detection
- **EffectComposer + UnrealBloomPass** for the glow

## License

MIT — see [LICENSE](LICENSE).

## More from Dato Music Lab

The same camera-driven idea turns up in a maths game where students play goalkeeper against falling multiples, catching the right numbers with their hands. Elsewhere the studio builds for the music room: a course where sixth-graders collect the sounds of their school for a Voyager-style golden record, and a whole-class game for identifying instruments by timbre alone. All at **https://datomusiclab.dpdns.org**.
