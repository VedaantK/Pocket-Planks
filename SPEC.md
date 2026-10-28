# SPEC: Pocket Planks

## The Game

Pocket Planks is a relaxed, quick puzzle-platformer that feels like a browser game. Each level gives you a small set of blocks. First you place them with the mouse, then you play the level with WASD and try to reach the win zone using only what you placed.

The fun comes from figuring out how to get across with the limited blocks you're given. Levels are short and low-pressure. Failing isn't harsh: if you fall off the bottom of the screen, you drop back in from the top onto the starting platform.

**Feel:** relaxed, fun, and quick. The jump should feel clicky and responsive, like a good platformer: no floatiness and no delay.

## How a Level Works

1. **Build phase.** The level appears with the player on the starting platform. The player can see which blocks they've been given ("in hand"). They place blocks into the level with the mouse.
2. **Play phase.** The player presses Space to start. Blocks stay where they were placed, and the player moves with WASD to try to reach the win zone.
3. **Win.** Landing in the win zone completes the level and moves on to the next one.
4. **Falling.** If the player falls off the bottom of the screen, they fall back in from the top of the screen onto the starting platform. Placed blocks stay where they are.
5. **Editing.** Whenever the player is standing on the starting platform, they can press Space to go back to the build phase, move or remove their placed blocks, and try again.

## Blocks

- **Plank:** a wide, flat platform the player can stand on. Its exact size is up to the builder; it should be a sensible size relative to the player and the rest of the level.
- **Box:** a solid square block, roughly the player's size. Unlike the plank, it's tall enough to use as a step, and boxes can be stacked.
- **Spring:** launches the player upward when they land on it, to about twice the height of a normal jump.

## Obstacles

- **Spikes:** make levels harder. Touching spikes makes the player freeze briefly, then fall straight down off the bottom of the screen. From there it works like any other fall: they drop back in from the top onto the starting platform.

## Levels

The game has 3 levels. Each level gives a different set of blocks and has different obstacles.

- **Level 1 (tutorial):** In hand: 1 plank, 1 spring. The player places the plank, jumps onto it, then jumps onto the spring to reach the win zone.
- **Level 2 (spikes):** Spikes are placed around the level. In hand: 2 boxes, used as steps to help the player get up and over the spikes. The challenge is jumping over the spikes to reach the win zone.
- **Level 3 (springs):** In hand: several springs (the builder picks the exact number to fit the layout). The player must place them so they can bounce from spring to spring, landing on each one consecutively, until they reach the win zone at the end.

## Acceptance Criteria

**Build phase**
1. Each level starts in the build phase, with the player standing still on the starting platform.
2. The blocks available for the level are shown on screen, including how many of each are left.
3. The player can choose a block and place it in the level using the mouse.
4. The player cannot place more blocks than the level gives them.
5. During the build phase, the player can pick a placed block back up (returning it to their hand) or move it.
6. Pressing Space ends the build phase and starts the play phase. During the play phase, blocks can't be moved.
7. While the player is standing on the starting platform during the play phase, pressing Space returns to the build phase with all placed blocks where they were.

**Play phase**
8. A moves the player left and D moves them right. W jumps. S does nothing.
9. The player can only jump while standing on something, and the jump starts immediately when W is pressed.
10. The player can stand on planks and boxes, and can't walk through them.
11. Landing on a spring launches the player about twice as high as a normal jump.
12. Falling below the bottom of the screen makes the player fall in from the top of the screen and land on the starting platform. Placed blocks stay where they are.
13. Touching spikes freezes the player briefly (they can't move), then they fall straight down off the bottom of the screen and respawn as in criterion 12.
14. Landing in the win zone completes the level and loads the next level.
15. Completing the last level shows a message saying the player beat the game.

**Levels**
16. Level 1 is solvable as described above with 1 plank and 1 spring.
17. Level 2 is solvable as described above with 2 boxes, and touching its spikes behaves as in criterion 13.
18. Level 3 is solvable as described above by bouncing across consecutive springs.

## Priorities

Build the core basics first. If time runs short, protect things in this order:

1. **Most important:** Level 1 fully works from start to finish: placing blocks (criteria 1–4, 6), moving and jumping (8–9), planks and springs (10–11), falling back to start (12), and the win zone (14, 16).
2. **Next:** spikes and Level 2 (13, 17), editing blocks (5, 7), and Level 3 (18).
3. **Cut first:** the end-of-game message (15).

## Out of Scope

Not needed: art beyond simple shapes, sound, menus, level select, timers, and scores. Simple and working beats fancy.
