# Ex.No: 5  Implementation of Steering behaviour-Pursue and Evade in Unity
### DATE:      02/11/2026                                                                      
### REGISTER NUMBER : 212224240174
### AIM: 
To write a program to simulate the process of Pursue and Evade behavior in Unity using NavigationMeshAgent. 
### Algorithm:
```
1. Create a New Unity Project by Open the  Unity Hub and create a new 3D Project.
2. Name the project "SteeringBehaviors" and select a location. Click Create.
3.Open Unity Scene (default is SampleScene).
  In the Hierarchy, create a Plane:
  Right-click → 3D Object → Plane (this will be the ground).
  Set its Scale to (10, 1, 10) for a larger surface.
  Create three Capsule for the Player, Pursuer, and Evader:
  Rename them to "Player", "Pursuer", and "Evader".
  Set their Y Position to 0.5 (so they sit on the ground).
  Change their Material for better distinction (optional).
3. Check AI navigation in window.
 Window → AI → Navigation (opens the Navigation tab).  If it is not available then add package by name "com.unity.ai.navigation"
4. Select the Plane, go to the Navigation tab, and mark it as Navigation Static.
   Go to the Bake tab and click Bake.
   or
   Add navMeshSurface to plane and bake 
4. Add NavMeshAgent Component 
    Select Pursuer, and Evader.
    Click Add Component → Search for NavMeshAgent and add it.
    Adjust NavMeshAgent Settings:
    Player: Set Speed = 5.
    Pursuer: Set Speed = 4.
    Evader: Set Speed = 6.
5. Write a script for  Player_movement behavior and save it

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Player_movement : MonoBehaviour
{
    // Start is called before the first frame update
    public float speed;
    void Start()
    {
        float xdir = Input.GetAxis("Horizontal") * speed;
