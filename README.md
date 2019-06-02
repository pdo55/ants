# ants
AntsVersusSomebees game

## Core concepts
- The Colony. This is where the game takes place. The colony consists of several places that are chained together to form a tunnel where bees can travel through. The colony has some quantity of food that can be expended to deploy ant troops.

- Places. A place links to another place to form a tunnel. The player can place a single ant into each place. However, there can be many bees in a single place.

- The Hive. This is the place where bees originate. Bees exit the hive to enter the ant colony.

- Ants. Ants are the usable troops in the game that the player places into the colony. Each type of ant takes a different action and requires a different amount of food to place. The two most basic ant types are the HarvesterAnt, which adds one food to the colony during each turn, and the ThrowerAnt, which throws a leaf at a bee each turn. You will be implementing many more.

- Bees. Bees are the antagonistic troops in the game that the player must defend the colony from. Each turn, a bee either advances to the next place in the tunnel if no ant is in its way, or it stings the ant in its way. Bees win when at least one bee reaches the end of a tunnel.

- Queen Ant: There is one queen ant in the whole colony. She is able to attack bees but she also has a special ability of fortifying the other ant troops. Bees can also win if they destroy the queen ant.

## Different kinds of ants
### Offensive ants

- ThrowerAnt is a great offensive unit, but it'd be nice to have a cheaper unit that can throw.
![img](https://inst.eecs.berkeley.edu/~cs61a/su18/proj/ants/assets/insects/ant_shortthrower.gif)

The LongThrower can only throw_at a Bee that is found after following at least 5 entrance transitions. It cannot hit Bees that are in the same Place as it or the first 4 Places in front of it. If there are two Bees, one too close to the LongThrower and the other within its range, the LongThrower should throw past the closer Bee, instead targeting the farther one, which is within its range.

![img](https://inst.eecs.berkeley.edu/~cs61a/su18/proj/ants/assets/insects/ant_longthrower.gif)

The ShortThrower can only throw_at a Bee that is found after following at most 3 entrance transitions. It cannot throw at any ants further than 3 Places in front of it.

![img](https://inst.eecs.berkeley.edu/~cs61a/su18/proj/ants/assets/insects/ant_fire.gif)

- FireAnt damages all the bees in the same place as itself when it dies

![img](https://inst.eecs.berkeley.edu/~cs61a/su18/proj/ants/assets/insects/ant_hungry.gif)

- HungryAnt selects a random Bee from its place and eat it whole. After eating a Bee, it must spend 3 turns digesting before eating again. If there is no bee available to eat, it will do nothing.

![img](https://inst.eecs.berkeley.edu/~cs61a/su18/proj/ants/assets/insects/ant_ninja.gif)

- NinjaAnt damages all Bees that pass by, but can never be stung. A NinjaAnt does not block the path of a Bee that flies by.

### Defensive ants

![img](https://inst.eecs.berkeley.edu/~cs61a/su18/proj/ants/assets/insects/ant_wall.gif)

- WallAnt is an ant that does nothing each turn. It is useful because it has a large armor value.

![img](https://inst.eecs.berkeley.edu/~cs61a/su18/proj/ants/assets/insects/ant_bodyguard.gif)
- BodyguardAnt differs from a normal ant because it is a container; it can contain another ant and protect it, all in one place. When a Bee stings the ant in a Place where one ant contains another, only the container is damaged. The ant inside the container can still perform its original action. If the container perishes, the contained ant still remains in the place (and can then be damaged).

![img](https://inst.eecs.berkeley.edu/~cs61a/su18/proj/ants/assets/insects/ant_tank.gif)

- TankAnt is a container that protects an ant in its place and also deals 1 damage to all bees in its place each turn.

# How to start the GUI
-optional arguments:

  -h, --help     show this help message and exit
  
  -d DIFFICULTY  sets difficulty of game (test/easy/medium/hard/extra-hard)
  
  -w, --water    loads a full layout with water
  
  --food FOOD    number of food to start with when testing
```
python3 gui.py [-h] [-d DIFFICULTY] [-w] [--food FOOD]
```

(source: cs61a summer 2018)
