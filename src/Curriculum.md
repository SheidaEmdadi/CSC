
# Curriculum for Teaching CSC
This guide walks teachers through the curriculum of making a multi-user application through CSC.

No prior coding knowledge is required for either of the teacher or the students.
However, for the first time, **teachers** should consult the [Try at Home guide](src\Try-at-Home.md)
to learn about the design and development processes through CSC and CSCDraw. 


<!-- ------------------------------------------------------------------------------------------------------------------------------------------------------- -->
## Table of Contents
- [Downloadable Files](#downloadable-files)
- [Curriculum](#curriculum)
    - [Introduction](#1-introduction)
    - [Play and Design](#2-play-and-design)
    - [Play and Choose (Challenge)](#3-play-and-choose)
    - [Read, Design, and Code](#4-read-design-and-code)
    - [Evaluation (Quiz)](#5-evaluation)


<!-- ------------------------------------------------------------------------------------------------------------------------------------------------------- -->
## Downloadable Files
To teach students how to design and develop multi-user applications through CSC and CSCDraw,
we have prepared a [curriculum package](Curriculum.zip).

In case of facing any troubles with opening the package, please download these files manually:
1. [Lights Game](src\1-LightsGame\LightsGameCSC.json),
2. [Hiking Game](src\2-HikingGame\HikingGame.json),
3. [Party Game](src\3-PartyGame\PartyGame.json),
4. [Rope Game](src\4-RopeGame\RopeGame.json),
5. [Teaching Guide](Curriculum.md).


<!-- ------------------------------------------------------------------------------------------------------------------------------------------------------- -->
## Curriculum
This curriculum is structured into five main steps, each supported by dedicated teaching materials. 
It includes two challenges (in the first and third steps), 
a multiple-choice quiz (in the fifth step), and introductory content.

The intended learning outcome is for students to reach the first three levels of Bloom’s Taxonomy: **Remember**, **Understand**, and **Apply**.

<img src="Graphics\Blooms.png" alt="Bloom's Taxonomy" width="500"/>

Particularly, the [first step](#1-introduction) tries to achieve the *Remember* level,
the [second](#2-play-and-design) and [third](#3-play-and-choose) steps of the study aim to achieve the *Understand*
level,
and the [fourth](#4-read-design-and-code) and [fifth](#5-evaluation) steps try to accomplish the *Apply* level.

These teaching steps are:

<!-- ------------------------------------------------------------------------------------------------------------------------------------------------------- -->
### 1. **Introduction** 

In this step, students should learn how to separate their designs into *local* and *global* portions.
In this regard,
a basic multi-player game, called [Lights Game](src\1-LightsGame\LightsGameCSC.json) 
is used to conceptualize the
private and shared portions of the system. Particularly, in this game, when
a player hovers over a button it will light up only for them (*local*),
and when they click on a button, it will switch ON/OFF
the lights for everybody connected to the server (*global*).
Therefore, the design of this game consists of two global states: *`LightsOFF`*
and *`LightsON`*, and three local states: *`NoHighlight`* (When no button is
being hovered over), *`HighlightONBtn`* (When the TurnONLights button is
being hovered over), *`HighlightOFFBtn`* (When the TurnOFFLights button
is being hovered over).

- You may also switch to the Analogy mode of the CSCDraw to better conceptualize the materials.
In this analogy, our user is Santa who is trying to turn the lights on for everybody in the town.
Each Santa's button click turns into a message (represented by envelops),
transmitted via a pneumatic pipe system.


<!-- ------------------------------------------------------------------------------------------------------------------------------------------------------- -->
#### **Challenge**

This challenge is designed to measure how well students can *remember* the CSC concepts (e.g., local/global portions).


> **🎯 Challenge**  
> Imagine we have a festival and we want to play the music for the whole town. The first facilitator who arrives at the concert hall can turn the speakers ON. Which option describes the scenario best in terms of a CSC?  (The answer is shown in bold.)
>  
> a) The facilitator walking in town is the global portion and the music being played or not is the local portion.  
> **b) The facilitator walking in town is the local portion and the music being played or not is the global portion.**  
> c) The facilitator walking in town and the music being played or not are both local.  
> d) The facilitator walking in town and the music being played or not are both global.




-----------------------------
<!-- ------------------------------------------------------------------------------------------------------------------------------------------------------- -->
### 2. **Play and Design**

To allow students to better *understand* the
CSC concepts introduced in the previous step,
please ask them to design the CSC of a game called *Hiking Game*.
This game consists of seven local states:
`MainStreet`, `Park`, `Jungle`,
`Waterfall`, `Pond`, `Lake`, and `Terminal`
,
and two global states: `Waiting` (for three players
to arrive) and `GatesOpened`.
The player starts from the `MainStreet` and hikes through
other states until they reach the `Terminal`. They should be able to go back
and forth between different states, except for the `Terminal`. 
Terminal gates remain closed until three players finish
the hike and arrive at the Terminal.

This step focuses on improving students' *understanding*, and the measurement
of how well this learning outcome is achieved will be done in [Step 3](#3-play-and-choose). 
In this regard, after students finish their task of drawing the state diagram,
please reveal the [correct solution](src\2-HikingGame\HikingGame.json) and discuss any potential misconceptions.




-----------------------------
<!-- ------------------------------------------------------------------------------------------------------------------------------------------------------- -->
### 3. **Play and Choose**

In this step, students should first play a game
(called [Party]()[Link removed for review]), and then,
they should be asked to choose the exact mapping
CSC of that game out of four different CSCs: 
(Note: the wrong design choices are provided in the [Party Game folder](3-PartyGame).)
- [Design a](3-PartyGame\wrong-party1.json) (❌ Missing synchronizing messages.)
- [Design b](3-PartyGame\wrong-party2.json) (❌ Wrong transition in the global statechart; there should be a way to get from the `waiting` state to the `PartyStarted` instead of from `PartyCancelled`.)
- [**Design c**](src\3-PartyGame\PartyGame.json) (✔ Correct)
- [Design d](3-PartyGame\wrong-party3.json) (❌ The local messages should be connected to the user's channel (they are generated by user interaction.))



This challenge measures how
well students *understood* CSC concepts, namely Local/Global models,
synchronizing messages, conditionals, and interactive design. 
Next, the [correct answer](src\3-PartyGame\PartyGame.json) should be released and any misconceptions
or questions should be discussed.

> **Detailed description of the Party Game**
>
> Each player starts from their home and initially has a hundred dollars. Before going to the `party`, each player can buy a `pizza` ,
a `cake`, or `groceries`, which will cost
fifty, thirty-five, and twenty dollars, respectively. They can also access then `ATM`, from wherever they are, before going to the `BusStop`.
Each time they visit the `ATM`, they withdraw forty dollars. Going to the
`party` requires taking a bus which will cost them fifteen dollars, so they
won’t be able to catch the bus unless they have that money when they arrive
at `BusStop`. If they don’t have the required money they will have to walk back `home`,
and the party will be cancelled. Once a player arrives at the `party room`, they will wait until
two other people join them. The party will start when the
third player arrives at the `party room`.



-----------------------------
<!-- ------------------------------------------------------------------------------------------------------------------------------------------------------- -->
### 4. **Read, Design, and Code**

Prior to the evaluation of how well students
can apply the covered CSC materials in new situations, 
they will have the opportunity to implement a multi-player game themselves.
In this regard, please give them the scenario of the *Rope Game* and ask them to interpret the English context with
respect to CSC concepts.

This task includes designing the CSC of the scenario that students read,
comparing their design with the [revealed solution](src\4-RopeGame\RopeGame.json), 
discussing any potential questions with teachers,
code generation, and compiling the code on our web-based
IDE [link to the IDE is removed for review.]
<!-- (STaBL.Rocks). -->


> **🎯 Rope Game Scenario**
>
> A tour guide is advising a group of adventurers to visit a waterfall:
> "When you leave the `hotel` you will see the `jungle` right in front of you. As
you enter, the first thing that will catch your attention is a beautiful `pond`.
If you look carefully, you will spot a rabbit `burrow` beneath an old oak tree.
That is the only oak tree there, so you will find it easily. By then, you will
probably hear the sound of the `waterfall`. Be careful about the `pit` in your
way, and then you can find the `waterfall`."
>
>The group of friends started their journey and everything happened as
planned, until they arrived at the `burrow`. They heard the sound of the
`waterfall`, and they started approaching, carefully. They were walking gingerly,
and finally, they saw the `pit`. They changed their path to avoid falling
down, but there was a `trap` dug by hunters on the other side. Some of them
fell into the `trap` and the others fell into the `pit` while they were panicking.
Fortunately, the `rope` was still inside the `pit`, so they could climb up and
stand on a big `rock` that was in between the `trap` and the `pit`. Then, they
threw the `rope` into the `pit` to allow the others to get out of that `trap`.
Thereafter, they moved forward to reach the `waterfall`.





-----------------------------
<!-- ------------------------------------------------------------------------------------------------------------------------------------------------------- -->
### 5. **Evaluation:**

A quiz is designed as the final step to evaluate how well
students can use their learned information and *apply* them in solving
new challenges.
This quiz has four multiple-choice questions.
In particular, the first two questions evaluate their ability
to design the statecharts, as well as distinguish the local and global portions
of the app, after interpreting a scenario into a CSC. The third question
evaluates their ability to design the communication of statecharts through
channels. The last question measures their ability to apply changes in the
low-level implementation code.


The quiz questions and their answers (shown in bold font) are as follows:

> **🎯 Quiz**
>
>Read the scenario of a multi-player adventure game called Open the Cave
and answer the questions.
>
> **Cave Game Scenario**
> > A cave’s entrance is frozen because of the polar vortex, and our adventure
pieces of equipment are trapped. We had to leave them behind,
when we received the weather alert. Now, we need a team to gather
wooden sticks to build a fire and melt the ice. At least 150 sticks are
required to start the fire. The sticks can be collected from the jungle.
The team must start from our station, cross the lake, river, and castle,
and then reach the jungle. Each team member can carry up to 5 pieces
of stick each time they visit the jungle. After collecting sticks, they
must pass the old train station and the mountain, before reaching the
cave. Once 150 sticks are gathered, the fire will start and melt the ice.
Once the ice melts, we can retrieve our equipment pieces!
>
> **Questions**
>
>> **Q1**. Consider the CSC of the Open the Cave Game. What are the global
state(s)?
>>
>>a) **Cave Blocked and Cave Opened**
>>
>>b) Cave and Jungle
>>
>>c) Just Jungle
>>
>>d) None of the above
>
>>**Q2**. Which transition can trigger a synchronizing message from the local
statechart to the global statechart?
>>
>>a) Collect Sticks
>>
>>b) **Drop Sticks (in front of the cave)**
>>
>>c) Go to Jungle
>>
>>d) None of the above
>
>>**Q3**. Choose the correct sentence.
>>
>>a) Starting the fire is a local transition.
>>
>>b) Going to the Jungle is a global transition.
>>
>>c) The number of collected sticks is local.
>>
>>d) **The number of collected sticks is global.**
>
>>**Q4**. Which code snippet refers to a correct conditional state in the global
statechart?
>>
>> a) 
>> ```
>>    case globalModel.state of
>>        CaveOpened ->
>>           case globalModel.sticks >= 150 of
>>                False ->
>>                      ({ globalModel | state = CaveOpened }, Cmd.none , Cmd.none )
>>
>>                True ->
>>                      ({ globalModel | state = CaveBlocked }, Cmd.none , Cmd.none )
>>                otherwise ->
>>                      ( globalModel , Cmd.none , Cmd. none )
    
>> **b)** (This is the answer.)
>>```
>>    case globalModel.state of
>>        CaveBlocked ->
>>           case localModel.sticks >= 150 of
>>                False ->
>>                      ({ globalModel | state = CaveBlocked }, Cmd.none , Cmd.none )
>>
>>                True ->
>>                      ({ globalModel | state = CaveOpened }, Cmd.none , Cmd.none )
>>                otherwise ->
>>                      ( globalModel , Cmd.none , Cmd. none )

>> c)
>>```
>>    case globalModel.state of
>>        CaveBlocked ->
>>           case globalModel.sticks >= 150 of
>>                False ->
>>                      ({ globalModel | state = CaveBlocked }, Cmd.none , Cmd.none )
>>
>>                True ->
>>                      ({ globalModel | state = CaveOpened }, Cmd.none , Cmd.none )
>>                otherwise ->
>>                      ( globalModel , Cmd.none , Cmd. none )

>> d) None of the above.