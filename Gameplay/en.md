# Quaver Gameplay

This section explains the different parts of gameplay within Quaver. It gives a synopsis of how the game is played, its scoring, rating, and grading systems, and much more!

## Game Mode: Keys

<p align="center">
  <img src="https://i.imgur.com/F93JRWw.png" width="409px" height="230px">
</p>


Quaver is built to support multiple game modes, but the main focus of the game is the Keys game mode. The concept of this game mode has been used in a variety of different rhythm games such as Beatmania, Dance Dance Revolution, and osu!.

The concept of the game mode is simple - notes fall down from the screen (or up depending on scroll direction), and the objective is to press the correct key at the correct time. 

Quaver has both 4 Keys (4K) and 7 Keys (7K) which are treated as two game modes and have separate leaderboards.

The game also has the potential to be skinned and played with upwards scrolling - which ultimately makes the game able to look and feel like a majority of different rhythm games. It has support for colored arrow skins (DDR), or bar skins (Beatmania-styled).

### Scoring Systems

This section explains the different types of scoring and grading systems Quaver has.

#### Grading

This section outlines the accuracy percentage that is needed to achieve each grade.

| Grade | Accuracy%                                                  |
|-------|------------------------------------------------------------|
| X     | 100% (Only achievable by getting all Marvelous judgements) |
| S+    | 99% Accuracy                                         |
| S     | 95-98% Accuracy                                         |
| A     | 90-94% Accuracy                                         |
| B     | 80-89% Accuracy                                         |
| C     | 70-79% Accuracy                                         |
| D     | 60-69% Accuracy                                         |
| F     | Failed                                      |

#### Accuracy

Accuracy is a weighted average of received judgements out of the sum of judgements throughout a play.

You receive one judgement per regular note and two judgements for a long note (press and release).

| Judgement | Weighting                                            |
|-------|------------------------------------------------------------|
|  Marvelous    | 100% |
|  Perfect    | 98.25% |
|  Great    | 65% |
|  Good    | 25% |
|  Okay    | -100% |
|  Miss   | -50% |

#### Performance Rating

Your performance rating is an assessment of your performance throughout a given play in correlation to the map's difficulty rating. It is the same metric that is used to measure scores in global rankings.

The formula is relatively simple with it being:

`DifficultyRating * Math.Pow(Accuracy / 98, 6);`

#### Overall Rating

Your overall rating is a weighted sum of all your plays in the Keys (4K or 7K) game mode. 4K and 7K are separate and have two different leaderboards for them.

Only your top score will account for the full amount of performance rating, and it will decrease will each lower score.

The weighted sum calculation is similar to Performance Points, used in the rhythm game osu!.

`overall = performanceRating[1] * 95^0 + performanceRating[2] * 95^1 + performanceRating[3] * 95^2 + ...`

#### Score

Score is another measurement of your performance throughout a play in Quaver. It is mainly a measurement of how frequently you are able to combo in correlation to the judgements received. It isn't used in any metric for global rankings and is purely in the game as a form of "XP." Score is capped at 1 million points per play.

#### Judgement Timing Windows

This section explains the judgement windows that are used within Quaver. It details the time in milliseconds needed to press a key for a note in order to receive it. Currently there is one standard judgement timing window in Quaver, however this may change in the future.

| Judgement | Window                                  |
|-------|------------------------------------------------------------|
|  Marvelous    | ±18ms |
|  Perfect    | ±43ms |
|  Great    | ±76ms |
|  Good    | ±106ms |
|  Okay    | ±127ms |
|  Miss   | ±164ms |

Players can change between different judgement windows and create custom ones from the game modifiers. 

#### Combo

Combo is when you successfully hit objects without missing. 

* Not pressing an object within its judgement timing windows will result in a Miss, restting your combo.
* Pressing an object too early (164ms) will result in a Miss, resetting your combo.
* Not releasing a long note will result in a Good, which does not reset your combo.

### Modifiers

You can customize several aspects of gameplay with game modifiers (mods). Modifiers divide into two categories, ranked and unranked.

#### Ranked Modifiers

Scores submitted with any of these modifiers enabled are eligible for global rankings.

* • **Speed** (rate) - Change the audio playback rate of song between 0.5x and 2x, in intervals of 0.05. Difficulty rating scales with each rate.
* • **Judgement Windows** - Change between different judgement windows and create custom ones.
* • **Mirror** - Flips the map horizontally.

#### Unranked Modifiers

Scores submitted with any of these modifiers enabled are not eligible for global rankings. However, scores will save on local leaderboards.

* • **Autoplay** - Watch perfect replay of the map.
* • **Co-op** - Creates second playfiled for you to play the map with your friends! You can configure the keybinds of second player in the Options menu.
* • **No Fail** - The play doesn't end even if your HP reaches 0.
* • **No Scroll Velocities** - Play the map without any changes in the scroll speed.
* • **No Long Notes** - All long notes are converted to regulare notes.
* • **Full Long Notes** - All notes are converted to long notes. The gap between release and next note press is fixed to 1/4 snap.
* • **Inverse** - All long notes are converted to regular notes while all regular notes are converted to long notes.
* • **Randomize** - Mixes up the the order of lanes.

### Skins

You can completely customize the game to your liking. [See the Skins/Keys section of the wiki](/Skins/Keys).
