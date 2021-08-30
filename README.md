

# UI-Assets ReadMe

This is a collection of standard UI elements and tools, meant to provide a solid starting point for any project. 

## Organization

- UI Set: At present we have two sets of UI assets
  - **TP_Blanc**: Our standard set, these are all white so that they can be tinted to any color in code
  - **TP_Noir**: These are inverted black and white assets, off-black shapes with white outlines
- Asset Type: Inside the UI set folder assets are mostly sorted into folders by type
  - **Button** - Base shapes for buttons
    - 
    - **Decoration** - Decorative elements like shines and gradients that can be put on top of buttons to dress them up
  - **Symbol** - A collection of common symbols
  - **Tool** - Items meant to aid in setting up or designing UIs

## Naming Conventions

\[Item\]RX-Depth-Deep_64px

- \[Item\]: Idetifies the item type
- RX: Indicates the roundness of the corners. Measured in points at the 64px scale. At present the options are:
  - R0: Square corners (nearly, 1pt at 128px scale)
  - RS: Small radius corners (4pt at 128px scale)
  - RL: Large radius corners (10pt at 128px scale)
  - R00: Rounded (a circle, or a pill shape)
- Depth: If present indicates that there are subtle highlights and shadows creating a 3D appearance
- Deep: If present indicates that the border is thicker on the bottom, creating an appearance of thickness
- ##px: Indicates scale
  - 128px is the base scale, based on a 128px button size
    - On a modern iPhone, 128 pixels equates to roughly 42 points, which is almost the recommended smallest size for a touchable UI element (44pt), and a bit larger than the recommended visual minimum (32pt). It is also a Power of 2, which is why it was chosen
    - Button blocks at this scale are 64px squares (or circles)
    - Radius numbers are measured as Points at this scale, at larger scales the radii will be multiplied
  - 256px to 1024px are sized starting from the 64px scale and doubling each time
  - Items with the same scale number are scaled to each other

## Notes

- 9-Slice: Any square items, such as buttons, are meant to be 9-sliced so that they can be resized without altering the corners
  - The rounded corners are smoothed at 100%, which gives them a cleaner look
  - This means the distance the slices need to be from each edge is twice the coerner radius
  - So, for an RL button at 128px scale (10pt radius = 30px), each slice needs to be at least 60px from each edge to avoid stretching the corner radii
  - To be safe, it is simplest to set the slices at the third points (42px for an RL button at 128px scale)