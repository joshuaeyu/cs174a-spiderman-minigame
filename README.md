### CS 174A Final Project - Spider-Man Minigame!

This was my group's final project submission for *COM SCI 174A: Introduction to Computer Graphics* at UCLA in Fall 2018. We implemented physics, swinging and wall-climbing mechanics, collision detection, audio, and player/camera controls on top of the basic WebGL-based graphics library that was provided by the course.

When copying this project from its original repository to this repository on my personal GitHub, I fixed a bug in the original project that may not have been observable previously due to changes to OpenGL drivers between then and now. The implementation of `phong_model_lights()` in the fragment shader code in dependencies.js expects `const int N_LIGHTS = 2` lights to be specified, but only one was defined in main-scene.js. This resulted in undefined behavior when the function attempted to the access the second element of several `N_LIGHTS`-length uniform arrays declared in the shader. To resolve this quickly I simply added a second, dummy light with no color to the scene in main-scene.js.

# term-project-group-17

Our project is a playable game that allows a player to explore a city as Spider-Man. 
Spider-Man can move, jump, shoot webs with sound effects, swing in the air, and stick to and climb walls. 
He can also collect coins scattered around the map. 
Our advanced topics were implementing physics, collision detection, and scene graphs.

The work breakdown was as follows: 
 - Justin Lee - physics engine, jumping, gravity, swinging, web, sounds
 - Gladys Ng - collision detection (bounding boxes), coins, building generation, texture mapping, object placement, game aspect
 - Daniel Park - scene graphs, smoothing out movement, car/people design, collisions involving cars/people, movement of cars/people, world design
 - Joshua Yu - physics engine, player movement/control, camera movement/control, climbing/sticking to walls, bird's-eye view

Keyboard inputs control Spider-Man’s movements while the mouse controls which direction he is facing. Controls:
    
 - "w" - grounded: move forward (relative to camera orientation); on wall: move upward
 - "a" - grounded: move left (relative to camera orientation); on wall: - move left
 - "s" - grounded: move backward (relative to camera orientation); on wall: move downward
 - "d" - grounded: move right (relative to camera orientation); on wall: move right
 - spacebar - jump
 - click and hold - while airborne, shoot web and swing (release to retract web)
 - "m" - toggle bird's-eye view of world
 - "v" - reset camera view to face forward
 - "h" - reset Spider-Man back to spawnpoint
 - esc - release pointer from game

To play, simply run host.command or host.bat, then navigate to localhost:8000 in Google Chrome.
