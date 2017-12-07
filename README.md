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

```html
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

***Go look at your webpage***, see if everything looks fine.

Now you can continue working on our scene, knowing that everything is looking the way it should.

## Add textures

1. Find an image like this one:
http://texturelib.com/Textures/brick/pavement/brick_pavement_0099_02_preview.jpg
Tip: **get a square image** - it's easier to work with.
2. Save it with a simpler name like `ground.jpg` on the same folder as your project
3. Import it as an asset (all images, 3d models and sounds should be imported like this):
```
<a-assets>
  <img id="ground" src="media/img/ground.jpg">
</a-assets>
```
When you need to use these assets you just need to refer to them by their *id*.

4. Create a plane for the ground. Make it 40x40 or more. Add the texture like this:
```
<a-plane src="#ground"></a-plane>
```
Notice we refer to it by doing *#id*.

## Add a 3d model

As you've seen with the street lamp earlier, using primitives can make the code quite lengthy even for simple designs.
Imagine doing a house or a car... you'd have hundreds or thousands of lines of code.
Fortunaely you can import 3d models made with software like Blender, 3dsmax, etc.

1. Find a model that you like on https://poly.google.com/
Look for the models that are downloadable, preferably in OBJ format.
You should get a *.zip* with two files: model-xpto*.obj* and model-xpto*.mtl*

2. Import the files into <a-assets> and put them in an <a-entity>:

```
<a-asset-item id="tree-obj" src="/path/to/tree.obj"></a-asset-item>
<a-asset-item id="tree-mtl" src="/path/to/tree.mtl"></a-asset-item>
```

```
<a-entity
  obj-model="obj: #car-obj; mtl: #car-mtl">
</a-entity>
```

3. Adjust the scale until it looks right.

## Add a skybox

1. Look for *equirectangular* pictures like this one:
https://www.google.pt/search?client=ubuntu&hs=9Y1&channel=fs&dcr=0&tbm=isch&q=equirectangular&spell=1&sa=X&ved=0ahUKEwjVsL-3pvjXAhVK5xoKHQnsBxkQvwUImQEoAA&biw=1708&bih=835&dpr=0.8#imgrc=nJ7brK9YVhC_eM

2. Import it just like you did with the *ground* texture:
```
<a-assets>
  <img id="sky" src="sky.png">
</a-assets>
```

```
<a-sky src="#sky"></a-sky>
```

##Lights

Getting the lights and shadows right is one of the hardest things to do in A-frame. It is also one of the most important things to add depth to a scene.

1. Add an *ambient* light with low intensity to make it look like it's night time.

**Note**: by default the skybox is not affected by the lighting in your scene. To change that you must change the material:
```
<a-sky
  src="#sky"
  material="shader: standard">
</a-sky>
```

2. Add a spot light to the street lamp:
```
 <a-entity light="type:spot"></a-entity>
```

Play around with the rotation, angle, color and penumbra until you find something you like. **Use the inspector!**

## Shadows

Are there any shadows? Do they look right? Read more about shadows here: https://aframe.io/docs/0.7.0/components/shadow.html

1. Add `castShadow: true` to the spotlight:
```
<a-entity light="type:spot; castShadow: true"></a-entity>
```

2. Add the `shadow` component to the objects that receive and cast shadows:
```
<a-entity
  obj-model="obj: #car-obj; mtl: #car-mtl"
  shadow="receive: true">
</a-entity>
```
Tip: **use the inspector** to work with the shadow properties of each entity.

3. Deploy your scene again and see if the floor, skybox and 3d model are loaded correctly.

## Add fog and rain

1. Apply fog to <a-scene>.
Go easy on the fog to help you *mask* the horizon whyle keeping the sky visible; Or go crazy and make a super creepy scene.
Play with color and type to achieve the look you want.
https://aframe.io/docs/0.7.0/components/fog.html

2. Add rain to the scene. Check out how it works here:
https://github.com/takahirox/aframe-rain




