## Customization
#### Map Settings
Note that expressions such as `64*/*insert number*/` can be replaced with their evaluated solutions.
* Example: Replace `64*5` with `320`, and `64**2` with `4096`.
##### To change the size of a pixel:
  * Change all of the fives in `e%Q*5,(z=e>>6)*5,5,5` to a different number.
  * Change `b.width=b.height=320` to `b.width=b.height=64*/*insert number*/`
    * Replace `/*insert number*/` with the same number used in the first step.
    * The `64` in the middle should be set to the number that `Q` has been set to.
      * `Q=64` is the default.
##### To change the width and height of the playing area:
  * Change `(z=e>>6)` to `(z|=e/Q)`.
  * Change the value of `Q` to a different number.
  * Change `b.width=b.height=320` to `b.width=b.height=/*insert number*/*5`.
    * Replace `/*insert number*/` with the same number used for `Q`.
    * The `5` at the end should be set to the number being used for the size of a pixel.
  * Change `m=b=4096` to `m=b=/*insert number*/**2`.
    * Replace `/*insert number*/` with the same number used for `Q`.
##### To remove the red borders:
  * Replace `z=F[e]=!(e%Q--%Q&&z%Q)|(Q=e==h)+Q` with `z=F[e]=(Q=e==h)+Q`.
#### Gameplay Settings
##### To show decimals in the score:
  * Change `S|!setTimeout(F,50)` to `S+!setTimeout(F,50)`.
##### To change the snake's speed:
  * Change the `50` in `S|!setTimeout(F,50)` to a different number.
    * A smaller number means a faster speed, and a larger number means a slower speed.
    * Decimals will be accepted as well.
##### To change input keys:
###### Directional Input
Uhh, good luck with this one. `4/e>1&e+b` is hardcoded to accept 4 keys *that follow each other in sequential order* according to `KeyboardEvent.keyCode`.  
  
In this instance, it is determined by `e=e.keyCode-37`, with `e.keyCode` returning `37` upon pressing the left arrow key.  
Alter the number at the end to set the left input key and the keys that follow it. The table below shows the currently used key codes:  
Key | Code
--- | ----
`ArrowLeft` | `37`
`ArrowUp` | `38`
`ArrowRight` | `39`
`ArrowDown` | `40`
`P` | `80`
  
More information can be found [here](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/keyCode#constants_for_keycode_value).
###### Pausing
Notice how the key code for `P` is `80`. Part of the code that handles user input contains `(e=e.keyCode-37)-43`, and in that code, the `37` and `43` add up to equal `80`. The pause button is determined in the same way, by taking the sum of the two numbers being used.  
  
To set the pause key, change `43` to the difference between the new key's code and `37` (the left input key's code). Since the pause key is currently `P`, this would be represented by `80 - 37 = 43`.
##### To change built-in messages:
  * Change ```alert`Game Over` ``` to ```alert`Insert Message Here` ```.
  * Change `'Press P'` to `'Insert Message Here'`.
