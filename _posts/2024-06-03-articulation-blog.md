# Game Control Code
## Javascript Objects in GameSetup
![image](https://github.com/LiliWuu/lilian-stu-2/assets/142454293/9106fc84-e030-4266-8cad-006f5bb784b0)
We created new javascript game objects within our level in GameSetterGreece.js by storing the objects inside an array called objects. Each object has properties attached to it, like name, id, class, data. These properties help organize information regarding the game objects and store code in separate files. 
Here's our Greece game objects we created based on OOP: 
```ruby
/ Define the GameSetup object literal
const assets = {  
  obstacles: {
    tubeU: { src: "/images/platformer/obstacles/blue-tube-up.png",
    hitbox: { widthPercentage: 0.5, heightPercentage: 0.5},
    width: 300,
    height: 300,
    scaleSize: 100,
    },
    tubeD: { src: "/images/platformer/obstacles/blue-tube.png",
    hitbox: { widthPercentage: 0.5, heightPercentage: 0.5},
    width: 300,
    height: 300,
    scaleSize: 100,
    },
    flag: {
      src: "/images/platformer/obstacles/flag.png",
      hitbox: { widthPercentage: 0.5, heightPercentage: 0.5 },
      width: 300,
      height: 300,
      scaleSize: 120,
    },
  },
  platforms: {
    grass: { src: "/images/platformer/platforms/grass.png" },
    lava: { src: "/images/platformer/platforms/lava.jpg" },
    sandstone: { src: "/images/platformer/platforms/sandstone.png" },
    island: { src: "/images/platformer/platforms/island.png" },
  },
  backgrounds: {
    greece: { src: "/images/platformer/backgrounds/greek.png" },
  },
  transitions: {
    loading: { src: "/images/platformer/transitions/greenscreen.png" },
    hillsEnd: { src: "/images/platformer/transitions/hillsEnd.png" },
    winterEnd: { src: "/images/platformer/transitions/winterEnd.png" },
    greeceEnd: { src: "/images/platformer/transitions/greeceEnd.png" },
    waterEnd: { src: "/images/platformer/transitions/waterEnd.png" },
    quidditchEnd: { src: "/images/platformer/transitions/quidditchEnd.png" },
    miniEnd: { src: "/images/platformer/transitions/miniEnd.png" },
    iceminiEnd: { src: "/images/platformer/transitions/IceMinigameEnd.png"},
  },
  players: {
    knight: {
      src: "/images/platformer/sprites/knight.png",
      width: 128,
      height: 128,
      scaleSize: 120,
      speedRatio: 0.7,
      idle: {
        left: { row: 1, frames: 23 },
        right: { row: 0, frames: 23 },
      },
      walk: {
        left: { row: 7, frames: 20 },
        right: { row: 6, frames: 20 },
      },
      run: {
        left: { row: 5, frames: 23 },
        right: { row: 4, frames: 23 },
      },
      jump: {
        left: { row: 3, frames: 23 },
        right: { row: 2, frames: 23 },
      },
      hitbox: { widthPercentage: 0.3, heightPercentage: 0.8 }
    }, 
  },
  enemies: {
    cerberus: {
      src: "/images/platformer/sprites/cerberus.png",
      width: 103,
      height: 103,
      scaleSize: 80,
      speedRatio: 0.85,
      left: { row: 0, frames: 0, idleFrame: { column: 0, frames: 0 } }, // Left Movement
      idle: { row: 0, frames: 0 }, // Stop the movement 
      right: { row: 0, frames: 0, idleFrame: { column: 0, frames: 0 } }, // Right Movement 
    },
    dragon: {
      src: "/images/platformer/sprites/dragon.png",
      width: 152,
      height: 119,
      scaleSize: 60,
      speedRatio: 0.7,
    },
  }
  };

 // Hills Game Level defintion...
  const objects = [
    // GameObject(s), the order is important to z-index...
    { name: 'greece', id: 'background', class: Background, data: assets.backgrounds.greece },
    { name: 'grass', id: 'platform', class: Platform, data: assets.platforms.grass },
    { name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.2, yPercentage: 0.82 },
    { name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.2368, yPercentage: 0.82 },
    { name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.2736, yPercentage: 0.82 },
    { name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.3104, yPercentage: 0.82 },
    { name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.3472, yPercentage: 0.82 },
    { name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.384, yPercentage: 0.76 },
    { name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.4208, yPercentage: 0.70 },
    { name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.5090, yPercentage: 0.64 },
    //{ name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.5642, yPercentage: 0.34 },
    //{ name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.5274, yPercentage: 0.34 },
    //{ name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.4906, yPercentage: 0.34 },
    { name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.6, yPercentage: 1 },
    { name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.6, yPercentage: 0.94 },
    { name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.6, yPercentage: 0.88 },
    { name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.6, yPercentage: 0.82 },
    { name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.6, yPercentage: 0.76 },
    { name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.6, yPercentage: 0.70 },
    //{ name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.6, yPercentage: 0.64 },
    //{ name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.6, yPercentage: 0.58 },
    //{ name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.6, yPercentage: 0.52 },
    //{ name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.6, yPercentage: 0.46 },
    //{ name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.6, yPercentage: 0.40 },
    { name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.6, yPercentage: 0.34 },
    { name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.6, yPercentage: 0.28 },
    { name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.6, yPercentage: 0.22 },
    { name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.6368, yPercentage: 0.64 },
    //{ name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.6, yPercentage: 0.16 },
    //{ name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.6, yPercentage: 0.1 },
    //{ name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.6, yPercentage: 0.06 },
    { name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.75, yPercentage: 1 },
    { name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.75, yPercentage: 0.94 },
    { name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.75, yPercentage: 0.88 },
    { name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.75, yPercentage: 0.82 },
    { name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.75, yPercentage: 0.76 },
    { name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.75, yPercentage: 0.70 },
    { name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.75, yPercentage: 0.64 },
    { name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.75, yPercentage: 0.58 },
    { name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.75, yPercentage: 0.52 },
    //{ name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.75, yPercentage: 0.46 },
    //{ name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.75, yPercentage: 0.40 },
    //{ name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.75, yPercentage: 0.34 },
    //{ name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.75, yPercentage: 0.28 },
    { name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.75, yPercentage: 0.22 },
    //{ name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.75, yPercentage: 0.16 },
    //{ name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.75, yPercentage: 0.1 },
    //{ name: 'sandstone', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.sandstone, xPercentage: 0.75, yPercentage: 0.06 },
    { name: 'cerberus', id: 'cerberus', class: Cerberus, data: assets.enemies.cerberus, xPercentage: 0.2, minPosition: 0.09, difficulties: ["normal", "hard", "impossible"] },
    { name: 'cerberus', id: 'cerberus', class: Cerberus, data: assets.enemies.cerberus, xPercentage: 0.5, minPosition: 0.3, difficulties: ["normal", "hard", "impossible"] },
    { name: 'cerberus', id: 'cerberus', class: Cerberus, data: assets.enemies.cerberus, xPercentage: 0.7, minPosition: 0.1, difficulties: ["normal", "hard", "impossible"] },//this special name is used for random event 2 to make sure that only one of the Goombas ends the random event
    { name: 'dragon', id: 'dragon', class: Dragon, data: assets.enemies.dragon, xPercentage: 0.5, minPosition: 0.05 },
    { name: 'knight', id: 'player', class: PlayerGreece, data: assets.players.knight },
    { name: 'flyingIsland', id: 'flyingIsland', class: FlyingIsland, data: assets.platforms.island, xPercentage: 0.82, yPercentage: 0.55 },
    { name: 'tubeU', id: 'minifinishline', class: FinishLine, data: assets.obstacles.tubeU, xPercentage: 0.66, yPercentage: 0.9 },
    { name: 'flag', id: 'finishline', class: FinishLine, data: assets.obstacles.flag, xPercentage: 0.875, yPercentage: 0.275 },
    { name: 'hillsEnd', id: 'background', class: BackgroundTransitions, data: assets.transitions.hillsEnd },
    { name: 'lava', id: 'lava', class: Lava, data: assets.platforms.lava, xPercentage: 0, yPercentage: 1 },
  ];
```
The objects variable along with the tag and the assets variable is stored inside the variable, GameSetterGreece, which contains all the code for our level. GameSetterGreece is then passed as one of the arguments into the GameLevelSetup function in GameSetup.js, which handles creating the game levels. This allows our Greece level to be created:
```ruby
const GameSetterGreece = {
    tag: 'Greece',
    assets: assets,
    objects: objects
  };
```
```ruby
// Initialize Game Levels
    function GameLevelSetup(GameSetter, path, callback, passive = false) {
      var gameObjects = new GameSet(GameSetter.assets, GameSetter.objects, path);
      return new GameLevel({ tag: GameSetter.tag, callback: callback, objects: gameObjects.getGameObjects(), passive: passive });
    }

   // code hidden
    GameLevelSetup(GameSetterGreece, this.path, this.playerOffScreenCallBack);
  ```
## Game Level in Game Control
The following code in GameControl handles creating a new level and transitioning. While it's in transition, the existing game objects are destroyed,  the new level is loaded, and the current level is set as the new level, then this.transition is set as false to end the transition code:
```ruby
/**
     * Transitions to a new level. Destroys the current level and loads the new level.
     * @param {Object} newLevel - The new level to transition to.
     */
    async transitionToLevel(newLevel) {
        this.inTransition = true;

        // Destroy existing game objects
        GameEnv.destroy();

        // Load GameLevel objects
        if (GameEnv.currentLevel !== newLevel) {
            GameEnv.claimedCoinIds = [];
        }
        await newLevel.load();
        GameEnv.currentLevel = newLevel;

        // Update invert property
        GameEnv.setInvert();
        
        // Trigger a resize to redraw canvas elements
        window.dispatchEvent(new Event('resize'));

        this.inTransition = false;
    },
```

## GameLoop in GameControl
GameLoop runs the game levels by updating the game environment and handling transitions between levels. It includes GameEnv.update() to update and draw game objects in the current level: 
```ruby
gameLoop() {
        // Turn game loop off during transitions
        if (!this.inTransition) {

            // Get current level
            GameEnv.update();
            const currentLevel = GameEnv.currentLevel;

            // currentLevel is defined
            if (currentLevel) {
                // run the isComplete callback function
                if (currentLevel.isComplete && currentLevel.isComplete()) {
                    const currentIndex = GameEnv.levels.indexOf(currentLevel);
                    // next index is in bounds
                    if (currentIndex !== -1 && currentIndex + 1 < GameEnv.levels.length) {
                        // transition to the next level
                        this.transitionToLevel(GameEnv.levels[currentIndex + 1]);
                    } 
                }
            // currentLevel is null, (ie start or restart game)
            } else {
                // transition to beginning of game
                this.transitionToLevel(GameEnv.levels[0]);
            }
        }

        // recycle gameLoop, aka recursion
        requestAnimationFrame(this.gameLoop.bind(this));  
    },
};
```
## End of Level and Transitioning
The end of a level is determined in the gameLoop method, where it checks whether the current level is complete, then it executes the code that adds 1 to the currentIndex (representing the current level) to transition to the next level. If none of the if statement conditions apply, then the code within the else statement is executed, which takes the player to the first level:
```ruby
// currentLevel is defined
            if (currentLevel) {
                // run the isComplete callback function
                if (currentLevel.isComplete && currentLevel.isComplete()) {
                    const currentIndex = GameEnv.levels.indexOf(currentLevel);
                    // next index is in bounds
                    if (currentIndex !== -1 && currentIndex + 1 < GameEnv.levels.length) {
                        // transition to the next level
                        this.transitionToLevel(GameEnv.levels[currentIndex + 1]);
                    } 
                }
  // currentLevel is null, (ie start or restart game)
            } else {
                // transition to beginning of game
                this.transitionToLevel(GameEnv.levels[0]);
            }
        }

```


## Examining GameObjects through Inspect

https://github.com/LiliWuu/lilian-stu-2/assets/142454293/f2a0e39b-797e-4b7d-88aa-9fd707180195

By selecting the player canvas through inspect, we can see that the the player's canvas properties, like the left and the top, were constantly updating and changing values based on player movement.


# GameObjects Design Using DrawIO
<img width="751" alt="articulation-blog-drawio" src="https://github.com/LiliWuu/lilian-stu-2/assets/142454293/df921ccf-1025-4ce2-8846-1ce441e5ccf2">

# More (My Work)
## Mini Level
![image](https://github.com/LiliWuu/lilian-stu-2/assets/142454293/b9d6e2d9-7d58-4b50-be66-9ab789997620)
We created a new mini level that acts as a level that allows the player to collect coins without getting killed by enemies. We did this by adding new game objects to our Greece mini level in GameSetterGreeceMini.js:
```ruby
const objects = [
    { name: 'mini', id: 'background', class: Background, data: assets.backgrounds.mini },
    { name: 'rockslava', id: 'platform', class: Platform, data: assets.platforms.rockslava },
    // { name: 'rock', id: 'platform', class: Platform, data: assets.platforms.rock },
    { name: 'blocks', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.lava, xPercentage: 0.59, yPercentage: 0.35 },
    { name: 'blocks', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.lava, xPercentage: 0.6268, yPercentage: 0.35 },
    { name: 'blocks', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.lava, xPercentage: 0.3, yPercentage: 0.35 },
    { name: 'blocks', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.lava, xPercentage: 0.3368, yPercentage: 0.35 },

    { name: 'blocks', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.lava, xPercentage: 0.3, yPercentage: 0.85 },
    { name: 'blocks', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.lava, xPercentage: 0.3368, yPercentage: 0.85 },
    { name: 'blocks', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.lava, xPercentage: 0.4684, yPercentage: 0.85 },
    { name: 'blocks', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.lava, xPercentage: 0.6, yPercentage: 0.85 },
    { name: 'blocks', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.lava, xPercentage: 0.6368, yPercentage: 0.85 },
    { name: 'blocks', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.lava, xPercentage: 0.3736, yPercentage: 0.35 },
    { name: 'blocks', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.lava, xPercentage: 0.3736, yPercentage: 0.4334 },
    { name: 'blocks', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.lava, xPercentage: 0.3736, yPercentage: 0.5167 },
    { name: 'blocks', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.lava, xPercentage: 0.3736, yPercentage: 0.6 },
    { name: 'blocks', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.lava, xPercentage: 0.4104, yPercentage: 0.6 },
    { name: 'blocks', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.lava, xPercentage: 0.4472, yPercentage: 0.6 },
    { name: 'blocks', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.lava, xPercentage: 0.484, yPercentage: 0.6 },
    { name: 'blocks', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.lava, xPercentage: 0.5208, yPercentage: 0.6 },
    { name: 'blocks', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.lava, xPercentage: 0.5576, yPercentage: 0.6 },
    { name: 'blocks', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.lava, xPercentage: 0.5576, yPercentage: 0.5167 },
    { name: 'blocks', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.lava, xPercentage: 0.5576, yPercentage: 0.4334 },
    { name: 'blocks', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.lava, xPercentage: 0.5576, yPercentage: 0.35 },

    { name: 'blocks', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.lava, xPercentage: 0.8576, yPercentage: 0.6 },
    { name: 'blocks', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.lava, xPercentage: 0.8576, yPercentage: 0.5167 },
    { name: 'blocks', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.lava, xPercentage: 0.8576, yPercentage: 0.4334 },
    { name: 'blocks', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.lava, xPercentage: 0.8576, yPercentage: 0.35 },

    { name: 'blocks', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.lava, xPercentage: 0.8576, yPercentage: 0.6 },
    { name: 'blocks', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.lava, xPercentage: 0.8208, yPercentage: 0.6 },
    { name: 'blocks', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.lava, xPercentage: 0.784, yPercentage: 0.6 },
    { name: 'blocks', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.lava, xPercentage: 0.7472, yPercentage: 0.6 },
    { name: 'blocks', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.lava, xPercentage: 0.7104, yPercentage: 0.6 },
    { name: 'blocks', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.lava, xPercentage: 0.6736, yPercentage: 0.6 },

    { name: 'blocks', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.lava, xPercentage: 0.1736, yPercentage: 0.35 },
    { name: 'blocks', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.lava, xPercentage: 0.1736, yPercentage: 0.4334 },
    { name: 'blocks', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.lava, xPercentage: 0.1736, yPercentage: 0.5167 },
    { name: 'blocks', id: 'jumpPlatform', class: BlockPlatform, data: assets.platforms.lava, xPercentage: 0.1736, yPercentage: 0.6 },

    { name: 'coin', id: 'coin', class: Coin, data: assets.obstacles.coin, xPercentage: 0.28, yPercentage: 0.25 },
    { name: 'coin', id: 'coin', class: Coin, data: assets.obstacles.coin, xPercentage: 0.32, yPercentage: 0.25 },
    { name: 'coin', id: 'coin', class: Coin, data: assets.obstacles.coin, xPercentage: 0.29, yPercentage: 0.75 },
    { name: 'coin', id: 'coin', class: Coin, data: assets.obstacles.coin, xPercentage: 0.33, yPercentage: 0.75 },
    { name: 'star', id: 'star', class: Star, data: assets.obstacles.star, xPercentage: 0.4584, yPercentage: 0.75 },
    { name: 'coin', id: 'coin', class: Coin, data: assets.obstacles.coin, xPercentage: 0.40, yPercentage: 0.5 },
    { name: 'coin', id: 'coin', class: Coin, data: assets.obstacles.coin, xPercentage: 0.42, yPercentage: 0.5 },
    { name: 'coin', id: 'coin', class: Coin, data: assets.obstacles.coin, xPercentage: 0.44, yPercentage: 0.5 },
    { name: 'coin', id: 'coin', class: Coin, data: assets.obstacles.coin, xPercentage: 0.46, yPercentage: 0.5 },
    { name: 'coin', id: 'coin', class: Coin, data: assets.obstacles.coin, xPercentage: 0.48, yPercentage: 0.5 },
    { name: 'coin', id: 'coin', class: Coin, data: assets.obstacles.coin, xPercentage: 0.5, yPercentage: 0.5 },
    { name: 'coin', id: 'coin', class: Coin, data: assets.obstacles.coin, xPercentage: 0.59, yPercentage: 0.75 },
    { name: 'coin', id: 'coin', class: Coin, data: assets.obstacles.coin, xPercentage: 0.63, yPercentage: 0.75 },
    { name: 'coin', id: 'coin', class: Coin, data: assets.obstacles.coin, xPercentage: 0.58, yPercentage: 0.25 },
    { name: 'coin', id: 'coin', class: Coin, data: assets.obstacles.coin, xPercentage: 0.62, yPercentage: 0.25 },

    { name: 'coin', id: 'coin', class: Coin, data: assets.obstacles.coin, xPercentage: 0.6475, yPercentage: 0.5 },
    { name: 'coin', id: 'coin', class: Coin, data: assets.obstacles.coin, xPercentage: 0.6675, yPercentage: 0.5 },
    { name: 'coin', id: 'coin', class: Coin, data: assets.obstacles.coin, xPercentage: 0.6875, yPercentage: 0.5 },
    { name: 'coin', id: 'coin', class: Coin, data: assets.obstacles.coin, xPercentage: 0.7075, yPercentage: 0.5 },
    { name: 'coin', id: 'coin', class: Coin, data: assets.obstacles.coin, xPercentage: 0.7275, yPercentage: 0.5 },
    { name: 'coin', id: 'coin', class: Coin, data: assets.obstacles.coin, xPercentage: 0.7475, yPercentage: 0.5 },
    { name: 'coin', id: 'coin', class: Coin, data: assets.obstacles.coin, xPercentage: 0.7675, yPercentage: 0.5 },
    { name: 'coin', id: 'coin', class: Coin, data: assets.obstacles.coin, xPercentage: 0.7875, yPercentage: 0.5 },
    { name: 'coin', id: 'coin', class: Coin, data: assets.obstacles.coin, xPercentage: 0.8075, yPercentage: 0.5 },
    { name: 'knight', id: 'player', class: PlayerMini, data: assets.players.knight },
    { name: 'tubeD', id: 'finishline', class: FinishLine, data: assets.obstacles.tubeD, xPercentage: 0, yPercentage: 0.0685 },
    { name: 'tubeU', id: 'finishline', class: FinishLine, data: assets.obstacles.tubeU, xPercentage: 0.85, yPercentage: 0.85 },
    { name: 'greeceEnd', id: 'background', class: BackgroundTransitions,  data: assets.transitions.greeceEnd },
  ];
```
## Tubes
![image](https://github.com/LiliWuu/lilian-stu-2/assets/142454293/e5475f2c-c453-45ec-9bf9-ef6b72e5b280)
The mini level has two tubes, one at the top left corner and the other at the bottom right corner. We created a new property in PlayerMini.js to have the player's y position start at the top of the screen and drop down from where the first tube is. It does this by setting the player y as 0, because the y coordinate increases going downwards. This if statement only executes when the level loads: 
```ruby
constructor(canvas, image, data) {
        super(canvas, image, data);
        const scaledHeight = GameEnv.innerHeight * (100 / 832);
        const finishlineX = .01 * GameEnv.innerWidth;
        this.setX(finishlineX);
        this.hillsStart = true;

        // Goomba variables, deprecate?
        this.timer = false;
        GameEnv.invincible = false; // Player is not invincible 
    }

// code hidden
update(){
            super.update();
        if (this.hillsStart) {
                this.setY(0);
                this.hillsStart = false;
            }
        }
```
