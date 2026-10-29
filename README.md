# Moving Like Goofy

**Teaching any character a cartoon's way of moving, from 71 example clips.**

Omar Alromaihi · Technical report, October 2026 · work in progress

[**Project page**](https://omarintern.github.io/moving-like-goofy/)

![The golf swing: the original input on the left, the Goofy-style output on the right](teaser.gif)

*Left: the original input, a person's golf swing. Right: the Goofy-style output, the same swing with his bearing. One clock.*

## What this is

A project page, not a paper and not software to install. It shows a motion model that learned Goofy's way of moving from his own films: 71 short clips, 195 seconds of footage, each paired with a person doing the same action plainly, trained for 103 minutes on one GPU. After that, any plain performance comes out as his. The page shows the results as 3D figures beside the original input, painted back into the person's own footage by a video model, and on a humanoid robot in a physics simulation.

## What is on the page

- **Results.** Pairs on one clock: the original input, a person doing the action, beside the Goofy-style output, the same action with his bearing. A shot put, a golf swing, a wait at a bus stop as the bus arrives, a ballet phrase. Then a kick and a skid through three stages of the model, trained on 17, 40 and 71 example clips.
- **In the shot.** A skid and a kick rendered into the person's own footage by a video model, each shown three ways: the original input, the output at the person's pace, and the same output a quarter faster.
- **On a robot.** A walk from his own films, kept out of training, on a Unitree G1 in simulation, with the original input on the same robot beside it.
- **Method** and **How it is made.** From his films to a fit, the pairs, the training, and the single solve that keeps the output on the person's path and footing.
- **What's next.** What the training clips hold and where his manner shows most, two ways to grow the data, finer phases, and better pairs.

Some captions point at moments where his manner shows. Each time is a link: a click sends every panel of that clip to one second before the moment and plays it.

## How it works, in short

The model builds on [STyMo](https://doi.org/10.1145/3811356) (Ponton, Winkler, Kavan, Ye and Kadlecek, SIGGRAPH 2026): the split of a style into a posture and a way of moving through it is STyMo's. Here the posture is one fixed pose, set by hand and laid onto every input the same way. The way of moving is the learned part: the difference from the person's motion to his, over windows of 32 frames, about a second around each frame, learned by a small transformer from the 71 pairs. Around that, this project adds the character's manner learned from his films rather than from motion capture, the extraction and checks that make old film usable as training data, a final pass that keeps him on the person's path and footing, and the two uses after the motion: the video model and the robot.

## What is in this repository

The page and its clips. Nothing to build or run.

- `index.html`: the page.
- `media/`: the 17 videos and 6 posters it plays.

Open `index.html` in a browser, or visit the project page.

## Credits

Goofy is a Disney character; the footage is the 1940s shorts, used here as the subject of study. The robot is a Unitree G1 in MuJoCo under NVIDIA's [GEAR-SONIC](https://github.com/NVlabs/GR00T-WholeBodyControl) balance controller; the motions were mapped onto it with [GMR](https://github.com/YanjieZe/GMR), an open retargeting tool. The model builds on [STyMo](https://joseluisponton.com/stymo-project-page/).

## To refer to this page

Omar Alromaihi. *Moving Like Goofy: teaching any character a cartoon's way of moving, from 71 example clips.* Technical report, October 2026. https://omarintern.github.io/moving-like-goofy/

Omar Alromaihi, 2026.
