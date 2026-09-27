# GAME_PROGRAM-EX--5

Making Player to collect the ammo and increase the bullet spawn count.


Aim


To implement a gameplay feature where the player collects ammo pickups in the game world. Upon collecting ammo, the player's ammo count increases, enabling more bullet spawns (shots).


Procedure


Setup Player Character



Open your PlayerCharacter Blueprint.s

Add a new Integer variable named AmmoCount.

Set an initial default value (e.g., AmmoCount = 10).

Ensure you have a shooting mechanism in place that uses AmmoCount to determine if a bullet can be fired.

Create Ammo Pickup Blueprint

Go to the Content Browser → Right-click → Blueprint Class → Select Actor → Name it BP_AmmoPickup.

Add components: * Static Mesh: Representing the ammo (e.g., a bullet or crate). * Sphere Collision: To detect overlap with the player.

In the Event Graph of BP_AmmoPickup:

Use OnComponentBeginOverlap on the Sphere Collision.

Cast to PlayerCharacter.

Increase the player’s AmmoCount (e.g., AmmoCount += 5).

Optionally, play a pickup sound or effect.

Destroy the ammo pickup actor.

Update Shooting Logic (Optional)

In your player’s shooting logic:

Before spawning a bullet, check if AmmoCount > 0.

If true:

Spawn bullet.

Decrease AmmoCount by 1.

Place Ammo in the World

Drag instances of BP_AmmoPickup into your level from the Content Browser.

Adjust position, mesh, and pickup range as needed.

OUTPUT

<img width="1918" height="856" alt="image" src="https://github.com/user-attachments/assets/6b383c5c-fb00-4f91-8af5-5fb8f6e41b5f" />


<img width="1919" height="1013" alt="image" src="https://github.com/user-attachments/assets/552ad331-0844-46d9-9c5f-4c0a8ba56522" />



<img width="1335" height="839" alt="image" src="https://github.com/user-attachments/assets/1c6b4279-2e9b-45d2-bb36-54b9852a6da4" />



<img width="1134" height="765" alt="image" src="https://github.com/user-attachments/assets/53b9b163-05ad-44b8-a497-d12a6a12c885" />



RESULT:


The player starts with a limited number of bullets.

When the player overlaps with an ammo pickup:

The ammo is collected.

The player's AmmoCount increases.

The player can now fire additional bullets based on the updated ammo count.
