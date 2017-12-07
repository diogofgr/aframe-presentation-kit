# A-frame Workshop for Beginners

Adapted from the "Official starter slides for giving talks and presentations about A-Frame".
https://github.com/aframevr/aframe-presentation-kit

Here you'll learn how to build a VR scene using A-frame. For this workshop basic understanding of html is recommended but not required.

## Setting Things Up
1. Install Git
2. Install Sublime Text 3 or other text editor
3. Install ` node ` and ` npm `
4. Install ` live-server ` or any other server
```
npm install -g live-server
```
note: On Windows you can use Mongoose
https://cesanta.com/

## Create a Scene

You should only have one ` <a-scene> ` inside each html document.

```
<html>
  <head>
    <script src="https://aframe.io/releases/0.7.0/aframe.min.js"></script>
  </head>
  <body>
    <a-scene>





    </a-scene>
  </body>
</html>
```

## Add an entity with components to your scene

```
<a-box
  position="-1 0.5 -3"
  rotation="0 45 0">
</a-box>
```

In this case ` position ` and ` rotation ` are the *components* of the ` <a-box> ` *entity*.
**Challenge:** add two more components to this entity.

## Build a Street Lamp

Build a simple street lamp using only primitives (box, cylinder, sphere, etc).
Pro-tip: put all your entities inside another entity to make it easier to move, scale, and rotate once you're finished with the design.

```
<a-entity position="0 0 -3" rotation="0 45 0">
  <a-box
    scale="0.1 5 0.1"
    color="gray">
  </a-box>
  <a-box
    scale="0.1 0.1 1.5"
    position="0 2.5 0.75"
    color="gray">
  </a-box>
  <a-box
    scale="0.3 0.1 0.6"
    position="0 2.42 1.3"
    color="gray">
  </a-box>
  <a-sphere scale="0.1 0.1 0.2"
    position="0 2.42 1.3"
    color="yellow">
  <a-sphere>
<a-entity>
```

## Deploy your scene

1. Create a repository on Github, push your local repository and set the *main* branch to be hosted.
2. Push your code to that repository:
```
git add .
git commit -m "my commit message"
git push origin master
```
The **commit message** should contain what you've done since the last commit. This is the first commit so it's common to put **"start repo"**.
Go look at your page, see if everything looks fine.
Now you can continue working on our scene, knowing that everything is looking the way it should.

## Add textures

1. Find an image like this one:
http://texturelib.com/Textures/brick/pavement/brick_pavement_0099_02_preview.jpg
Tip: **get a square image** - it's easier to work with.
2. Save it with a simpler name like `ground.jpg` on the same folder as your project
3. Import it as an asset (all images, 3d models and sounds should be imported like this):
```
(TODO) asset.. etc
```
4. Create a plane for the ground. Make it 40x40 or more. Add the texture that you imported earlier like this:
```
(TODO) plane with texture.
```

## Add 3d models

As you've seen with the street lamp earlier, using primitives can make the code quite lengthy even for simple designs.
Imagine doing a house or a car... you'd have hundreds or thousands of lines of code.
Fortunaely you can import 3d models from other software like Blender, 3dsmax, etc.
1. Find a model that you like on https://poly.google.com/ and import it:

```
(TODO) import model and put it in an entity.
```

2. Adjust the scale until it looks right.

## Add a skybox


(TODO)

## Add some lights

Getting the lights and shadows right is one of the hardest things to do in A-frame.

1. Add a directional light with low intensity to make it look like it's night time.

2. Add a spot light to the street lamp. Play around with the the angle, color and penumbra until you find something you like. **Use the inspector!**

3. Are there any shadows? Do the look right? Read more about shadows here: https://aframe.io/docs/0.7.0/components/shadow.html
Tip: **use the inspector** to work with the shadow properties of your spot light.
(TODO)

4. Deploy your scene again and see if the floor, skybox and 3d model are loaded correctly.

## Add fog and rain

(TODO)
