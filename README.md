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
Pro-tip: put all your entities inside another entity to make it easier to move, scale, and rotate once your finished with the desing.

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

(TODO)

## Add textures

(TODO)

## Add 3d models

(TODO)

## Add a skybox

(TODO)

## Add some lights

(TODO)

