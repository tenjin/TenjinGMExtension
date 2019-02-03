###Taptics: A simple extension for using the new Taptic Engine in iPhone 7
Available Haptic Patterns:
----
Apple has made 7 different haptic patterns available to developers with the Taptic Engine in iPhone 7. They can be played with the following functions:

- `playLightImpactHaptic()`
- `playMediumImpactHaptic()`
- `playHeavyImpactHaptic()`
- `playSelectionChangedHaptic()`
- `playSuccessNotificationHaptic()`
- `playWarningNotificationHaptic()`
- `playErrorNotificationHaptic()`

These functions are named based on their suggested usage by Apple, but feel free to get creative.
Usage: 
----
Let's say you want to play the light impact haptic when an object collides with another object. Before the collision occurs, call `prepareHapticGenerator()` to prepare the Taptic Engine. (__This is optional, but Apple strongly recommends preparing the Taptic Engine before playing a haptic for minimal latency.__)


After preparing the Taptic Engine, simply call `playLightImpactHaptic()` in the collision event, and the haptic will play.

After a haptic has played, you should call `prepareHapticGenerator()` again if you anticipate playing another haptic effect soon. 

###Notes on `prepareHapticGenerator()`:

The Taptic Engine will return to its idle state after calling `prepareHapticGenerator()` if you don't play a haptic within a few seconds. However, if you call `prepareHapticGenerator()` and then play a haptic too soon, the Taptic Engine may not have had enough time to get into its prepared state. 

You can also force the Taptic Engine to return to its idle state by calling `releaseHapticGenerator()`, but this is usually never necessary.

A sample project is included so you can see an example of how haptics can be used in your game.
Compatibility: 
----
These haptic effects __ONLY__ work on iPhone 7 and iPhone 7 Plus. Older iPhone models do not have the new Taptic Engine, so calling any of the haptic functions on an older device won't do anything.