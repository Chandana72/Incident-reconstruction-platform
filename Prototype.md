Each iteration below states what was attempted and why it was subsequently changed or abandoned. Development of this component is ongoing.

Iteration 1: Static Stick Figures. Plain, static stick figures with no animation were used to establish the dashboard's baseline visual style. This was moved on from as it conveyed no sense of activity or progression through the incident timeline, which is central to the project's purpose.
<img width="1470" height="956" alt="prototype 1 0" src="https://github.com/user-attachments/assets/c17fdfcb-32bd-4405-974d-fed7b4c14245" />

---------------------------------------

Iteration 2: Contextual Icons Added. Small icons (a desk and monitor, a password field, a laptop, a cloud) were placed beside each stick figure to give each panel the appearance of a scene. This was later removed, as it did not address the absence of motion and became visually inconsistent once the figures themselves changed in later iterations.
<img width="1466" height="646" alt="prototype 2 0" src="https://github.com/user-attachments/assets/cd2122da-436a-4f78-a971-65b599b42403" />

---------------------------------------

Iteration 3: Basic Keyframe Bounce. The original intention at this stage was for the figures' movement to resemble game-like character motion — convincing, dynamic movement similar to a game character walking or acting. What was implemented, however, was a simple vertical bounce animation, which in practice was closer to a static image being repeatedly shifted or rotated in place than genuine motion. This fell well short of the intended effect and read as a repetitive wobble rather than purposeful movement, and was abandoned on that basis.

---------------------------------------

Iteration 4: Third-Party Animated Characters (Rive, Lottie). Rive and Lottie, both platforms offering pre-built, professionally animated character assets, were evaluated as a replacement for the hand-drawn figures. This was not adopted, as asset retrieval required manual interaction through each platform's own web application and could not be integrated into the build process, and because the available characters were human-like and cartoon-styled, which would have clashed with the deliberately minimal visual style of the rest of the interface.

---------------------------------------

Iteration 5: Physics-Based Animation (Matter.js), Initial Build. A jointed stick figure was constructed using the Matter.js physics engine, with limbs as separate connected rigid bodies, so that motion emerged from simulated physics rather than predefined keyframes. This required correction after the figure was found to intermittently fall through the floor and exit the canvas entirely — traced to a known limitation in Matter.js, which does not check for collisions continuously and can allow a fast-moving body to pass through a thin boundary undetected. This was resolved by dividing each frame's physics calculation into several smaller steps instead of one large step, verified stable across a 60-second continuous simulation.
<img width="1470" height="956" alt="prototype 3 0" src="https://github.com/user-attachments/assets/a0b8a2af-1b96-436f-8c12-c35227832aff" />
<img width="1470" height="956" alt="prototype 3 1" src="https://github.com/user-attachments/assets/3901edaf-0352-4e33-84c4-da5b10a2554e" />

---------------------------------------

Iteration 6: Postural Collapse. After the falling issue was resolved, the figure remained on screen but gradually collapsed into a disordered, overlapping pile instead of holding a standing posture. This was traced to an incorrect setup in which all of a figure's body parts had been grouped to ignore collisions with one another entirely, allowing unconnected parts (such as the head and an arm) to drift into each other over time with nothing to stop them. Comparing against Matter.js's own official reference example showed that collision exclusion should instead be limited to the segments within a single limb, not the whole figure. Correcting the grouping this way resolved the collapse, again verified across a 60-second continuous simulation.
<img width="1470" height="956" alt="prototype 4 0" src="https://github.com/user-attachments/assets/a9493fec-e63e-461a-95c5-bc1734c03173" />
<img width="1133" height="358" alt="Screenshot 2026-07-28 at 3 11 34 AM" src="https://github.com/user-attachments/assets/95225bf4-d82a-49f7-81fe-7f302133cf8b" />
<img width="1470" height="956" alt="prototype 4 1" src="https://github.com/user-attachments/assets/ce7e7482-c40e-43cb-97bc-1999c9a4a811" />

---------------------------------------

Iteration 7 (Final Prototype, Current): Insufficient Motion and Move Away from Matter.js. With the above corrections applied, the figures now stand correctly and hold their posture. However, the resulting motion was found to be insufficient: physics-based simulation could only produce limited, idle-level movement, and could not be directed toward a specific pose or position — for example, a figure walking to a defined location and sitting down. Since animation is a central focus of this project, this limitation was assessed as a significant shortfall rather than a minor gap. As a result, Matter.js is being moved away from as the basis for figure animation, since motion produced by physics simulation cannot be reliably directed. The project is currently working on an alternative approach: hand-authored SVG poses animated through GSAP keyframe sequences, which allow movement to be explicitly directed toward specific positions and poses rather than emerging from simulated forces. The next planned step is building out full directed sequences (e.g., a figure walking to a location and adopting a seated posture) using this approach.
