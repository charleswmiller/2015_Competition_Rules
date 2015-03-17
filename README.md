# Defconbots 2015 - Tower Defense - Rules

These are the official rules for the Defconbots 2015, tower defense, competition.

If you have questions or comments about the rules create an issue in this repository.

**These rules are in development and are subject to change but will be finalized by May-2015.**

## Spirit of the Contest

 * Build an autonomous robot with an aiming mechanism and a laser
 * Write software for the robot to accurately aim and shoot the laser at moving and illuminated targets

Robots that go against the spirit of the contest will be disqualified. Examples of this would be a robot that randomly sweeps the laser across the Arena or is secretly remote controlled.

## Robot

### Physical

 * Must fit within 1 x 1 x 1 meter cube
 * Must be easy to move and stage for competition quickly (< 5 minutes)

### Shooting Device

 * One(1) TBD milliwatt Green laser
 * The laser should remain enabled at all times during the wave
 * The laser must be capable of encoding a 4800 baud 8N1 serial signal
 * A laser hit message may be broadcast once every 500 milliseconds
 * No specific laser is required but it is strongly recommended you use the laser used to develop the targets (TBD)
 * If a mirror is used to direct your laser it must not distort your laser beam (cannot be concave or convex)
 * The robot should only emit one laser beam (beam-splitters may be used internally but the robot may not emit multiple beams)

### Software

 * Autonomous (no remote control)
 * Your laser must encode a serial message in the following format:

    [NITT]

Where N is the target number (ascii encoded) '1','2','3','4','5' or the character '*'. And TT is an ID assigned to you at the contest. Target number hit IDs will be addressed below in the "Call Your Shots" section.


# Competition Mechanics

## Arena
 
 * TBD x TBD meters (See conceptual layout http://i.imgur.com/4RzQxc4.png)
 * Ground will be flat-black in color

## Targets

 * 5 targets
 * 5 to 12.5 cm off the ground
 * 12.5 cm apart
 * Three(3) possible speeds: 0 m/s, 0.25 m/s, and 0.33 m/s
 * TBD shape
 * White surface color
 * Illuminated blue (470nm) when active, red (631nm) when stunned, off when dead
 * Targets are numbered 1 to 5, with target #1 being closest to the engine and subsequent targets sequentially numbered

## Waves

 * Each wave starts at a specific point on the track
 * Initially all targets are illuminated and "alive"
 * A "hit" on a target is when a encoded serial laser message is successfully received by the target and verified
 * Once a target is hit (1)illumination on the hit target will transition from blue to red for two(2) seconds and (2) illumination on all other targets will be disabled for two(2) seconds
 * Wave #1 will require one(1) hit on each target
 * Wave #n(where n is the wave number) will require n hits on each target
 * Once n hits have been completed the target illumination will stop until the end of the wave
 * If there is a problem with the track or targets during a wave the event coordinators reserve the right to halt the wave and restart it (we will try our best to never let this happen!)

## "Call Your Shot"

There are two possible ways to send a laser hit message to a target -- with the wild-card('*') or with a specific address ('1' to '5').

### Wild-card Hits

If you decide to use the wild card then you may attempt to hit any target and as soon as the laser hit message registers a hit will be counted, the target will continue to move at normal speed, and the target illumination will cycle normally.

Each wild-card hit will count as **10 points** in your score.

### Addressed Laser Hit Messages (aka Calling Your Shot)

As an extra challenge competitors can choose to aim at specific targets by addressing them in their target hit message. If a target receives a hit that has a target number that matches its target number the hit will count as **15 points**.

## How to win

 * Qualification
   * Contestants are able to qualify on a first-come, first-serve basis
   * Contestants have 10 minutes to set up their robot. When the contestant is ready, the first wave will start
   * If a wave is completed, then the next wave will start. Otherwise the contestant has the ability to tweak their robot and retry the wave
   * After 3 failed waves, the contestants turn is over, and their score will be recorded on a leaderboard
   * If available, contestants are able to try to qualify again at a later time, but people who haven't qualified have first priority
 * Finals
   * After the qualification round is completed, the finals round will start
   * The top 4 contestants in the qualification round proceed to the finals
   * In order from fourth place to first place, each contestant will take a turn in order
   * Contestants have 10 minutes to set up their robot. When the contestant is ready, the first wave will start
   * If a wave is completed, then the next wave will start
   * After a failed wave, their turn is over, and their score will be recorded
 * The final ranking will be determined by the finals times for the people that were in first through fourth, followed by the runners up in order of their qualification score.
