# Thrust Issues VR

A VR boomer shooter where your guns are your jetpack. Your arms are machine-gun cannons, and every bullet pushes you the opposite way you're aiming. Built with Three.js and WebXR for the Quest 3. It also runs in a desktop browser.

**Play:** https://kungfukennyog.github.io/thrust-issues-vr/

## How to play

Survive waves of enemies. Clearing a wave gives bonus points and heals 30 HP, followed by a short breather before the next one. Your best score is saved.

- **Flyers** chase you and ram you.
- **Grunts** walk toward you and fire slow orbs you can dodge. Their visor flashes right before they shoot.
- **Snipers** (wave 2+) sit on the high ledges. They aim a red laser at you, the laser turns white when they lock on, and then they fire. Move off the line.
- **Heavies** (wave 3+) are armored, so bullets barely hurt them. Use charge blasts. They also slam the ground, so be in the air when they do.

Scoring: kills while airborne are worth 1.5x, killing several enemies with one blast adds a multi-kill bonus, and staying airborne for 3 s or more pays out when you land. Kills also cool both arms and heal 5 HP. When a wave is down to its last 3 enemies, each one gets a red beacon so you can find it.

## Controls

| | VR | Desktop |
|---|---|---|
| Fire left / right arm | Trigger | LMB / RMB |
| Charge shot (hold, release to blast) | Grip | Q / E |
| Move | Left stick | WASD |
| Turn | Right stick | Mouse |
| Jump | A | Space |
| Reset | X | R |
| Tuning panel | Hold Y (right stick ↑↓ / ←→) | Sliders on the start screen |
| Thruster stance (arms point down-back) | — | Hold Shift |

The wrist HUD (VR) and the bottom-right HUD (desktop) show speed, HP, kills, FPS, the worst frame time, and the enemy count.

## Aiming

Aiming a gun from your hand in VR is hard, so the game helps. If an enemy is within a 6° cone of where a barrel points, shots bend onto it. Recoil always follows the real barrel direction, so movement isn't affected. Enemy hitboxes are padded spheres, and each arm has a faint aim laser whose dot turns red when it's on a target. In a test with a bot that wobbles about ±4°, this took the hit rate from about 5% to about 61%. Assist cone, hitbox size, and the laser can all be changed on the tuning panel.

## Tuning

Every movement, heat, and combat value can be changed live, and changes are saved per browser. "Reset defaults" restores the tuned values.

## Art direction

A retro boomer shooter played across the rooftops of downtown Seoul at night. The arena is a grid of rooftops at different heights over a street 41 m below. You can sprint-jump the gaps, and you need recoil to climb to the higher roofs. Falling into the street costs 20 HP and drops you back on the last roof you stood on.

- A central skyscraper covered in LED ads that's too tall to climb. Fly around it to break line of sight.
- Glass towers with rooftop gardens and HVAC units, apartment blocks with helipad roofs, and older shop buildings with neon Hangul signs.
- Skybridges across some gaps, rooftop billboards (snipers like to perch on them), and a construction crane whose arm is the highest perch on the map.
- Rooftop huts, water tanks, and AC units to use as cover. Down in the street there's traffic, crosswalks, and lit storefronts.
- Textures are low-res and drawn procedurally with nearest-neighbour filtering. Enemies use toon shading with black outlines in loud colours.

Rendering cost is kept low for the Quest browser: level boxes are merged into one mesh per material, all signs share one texture atlas and one mesh, and each enemy is drawn in 3 draw calls.

Font: [Black Han Sans](https://fonts.google.com/specimen/Black+Han+Sans), SIL Open Font License (see `fonts/OFL.txt`).
