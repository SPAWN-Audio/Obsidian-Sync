---
Date: 2026-03-18
Author: Cody Cork
tags:
  - Resource/Audio/Wwise
---
# Random Containers

 > [!info] #### Good for things like:
 >- Footsteps
> - Gun / Attack sounds
> - Hit / Reaction sounds

## Standard vs Shuffle
Standard to keep the pool of objects intact. After an object is played, it is not removed from the possible list of objects that can be played and can therefore be repeated. 

Shuffle to remove objects from the pool after they have been played. This option avoids repetition until all objects have been played.

## Limit Repetion
In the Limit Repetition To property, choose the number of objects that must be played before an object can be repeated.
The behaviour of this option is affected by whether you are in Standard or Shuffle mode:

- **Standard Mode:** The object played is selected completely randomly, but the last x objects played are excluded from the list.
- **Shuffle Mode:** When the list is reset, the last x objects played will be excluded from the list.

![[Wwise - Containers.png]]