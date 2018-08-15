# ursina    ʕ •ᴥ•ʔゝ□
An easy to use game engine/framework for python.  



## Getting Started
1) Install Python 3.6 or newer
2) Open cmd/terminal and type:

       pip install ursina

Alternatively:
1) Make sure you have git installed.
2) Open cmd/terminal and type:

       pip install panda3d
       pip install screeninfo
       pip install pillow
       pip install git+https://github.com/pokepetter/ursina.git


If you want to easily edit the source, it's recommended to clone the git repo and install as develop like this:

       git clone https://github.com/pokepetter/ursina.git
       python setup.py develop       



## Dependencies
  * python 3.6+
  * panda3d
  
  * screeninfo, for detecting screen resolution
  * pillow, for texture manipulation
  * psd-tools, for converting .psd files
  * blender, for converting .blend files


## Examples
``` python
from ursina import *            # this will import everything we need from ursina with just one line.

app = Ursina()
ground = Entity(
    model = 'cube',
    color = color.magenta,
    z = -.1,
    y = -3,
    origin = (0, .5),
    scale = (50, 1, 10),
    collider = 'box',
    collision = True
    )

app.run()                       # opens a window and starts the game.
```


* [Minecraft Clone](/samples/minecraft_clone.py)

* [Platformer Game](/samples/platformer.py)


## How do I make a game?
Ursina games are made by writing Python code. You can use any text editor you want, but personally I like to use Atom.
1) Create an empty .py file called 'ursina_game.py'
2) Copy this text into your new file:
``` python
from ursina import *                    # this will import everything we need from ursina with just one line.

class Player(Entity):                   # inherits Entity, ursina's 'god class'
    def __init__(self):
        super().__init__()
        self.model = 'cube'             # finds a 3d model by name
        self.color = color.orange
        self.scale_y = 2

    def update(self):               # because Player is an Entity, update gets automatically called by the engine.
        self.x += held_keys['d'] * .1
        self.x -= held_keys['a'] * .1


app = Ursina()
player = Player()
app.run()                               # opens a window and starts the game.
```

3) Type this in the terminal to start the game:

       python ursina_game.py
   If you use Atom, I recommend installing the package atom-python-run to tun your scripts with the press of a button.

4) You can now move the orange box around with 'a' and 'd'!

   To close the window, you can by default, press shift+q or press the red x. to disable this, write 'window.exit_button.enabled =   False' somewhere in your code.

