# Portal 2 Workshop - Manual apworld

An Archipelago Manual world played over an endless queue of random Portal 2 Workshop maps.

## What is a Manual game?
A Manual game is a custom game that you've set an item list and location list for so that any game can be included in a multiworld game. You'll manually mark locations checked, and you'll manually restrict what items you use based on the items you've been sent. 



## What does randomization do to this game?
You randomize access to fictional locations represented by the ability to launch a random worshop test chambers
## What is the goal of a Manual game when randomized?
You need to find 5 Mac Guffin represented by 5 Diploma witch allows you to access to the Final Exam, clear its chambers and goal the game.





## How do I install the mod for a Manual game?
You don't. There is no mod. The tasks of marking locations as checked and limiting your items used based on items received is all performed by you (the player) while using the Manual client and its accompanying tracker. See `docs/setup_en.md` for setup instructions.

## What gates what

| Item | What it does |
| --- | --- |
| The four Keys | One key per testing region. `<Region> - Test Chamber #k` needs `k` copies of **that region's** key. |
| The four Clearances | One item each, one region each. `Enrichment Center`, `Glad0s Testing`, `Old Aperture`, `Wheatley Maintenance`. |
| The five Diplomas | Together they open `Final Exam` and its chambers. Clear them, then take the goal. |

## Map

```
                        ┌──────────────────────────────────┐
                        │        RELAXATION VAULT          │  
                        │  Test Chamber #0,                │
                        │  Clear gives a clearance         │
                        │  0FC 0M 3m                       │
                        └─────────────────┬────────────────┘
                                          │
       ┌──────────────┬───────────────────┼──────────────────┬──────────────────┐
       │              │                   │                  │                  │
  Enrichment     Glad0s Testing     Old Aperture      Wheatley Maint.      all 5 Diplomas
Center Clearance   Clearance          Clearance          Clearance         |@Diplomas:5|
       │              │                   │                  │                  │
       v              v                   v                  v                  v
┌────────────┐ ┌──────────────┐  ┌──────────────┐  ┌──────────────────┐  ┌────────────┐
│ ENRICHMENT │ │ PERSONAL     │  │ OLD APERTURE │  │ WHEATLEY'S       │  │ FINAL EXAM │
│ CENTER     │ │ GLAD0S TEST  │  │ ROOMS        │  │ CHAOTIC TESTS    │  │            │
│            │ │              │  │              │  │                  │  │ f chambers │
│ n chambers │ │ n chambers   │  │ n chambers   │  │ n chambers       │  │     then   │
│ 4 FC 2M 2m │ │ 4 FC 2M 2m   │  │ 4 FC 2M 2m   │  │ 4 FC 2M 2m       │  │  the goal  │
└────────────┘ └──────────────┘  └──────────────┘  └──────────────────┘  └────────────┘
  Enrichment      Glad0s          Old Aperture       Wheatley Maint.
  Center Key      Testing Key     Key                Key
  n copies        n copies        n copies           n copies

  FC = First Contact   M = Mastery   m = Milestone
  n  = chamber_count / 4, so 10 each by default, 13 at the maximum, 3 at the minimum
  f  = final_exam_count, 1 by default, 5 at the maximum
```

`Relaxation Vault` represent the tutorial level. It holds exactly one map, `Test Chamber #0`

Completing `Test Chamber #0` is what gets you out. That location is forced to hold a **random Clearance**

## Regions & Locations



| Region | Theme | Opened by | Chambers | First Contact | Mastery | Milestone |
| --- | --- | --- | --- | --- | --- | --- |
| **Enrichment Center** | Portal 1 mechanics | `Enrichment Center Clearance` | `#1 .. #13` | Cube on a Button, Emancipation Grid, Long Fall Boots, 3 Buttons | Purist, Use Gravity | Companion Cube, Chamber Sign Read |
| **Personal Glad0s Test** | Portal 2 early game mechanics | `Glad0s Testing Clearance` | `#1 .. #13` | Reflect Cube, Aerial Faith Plate, Hard Light Bridge, Tractor Beem | Bridge Execution, Laser Yourself | Overgrown Chamber Cleared, GLaDOS Heard |
| **Old Aperture Rooms** | Mechanics found after falling in abandonned aperture | `Old Aperture Clearance` | `#1 .. #13` | Repulsion Gel, Propulsion Gel, Conversion Gel | Gels, Overpaint | Cave Johnson Heard, Pellet to the Face |
| **Wheatley's Chaotic Tests** | Dangerous stuffs | `Wheatley Maintenance Clearance` | `#1 .. #13` | Crushers, Toxic Goo, Turret | Triple Threat, Deathsanity | Weathley Design, Creative Death |
| **Final Exam** | Graduation | all 5 Diplomas | `#1 .. #5` | `Graduation Ceremony`, the goal | | |

At full size that is 52 chambers plus the tutorial map, 3 Tutorial, 14 First Contact, 8 Mastery,
8 Milestone, the Final Exam chambers and the goal: **87 + `final_exam_count` locations**.

See heck References for detail on challenges.

## Items

| Item | Copies | Effect |
| --- | --- | --- |
| `Enrichment Center Key` | chambers in that region | `Enrichment Center - Test Chamber #k` needs `k` of them. Two are in your starting inventory. |
| `Glad0s Testing Key` | chambers in that region | `Personal Glad0s Test - Test Chamber #k` needs `k` of them. Two are in your starting inventory. |
| `Old Aperture Key` | chambers in that region | `Old Aperture Rooms - Test Chamber #k` needs `k` of them. Two are in your starting inventory. |
| `Wheatley Maintenance Key` | chambers in that region | `Wheatley's Chaotic Tests - Test Chamber #k` needs `k` of them. Two are in your starting inventory. |
| Clearances | 5 | Opens one region outright. |
| Diplomas | 5 | Together they open `Final Exam`. |
| `Auto-Win Chamber` | scales | Tick one `Test Chamber` without playing a map. Bail out of a roll you hate. |
| `Re-roll` | scales | Re-roll any map you want. |
| `Force Reset` | scales | **Trap.** Abandon the map you are on and roll a new one. |
| `Cave Johnson Pep Talk` | scales | Nothing. Pure filler. |
| `Lemons` | the remainder | Nothing. When life gives you lemons. |

## Options

The player settings page for this game is located <a href="../player-settings">here</a>. It contains all the options
you need to configure and export a config file.

| Option | Range | Default | Effect |
| --- | --- | --- | --- |
| `chamber_count` | 12 - 52 | 40 | How many `Test Chamber` checks the four testing regions hold, spread evenly with a floor of 3 each. Each region's Key gets one copy per chamber that region holds. |
| `final_exam_count` | 1 - 5 | 1 | How many maps you clear inside the `Final Exam` before the `Graduation Ceremony`. On top of `chamber_count`. |

The tutorial map `#0` and the Final Exam chambers are both on top of `chamber_count`, so a run is
`chamber_count + 1 + final_exam_count` maps.

## Check reference

Unlocking a region opens **all** of its challenges at once. Nothing inside a region gates
anything else inside it.

A challenge counts the first time you meet it, in **any** map you roll. It does not have to be a
map you are completing for a Test Chamber, it does not have to be a map you finish, and it does
not have to belong to the region the challenge is listed under. Roll as many extra maps as you
like hunting one: only Test Chambers care about map count. Every challenge is **not** precomtable.

Three kinds, and the difference matters when you are judging a borderline case:

- **First Contact** - Use a certain mechanic representing the theme of the region
- **Mastery** - A small and often funny challenge using mech and theme of the region
- **Milestone** - Not really a challenge, oftenly force a situation

### Relaxation Vault

Your starting region, always open.

`Relaxation Vault - Test Chamber #0` is the tutorial map, and completing it is what gets you out of here - it
**always holds a Clearance**, any of the four. It costs no Key and it is not part
of `chamber_count`.

| Challenge | How to tick it |
| --- | --- |
| `Relaxation Vault - Test Chamber #0` **(always holds a Clearance)** | Finish the tutorial map. |
| `Tutorial : Open a Door` | Open your first chamber door. Button, lever or scripted, it does not matter. |
| `Tutorial : First Portal Placed` | Place your first portal of the run. |
| `Tutorial : Take the Elevator` | Ride an end-of-chamber elevator. |

### Enrichment Center

| Challenge | How to tick it |
| --- | --- |
| `First Contact : Cube on a Button` | Finish a map whose solution runs through a cube sitting on a floor button. |
| `First Contact : Emancipation Grid` | Destroy an object by pushing it through an emancipation grid then finish the map. |
| `First Contact : Long Fall Boots` | Take a huge fall then finish the map. |
| `First Contact : 3 Buttons` | Press a button 3 times (not a floored one) then finish the map. |
| `Mastery : Purist` | Finish a map that uses no advanced mechanic: cubes, buttons, portals and doors only. |
| `Mastery : Use Gravity` | Propulse yourself in the Test Chamber using portal and gravity. |
| `Milestone : Companion Cube` | Give a cube a name, then destroy it. |
| `Milestone : Chamber Sign Read` | Read the Aperture signage panel that announces the chamber's mechanics. |

### Personal Glad0s Test

| Challenge | How to tick it |
| --- | --- |
| `First Contact : Reflect Cube` | Finish a map that uses a reflect cube on a laser |
| `First Contact : Aerial Faith Plate` | Finish a map that uses a faith plate. |
| `First Contact : Hard Light Bridge` | Finish a map that uses a light bridge. |
| `First Contact : Tractor Beem` | Finish a map that uses a Tractor Beem. |
| `Mastery : Bridge Execution` | Destroy something (cube, ball, turret) using a bridge (either push or disable to make them fall) |
| `Mastery : Laser Yourself` | Send the laser through a portal and take it in the face. On purpose. |
| `Milestone : Overgrown Chamber Cleared` | Finish a ruined map, overgrown or visibly abandoned. |
| `Milestone : GLaDOS Heard` | Get commented on by GLaDOS during a test. |

### Old Aperture Rooms

| Challenge | How to tick it |
| --- | --- |
| `First Contact : Repulsion Gel` | Finish a map that uses blue gel. |
| `First Contact : Propulsion Gel` | Finish a map that uses orange gel. |
| `First Contact : Conversion Gel` | Finish a map that uses white gel. |
| `Mastery : Gels` | Finish a map that uses two different gels. Cleansing gel does not count as one of the two. |
| `Mastery : Overpaint` | Paint far more surface than the puzzle asks for, well past what you need. |
| `Milestone : Cave Johnson Heard` | Listen to a Cave Johnson recording. |
| `Milestone : Pellet to the Face` | Take an energy pellet in the face. |

### Wheatley's Chaotic Tests

| Challenge | How to tick it |
| --- | --- |
| `First Contact : Crushers` | Finish a map that uses crushers or lethal pistons. |
| `First Contact : Toxic Goo` | Finish a map where the goo is a real hazard, not scenery under a walkway. |
| `First Contact : Turret` | Take out an active turret, or escape it and finish the map. |
| `Mastery : Triple Threat` | Finish a map that uses three distinct stuff that wants to kill you. |
| `Mastery : Deathsanity` | Die by falling, turrets and crushed |
| `Milestone : Weathley Design` | Finish a map designed by Wheatley: low effort or ugly looking. |
| `Milestone : Creative Death` | Die by combining two mechanics. |


### Final Exam

*Graduation.* Opens with all five Diplomas: `Aperture Gel Mastery`, `Portal Gun Expert`,
`Laser Redirection Master`, `Turret Evasion Diploma`, `Trivia Cube Champion`.

The exam chambers need no Key - the Diplomas are the whole gate. They are ordinary rolled maps,
`final_exam_count` of them, and you play them before you graduate.

| Challenge | Requirement |
| --- | --- |
| `Final Exam - Test Chamber #1 .. #f` | Roll and finish a map, once per exam chamber. `f` is `final_exam_count`. |
| `Graduation Ceremony` | Clear every Final Exam chamber. This is the goal. |