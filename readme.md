# RL x ATC

 - trying to play the game [ATC](https://manpages.debian.org/jessie/bsdgames/atc.6.en.html) with with RL
 - [accompanying youtube playlist](https://youtu.be/OrClhC7IUMM?si=cA6lyDJ9Ve4kT8As)

---

# Work Log (Chronologically Ascending)

# Sunday 10 March 2024 09:10:05 AM IST

## Crude Env Plan init

 - decision making agent that takes in an image of the current state, and returns an action that takes the game state towards prolonging the rewards.
 - will need to define a structured environment for interaction before I do anything
 - have a choice to use the image or the ASCII vector of the characters as the game state.
# Environment Abstract

## Command Domain

For a particular plane, you may:
 - change its altitude
 - change its direction
 - land or take off from an airport
 - exit the airspace at a designated exit space

## Goals 

 - guide planes to their correct destinations
 - prevent collisions between planes (collision if within 1 unit cube of each other)
 - keep the game going as long as possible
 - maximize the number of planes exiting from a given exit space or landing at an airport in a time frame

## Losing conditions

 - plane collision (with walls, ground or other planes)
 - plane runs out of fuel
 - plane exits wrong airspace (or right one with wrong altitude) or lands at wrong airport (or right one at from wrong direction)

# Structuring the environment 

 - ATC (bsd-games) is open source , getting my hands dirty with the source code would allow me to expose functionalities and run the game in a headless manner to build a repository of episodes to train on.
 - first order of business : build an interaction environment in an independent manner
 - checking out the [source code](https://github.com/vattam/BSDGames/tree/master/atc).
 - added as a submodule,
    - pull as `git clone --recursive` if you wish to see the source in this tree itself
