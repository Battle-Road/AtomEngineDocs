# AtomEngineDocs

INTRODUCTION TO ATOM-ENGINE

Welcome to the AtomEngine documentation! AtomEngine, developed by Battle Road Digital, is a versatile and robust wargame development engine designed to empower orgnanizations with the tools needed to bring their ideas to life. Whether you're a seasoned wargamer or just starting out, AtomEngine provides a comprehensive suite of features to streamline the creation process.

AtomEngine is built to handle both 2D and 3D game development, offering a flexible environment that supports a wide range of game genres and styles. Its intuitive interface and powerful scripting capabilities make it accessible to developers of all skill levels, while its advanced features cater to those with more specific needs.

KEY CONCEPTS

User-Friendly Interface: AtomEngine boasts a clean and accessible interface that simplifies the game design process, making it easier to visualize and manipulate game elements.
Powerful Editing Tools: With a robust suite of authorship tools, AtomEngine allows for deep customization and control over entities and game mechanics, enabling developers to create intricate gameplay experiences. This suite of tools includes, but is not limited to, the Entity Authorship tool, the Behavior Authorship tool, a Scenario Creation Wizard, and a flexible injects system to drive custom events. (Please note that many of these tools are still in development and are not yet user-facing.)
Asset Management: Efficient asset management tools help you organize, import, and utilize game assets effectively, ensuring a smooth development workflow.
Cross-Platform Support: AtomEngine supports multiple platforms, allowing you to deploy your wargame across various devices and operating systems with minimal adjustments.
Functional Terrain: AtomEngine adjudicates many systems using a three-dimensional terrain model consisting of dozens of terrain classifications. These classifications and elevation maps have a direct impact on entity movement and capabilities, line of sight calculations, radar masking, weather patterns, and more.


LOGGING IN 

For Local Installation of AtomEngine, please go to the installation folder you've extracted the build to and find the AtomEngine.exe pictured below. Double click on it to run the AtomEngine application. 

![Screenshot 2024-08-26 123113](https://github.com/user-attachments/assets/03acbf7e-0098-4a4b-8fa6-0ef5a25cbdf0)

After running the application, a window should appear with a number of selectable options. Please choose the "Headless" config option and click "Log In".

![Screenshot 2024-08-26 123316](https://github.com/user-attachments/assets/665c1ff9-4592-49c9-b60a-ebe6bd40e8a3)

CREATING A PROJECT

There are two ways to create a new project. The first is the “Quick New” button, which instantly creates a new project with default settings, and the project will be automatically named as “project-date-timestamp" 
The second method is the “Create New” button. This path will provide an option to name and configure some starting parameters for this project, such as a date and time for the beginning of the simulation. 
Both methods will automatically add the new project to the list of saved projects in the launch window.

![Screenshot 2024-08-26 123427](https://github.com/user-attachments/assets/c8aefe0d-a790-4179-aaf0-cd64ea33e747)

SAVING A PROJECT

In AtomEngine, a project is a collection of all the saved game states on the timeline, both on the origin and on any branches. Therefore, saving the current game state is the same as saving the project.
To save the game state, press the save button on the left-most edge of the timeline panel corresponding to the Origin or currently active branch. This will create a save node at the current location of the playhead on the active timeline. Additionally, you can see if you have unsaved changes on the timeline by the line appearing as a teal color rather than white.

AtomEngine also autosaves the game state when certain actions are taken, such as changing the time scale or creating a branch while unsaved changes are present. Just like manual saves, these autosaves will appear as save nodes on the timeline.

LOADING A PROJECT

A project can be loaded from the “Load Saved Project” list in the launch window. Keep in mind that a project with no saved game states can be loaded, but it will appear as if it were a new blank project.
Also, from the Project List menu you can load, rename, or delete existing projects. 

INITIAL ORIENTATION

The Viewport is where location and spatial relationships are visualized, and where most user commands are issued to simulated entities. By default, a new project will have the entire globe visible in the Viewport.  
Controlling the camera 
⦁	Left-click and drag anywhere on the globe to pan the camera. 
⦁	Scroll the mouse wheel to zoom in and out. 
⦁	Press and hold the mouse wheel button while moving the mouse to control camera pitch and rotation. 

![Screenshot 2024-08-26 165719](https://github.com/user-attachments/assets/191ae85f-a81f-49bd-8cf3-e489d23f650e)

Viewport quick-access buttons 

![Screenshot 2024-08-26 165801](https://github.com/user-attachments/assets/405a74c6-9ab8-4225-90e3-bb0b24f73467)

A.	Compass – Resets the camera’s rotation to default 
B.	Top View – Resets the camera’s pitch to default 
C.	Team Selector – Dropdown list that allows a user to change their team. This is only available to admins and scenario authors to update their viewport to show only what the selected team can currently see. This also prevents the user from issuing commands to entities belonging to other teams. 
D.	Entity Insignia Display – Choose whether to display entities as mil2525D insignias, or to display the name of the entity. 
E.	Entity Health Bar – Toggle visibility. 
F.	Entity Location Dot – Toggle visibility of a very small white dot on the surface of the earth directly below the center of every entity. Useful for visualizing the exact location of airborne entities. 
G.	Entity Orientation Arrow – Toggle visibility. 
H.	Entity Flanking Angles – Toggle visibility. 
I.	Global Grid – Toggle visibility. 
J.	Global Administrative Layer – Toggle visibility of national/municipal boundaries and labels. 
K.	Global Illumination – Toggle time-based illumination on/off. 
L.	Settings Menu – Open the Settings Menu. 

NECESSARY LAYERS

All new scenarios or "projects" require data layers for entities to be able to move around and conduct behaviors. We call these layers "vectors" or Nav Mesh Tiles. Click on the Globe Icon in the top left, then the "Vector" tab. You can see a number of layers to load, but for a sample example please find the "Taiwan_Only.geojson" and "navmesh_global_ocean_canals.geojson" and click on the slider to their left to load them. 

You should see the AtomEngine logo and a loading screen each time you do this. The program is loading the requested data. Now let's make sure we have those layers loaded by checking the "Draw Loaded Layers" box on the bottom. 

![Screenshot 2024-08-26 124635](https://github.com/user-attachments/assets/93235d38-38f9-4bdb-bf6e-597ef771f686)

We can now see that we have layers loaded indicated by the various colors on the screen. You can think of this as the heatmap for our geospatial data that you are loading in, but the colors also represent things like classification of data types, like the difference in terrain between a swamp or a hill. 

FORCE DEPLOYMENT

Now that we have a sample project created with our navmesh tiles loaded, let's look at adding some forces to the battlespace. 

Let's start with adding a preloaded template of forces. Look to the right of the screen, you should see the Forces panel for Blue Team and Red Team respectively. Click on Blue Team, then just below it you will see folders. Select the Military Entities Folder and then click on "Auto-Deploy Selection". 

You should see Blue Forces populate on Taiwan, Georgia, and some sustainment in Guam. Now do the same thing but for the Red Team panel, following the same steps. 

![Screenshot 2024-08-26 130948](https://github.com/user-attachments/assets/21f680f7-f519-47f6-82b5-d567a3db9c12)

The forces panel is separated into "Equipment" and "Task Organizations". You can think of equipment as munitions and weapon systems while Task Organizations are the playable entities that you select and give orders too. 

If you click on the dropdown arrow next to the Military Entities tab you can see this displayed.

![Screenshot 2024-08-26 131324](https://github.com/user-attachments/assets/a63c9f11-1bb5-4b86-9388-2c1df275b0ed)

To deploy an entity from this last, it's as easy as clicking and dragging. Find the below vessel and click and drag somewhere on the map to place it there

![Screenshot 2024-08-26 131638](https://github.com/user-attachments/assets/22c5efe8-be95-4066-8725-3373dcf05bb2)

You should now see the USS Dewey wherever you placed it. To delete the entity, select it and press the delete key on your keyboard. To duplicate an entity, you select it and press the D key on your keyboard. It is important to note that currently you can only duplicate entities to place multiple of the same one and cannot keep dragging it out from the forces panel onto the map. 

MOVING FORCES

Issuing movement orders to ground and maritime entities are the same (Air will be covered in its own section). First you must select the ground or maritime entity you want to move and then hold the corresponding hotkey for the type of path you want it to take (Q = Quick, E = Efficient, R = Roads Only, W = Walking Paths). You will then see a path generated in real-time, with a box pop up indicating the distance and time it takes for arrival. While holding the hotkey, once you are satisfied with the final destination, left click and you have confirmed your movement order for the selected entity. 

You can also chain movements by selecting the entity again and making additional movement orders. 

Tip: These pathfinding commands can also be selected from the toolbar on the left edge of the viewport. Currently Maritime entities can only use Q and E hotkeys for movement. 

![Screenshot 2024-08-26 163944](https://github.com/user-attachments/assets/85f1f6c3-1548-4b05-bf08-221083536f3a)

Additional Movement

Attach/Detach 
Entity Task Organization can be modified at runtime utilizing the Attach and Detach commands for Ground type entities. Attaching or Detaching entities will Add or Remove capabilities and combat power proportional to the attached or detached entities contribution. 
Attaching is performed by selecting the ground entity you would like to attach to another force. Right clicking the entity that the selected entity should attach to will allow the use of the Attach command. An attaching entity will move toward the entity it is attaching to until it reaches it, at which point it will become a child of the entity it attached to. 

Detaching is performed by selecting the ground entity you would like to detach from the Composition tab of the Entity Details Panel of the entity it is currently a part of. Right clicking valid terrain will allow the use of the Detach command and will determine the location the detaching entity will move to. 

![image021](https://github.com/user-attachments/assets/90cf1abe-d869-4ed4-aff6-54e4e014b2ab)

Dock/Undock 
Naval type entities can enter and leave entities with subtype Port utilizing the context menu commands Sail Into and Disembark.  
The Sail Into command is available with a Naval type entity selected when right-clicking any entity with subtype Port that has enough capacity for the ship. To fulfill the command the Naval entity moves until it reaches the port and then embeds itself into the port’s Vehicles composition. 
The Disembark command is available when right-clicking valid terrain with a Naval type entity selected from the Composition tab of a Port entity. To fulfill the command, the Naval entity is removed from the Port’s Vehicle Launcher and moves to the location that was right-clicked to open the context menu. 

Tip: Cancelling Assigned Commands 
Any currently active or assigned command can be cancelled by selecting the entity performing or set to perform the command, then pressing the LEFT CTRL key.  



TACTICAL MISSIONS

Tactical Missions are orders given to entities with a predefined set of behaviors applied to them. There are two primary types of Tactical Missions: Area Missions, and Targeted Missions. 
Targeted Missions are easy to assign. Simply select a unit and right click on an enemy to see the possible Tactical Missions that can be performed against that target.
Tip: Anytime a context menu option is unavailable, you can hover the mouse over it for a description of why it’s not possible.

![image023](https://github.com/user-attachments/assets/6e5f9785-a165-473e-b353-ac8c9ffb472a)

Area Missions require a defined area for the entity AI to operate within. In AtomEngine we call these Polygon Regions. To create a Polygon Region, select the Polygon Draw tool from the toolbar on the left edge of the viewport.

![image025](https://github.com/user-attachments/assets/ed4793dd-df2f-463d-9925-6c515e10ef66)

Once you have selected the tool, click anywhere on the globe to add points until you have your desired shape and then click the first point you made to complete the polygon. Now you should see an orange shape on the screen indicating your polygon. Select the entity you want to conduct the tactical mission, then right click the polygon to bring up the context menu. Hover over Tactical Missions and choose the one you want. 
Tip: Right-click with any tool selected to clear it and return to the standard selection tool.

![image027](https://github.com/user-attachments/assets/c34e9ce6-1bee-4683-a750-59c7a3702a82)


Now when you hit play you should see the entity take a few moments to head out and then conduct their tactical mission in the Polygon you have created. You can create multiple Polygons at any time for multiple missions if you want to create complex courses of action with multiple entities. 

AIR DOMAIN 
Air missions can be performed by Squadron entities inside another entity’s Vehicle Launcher (typically an Airbase). The requirements for an entity to be capable of performing an air mission varies from mission to mission. Air missions can only be issued close enough to the issuing location that the assigned aircraft could fly there and back without refueling. (Aerial refueling feature coming soon.) 
You do not need Polygons set up to conduct an air mission. (Air mission integration with custom regions coming soon.)
Mission types and their requirements:
⦁	OCA and DCA Missions can be performed by aircraft equipped with missiles with the subtype AAM.
⦁	Strike and CAS Missions can be performed by aircraft equipped with missiles with the subtypes AGM or GBU.
⦁	Reconnaissance Missions can only be performed by aircraft equipped with a radar .

To create an air mission, first select the airbase the entities are located at, then under the children panel find the squadron you wish to deploy. Left click on them to select them.

![image029](https://github.com/user-attachments/assets/c36ba3b8-8bc2-4e2a-8ef8-7b3250a8940e)

With the squadron selected, right click anywhere on the map to order them on an air mission following the same steps from the Tactical Missions section once you see the context menu. 

![image031](https://github.com/user-attachments/assets/b011ce6a-6b5f-466b-a1e3-d73662b585c2)

ENGAGEMENTS

Combat between entities in AtomEngine happens through Engagements. When an entity with one or more weapons comes within range of an enemy and meets a number of other required conditions such as having line of sight to the target, an engagement is automatically created to that target. 

![image033](https://github.com/user-attachments/assets/8ae0f9e0-44eb-4ea6-9df6-b88d89ab60fa)

As long as an engagement persists, damage is constantly applied to the defending unit every simulated second. The amount of damage inflicted is calculated based on a ratio of relative combat power between the attacker’s weapons and the defender’s resistances.
Tip: Direct fire weapons will create a flat line to the target, while indirect fires will create a parabolic line. The specific weapons participating in the engagement can be seen by hovering over either of these engagement lines.

![image035](https://github.com/user-attachments/assets/8a1c77d4-88f2-4430-b489-e49592003be6)

By default, entities will automatically engage enemies that are detected and within range. To engage a specific unit, follow similar steps to the Tactical Missions section. First select the entity you want to conduct the attack, and then right click on the enemy you wish to engage. Go into the tactical missions menu and select the appropriate action. 

LOGISTICS

Currently AtomEngine operates on automated supply networks consisting of Providers and Requesters. When units hit a designated supply threshold, they will automatically call for sustainment convoys from the nearest supply point which can provide the requested cargo. 

![image037](https://github.com/user-attachments/assets/1f4b76ea-815a-4e8b-8a45-8c423c9c89e5)

A Supply Convoy automatically dispatched to deliver ammunition to the front. Note the cargo displayed in composition tab of the Entity Details Panel on the right.

In order to setup up simple, ground-based supply networks you only need to place down the supply points on the globe where you want them and let the automatic behaviors do the rest for you. 

Cargo can also be transferred manually between two entities. To do this, select a unit and right-click on a nearby friendly unit. From the context menu select Logistics -> Initiate Cargo Transfer. The initiating entity will then move to the targeted entity and open the logistics window.

![image039](https://github.com/user-attachments/assets/79f3eb51-3513-4505-8996-99e510dbb952)

In the Trade Subject portion of the trade window you can select which two entities within their parent units are going to trade cargo. After selecting entities, the Cargo Items section will be populated with all the cargo that each of the two entities is carrying. From here you can choose to send items between entity A and entity B, with information detailing the weight, carrying capacity, and time required for the transfer. When the trade is configured, select Complete Trade and the entities will begin the exchange.

![image041](https://github.com/user-attachments/assets/4ae52d71-5092-44eb-93b2-71594cb58dbf)


BRANCHING SAVES

AtomEngine has the capability to pause the sim and save a branch of the timeline for later execution or during instride wargaming to test different courses of action. Simply pause the simulation at the appropriate time you want to create a branch, go to the bottom left of your screen to the Timeline panel, and click on the Create Branch button.

![image043](https://github.com/user-attachments/assets/037facfd-12ac-40ea-9df0-a698913ed91b)

You can then jump freely between save nodes on either of the displayed timelines and the game state will update accordingly. However if you attempt to load any save node while there are unsaved changes to the game state, the viewport will be dimmed and you’ll be presented with this confirmation popup. 

![image045](https://github.com/user-attachments/assets/1c409b11-da8f-4fb0-ad38-945c4d95da60)

Project files contain all the branches in that project, with all of their individual game states preserved. Loading a project that contains branches will default to showing the Origin and an empty secondary timeline. Selecting the empty secondary timeline title will open the Load Branch window, where you can find and select branches previously created. You can also rename and delete branches from this window. Note that the Origin cannot be renamed or deleted, but it can be deselected in favor of displaying two different branches, if desired.

![image047](https://github.com/user-attachments/assets/85d8bad9-4d2f-4d1f-85de-5638e322cf46)

ENTITIES

Entities are the basic element of every interactive thing in AtomEngine, from battalions and airfields to vehicles and weapons. Every entity is made up of a collection of components, which give it all of its capabilities and relationships to other entities.
Entities can be combined to create complex hierarchical structures. These hierarchies always have a single Root Entity at the top, and can have an unlimited number of children, grandchildren, etc.

![image049](https://github.com/user-attachments/assets/abe6b9da-f501-4f27-9b7d-2ac0d02b678d)

SHUTDOWN PROCEDURE 

As long as the game state has been saved by using the save button on the Timeline panel, you’re free to close the application without losing any data. The application may take some time to fully shut down, but it will eventually.

TIPS

In order to duplicate a unit, press D on your keyboard after you have selected the entity you wish to clone. This is a current work around for needing the same entity in multiple places. 

In order to teleport a unit, Duplicate it and then delete the original. 

POINT OF CONTACT

Point of contact for this documentation and any support will be Kevin Williamson (kevin.williamson@battlerd.com)
