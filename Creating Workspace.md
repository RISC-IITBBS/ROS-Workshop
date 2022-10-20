# Steps to create a catkin workspace

1. Open up a terminal.

Shortcut: Press CTRL+ALT+T


2. Create the root workspace directory. You can name your directory anything but by ROS convention we will use catkin_ws as the name.
```bash
mkdir -p ~/catkin_ws/src
```
3. Move to the newly created workspace
```bash
cd ~/catkin_ws/src
```
4. Initialize the catkin workspace.
```bash
catkin_init_workspace
```
Look for the statement “Workspace configuration appears valid”, showing that your catkin workspace was created successfully. If you forgot to create the src directory or did not run catkin init from the workspace root (both common mistakes), you’ll get an error message like “WARNING: Source space does not yet exist”.

5. Build the workspace.
Move back to catkin_ws directory either by…
```
cd  ..
```
OR
```
cd ~/catkin_ws
```
6. Finish the creation of the workspace by building it. Note: Build your workspace after every change in C++ scripts. Changes in the Python scripts don’t need rebuilding.
```
catkin_make
```

Now your catkin workspace will have additional directories build, devel.
```
ls
```

Now to make your workspace visible to ROS. Source the setup file in the devel directory.
```bash
source ~/catkin_ws/devel/setup.bash
```
By doing this, all the packages that you create inside the src folder will be visible to ROS.

7. This setup.bash file of your workspace must be the source every time when you want to use ROS packages created inside this workspace.

To save typing, add this to your `.bashrc`,
```
gedit ~/.bashrc
```
Add to the end: `source ~/catkin_ws/devel/setup.bash`

Save and close the editor.
