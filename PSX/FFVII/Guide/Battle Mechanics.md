THE FF7 BATTLE MECHANICS v1.10
======================== =====

by Terence Fergusson <tf_faq@btinternet.com>

Final Fantasy 7 Copyright 1997, 1998 Square Co., Ltd.  Final Fantasy and
Squaresoft are registered trademarks of Square Co., Ltd.

This document is entirely my work, and was written and is owned by me,
Terence Fergusson.  All copyrights and trademarks are acknowledged where not
specifically mentioned.  If you wish to reproduce this document AS IS, you
may do so without having to ask my permission, providing that the entire
document including this copyright notice is left intact, preferably in ASCII
text format, and is done so for non-profit purposes.  I do, however, reserve
the right to revoke permission and ask for it to be taken down should I feel
it necessary.



-----------------------------------------------------------------------------
VERSION HISTORY
---------------

v0.80 : 23/03/02 : Original Release - Not accompanied by sister guides
v1.10 : 29/06/09 : Rewrote entire sections of the guide, bringing it up to
                     date with its sisters.  All three guides are finally in
                     synch


-----------------------------------------------------------------------------
FOREWORD
--------

These guides have been a long time in the making.

It started with a webpage.  Just a small private one that I created early
in April 1999.  It was more practice than anything else, and I put up most
of my findings about the game at that time.  Most of it was inaccurate or
incorrect, but I had some basics down.

I changed to pure text format soon after when I realised that a webpage was
very difficult to update with the number of tables such a Mechanics document
requires.  Pure text is also a lot easier to simply add stuff to.  Updates
can be made in seconds.

But this was still a private thing.  It's been private for years, in fact.
But that's not to say it wasn't added to or the information wasn't utilised.

During this time, I met many people who shared the same fascination that I
had with the subject.  We helped each other too; some of the information
included here is due to information that was pointed out to me in the memory
dumps.  I learned from it, I progressed.  And the guide grew.


After a while, it became more and more apparent that this kind of information
was not only useful, but also in demand.  True, it doesn't help the average
player, whose only concern is to get from A to B without too much trouble and
just having fun along the way... but to others, it's fun to learn how the
game works, and exactly what makes the monsters they fight tick.


And so, I compiled the Battle Mechanics guide, which was later joined by
two companion guides to cover specific parts of FF7's battle system.

This process alone took several years of on and off work.  Part of this was
due to the enormity of the task, but other delays were due to tiredness,
distractions, and sometimes the difficulty and incovenience of continually
working with the PC version of FF7 this long after its release.


For what its worth, this update has been sitting at about 90% complete for
the last two to three years, and only recently did I finally gain the
motivation to put together the finishing touches.  So this isn't the result
of five years work.  I apologise for how long it's taken to get this far.
But I do hope you'll be pleased with what *has* been added.

It's been over ten years since I first started exploring the mechanics of
this game.  You *can* still learn new things about old games.


If you have further questions about the guide, I would ask that you please
direct your questions to the FF7 board on GameFAQs, where I sometimes can be
found.  And even if I can't, there are others there who will most likely be
able to help you far faster than e-mailing me would.  Another good place to
ask would be at Qhimm's Forum (http://forums.qhimm.com), who have done a
large amount of work in figuring out and modifying FF7's inner workings.

If there are some parts you don't quite understand, don't worry!  It's very
difficult to make some of the more intricate parts of FF7's systems
understandable, especially given some of the rather arcane (and bugged) ways
it does stuff.  Instead, try to focus on the parts you do understand, and
see how it all gels together.  The term definitions and damage formulas are
good places to start, and from there, you can go over the Party and Enemy
Mechanics guides, which are more useful to the average player.

Also, fair warning: I've tried to get rid of the many mistakes that littered
the original version of this guide, but FF7 is, as I mentioned prior, rather
arcane in its workings.  I may have misunderstood something, or forgotten to
change a formula, or simply mistyped something.  In other words, there may be
errors yet that I've missed or unintentionally let slip in.  If something
*does* look suspicious, then please feel free to ask about it on the GameFAQs
message board.

Above all else, please have fun, and enjoy putting the knowledge to good use.



-----------------------------------------------------------------------------
COMPONENT GUIDES
----------------

The FF7 Game Mechanics Guides are split into three files.  This guide, the
first, will detail the basic formulas, terms and statuses used in battle.
The other two are:

  The FF7 Party Mechanics:
    Covers the various battle data relating to the party, notably data
  regarding spell stats, materia use, and limit breaks.

  The FF7 Enemy Mechanics:
    A list of enemies focusing on their attacks and attributes, and how the
  damage from those attacks are factored into the battle mechanics formulas.


The FF7 Battle Mechanics is the main one to start with, since it will define
many terms and formulas that will be referenced in both Party and Enemy
Mechanics.

Note that this guide is based on the PC version.  While most alleged
gameplay differences between the PC and PSX versions have been proven false,
more may exist.


-----------------------------------------------------------------------------
CONTENTS
--------

1.  Definitions
1.1   Character Stats
1.2   Special Term Definitions
1.2.1   Basic Terms
1.2.2   Types of Attack
1.2.3   Formula Types
1.2.4   Target Types
1.2.5   Equipment Modifiers
1.2.6   Mathematical Terminology
2.  Time
2.1   Battle Speed
2.2   The Global Timer
2.3   The V-Timer
2.4   The C-Timer
2.5   The Turn Timer
2.6   Timer Interaction
2.7   Escaping Battles
3.  Battle Damage
3.1   Setup
3.2   Status and Elemental Resistance
3.3   Hit Chance
3.3.1   Physical
3.3.2   Magical
3.3.3   Critical
3.3.4   Status
3.4   Formula Types
3.4.1   Physical
3.4.2   Magical
3.4.3   Cure
3.4.4   Item
3.4.5   Other Formulas
3.4.6   Formula Modifiers
3.5   Lucky 7s
3.6   Final Checks
4.  Statuses
4.1   Status Attributes
4.2   Special Notes On Statuses
5.  Game Over
6.  Credits


-----------------------------------------------------------------------------
1. DEFINITIONS
--------------

---  ---------------
1.1  Character Stats
---  ---------------
There are seven Primary Stats and seven Derived Stats that make up your
basic character.  The Primary Stats are:
  Str: Strength           Dex: Dexterity
  Vit: Vitality           Mag: Magic
  Spr: Spirit             Lck: Luck
  Lvl: Level

The Derived Stats are:
  Att: Attack             At%: Attack%
  Def: Defense            Df%: Defense%
  MAt: Magic atk          MDf: Magic def
  MD%: Magic def%


The Primary Stats dictate the overall strengths of your character.  Level
dictates exactly how powerful the character is, while the last six stats
round off the character.  Each character has a starting value for their
Primary Stats, and every level, there is a chance that these stats will
be raised by a random number of points.  In addition, it's possible to
further raise these stats permenantly using Sources.


The Derived Stats are based from your Primary Stats and your currently worn
equipment.  They are derived as such:
  Att =  Str      + Weapon Attack Bonus
  At% =             Weapon Attack% Bonus
  Def =  Vit      + Armour Defense Bonus
  Df% = [Dex / 4] + Armour Defense% Bonus
  MAt =  Mag
  MDf =  Spr      + Armour MDefense Bonus
  MD% =             Armour MDefense% Bonus


Your Derived Stats, along with a few of the Primary Stats (mostly Level,
Dexterity and Luck), are what's used in every battle to determine battle
damage, spell strength, and so on.

NOTE: There is a bug in FF7 such that Armour MDefense Bonus is *not* added
to Magic Def.  This is reflected in many places, including the Status screen
(but the bonus you are supposed to get is visible in the Equip screen).  To
my knowledge, it is definitely evident in both the PC version and the PSX
version.  You will take the same amount of magic damage regardless of your
Armour's MDefense rating.


In addition to the above, many pieces of armour, weaponry and accessories
will give you special bonuses to your Primary Stats which, in turn, affect
your Derived Stats.  You can only see these bonuses in effect on the Status
screen though, not on the Equip screen.  These bonuses are factored into
battle, however.

The stats have the following main effects:

  Att: Calculated from your Str and equipment.  Dictates the strength of
       Physical attacks using either the Physical, Magical or Cure Formulas.
       The higher this is, the more damage you will do with those type of
       attacks.

  MAt: Calculated from your Mag and equipment.  Dictates the strength of
       Magical attacks using either the Physical, Magical or Cure Formulas.
       The higher this is, the more damage you will do with those type of
       attacks.

  Def: Calculated from your Vit and equipment.  Reduces the damage you take
       from Physical attacks that use either the Physical, Magic or Item
       Formulas.  The higher it is, the less damage you take.  At 255 Def,
       you will take about half damage from Physical attacks as compared to
       0 Def.

  MDf: Calculated from your Spr and equipment.  Reduces the damage you take
       from Magical attacks that use either the Physical, Magic or Item
       Formulas.  The higher it is, the less damage you take.  At 255 MDf,
       you will take about half damage from Magical attacks as compared to 0
       MDf.  Note that a bug exists that causes the MDf of all armor to not
       be counted.

  At%: Based on your equipment only.  This is the chance you have of hitting
       with your current weapon.  Non-weapon abilities have their own unique
       At%.  The higher it is, the higher the chance you have of hitting.
       Certain abilities and statuses may raise or lower this value.

  Df%: Calculated from your Dex and equipment.  This is the chance you have
       of evading a Physical attack.  The higher it is, the less chance you
       have of being hit with evadable Physical attacks.  It is also used as
       a factor to improve your chance to hit with Physical attacks.

  MD%: Based on your equipment only.  This is the chance you have of evading
       a Magical attack.  The higher it is, the less chance you have of being
       hit with evadable Magical attacks.

  Dex: Primary Stat Value.  Affects the rate your Turn Timer increases.
       Higher Dex also affects both your accuracy and chance to evade with
       Physical attacks.

  Lck: Primary Stat Value.  Affects the chances of earning Lucky Hits (100%
       chance to hit a target with a standard Physical attack), Lucky Evades
       (100% chance to evade an evadable Physical attack - doesn't work
       against Lucky Hits) and Critical Hits (double damage used with most
       Physical attacks).

  Lvl: Primary Stat Value.  Increases the effect of almost everything you do.
       Helps improve your physical damage, magical damage, chance to hit with
       magical attacks, chance to land critical hits, chance to steal, chance
       to manipulate, etc.  Also affects your current stat growth and the
       effect of certain attacks.


From now on, the three letter abbreviations next to each Stat will be used
instead of their full names.



---  ------------------------
1.2  Special Term Definitions
---  ------------------------
The following terms will be used throughout the Game Mechanics guides.

1.2.1 Basic Terms
----- -----------
Base Damage:
  This is a special term which means the basic power of most basic types of
attack.  For physical attacks, Base Damage is dependent on Att and Lvl.  For
magical attacks, it is dependent on MAt and Lvl.  Most attacks will use Base
Damage to determine the damage they do.  In ability formulas, this will be
listed as Base.



Power:
  The next most important stat, this determines how strong an ability is.
Power is an integer given to almost all standard abilities that can affect HP
or MP in some way, and the higher it is, the stronger the effect.  In the
Party and Enemy Mechanics Guides, Power will be expressed in its fully
calculated form depending on the Formula used (see below): for example, a
Power of 16 for the Physical Formula would be a 1x Base damage attack.  In
all cases where a formula is being stated, however, the integer version of
Power will be used for greater accuracy.

  Please see Section 3.4 for details on how Power is converted under the
various formulas.
 


NRV:
  Short for No Random Variation, this means that the attack will not vary in
power according to a random factor.  Note that Random Variation is only used
with the Physical, Magical, Cure and Item Formulas - all others are
automatically considered to have no Random Variation.



Caster/Attacker:
  The character that used the ability.  Also known as the source of the
attack's effect.



Target:
  The character that is affected by the ability.



Before Damage Effect:
  This term is applied to certain effects that take place immediately before
the standard damage procedure for a target is looked at.  These sort of
effects usually adjust the Power of the ability, which can cause a change in
damage.  You will notice that all the Ultimate Weapons use a Before Damage
Effect in precisely this manner, which allows them to adjust the strength of
your attack before damage is calculated.



After Damage Effect:
  This term is applied to certain effects that take place immediately *after*
the standard damage formulas.  In virtually all cases, it ends up adjusting
the final damage total, usually by multiplying it by some amount depending
on certain factors.



Element:
  Some abilities will use a special Element that will determine certain
factors about the attack.  Most enemies will have certain elemental
weaknesses and strengths; this factor will determine whether the attack will
do extra damage or be defended against.  For example, an attack described as
a 'Elm: Fire' attack will do Fire Elemental damage.

  Note that FF7 uses the following common Elements:
    Fire, Ice, Lightning, Earth, Poison, Gravity, Water, Wind, Holy,
    Restorative.

  The absence of any Element is termed Non-Element, which, while not
technically an element in itself, will be used to denote this state.

  Also note that there are five more Elements that tend to apply only to
Physical Attacks.  While FF7 is aware of them, they are not normally utilised
in Elemental calculations because almost nothing is weak or defends against
them:
    Cut, Hit, Punch, Shoot, Shout.

  And finally, there is a 16th Hidden Element that was obviously supposed to
have been dummied out, but due to sloppy coding, has ended up having
unexpected effects with the Elemental Materia and certain attacks.

  Of the above Elements, Restorative, Cut, Hit, Punch, Shoot, Shout and
Hidden are not made known to the player.  They can be described as follows:

  Restorative :- See below for the definition of Restore.  Restorative is the
    difference between the Cure and Life series of spells which give back HP,
    and the Holy Elemental attack spells like Alexander, which cause Holy
    Element damage.  While Undead are often said to be Weak to Holy, they
    *Absorb* Restorative instead.
  Cut :- Used to describe an attack that uses an edged weapon.
  Hit :- Used to describe an attack that uses a blunt weapon.
  Punch :- Used to describe an attack that uses a piercing weapon.
  Shoot :- Used to describe attacks that use projectile weapons.
  Shout :- Used to describe attacks that are sonic or energy-based in nature.
  Hidden :- Unknown.  Unlike the others, Hidden is the name I've given it.
            Very few attacks have this element.  Any that do can be protected
            against by linking any non-Element Materia with the Elemental
            Materia in a character's armour.



Berserk Attack:
  This term will show up often in the Enemy Mechanics Guide.  If an enemy is
under the status effect Berserk, it will ignore its AI script and will
instead use its designated Berserk Attack.  This will be listed under the
Attributes section of one of the attacks listed in its Attack List.  Note
that there are a number of enemies who are not immune to Berserk but do *NOT*
have a designated Berserk Attack.  This causes a bug where the monster will
try to use an attack that does not exist.  This attack costs a phenomenal
amount of MP, and the monster will fail to use it and give an "Out of Skill
Power" message instead.  This is fortunate, since a successful use of this
particular ability would crash the game.



1.2.2  Types of Attack
-----  ---------------
When an attack type is given, the following terms will be used to describe
them.  These are the most common terms; unique terms will be described
within the notes for the appropriate ability itself.


Physical:
  Any attack termed as Physical will use Att and Def as the primary damage
calculating stats, and is affected by Barrier.  It will also normally use the
Physical Formula for Base Damage, unless noted otherwise.



Magical:
  Any attack termed as Magical will use MAt and MDf as the primary damage
calculating stats, and is affected by MBarrier.  It will also normally use
the Magical Formula for Base Damage, unless noted otherwise.



Piercing:
  This means that the attack will ignore the target's Def and MDf stats when
determining how much damage it will do to them.  Def and MDf are only
factored into the Physical, Magical and Item Formulas normally, so only
attacks that use these formulas will actually be marked Piercing.  All other
formulas will not be marked since they're already considered Piercing.



Attack:
  Any attack with this modifier will cause damage to some stat.  By default,
this is HP, but this can be modified.  For example, MP Attack would mean an
ability that reduces the target's MP.



Absorb:
  The same as Attack, except that the attacker benefits in some way from the
damage given to the target.  Unless otherwise noted, the benefit is equal and
opposite to the damage dealt to the target.



LR:
  Short for Long Range, this means that the ability will not factor Back Row
modifiers into the formula.  Thus, the ability will do full damage no matter
what the distance.  This also means that the ability can target enemies that
are 'Can't reach'.  Magical attacks are automatically considered to be Long
Range.



Restore:
  Restorative is a special Element that has the damage rules for Elements
reversed.  Specifically, with no Restorative affinity, targets will gain
HP or MP from this Element.  However, targets that are listed as Absorbing
Restorative will instead take damage from this element.

  If an attack is listed as Restorative, it will replace the Attack modifier.
Restore is used just to remind that this is a healing ability;
'Elm: Restorative' will still be listed within the attack, and in all other
ways, it is classed as an Attack.



Recovery:
  A special type of attack, this ability will completely refill the target's
HP and MP.  It can function without an Element, but if it does have one, then
against any target that Absorbs the ability's Element, it will inflict Death
status instead of restoring their HP and MP.  The words 'Recovery' or 'Death'
will flash up over the target to demonstrate which is being used.

  All Recovery abilities are considered to have a non-zero Power stat, which
can lead to certain interesting effects - for example, Cloud defending Barret
from Yuffie's use of an Elixir on him....



Change Status:
  This attack type attempts to change the statuses on a target.  Changes in
Status are divided into three types: Cure, Inflict or Toggle.  Cure will
remove an instance of that Status.  Inflict will attempt to give the target
that Status.  Toggle will either Inflict the Status on the target, or Cure
it if the target already has that Status.  If at any time a spell or ability
is described as Curing, Inflicting or Toggling a Status, it will also have
either a number in square brackets or the term '100%'.  When a number in
brackets appears, this is the relative chance of success.

  For example: [ 60] Inflict 'Death' is a Rating 60 chance of inflicting the
Death Status.  Without other factors modifying this chance, this would give a
59% chance of inflicting the status.  [100] Inflict 'Slow' would, without
other factors, equal a 99% chance of inflicting Slow.

  A Change Status ability, like any other attack, will be either Physical or
Magical; however, if Change Status is used, then this means that the attack
itself does no damage.  The only reason Physical or Magical is listed is for
certain enemies that may react to one or the other.  This also means that the
ability has a Power of 0, which is an important attribute that changes the
way the game treats the ability.

  If the chance reads 100%, then the Status Chance cannot fail by random
chance.  The few methods of avoiding it in that case require either immunity
to the status, or for the Ability itself to miss.



Misc Ability:
  Any ability that is not adequately described by the above categories falls
under this category by default.  Whatever effect the ability has will be
depicted under Notes.



1.2.3  Formula Types
-----  -------------
An attack that causes damage also has a Damage Formula.  While the specifics
of this will be listed on the Str stat for each ability in the guides, the
basic properties of the attack can be described as the formula.  The complete
list of Formula Types are as follows.


Physical:
  Uses the standard Physical Damage formula.  This type of ability will take
the most things into account, and has the most bonuses and penalties
attributed to it.  The ability will usually be defended against with the
Def stat and will be further reduced by the Barrier status.  All area attacks
using this formula will Split their damage, and the final result is subject
to Random Variation.



Magical:
  Uses the standard Magical Damage formula.  Generally less powerful and
more stable than the Physical Damage formula, but has higher damage abilities
to go with it in order to compensate.  MDf will defend against almost all of
these attacks, and MBarrier will also help.  The end result is also subject
to Random Variation.



Cure:
  Uses the standard Cure formula.  Similar to the Magical formula, except
that your stats act as a base for the strength of the spell instead of the
usual multiplier: improving your stats increases the strength of *all* Cure
abilities by the same amount.  On top of this, the Cure formula is not
affected by Def or MDf.  Apart from these main differences, almost all other
factors that adjust Magical damage will also affect the Cure formula.



Item:
  The final formula subject to Random Variation.  Abilities that use the
Item formula have a fixed strength that your stats can't touch.  However,
the damage can be defended against with either Def or MDf, and the final
result is subject to Random Variation.  On the other hand, none of the other
factors specific to Physical, Magical or Cure will affect the Item formula -
in particular, it will ignore the presence of Barrier and MBarrier status.



HP%, Max HP%:
  These two are very similar - one is based on a fraction of the HP you have,
the other is based on a fraction of your *Max* HP.  Abilities that target MP
use these same formulas - the formula is smart enough to know which stat to
check, so don't be surprised if you see a MP Attack using the HP% Formula: it
will correctly take a percentage of your MP instead.  Almost nothing affects
the final damage done by this formula - it ignores Barrier and MBarrier and
either Defense stat, and there is no Random Variation.



Fixed:
  An ability using the Fixed Formula does a specified amount of damage, and
none of the usual factors may modify this.  Elements and other factors that
take place outside the formulas can still change this, but Fixed itself is
immune to Def/MDf, Barrier/MBarrier, Random Variation and Split Damage.



Recovery:
  A special formula set aside for the Recovery-type abilities.  Please see
the previous section for details - it's listed here merely for completeness.
Note that all abilities that use the Recovery formula have a non-zero Power
stat - this can be important for particular things in battle.



Custom:
  Finally, there are the Custom formulas.  Like the Fixed formula, none of
the standard effects modify their damage, so their base damage is as listed
next to the relevant abilities in the guide.  The full list of abilities
using a Custom formula are as follows: White Wind, ????, Chocobuckle, Coin,
Dice, Heartless Angel, Time Damage, Everyone's Grudge, Aire Tam Storm.



1.2.4  Target Types
-----  ------------
Any ability used will often require a target to be given.  The following
shorthand will be used:

Op:  Opponent
Al:  Ally
Tar: Target (Opponent or Ally)



1 Tar:
  This means that the ability can only hit one selected target.  Normally,
this target will be selected by the player or enemy.  Multi-hit attacks that
only hit one selected target also fall under this category.



<n> Tar:
  This special variation of the above means that the ability will hit <n>
randomly selected targets in the chosen target group.  For example,
Omnislash will be listed as '15 Op', which means it will hit 15 randomly
selected targets in a selected opponent target group.



All Tar:
  This means that the ability will hit all targets within the selected
target group once each.  If this Target Type is used, the strength of the
ability must be multiplied by 2/3; that strength is then used to determine
the damage for each single target in the group.  Note that if there is only
one Target in the group, then the ability is used at full strength instead;
it's counted as a 1 Tar attack.



All Tar (NS):
  NS stands for No Split.  This means that the strength of the ability is
NOT multiplied by 2/3 when used against All Targets.  It will thus do full
damage to each and every single target in the group.



Area:
  This means that the entire battlefield is a valid target for the ability.
Both the party and the enemies will be affected.



Random:
  This means that the target will actually be a randomly selected single
target out of a valid group.  Similar to <n> Tar, except that the valid group
is what's being specified.  Random [All] specifies a single random target out
of a single target group.  Random [Area] specifies a single random target out
of all valid target groups in battle.  (Example: Random [All Tar] would allow
you to decide which target group to attack, and then a single target would be
picked randomly from that group.  Random [Area] would have no such choice,
and the single target would be picked from all targetable characters in the
battle.)



1.2.5  Equipment Modifiers
-----  -------------------
The following terms will be used as shorthand to describe various modifiers
equipment and accessories may give.

+?? <Stat>:
  This indicates that wearing the given equipment will give the indicated
bonus to the described Basic Stat.  In the Weapon List found in the FF7
Player Mechanics, there are columns already for Mag, Spr, Vit and Dex
bonuses, so bonuses for those stats given by Weapons will be found in those
columns instead.



Half/Void/Absorb <Elemental>:
  The equipment will automatically allow you to either Halve, Void or Absorb
damage from the relevant Elements.  If you have a better Elemental Defense
than the one given, it will not be affected; the better Defense automatically
takes priority.



Immune <Status>:
  Wearing this equipment will automatically make you immune to the given
Status.  Note that Immunity affects any interaction with the named status:
if you are Immune to that Status, then it is also impossible to Cure or
Toggle the Status should you have it on you.  This is best shown by wearing a
Ribbon and using a Hyper outside of battle; you will gain the 'Fury' Status,
but nothing will be able to remove that Status while you are inside battle.



Start with <Status>:
  This means that wearing the piece of equipment will make sure you begin
each battle with the named Status(es).  You cannot protect yourself from this
initial infliction, even if you are immune to the status under normal
circumstances.



1.2.6  Mathematical Terminology
-----  ------------------------
Finally, before we begin, it is important that you are familiar with the
following conventions.


[x]
  The use of square brackets around a number - [3.5] for example - means that
the result must be truncated.  That is, everything to the right of the
decimal point must be removed.  For positive numbers, we call this rounding
down.  Basically, [3.0], [3.5] and [3.8] would all equal 3, while [4.0] would
be 4.  But [-3.8] would actually be -3, since we are truncating rather than
rounding down.


x MOD y
  This means to take the modulus of x with respect to y.  That is, you divide
x by y and instead of the dividend, the remainder is what we use as the
answer.  For example, 10 MOD 3 would be 1, because 10/3 gives a remainder of
1.  Likewise, 5 MOD 3 would be 2, 6 MOD 9 would be 6, and 88 MOD 37 would
be 14.


Rnd(x..y)
  This term means we require a random integer between x and y inclusive.
For example, Rnd(3..8) would be a random number out of 3, 4, 5, 6, 7 and 8,
with an equal chance of each.


RU(x)
  This simple function just means to round the number x *up* instead of down
or towards the nearest number.  So RU(2.1), RU(2.5), RU(2.9) and RU(3) are
all equal to 3, but RU(3.01) would be 4.


With these terms out of the way, we can get started with how damage works in
the game.



-----------------------------------------------------------------------------
2. TIME
-------

There are no less than four different methods FF7 uses to measure how long
things take in battle.  First, let's define the five major timer units used
in the game.


Tick
  The absolute smallest sub-unit of time used by FF7.  The other timers are
updated every tick, and it is this unit of time that dictates how fast or
slow they move with help from the Battle Speed option.  It is used mainly for
updating and maintaining various effects, but it is never used to time how
long something will last.


Global Timer
  The timer for the entire battle.  Only the Battle Speed option in the
Config menu adjusts how quickly this increases.


V-Timer
  Here, V stands for "Variable", due to how this timer varies based on Battle
Speed and other conditions.  Each player character and enemy have their own
V-Timer.  This is the character's sense of personal time.  Haste and Slow can
speed it up or slow it down, and if you're Stopped or Dead then the V-Timer
stands still as well.  Other than this, the Battle Speed option also adjusts
this.


Turn Timer
  Similar to the V-Timer, except that it takes your Dexterity into account
as well.  Note, however, that more Dex doesn't necessarily mean you move
faster.  The increase to your Turn Timer is instead normalised by a factor
which is derived from your party's average Dexterity - to be exact, their
*Base* Dexterity.  We'll cover this in more detail later.  Faster characters
still take their turn more quickly than slower ones, but since the other
Timers are unaffected, you may not see a huge amount of difference in speed
as you progress through the game.  The effect you'll mainly notice is that
the same enemies will seem to be moving slower as you progress through the
game.
  Paralysed, Petrify and Sleep will all halt the Turn Timer, but will not
affect the other timers.


C-Timer
  This final one is a tricky one.  Where V meant "Variable", the C stands for
"Constant".  Like the V-Timer, it's affected by Haste and Slow, and it stops
if *you're* Stopped (or Dead).  However, the Battle Speed option in the
Config menu does *NOT* adjust the speed of the C-Timer.  It's more accurate
to say it's somewhat similar to the game's clock.  It doesn't matter what
Battle Speed you're playing on: it'll still progress at the same rate.



Now that we've covered the four timers, let's go over the details more
carefully.  First, we'll cover Battle Speed.



---  ------------
2.1  Battle Speed
---  ------------
The Battle Speed option, located in the Config menu, gives us a value between
0 and 255, where 0 is on the far left (and is the fastest), while 255 is on
the far right (and is the slowest).  The default Battle Speed is 128.

As soon as you enter battle, the Battle Speed is converted into our Speed
Value via the following equation:

       Speed Value = [32768 / (120 + [Battle Speed * 15 / 8])]


This formula gives the following Speed Values for key values for Battle
Speed:

    Battle Speed     Speed Value           Battle Speed     Speed Value
        0 (  0%)      273 (300%)             144 ( 56%)       84 ( 92%)
       16 (  6%)      218 (240%)             160 ( 63%)       78 ( 86%)
       32 ( 13%)      182 (200%)             176 ( 69%)       72 ( 79%)
       48 ( 19%)      156 (171%)             192 ( 75%)       68 ( 75%)
       64 ( 25%)      136 (149%)             208 ( 82%)       64 ( 70%)
       80 ( 31%)      121 (133%)             224 ( 88%)       60 ( 66%)
       96 ( 38%)      109 (120%)             240 ( 94%)       57 ( 63%)
      112 ( 44%)       99 (109%)             255 (100%)       54 ( 59%)
      128 ( 50%)       91 (100%)             ----------       ---------


The percentage values next to Battle Speed are simply how far along the scale
the number is (128 is at the 50% mark on the scale).  The percentage values
next to the Speed Value are what percentage of the default speed the value
is.  So at Battle Speed 0, you have a Speed Value of 273, which is three
times the default speed (or 300%).

The Speed Value is the base amount any of the timers (except the C-Timer) are
incremented.  Now let's look at each of the timers in more detail.



---  ----------------
2.2  The Global Timer
---  ----------------
The Global Timer isn't used for much, but its main use is to give us a
reference of overall time.  Primarily, this is used to work out when the
Stop Status should wear off.

Every tick, the Global Timer is incremented by the Speed Value.  A Global
Timer Unit is earned for every mark of 8192 the Global Timer passes.  So on
the fastest Battle Speed, it would take just over 30 ticks for a single
Unit of Global Time to pass.  On the slowest, this would increase to 152
ticks.



---  -----------
2.3  The V-Timer
---  -----------
The V-Timer, Turn Timer and C-Timer are character-specific.  This means that
the state your character is in helps dictate how fast they are.  The main
tests are as follows:


Target is under Death or Stop Status:
    V- and C-Timer progression is halted.

Target is under Slow Status:
    V- and C-Timer progression is halved.

Target is under Haste Status:
    V- and C-Timer progression is doubled.

Target is not under any of the above Statuses:
    V- and C-Timer progression is at normal.


The base increase for V-Timer is equal to twice your Speed Value.
Essentially, every tick:

                   V-Timer Increase = 2 * Speed Value


Again, V-Timer Units are required to measure the duration of things.  Like
the other timers, a unit is earned for every 8192 points the Timer
accumulates.



---  -----------
2.4  The C-Timer
---  -----------
The C-Timer is a lot simpler to describe than the V-Timer, since it doesn't
use Speed Value at all.  The base increase for the C-Timer per tick is
instead:

                        C-Timer Increase = 136


Like the other timers, a C-Timer Unit is earned for every 8192 points.
Finally, do note that the statuses listed in the previous section that affect
V-Timer progression will also affect the C-Timer.

NOTE: The base C-Timer Increase is actually 68 and a Unit is earned every
4096 points, but it is easier to understand how the timers interact if we
adjust all the timers to work on the same scale.



---  --------------
2.5  The Turn Timer
---  --------------
Finally, the Turn Timer.  This is the most complicated of the four timers,
since it is based around the relative Dex stats of the combatants.

First, we must find the normal value: the base Dex to be used for this
battle.  This is calculated by taking the average *BASE* Dexterity of all
three combatants in your Battle Party, making sure to round up any fractions.
Finally, we add 50 to this average.  We call this the Normal Speed.

For example, if you enter battle with Cloud at 31 Agi and Barret at 24 Agi,
then the Normal Speed would be:

                Normal Speed = RU((31 + 24) / 2) + 50
                             = RU(55 / 2) + 50
                             = RU(27.5) + 50
                             = 28 + 50
                             = 78


Keep in mind that only *BASE* Dexterity counts for Normal Speed.  The use of
Speed Sources, Materia and Dex-altering abilities or equipment do *NOT* count
towards this value.


Now, the amount your Turn Timer increases by revolves around the V-Timer.  As
such, the Turn Timer will also pause when the V-Timer pauses, and change
speed when the V-Timer does so.

Furthermore, the amount of increase you get is different from party members
to monsters.  Your party members get the following increase:

  Turn Timer Increase = [(Total Dex + 50) * V-Timer Increase / Normal Speed]


While monsters get this per tick instead:

        Turn Timer Increase = [Dex * V-Timer Increase / Normal Speed]


If you've noticed that enemies seem to have rather high Dex values, this is
why.  Also, while Sources, Materia and Equipment are not used for Normal
Speed, they *are* used to calculate your Total Dex - so the use of Sources
will make you much much faster than normal.

Finally, the Turn Timer itself (but not the V- or C-Timers) will be halted
under the following statuses: Paralysed, Petrify and Sleep.



You'll find that unless you use a lot of Sources or Dex-increasing items,
your Turn Timer Increase will tend to be very close to your V-Timer Increase;
after all, we're dividing your character's 'Dex + 50' by the party's average
'Dex + 50'.  This also means that no matter what your level, you will seem
to get your turns just as quickly as you used to.

However, as you achieve higher Dex ratings, it will begin to appear to you
that the monsters are moving *SLOWER* than they used to.  A L6 Cloud only has
a Dex of 6, while a L99 Cloud has an average Dex of 59.  Going by what we
know about the Turn Timer now, this means that the L99 Cloud is almost twice
as fast as the L6 Cloud.  However, to you, it'll likely look like the exact
same speed as before.  Instead, the *monsters* will be moving twice as slow
to you.

One final thing we'll look at in detail is the use of Sources or Dex-
modifying equipment here.  As stated, our L99 Cloud has an average Dex of 59.
Using Sources, we can increase his total Dex up to a nice total of 255.
Cloud with 255 Dex is 2.8x faster than when he was at 59 Dex.  However,
unlike the natural growth, we will *see* his Turn Timer increasing that much
faster, since the Normal Speed hasn't changed.  Understanding this is one of
the keys to understanding how the four different timers interact.



Having looked at how the Turn Timer increases, let's now look at what it
starts at and how it's used.

Every time you take a turn, your Turn Timer is reduced to 0, and then
increases using the formulas given above every tick.  When this reaches
65535, you will be able to take your next turn.  This is equal to just under
8 Units of 8192, so at average Dex, about 8 V-Timer Units will pass between
turns.


The Turn Timer of every party member and enemy is set to certain random
values when battle starts.  These values are not dependent on your Dex, but
can be altered based on which battle formation you get.

First, when battle begins, everyone's Turn Timer is each set to a random
value between 0 and 32767 (50% full).  There are four different ways these
values can then be further adjusted:


  Normal Battles
  ==============
The character with the highest Turn Timer has it increased until it reaches
57344 (87.5% full).  All other characters have their Turn Timer increased at
the same rate.  For example, if the highest Turn Timer had been 30000, all
characters would have their Turn Timer increased by 57344 - 30000 = 27344.
As such, in Normal Battles all characters will start with a Turn Timer
between 37.5% and 87.5% full, with the luckiest guaranteed to have a 87.5%
full Turn Timer.


  Pre-emptives / Side Attacks
  ===========================
During these formations, your party members have a distinct advantage.  The
Turn Timer for all enemies is divided by 8 (reducing them to between 0% and
6.25% of a Turn Timer bar), while the Turn Timer of each of your party
members is increased to 65534, meaning that they'll all get their first turn
immediately.


  Back Attacks / Ambushes
  =======================
These formations have your party at a disadvantage.  First, like normal
battles, everyone has their Turn Timer increased such that the character with
the highest Turn Timer is set to a certain value - but in this case, this
value is 61440 (93.75% full).  That means that all characters now have a
Turn Timer between 43.75% and 93.75% full.

Immediately following this, all party members have their Turn Timer reduced
to 0, forcing them to build up their bar from scratch.  This almost
guarantees that the enemy will get the first attack.



There is a final special case where the Turn Timer of all party members is
set to 65534, while the Turn Timer of all enemies is set to 0.  This only
occurs during the final 1v1 plot battle in the game.



We can use the above values to make a few quick observations.  In the best
case scenario, your party will begin a normal battle with a 87.5% full Turn
Timer, while your enemies will only have it at 37.5% full.  In the worst case
scenario, these are clearly reversed.

What we can calculate from this is the amount of Dex you need to guarantee
getting the first turn.  This would be as follows:

    PDex = Party Member's Dex
    EDex = Enemy's Dex
    PBar = Fraction of Party Member's Time Bar filled
    EBar = Fraction of Party Member's Time Bar filled
    Haste Factor = 1 if Party Member is not Hasted
                 = 2 if Party Member is Hasted

    Time = (1 - EBar) / EDex
         = (1 - PBar) / ((PDex + 50) * Haste Factor)

    (1 - PBar) / ((PDex + 50) * Haste Factor) = (1 - EBar) / EDex
    (PDex + 50) * Haste Factor = EDex * (1 - PBar) / (1 - EBar)

    PDex = (EDex * (1 - PBar) / ((1 - EBar) * Haste Factor)) - 50


PDex must thus be higher than the above calculated value to beat an enemy of
a certain Dex when the Time Bars start filled at particular values.  If we
use the values for the worst case scenario, we get:

    PDex = (EDex * (1 - 0.375) / ((1 - 0.875) * 1)) - 50
         = (EDex * 0.625 / 0.125) - 50
         = 5*EDex - 50



We can reverse this formula to work out how much Dex the enemy needs to beat
a party member with a certain amount of Dex:

    EDex = (PDex + 50) / 5


This means, for example, that at 255 Dex, the enemy would need at least 61
Dex in order to beat the player even in the worst case Normal Battle scenario
for the player.

If the party member is hasted, it's a little better:

    PDex = (EDex * (1 - 0.375) / ((1 - 0.875) * 2)) - 50
         = (EDex * 0.625 / 0.25) - 50
         = 2.5*EDex - 50

We can reverse this and find that at 255 Dex, the enemy now needs at least
122 Dex in order to beat the player in the worst case Normal Battle scenario.

Obviously, since we've only been looking at worst case only, we can see that
the enemy will usually need much more Dex in order to beat your party members
most of the time - on average, you and the enemy will have roughly equal
Time Bars, so all you'd need most of the time is to make sure that your Time
Bar fills faster than the enemy: this happens when EDex < PDex + 50.

However, do note that your enemies choose their actions instantly when their
Time Bar fills, so it is not always enough to *just* beat them to getting the
next turn.  Keep this in mind when it seems that enemies are just a little
faster than expected.



---  -----------------
2.6  Timer Interaction
---  -----------------
Now that we've covered each of the timers in detail, we can see how they
compare with each other.


For a player with average Dex and no statuses, the timers will increase at
the following different rates:


                  +=======================================================+
                  |                     Speed Value                       |
                  |      Min (54)         Avg (91)         Max (273)      |
 +================+=======================================================+
 | Global Timer   |         54               91              273          |
 | V-Timer        |        108              182              546          |
 | Turn Timer     |        108              182              546          |
 | C-Timer        |        136              136              136          |
 +================+=======================================================+


Now, we consider the following ways to change these values.  Global Timer
is purely tied to the Speed Value, so we can use that as the baseline.
C-Timer, however, is constant, and can only be changed by the standard Haste,
Slow or Stop statuses.  Death-sentence and Slow-numb both use the C-Timer
to count down to 0, so it makes sense that both statuses are far more
dangerous at slower Battle Speeds.

V-Timer and Turn Timer are linked, as usual.  But as we saw in the last
section, we can use Dex modifications to make the Turn Timer move faster,
whilst leaving all the other timers alone.  Since the rest of the statuses
rely on V-Timer, this can be especially advantageous to us.

It also allows us to make comparisons between the timers, especially for
Status durations.  The main outliers are Stop (lasts 30 Units of Global
Time), Death-sentence (lasts 60 Units of C-Time) and Slow-numb (lasts 30
Units of C-Time).

At max Battle Speed, we get 1 C-Timer Unit for every 4 Units of V-Time.  By
comparison, at minimum Battle Speed, we get 1 C-Timer Unit for every 80% of a
single V-Timer Unit accumulated.  Quite the difference.  At the default
Battle Speed, it's about 1 C-Timer Unit per 133% of a V-Timer Unit, which is
a little better.  This is something to keep in mind for the aforementioned
Slow-numb and Death-sentence Statuses.  Essentially, Death-sentence (60
C-Timer units) would last 30 turns on max Battle Speed, 10 turns on default
and 6 turns on minimum, with Slow-numb lasting half the time.

Since the Global Timer usually progresses half as fast as the average player
character, we can suggest that Stop lasts the equivalent of 60 V-Timer Units,
during which a total of 7 turns could be taken.

Of course, with the time it takes to make decisions about what to do each
turn, and with how time carries on during ability use if you set the Battle
Mode to Active rather than Wait, these statuses will often seem to wear off
faster than this.

By comparison, the Sleep Status lasts 100 V-Timer Units (12 turns), while
Paralysed lasts 20 V-Timer Units (a mere 2 turns).  Of course, if we were
to use equipment or other such options to increase our Dex, we might even
get *more* turns in that same amount of time.  Such is the way the timers
interact.



---  ----------------
2.7  Escaping Battles
---  ----------------
For this last section, we'll quickly go over how fleeing the battle works,
since the main method for doing so is tied in with the timing system.

The normal method of running - where you hold two buttons down until you
escape - uses the Global Timer to help determine when to check the chance of
fleeing.  While no record of how *long* you've been running is kept, every
time a Global Timer Unit is finished, the game checks if you've spent more
than 50% of that Unit running.  If you haven't, then no further check is
made, and it won't check again until the end of the next unit.

If you *have* spent more than half of the unit running, then you have a
chance to escape: we shall call this a Run Check.

Escaping battle uses a variable called Run Difficulty to help determine how
easy it is to run away.  This variable is set by which encounter you're in:
some encounters are easier to escape than others.  Most encounters have a Run
Difficulty of 1, but Back Attack encounters tend to increase this value by 1,
and encounters with certain enemies also have higher Run Difficulty.

You will flee the battle if the Run Difficulty of the encounter falls to
zero.  This is done during the Run Check noted above, and is dealt with in
the following manner:

  * If you had a Pre-emptive attack in this encounter or the formation
    is Side Attack (you surround the enemy), then Run Difficulty is
    automatically reduced by 1 each time a Run Check is made.

  * For all other formations, there is only a 25% chance per Run Check that
    the Run Difficulty will be reduced by 1.


This can basically be simplified to a 25% chance per Global Timer Unit that
you will flee most battles.  If you remember the comparisons in the last
section, you'll note that you usually get about 4 Global Timer Units during
the average character turn, so on average, Run Difficulty drops by 1 per
turn.

Note that you cannot escape from Ambushes until all the enemies on one side
are removed.  Both the Ambush restriction and Run Difficulty itself only
apply to normal running however; you are able to use the Escape spell or the
Smoke Bomb item at any time to instantly escape battles without having to
deal with the hassle that higher Run Difficulty values can cause.



-----------------------------------------------------------------------------
3. BATTLE DAMAGE
----------------

---  -----
3.1  Setup
---  -----
Before we can even start calculating damage, certain things need to be setup
by the system, usually due to certain aspects of the ability being used, or
perhaps what Materia it's linked to, or the like.  Also, we can use this
section to explain certain things that need to be known before we can put the
basic formulas to use.


One of the important things we need are the final values for both the
Attacker and Target's stats.  We already know that the basic stats used in
battle are Att, At%, Def, Df%, MAt, MDf, MD%, Dex and Lck.  However, under
circumstances in battle, these values can *change*:

  * Certain items and abilities (Dragon Force and Hero Drinks in particular)
    can increase or decrease your stats.  The stats that can be affected are
    Att, Def, MAt, MDf, Df% and Dex.  This is called a Stat Modifier.  The
    Stat Modifier is an integer percentage between -100% to 100%, and starts
    the battle at 0%.  The use of certain abilities will increase or decrease
    this value for certain stats up to the maximum or minimum after repeated
    use.  Unless noted, *any* formula that uses any of the six stats
    mentioned must apply this Stat Modifier like so:

                    Stat = Stat + [Stat Modifier * Stat]

    So an Att Modifier of 100% would double your Att whenever it was used in
    any formula.

    Hero Drinks increase the Stat Modifier for Att, Def, MAt and MDf by 30%
    each when they're used, while Dragon Force increases only Def and MDf by
    50% each.  Other abilities exist that also adjust these stats, and this
    will be mentioned when we cover those abilities.


  * Also, if the ability being used is Piercing, then the Target's Def and
    MDf is considered to be 0.  As such, they're ignored.  Note that only the
    Physical, Magical and Item Formulas utilise Def and MDf; all others
    naturally ignore both stats.


Once we've ascertained the values of the various stats that may be used, we
can move on.



---  -------------------------------
3.2  Status and Elemental Resistance
---  -------------------------------
Among the first things checked is the resistance or weakness to any Elements
or Statuses the ability has.  This is done early because it can affect so
many different parts of accuracy and damage.

To start with, if the Ability has any statuses to Inflict, Toggle or Cure,
then the chance of these hitting is calculated first, as detailed in Section
3.3.4.  If this chance fails, then the Ability will no longer be considered
to have any statuses attached to it for this particular hit.  Furthermore,
if the Ability has a Power of 0, then failing to cause a change in status
will cause the entire ability to miss.


Now we can look at resistances to the ability.

There are eight levels of Elemental Resistance, listed as follows:
  Death     :- The Target is instantly killed by this Element.
  Auto-Hit  :- The Target cannot evade this Element.
  Weak      :- The Target takes double damage from this Element.
  Normal    :- The Target takes normal damage from this Element.
  Resist    :- The Target takes half damage from this Element.
  Immune    :- The Target takes no damage from this Element.
  Absorb    :- The Target is healed by this Element.
  Recovery  :- The Target is completely recovered by this Element.


First, the Target's current resistances to all Elements and Statuses are
collected.  For the most part, this is simply based off of the inherent
qualities of the enemy or equipment/materia your party has equipped, and is
thus self explanatory.  However, there are certain extra resistances that are
added depending on various factors.



                          Extra Status Resistances
                          ------------------------

  * A party member under AI control (Vincent under Limit Break or Sephiroth
    during the Kalm Flashback) gains immunity to Berserk, Frog and Confusion.

  * Targets under the Resist Status are immune to all Statuses except Resist
    and Imprisoned.  Targets under the Death Force Status are immune to
    Death.  Both of these immunities are not applied against the *damage*
    portion of any Item command.  This exception is only for the Item command
    however; the W-Item command works as normal.  As an example of this,
    using W-Item M-Tentacles on a target with the Resist status but no Poison
    immunity would cause zero damage, but using it via the Item command would
    cause damage but no Poison status.

  * Targets under the Peerless Status are immune to all Statuses except
    Imprisoned.

  * Targets immune to either Haste or Slow Status are immune to *both*
    Statuses.

  * Party members have Death immunity temporarily removed if the ability
    being used is trying to remove Death Status.

  * Targets that have had their Death Handling turned off (disables death
    animation so that the AI script can handle it itself) gain Death
    immunity.  Note that any enemy that does this is invariably immune to
    Death anyways.

  * Targets that are immune to Death gain an additional immunity to
    Death-sentence.

  * Finally, if the ability ignores Status immunities, all Status immunities
    set up to this point are cleared for this attack.



                         Extra Elemental Resistances
                         ---------------------------

  * Targets under the Shield Status can absorb the following Elements: Fire,
    Ice, Lightning, Earth, Poison, Gravity, Water, Wind, Holy.  They are also
    immune to Cut, Hit, Punch, Shoot, Shout and Restorative Elements.
    However, these resistances are not added if the ability being used is
    from the Item command.  W-Item command allows Shield to work as normal.

  * Targets that are immune to the Poison Status gain immunity to both Status
    and Element - though Absorbing Poison Element still takes priority.



Element and Status Resistances are treated slightly differently depending on
whether we are looking at either the statuses the ability is changing, or the
entire ability itself.  We shall focus on the latter first, since it has
more rules to consider.  We will, however, keep a copy of the collected
Status Immunities safe, since it is used later to determine which of the
successful status effects the ability has will actually make it through if
the ability itself hits.

First, it should be noted that immunities - whether Element or Status - can
cause abilities to fail or miss.  Before an ability can properly take effect,
we must work out what level of resistance the Target has to it.  As such,
there are some extra rules to take into account:

  * For the purposes of an ability landing, if the Target is not immune to
    *all* the Statuses the ability is inflicting, then it is considered to be
    immune to none of the Statuses.  This only affects whether the ability
    hits the target - it has no bearing on whether the statuses will take
    hold.

  * Likewise, if the ability has a non-zero Power stat, then any Status
    Immunity is ignored - this allows the damage/healing part of the ability
    to still land if it is able to.  Other levels of resistance to Statuses
    that certain enemies have are kept intact however, in both cases.

  * At this point, Element and Status resistances are now factored together
    and compared with the exact Elements and Statuses of the ability being
    used.  Instead of knowing individual Element/Statuses, we now only care
    whether the Target has various levels of resistance to the ability.  Note
    that multiple levels can be in effect at once: we could both Resist and
    be Immune to an ability if we had a Resist to one Element but was Immune
    to another.

  * However, if the ability ignores Element and Status resistances, then the
    Target loses *all* resistances to the ability itself that it had
    accumulated at this juncture.  This includes detrimental effects such as
    being Weak to the ability or similar.



Now we can apply how the resistances interact with the ability's statuses.
The following checks are made at this point, in a particular order:

  * If the Target Absorbs an Element of the ability:

      -- Status Infliction and Removal are swapped.  That is, all statuses
         that the ability inflicts are removed instead, and vice versa.

      -- If the Ability now inflicts Death after swapping Status Inflict/
         Removal, then the Target is now considered to have Death Weakness
         to the ability, and the Death status is removed from the ability
         itself.

      -- Likewise, if the Ability now cures Death, then the Target is
         considered to gain a Recovery from the ability, and the Death
         status is again removed.
  
      -- Note that if a Target both Absorbs the ability *and* has Death
         Weakness to it, then the Death Weakness will not be negated, and
         may kill the Target.
    

  * If the Target has a Death Weakness to the ability:

      -- If the ability uses the HP% or Max HP% formulas, then the Power
         of the ability is converted to a success rate.  An ability that
         recovers 25% of a target's HP now has a 25% chance of killing
         the Target, as an example.

         If this rate then fails, then the Death Weakness is removed, and
         the Target is now considered to be Immune to the ability.  All
         other resistances remain untouched.


  * If the Power of the Ability is zero:

      -- As the ability has no damage for the Target to resist or be weak
         to, then the Base PAt% or MAt% of the ability is instead altered.
         If the Target is Weak to the ability, then the At% is doubled.
         On the other hand, if the Target Resists the ability, then the At%
         is halved, rounded down.

      -- Note that Immunity and Absorb does not play a part at this point.
         In general, these will instead cause the Ability to automatically
         hit so that the game can deal with how the Target resists the
         actual effect properly.

      -- Remember that if the Statuses that the Ability inflicts have
         already missed due to Status Accuracy, then the attack will have
         missed already.


At this point, the basic preparations of dealing with Elements and Statuses
are complete.  Any further effect they have is based on which attack formulas
will be used later on in the damage formula.  The only remaining thing to
note at this point is that if the Ability uses the Restorative Element, then
the Ability is flagged as Restorative.



---  ----------
3.3  Hit Chance
---  ----------
Eventually, we're going to need to see if our attack isn't going to end up
being evaded by the Target.  Of course, even if the attack connects, previous
element checks and other conditions yet to be looked at can cause the ability
to fail... but we'll cover one thing at a time.

There are four main variations of hit calculation: Physical, Magical,
Critical and Status.  On top of that, there are a bunch of miscellaneous
formulas that affect certain unique attacks - in general, these have been
explained next to the ability in question.

As such, let's go over the four main hit routines.


3.3.1  Physical
-----  --------
Otherwise known as a PAt%-based attack.  This is also the most involved and
complex formula, so we'll go over it slowly.

First, we check for any condition that allows for a maximum accuracy hit.
This will set your Hit% to 255, regardless of what ability you're using.  Any
of the following will give an automatic 255 Hit%:

   * Back Attacking an enemy
   * Using an Element that the target has Death Weakness to
   * Using an Element that the target has Auto Hit Weakness to
   * Using an Element that the target is Immune to
   * Using an Element that the target Absorbs
   * If the target has any of the following statuses:
        Death, Sleep, Confusion, Stop, Petrify, Manipulate, Paralysed
   * If the target is Covering someone


Note that if the target has Sleep, Confusion and/or Manipulate Status, then
these will be cured by the PAt%-based ability, assuming it hits.



If we don't get an automatic 255 Hit%, then we must calculate the correct
Hit% manually.  Do note that attacking with a 255 At% weapon does not count
as an automatic hit - we still have to work out Hit%.  We use the following
formula to do this:

   Hit% = ([Attacker's Dex / 4] + At%) + Attacker's Df% - Target's Df%

For party members, these values are exactly as you see on the status screen,
taking Stat Bonuses from things like Hero Drinks into account.  For example,
this means that half your Dexterity will be factored into this formula, since
25% is used in the formula itself, and another 25% is calculated into your
total Df%.

For enemies, their Dex and Df% are as shown in the Enemy Mechanics Guide, and
the At% is the PAt% shown by the ability they are using.  Enemies do not
carry weapons, so their abilities are the only things that will be used.
Also, do recall that the PAt% of the ability may have been altered by
previous Elemental considerations if the attack is not meant to do damage.

And yes, this is no mistake - your Df% contributes to how well you can hit a
target.  Just another reason why Mystile is such an incredible armor.

Finally, if the Attacker is under the Fury Status, this calculated Hit% must
be further modified:

    If Attacker is under Fury Status: Hit% = Hit% - [Hit% * 3 / 10]

This results in a 30% loss of Hit%, which can be rather critical in deciding
whether you hit the target or not.



At this point, we will have calculated a Hit%.  If the total is less than 1,
then it is increased to a minimum of 1.  (In a few moments, we will see that
a Hit% of 1 will never connect, but bear with us for now)

Next up, we must calculate the chances of a Lucky Hit or Lucky Evade.  These
are handled at the same time.  We roll a single random number - Rnd(0..99) -
which we will use to determine which of the two events occur.


Lucky Hit:
   The Attacker has a [Lck / 4]% chance of landing a Lucky Hit.  If this is
   successful, then Hit% is immediately increased to 255%.


Lucky Evade:
   The Target has a [Lck / 4]% chance of pulling off a Lucky Evade, but
   *ONLY* if a Lucky Hit was not pulled off.  Furthermore, it uses the same
   random number that was checked for Lucky Hit, so the Target's Lck must be
   *greater* than the Attacker's Lck to even have a chance at this.  The
   adjusted chance should therefore be expressed as:

        Evade Chance = ([Target's Lck / 4] - [Attacker's Lck / 4])%.

   Note that only party members may obtain a Lucky Evade and only if a
   non-party member is attacking them - enemies will never get a Lucky Evade.
   If a Lucky Evade is pulled off, then the Hit% is immediately decreased
   to 0%.



Finally, having got this far, we need to use the Hit% value to determine
whether we hit or miss the target.  The formula used for this is as follows:

        Random = [Rnd(0..65535) * 99 / 65535] + 1
        If (Random < Hit%) Then Attack Hits

Random gives us a number between 1 and 100 most of the time, but it has a
*VERY* tiny chance (probability of 1/65536) of returning 101.  As such, it's
not a true percentage check - a Hit% of 101 has a very rare but present
chance of missing, and a Hit% of 1 will never connect.  Since the various
Auto and Lucky Hits use a Hit% of 255 though, they're pretty much guaranteed
to hit (providing the target doesn't earn a Lucky Evade).



In summary, the procedure for calculating a PAt%-based hit is as follows:

   Check for Auto Hit Conditions
     If Auto Hit, Hit% = 255
     If not Auto Hit, Calculate Hit% and check for Fury
   Check for Lucky Hit and Lucky Evade
     If not a Lucky Hit or Evade, use Hit% to decide success of attack



3.3.2  Magical
-----  -------
Otherwise known as a MAt%-based attack.  Far simpler to calculate, especially
since we don't have Lucky Hits/Evades to worry about.

Once more, we start off working out the conditions for an automatic hit.
These are as follows:

   * If the MAt% of the ability is 255
   * Using an Element that the target has Death Weakness to
   * Using an Element that the target has Auto Hit Weakness to
   * Using an Element that the target is Immune to
   * Using an Element that the target Absorbs
   * Using a reflectable ability while the target has Reflect status
   * If the Ability is not inflicting a status and the target has any of the
     following statuses:
        Death, Sleep, Confusion, Stop, Petrify, Paralysed


Unlike PAt%-based abilities, an Automatic Hit does not need to check anything
else - we *will* hit the target.  If this is not the case, then we continue.

If we get this far without an Automatic Hit, then we must first calculate the
chance to hit manually.

To start, we take the MAt% of the ability and apply the modifier for Fury.
If the Attacker has the Fury Status, then:
 
    If Attacker is under Fury Status: MAt% = MAt% - [MAt% * 3 / 10]


Next, we check the Target's MD%.  This is a straight percentage chance to
either hit or miss - 99 MD% equates to a 99% chance to miss.  If this check
succeeds, then the attack misses, without question.


Only if the MD% fails do we calculate the final chance to hit.  The following
formula is used:

          Hit% = MAt% + Attacker's Lvl - [Target's Lvl / 2] - 1
        Random = Rnd(0..99)
        If (Random < Hit%) Then Attack Hits

As you can see, this is another percentage check once we've calculated the
Hit%; 100 Hit% will always connect.  Also note that it's Level that's used to
make the attack more or less likely to hit - the higher your Level, the more
likely you are to land a magical attack.



In summary, the procedure for calculating a MAt%-based hit is as follows:

   Check for Auto Hit Conditions
     If Auto Hit, attack hits
     If not Auto Hit:
        Apply Fury Modifier
        Check for MD%-based Evasion
        Calculate Hit%
        Use Hit% to determine success of attack



3.3.3  Critical
-----  --------
If a PAt%-based hit using the Physical damage formula successfully connects,
then with very few exceptions, the chance of a Critical Hit must next be
calculated.  This is very simple to do, and involves only two main steps.


First, we calculate the actual chance to Critical.  If the Attacker has the
Lucky Girl Status, then Crit% is set to 255.  Otherwise:

      Crit% = [(Attacker's Lck + Attacker's Lvl - Target's Lvl) / 4]
      If Attacker is Party Member: Crit% = Crit% + Weapon's Crit% Modifier

The higher your Luck and Level, the higher the chance of a Critical Hit.
Note that the Crit% Modifier of most weapons is 0, and you won't get more
than a 5% bonus from your weapon (with one unique exception early in the
game).


The second step is simply to work through the random chance:

        Random = [Rnd(0..65535) * 99 / 65535] + 1
        If (Random <= Crit%) Then Critical Hits


Once again, Random creates a number between 1 and 100 most of the time, with
a 1/65536 chance of 101.  However, Crit% is closer to a true percentage than
our PAt%-based hit was - with the exception of the very rare chance of a 101
from the Random value, a 0% Crit will hit 0% of the time, while a 100% Crit
will hit 100% of the time.


The summary of the procedure is simple:

   Check for Lucky Girl Status
   Calculate Crit%



3.3.4  Status
-----  ------
The final main routine for accuracy is for statuses.  Like Critical Hits,
the attack a status is attached to must succeed before we can figure out
whether the status itself may hit or not.

Status accuracy is actually checked for at the start of the Status and
Element phase, before Element/Status Resistances are dealt with.  If the
chance fails, then the ability will no longer be considered to be Inflicting,
Toggling or Curing any statuses.


First, we check for Auto Hit conditions, as per usual:

   * If Frog is the only Status the Ability is trying to Inflict, Cure or
       Toggle, and the Target has the Frog Status, then allow an Auto Hit
   * If Small is the only Status the Ability is trying to Inflict, Cure or
       Toggle, and the Target has the Small Status, then allow an Auto Hit
   * If the Target is a Party Member, and at least one of Haste, Berserk or
       Shield is being Inflicted, Cured or Toggled, then allow an Auto Hit
   * If the Status Chance is 100%, then allow an Auto Hit

If an Auto Hit is allowed, then the status effect will connect.  This doesn't
mean that the attack will work, of course - we still have to check for
immunity and the like later.


If there is no Auto Hit, then we must calculate the chance of success
manually.  The Status Chance of the ability is used: [32] is a Status Chance
of 32, as you'd expect.

We check for MP Turbo to start with - the Status Chance will be increased
by the MP Turbo factor if the ability is correctly linked to an MP Turbo
Materia:

        Status Chance = [Status Chance * (10 + MP Turbo Level) / 10]


Secondly, if the Ability is hitting more than one target, but the Ability
is not No Split, then:

        Status Chance = [Status Chance * 2 / 3]


Third, if we're using Quadra Magic linked to the Ability, then:

        Status Chance = [Status Chance / 2]



Finally, now that we have the final Status Chance, we can calculate whether
it lands or not:

        Status Chance = Status Chance - 1
        If Rnd(0..99) < Status Chance then Status Hits

So after subtracting the 1, we end up with a straight percentage chance.


NOTE: There is one more check the game does even if an Auto Hit was earned,
which revolves around the Death Status.  If the ability Inflicts, Cures or
Toggles the Death Status, then an unknown condition is also checked for.  If
the Target passes this condition, then the Status misses, even if it passed
the Status Chance test.  What exactly is checked for is unknown, but it
doesn't occur in normal battles, so do not worry overmuch about it.



---  -------------
3.4  Formula Types
---  -------------
As noted previously, there are different damage formulas which depend on the
ability being used.  This section will deal with differences between them,
and give us our starting base for damage.  Note that immediately prior to
using this section, any Before Damage Effects that occur will be applied.


3.4.1  Physical
-----  --------
The Physical Formula for Base Damage is defined as such:

  Base Damage = Att + [(Att + Lvl) / 32] * [(Att * Lvl) / 32]


Ability Power and the Defense Stat are then used:

  Damage = [(Power * (512 - Def) * Base Damage) / (16 * 512)]

Power is an integer, but in Ability listings found in the Party and Enemy
Mechanics Guides, it will be expressed as a fraction of Base Damage.  A Power
of 1 is equal to 1/16x Base Damage, while a Power of 16 is equal to 1x Base
Damage.  Naturally, a Power of 50 would therefore be 3 1/8x Base Damage.
However, since Defense and Power are multiplied at the same time before
division, in order to be completely accurate it is necessary to convert it
back to an integer before using the formula on it.  Also, all formulas where
I specifically use Power will assume it to be in its integer format - this is
especially important for Ultimate Weapons.

If all you need is a slightly less accurate estimate of how much damage you
will do, then you can simply multiply by the fraction of Base Damage as
listed in the Party and Enemy Mechanics Guides and then just multiply by
(512 - Def) / 512 to take Def/MDf into account.  This estimate can sometimes
be off by a point or two of damage due to rounding, but random variation will
usually make it such that you probably won't even notice.


After this, the Physical Formula will use the following modifiers:
   Critical Hit
   Berserk on Attacker
   Row Check
   Defend on Target
   Back Attacked Target
   Frog on Attacker
   Sadness on Target
   Split Damage and Quadra Magic
   Barrier/MBarrier on Target
   MP Turbo
   Mini on Attacker
   Random Variation


BUG: It is possible to get the application of Power, Def and Base Damage
high enough that the damage done will overflow.  This occurs when
"Power * (512 - Def) * Base Damage" becomes greater or equal to
2,147,483,648, which is equivalent to a predicted damage of 262,144 damage or
more.  Overflow in this manner will change the damage from 'x' to roughly
'((x - 262144) MOD 524288) - 262144'.  (In actuality, the 2,147,483,648
overflows to -2,147,483,647, and starts counting up again from there - it'll
reach 0 again when the original number hits 4,294,967,296.)

When overflow occurs, if the damage is now in the negative range, then the
attack will automatically kill the enemy - this occurs because negative
damage subtracted from an enemy's HP actually *increases* their HP, but FF7
believes that any attack that does damage *and* causes the enemy to have more
HP than they started with must have been so strong as to overflow HP.

Please note that attacks that enemies absorb to heal themselves are handled
differently - the game uses positive healing numbers and a special flag to
note the use of healing.  However, negative healing, caused by the same
overflow above (which can happen with use of HP Absorb, for example), will
often kill the unlucky victim instantly due to a different bug.



3.4.2  Magical
-----  -------
The Magical Formula for Base Damage is defined as such:

  Base Damage = 6 * (MAt + Lvl)


Ability Power and the Defense Stat are factored in at the same time, just
like the Physical formula:

  Damage = [(Power * (512 - MDf) * Base Damage) / (16 * 512)]

Power is again an integer, but it will be expressed as a fraction in Ability
listings.  A Power of 16 is equal to 1x Base Damage.


After this, the Magical Formula will use the following modifiers:
   Sadness on Target
   Split Damage and Quadra Magic
   Barrier/MBarrier on Target
   MP Turbo
   Random Variation


Note that while Att/Def and MAt/MDf are used in the above two formulas, it is
possible for FF7 abilities to be coded to use each formula with the opposite
attack and defense stat (using MAt instead of Att in the Physical Formula,
for instance).  A Physical Attack using the Magical Formula would use Att in
the Magical Formula.  However, this is purely academic, since no known
ability has been found within the game code that does this.



3.4.3  Cure
-----  ----
The Cure formula is very similar to the Magical Formula, and starts off in a
similar way.

   Base Damage = 6 * (MAt + Lvl)

   Damage = Base Damage + 22 * Power


As you can see from the second part of the formula, the way Power is applied
is completely different.

Like before, Power is an integer.  In Ability listings, it will be expressed
as Base + Constant, where Constant is the 22 * Power already multiplied out.
For example, a Power of 16 would result in a Constant of 352.


Furthermore, the Cure Formula does not use all the same modifications as the
Magical Formula - it does not check for Sadness:
   Split Damage and Quadra Magic
   Barrier/MBarrier on Target
   MP Turbo
   Random Variation



3.4.4  Item
-----  ----
Finally, the formulas get less complicated.  The Item Formula has a simple
formula and very few modifications:

   Base Damage = 16 * Power

   Damage = [Base Damage * (512 - Def) / 512]

In Ability listings, the base damage will be shown already multiplied with
Power.  A Power of 16 would cause Base Damage of 256.


And the only modification it has is Random Variation.

Note that the Item formula is used for both Physical *and* Magical abilities,
so for some abilities, MDf may be used in the above formula instead.



3.4.5  Other Formulas
-----  --------------
All other formulas have almost no modifications and very simple formulas.
They can be summarised as follows:


HP%, Max HP%
  For the HP% Formula, the damage is simply:
                 Damage = [Target's HP * Power / 32]

  If Max HP% is used instead, then the Target's Max HP is taken instead of
  the Target's HP.  If the ability is meant to do MP damage, then the
  Target's MP or Max MP will be used.  The only difference between the
  formulas is which stat is accessed.

  In Ability listings, the fraction of HP/MP/Max HP/Max MP will already be
  simplified.  A Power of 16, for example, would be expressed as:
    [Target's HP / 2]

  The only modification this formula uses is Quadra Magic.


Fixed
  Very simple formula:
                 Damage = Power * 20

  In Ability listings, this will already be multiplied out for you, with a
  Power of 16 giving a strength of 320.

  That's all there is to it.


Recovery
  Unlike the other formulas, there is no damage associated with this.  We
  will cover the effects of this later.


Custom
  None of the Custom Formulas have any modifications - they all ignore
  Defense and MDefense, have no Random Variation, and ignore any other
  conventional modifier for Formulas.  Their damage formulas will be given
  with the abilities themselves.



3.4.6  Formula Modifiers
-----  -----------------
Now that the formulas themselves have been defined, we should deal with the
different modifiers that can affect these.  This shall be done in the order
listed in the Physical Formula, since all other formulas use the same order.


Critical Hit   (Physical only)
  If the attack is a Critical Hit (either through luck, via the Deathblow
command, the Lucky Girl status, or any other move that has automatic
Criticals), then:
       Damage = Damage * 2


Berserk on Attacker   (Physical only)
  If the Attacker has Berserk Status then:
       Damage = [Damage * 1.5]


Row Check   (Physical only)
  If either the Attacker or the Target is in the back row, and the ability
has not been flagged as Long Range, then:
       Damage = [Damage / 2]


Defend on Target   (Physical only)
  If the Target has used the Defend command on their most recent turn, then
damage is modified as such:
       Damage = [Damage / 2]


Back Attacked Target   (Physical only)
  If the Target has its back to the Attacker, then Back Attack damage is
applied.  Note that a few rare abilities will calculate Back Attack as coming
from a certain direction rather than from the Attacker.  The damage is
modified as such:
       Damage = [Damage * Back Attack Multiplier / 8]

  For almost all enemies (including your party), the Back Attack Multiplier
is 16, leading to double damage.  However, on certain enemies, this value is
different, which can lead to even greater damage.


Frog on Attacker   (Physical only)
  If the Attacker has Frog Status, then:
       Damage = [Damage / 4]


Sadness on Target   (Physical and Magical only)
  If the Target has the Sadness status, then damage is reduced as such:
       Damage = Damage - [Damage * 3 / 10]


Split Damage and Quadra Magic  (Physical, Magical, Cure, HP%, Max HP%)
  Split Damage and the modifier from Quadra Magic are applied at the same
time.  The HP% and Max HP% formulas never use Split Damage though.  First,
Quadra Magic is checked.  If the ability is linked to Quadra Magic and
Quadra Magic works with it, then:
       Damage = [Damage / 2]

  If the Quadra Magic effect is applied, then Split Damage will not be looked
at.  Otherwise, we must work out if the ability is liable for Split Damage.
If the ability is only targetting a single character, then damage is not
Split.  If the Magical Formula is used, damage is only Split if the ability
can be toggled between All Tar and 1 Tar.  Physical and Cure Formulas are
always Split if they hit more than one target.

  If the ability's damage must be Split then:
       Damage = [Damage * 2 / 3]


Barrier/MBarrier on Target   (Physical, Magical and Cure only)
  If the ability is Physical and the Target has the Barrier status, or if
the ability is Magical and the Target has the MBarrier status, then the
following is applied:
       Damage = [Damage / 2]


MP Turbo   (Physical, Magical and Cure only)
  If the ability is compatible to and paired with the MP Turbo Materia, then
damage is adjusted based on the level of the materia:
       Damage = [Damage * (10 + MP Turbo Level) / 10]


Mini on Attacker   (Physical only)
  If the Attacker has the Mini status, then all our hard work up to now has
gone to waste, because:
       Damage = 0


Random Variation   (Physical, Magical, Cure, Item only)
  At last, damage is adjusted randomly by the following formula:
       Damage = [Damage * (3841 + Rnd(0..255)) / 4096]

  If Damage is 0 after this:
       Damage = 1

  This basically means that the calculated damage is the maximum it could do,
but damage could be as low as 15/16ths of that figure.  (Note: 15/16ths
is just an approximation - 3841/4096 is the true lowest value, but in the
large majority of cases, you won't see the difference.)

  Furthermore, it means that so long as the ability did not miss and things
like Immunity do not come into play, you will always do at least one point of
damage/healing.  Since this check is done before After Damage Effects and
Elemental Modifiers, you may still do more than just this 1 damage as well.

BUG: Again, due to the large numbers involved, it is possible to get the
base damage high enough that Random Variation itself causes it to overflow.
This occurs when "Damage * (3841 + Rnd(0..255))" becomes greater or equal to
2,147,483,648, which starts happening when the uncapped damage is at least
524,288 (requires Rnd(0..255) to be 255), with the chance increasing up to
100% at 559,095 damage.  It's rare to see this, but with enough bonuses from
things like Berserk and Critical Hits, and an already perilously high Power
from weapons like Missing Score or Death Penalty, it can happen.



---  --------
3.5  Lucky 7s
---  --------
Deserving of a section of itself, this state changes several rules throughout
the formulas for many abilities.

If a player or enemy happens to have 7777 HP exactly, then they enter a state
known as All Lucky 7s.  This has the following effects:

  * If any party member enters this state, or begins the battle in this
    state, then they will be forced to use the Attack command continuously
    on the enemy.  This does not take up their current turn, but it takes
    priority over all other moves and has no delay in its use.  If multiple
    party members have 7777 HP, then they will alternate attacks.  This
    continues until 64 forced attacks have been done overall, no matter how
    many party members are in All Lucky 7s.  This chain of 64 attacks can
    only be done once per battle.  It almost guarantees the death of whatever
    you're facing, with only a few exceptions.

  * The resulting Damage of any damage-causing Ability from the Attacker will
    be 7777, so long as it was going to cause at least 1 point of damage to
    start with.  This also includes damage from the Poison status, which is
    considered to be a self-inflicted ability.

  * Elements and status effects will be removed from any use of the
    following commands: Attack, Morph, D.blow, Mug, Slash-All, 2x-Cut,
    Flash and 4x-Cut.

  * After the battle ends, the HP of any party member still at 7777 HP will
    be reduced to 1.



---  ------------
3.6  Final Checks
---  ------------
After all success rates and damage values have been determined, we have
only a few checks left to apply to the damage.  These are, again, done in
a certain order.

 ---

First, all After Damage Effects from abilities and weapons are applied.

 ---

Next, we deal with Elemental effects on the resulting damage and statuses.

If the Target has Physical Immunity and the Ability is Physical, or Magical
Immunity and the Ability is Magical, then the Target gains Element Immunity
to the ability, and loses all other Element Resistances/Weaknesses to the
Ability.

If the Target Absorbs the Ability, then the Restorative flag is toggled:
that is, if the Ability was going to Restore the Target, then now it will
damage it instead, and vice versa.

If the Target is Weak to the Ability and doesn't Absorb it, then:
  dmg = dmg * 2

If the Target Resists the Ability and doesn't Absorb it, then:
  dmg = [(dmg + 1) / 2]

Note that if the Target is both Weak to and Resists the ability, then the
damage will be doubled and then halved, leaving it unchanged.

If the Target has Death Weakness to the Ability, then if the Target has Death
Status already, the Ability misses.  Otherwise, the attack hits (and cannot
reflect) and inflicts Death, even if the Target also absorbs the Ability and
the Restorative flag was set.  No further Element steps are done.

If the Target is Recovered by the Element of the Ability, then the attack
automatically hits (without reflecting).  It will fully restore the Target's
HP and MP, remove any Death Status, and the Restorative flag is set, no
matter what it was set to before by the Ability or Absorbs.  No further
Element steps are done.

If the Target is Immune to the Element of the Ability, then all Elements
and Statuses inflicted by the Ability are removed, and the damage is reduced
to 0.  In addition, if any Statuses had been successful or the Ability had
the Earth element, then the Ability is considered to have missed as well.

In summary, the various resistances have the following priority:
  Death Weakness
  Recover
  Immune
  Absorb
  Weak/Resist
  Normal

 ---

After dealing with Elements, various checks involving Reflect, Misses and
Death are done.  The next damage check involves sanity checking:
  If (dmg > 9999) Then: dmg = 9999

If the attack does damage to MP and the target does not have the 'HP<->MP'
Materia equipped, then the sanity check is instead:
  If (dmg > 999) Then: dmg = 999 

The 999 'Sanity Check' is also used if the target *does* have 'HP<->MP'
equipped and the damage is dealt to HP instead of MP (the 'HP<->MP' Materia
not only reverses HP and MP, but it also reverses the max damage allowed
against that target).

 ---

Physical/Magical Immunity, Peerless Status and Petrify Status are now
rechecked.  If the Target has any of them (and the Ability has the right
affinity in the case of Phys/Mag Immunity), then the damage is reduced to 0.

 ---

Now comes the Lucky 7s check.  If the Attacker has 7777 HP, then the damage
is set to 7777, so long as some damage was going to be done.  Note that this
is after the possible 999 dmg cap.  If the damage was currently 0 or the
ability missed, then naturally, this part is skipped.

 ---

The final damage has, at that point, been calculated.  Various other checks
still remain, like counters and the final application of statuses and status
immunities, but the damage calculations are complete.

There are a few final notes on how the damage is then applied.  First, the
Restorative flag will determine whether the attack heals or harms the Target.

If it heals the target, then the amount 'dmg' will be added to the target's
HP or MP.  If it harms them, then 'dmg' will be subtracted from their HP or
MP instead.  The new HP/MP is capped at the target's Max HP or MP for
healing, while resultant HP/MP from damage is capped at 0.

However, there are two sanity checks related to overflow here:

  * If the attack heals the target, then if the new HP is *less* than the
    old HP, then the target's HP is set to their Max HP.  In other words,
    overflow here will fully heal the target.

  * If the attack harms the target, then if the new HP is *more* than the
    old HP, then the target's HP is set to 0.  In other words, overflow
    here will kill the target.


BUG: Both of these checks use *unsigned* numbers.  This means that a new HP
of -1 actually counts as as an HP of 4,294,967,295.  For the healing sanity
check, this is obviously higher than your old HP, so it thinks that the
healing succeeded and will not fix it.  The ability that causes this will
not immediately be considered to have killed you, but the game will later
see that you have negative HP and kill you off regardless.

What this means is that if you take enough healing to cause your HP to become
negative, you will instantly die, but if you take just enough such that your
new HP is less than your old but still greater than 0, then you will be
fully recovered instead.





-----------------------------------------------------------------------------
4. STATUSES
-----------

There are 32 major Statuses in the game, although a few of them are not shown
on the Status screen and are sometimes transparent to the user.  The statuses
available are thus:
  Death, Near-death, Sleep, Poison, Sadness, Fury, Confusion, Silence, Haste,
  Slow, Stop, Frog, Small, Slow-numb, Petrify, Regen, Barrier, MBarrier,
  Reflect, Dual, Shield, Death-sentence, Manipulate, Berserk, Peerless,
  Paralysed, Darkness, Seizure, Death Force, Resist, Lucky Girl, Imprisoned.

Of those, Death Force, Resist and Lucky Girl are nearly transparent to the
player, and a few of the others (like Imprisoned) are completely invisible
save for their effect.  Several are not listed on the Status screen; these
are: Dual, Seizure, Death Force, Resist, Lucky Girl and Imprisoned.

What follows is a breakdown of the statuses visual effects and gameplay
attributes.



---  -----------------
4.1  Status Attributes
---  -----------------

Death
-----
The ultimate offensive Status Attribute.  If you're successfully hit with it,
you are immediately reduced to 0 HP.  Death is also the state of having 0 HP.
You can protect from it, fortunately.  That is, you can protect yourself from
'Sudden Death', which is any attack that causes you to instantly die,
regardless of how much HP you have or how much damage the attack actually
caused.  However, if you are reduced to 0 HP by taking too much damage...
well, you can't protect against that at all.

Visuals:      Character lies down
Effects:      Character cannot Act
              Character flagged as 'Dead'
              Removes all Statuses except for 'Frog' and 'Small'
              V-Timer and C-Timer speed reduced to zero
Duration:     Until cured
Protected by: 'Petrify', 'Peerless', 'Resist', Safety Bit,
              Destruct+Added Effect, Odin+Added Effect, Death Force
Cured by:     Life, Life2, Phoenix Down, Angel Whisper, Phoenix



Near-death
----------
When your character is heavily wounded, but still able to fight, they are
classed as Near-death.  They kneel down and their HP indicator turns yellow
to notify of this.  Otherwise, this Status Attribute means nothing else; it
occurs only when your HP is 25% or less of your current Max HP, and you are
not yet dead.

NOTE: No status effect is actually used for this.  While a named status named
Near-death exists, it does not really have any link with the character
kneeling within the game code.  The status itself is unused, even though all
the effects do exist normally.

Visuals:      Character kneels
Effects:      None
Duration:     Until cured
Protected by: Anything that prevents HP loss
Cured by:     Anything that serves to boost your HP above 25% of Max HP



Sleep
-----
This nasty affliction is one of four temporary 'Can't Act' Status Attributes
in FF7.  Once under this Status, the character is asleep, and cannot fight
normally.  It has a particularly long timer, taking a while to wear off.
However, Sleep is easily reversed: any Physical hit is enough to wake up a
sleeping character.

Visuals:      Character kneels/has Zzz above head
Effects:      Character cannot Act
              Turn Timer speed reduced to zero
Duration:     100 V-Timer Units
Protected by: 'Petrify', 'Peerless', 'Resist', Ribbon, Headband,
              Seal+Added Effect, Hades+Added Effect
Cured by:     Any PAt%-based Hit, Esuna, Remedy, White Wind, Angel Whisper



Poison
------
Any character inflicted with this Status will continually take Poison
Elemental damage throughout the battle.  It won't be purged naturally until
the battle ends.

Note: The Status Attribute Poison is different from the Element Poison.  But,
if you are Immune to Poison Elemental, any attack that does Poison damage
will no longer inflict the Poison Attribute.  Only Poison *Immunity* works
for this though - Absorbing Poison would still allow you to be inflicted with
the Poison Status from things like Bad Breath or Added Effect (although you
would subsequently be healed by the status rather than taking damage from
it).

The reverse is also true: being Immune to the Status Attribute Poison will
mean that you are also considered Immune to the element.

A few notes about the damage Poison causes.  First, the damage counts as an
attack coming from the character affected to itself.  It cannot be countered
or Covered or similar.  It can also be affected by All Lucky 7s because of
this - taking Poison Damage of 7777 is unquestionably fatal.

Secondly, the 10 V-Timer Units between each effect of Poison only counts
from the last time the effect went off.  And since the effect of Poison
counts as an attack, it won't take effect while another ability is being
used - it will wait until after the current ability has ended, and then do
the effect and reset the timer then.

Third, Poison Damage will remove the Defend action, since it counts as its
own action by the character (it doesn't count as an action for Mime though,
thankfully).  Defending while under Poison status is almost futile.

Visuals:      Character kneels/flashes Green
Effects:      Character takes [1/32 of Max HP] of Physical Poison Elemental
                damage every 10 V-Timer Units (uses Max HP% Formula)
Duration:     Until end of battle
Protected by: 'Petrify', 'Peerless', 'Resist', Ribbon, Poison Ring, Star
              Pendant, Fairy Ring, Poison+Added Effect, Hades+Added Effect
Cured by:     Poisona, Esuna, Remedy, White Wind, Angel Whisper, Antidote



Sadness
-------
A character inflicted with Sadness is more subdued and careful in battle.
They tend to take less damage from attacks, but they find it difficult to get
angry at anything.  Hence, the growth of their Limit Bar is severely reduced.
The Limit Bar turns blue to notify you of this condition.

Visuals:      None
Effects:      Damage to character from Physical and Magical Formula attacks
                 is reduced by 3/10ths
              Limit Bar growth is halved
Duration:     Until cured
Protected by: 'Petrify', 'Peerless', 'Resist', Ribbon, Peace Ring
Cured by:     Hyper, Esuna, Remedy



Fury
----
Anyone in Fury status is more prone to rushing the enemy, and attacking them
with greater fervour.  As such, while they don't benefit from the reduced
damage of Sadness, they instead get an increase in the growth of their Limit
Bar, allowing them to pull of Limit Breaks with increased frequency.
However, their attacks are more erratic, and miss more often.  The Limit Bar
turns red to notify you of this condition.

Visuals:      None
Effects:      Character Hit Chance for PAt% and MAt%-based abilities is
                 reduced by 3/10ths
              Limit Bar growth is doubled
Duration:     Until cured
Protected by: 'Petrify', 'Peerless', 'Resist', Ribbon, Peace Ring
Cured by:     Tranquilizer, Esuna, Remedy



Confusion
---------
The pure opposite of Berserk, despite the fact that the character suffering
from Confusion doesn't have any increased damage potential.  You immediately
lose control of the character, and they will randomly attack their allies,
even themselves.  Fortunately, it's easy to cure; a single Physical hit will
take care of it.  However, a recently Confused character will always carry
out the last command they were asked to irregardless - but it will always be
against you, if possible.

Enemies under the Confusion status will continue to use their standard AI
script, but with the definition of Allies and Enemies reversed in their
target choosing routines.

Visuals:      Character continually spins in place
Effects:      Character randomly attacks allies
Duration:     Until end of battle
Protected by: 'Petrify', 'Peerless', 'Resist', Ribbon, Peace Ring,
              Contain+Added Effect, Mystify+Added Effect, Hades+Added Effect
Cured by:     Any PAt%-based Hit, Esuna, Remedy, White Wind, Angel Whisper



Silence
-------
The power of this affliction is often underestimated.  While under its
influence, you are unable to cast any Magic, Enemy Skills or Summons.
However, your other commands are untouched.  Its usefulness lies in using it
on the enemy; many of them have attacks that would be better left sealed with
Silence.

Visuals:      Character kneels/has speech bubble over head
Effects:      Character cannot use Magic/Enemy Skills/Summons
Duration:     Until end of battle
Protected by: 'Petrify', 'Peerless', 'Resist', Ribbon, Seal+Added Effect,
              Hades+Added Effect
Cured by:     Esuna, Remedy, White Wind, Angel Whisper, Echo Screen



Haste
-----
One of the best Status Attributes, Haste has your time bar filling up twice
as fast as normal.  However, on the flip-side, all timed effects like
Slow-numb, Barrier and so forth, will run out twice as quickly.  But, the
pros far outweigh the cons in this instance.

Visuals:      Character Animation speed doubled
Effects:      V-Timer and C-Timer speed doubled
Duration:     Until end of battle
Protected by: 'Petrify', 'Peerless', 'Resist', Slow Immunity
Cured by:     DeSpell



Slow
----
The complete opposite of Haste, Slow causes your time bar to fill up twice as
slow as normal.  But, it has its good side; Barrier, MBarrier, Slow-numb,
Death-sentence... all those take far longer to run out of time.

Visuals:      Character Animation speed halved
Effects:      V-Timer and C-Timer speed halved
Duration:     Until end of battle
Protected by: 'Petrify', 'Peerless', 'Resist', Time+Added Effect,
              Haste Immunity
Cured by:     DeSpell, White Wind, Angel Whisper



Stop
----
The second worst of the four temporary 'Can't Act' Status Attributes, Stop
completely shuts off the Time counter for that character.  On the other hand,
things like Barrier, MBarrier, Regen and so on will not count down during
this time, until Stop has worn off or been dispelled.

Visuals:      Character Animation speed paused
Effects:      V-Timer and C-Timer speed reduced to zero
              Character cannot Act
Duration:     30 Global Timer Units
Protected by: 'Petrify', 'Peerless', 'Resist', Contain+Added Effect,
              Time+Added EFfect, Choco/Mog+Added Effect
Cured by:     DeSpell, White Wind, Angel Whisper



Frog
----
Perhaps the worst of the transformation Statuses, Frog both reduces your
attack power, as well as preventing you from using almost all of your
Materia.  The only options available to you are Fight, Item, and if you have
it equipped, the Magic Spell 'Toad'.  You will not even get the option to
use Limit Breaks while transformed into a frog.

Visuals:      Character is a frog!
Effects:      All Physical attacks do 1/4 of Base Damage
              Character can only use Fight (not Limit), Item (including
                W-Item) or cast Toad
Duration:     Until end of battle
Protected by: 'Petrify', 'Peerless', 'Resist', Ribbon, White Cape,
              Transform+Added Effect, Hades+Added Effect
Cured by:     Esuna, Remedy, White Wind, Angel Whisper, Toad, Maiden's Kiss



Small
-----
While not as bad as Frog, this is still a terrible condition.  Magic is still
wide open to you, but every physical attack you do will have its Damage
reduced to 0 - fortunately, the 1 HP minimum capping occurs after this,
giving us 1 point of damage until modifications added after the random
variation are applied.  Elemental attacks and Added Damage Effects will use
the 1 HP damage as the basis for their calculations.  You can, however,
still use other sources of physical damage like Items with no penalty.

Visuals:      Character size is significantly reduced
Effects:      Damage of Physical Formula Attacks is reduced to 0
              The 1 dmg Minimum Cap allows Elemental effect and Added Damage
                Effects to still be used
Duration:     Until end of battle
Protected by: 'Petrify', 'Peerless', 'Resist', Ribbon, White Cape,
              Transform+Added Effect, Hades+Added Effect
Cured by:     Esuna, Remedy, White Wind, Angel Whisper, Mini, Cornucopia,
              Shrivel



Slow-numb
---------
One of the banes of the beginner player, Slow-numb can easily take out a
character within moments if you're not prepared for it.  Essentially, it's a
countdown to petrify; you have 30 units of time (as shown by the counter
above the character's head) to cure them of the affliction, or end the
battle.  Otherwise, they are inflicted by the Status Petrify.

Visuals:      Character has timer above head/flashes Grey
Effects:      30-unit Timer set on character
              When Timer reaches 0, Petrify is inflicted on character
Duration:     30 C-Timer Units
Protected by: 'Petrify', 'Peerless', 'Resist', Ribbon, Jem Ring, Safety Bit
Cured by:     Esuna, Remedy, White Wind, Angel Whisper, Soft



Petrify
-------
Completely turned to stone, this is a very bad Status Attribute to earn.  You
can't act, and even worse, you're flagged as 'Dead'; if everyone in your
party is flagged as 'Dead', then the game is over.  However, it's easily
curable, and while Petrified, you cannot be inflicted with any other Status
Attributes, or take damage in any way at all.  However, that also means you
can't have damage healed while Petrified either.

Visuals:      Character Animation speed paused/Character coloured Grey
Effects:      Character cannot Act
              Turn Timer speed reduced to zero
              Character flagged as 'Dead'
              Voids all damage
              Prevents Status Infliction
Duration:     Until end of battle
Protected by: 'Peerless', 'Resist', Ribbon, Jem Ring, Safety Bit,
              Contain+Added Effect
Cured by:     Esuna, Remedy, White Wind, Angel Whisper, Soft



Regen
-----
An alternative to the standard healing spells, Regen has the potential to be
greater than any of them, for half the cost of Cure3.  However, its healing
ability takes place over time, and it heals at a rate proportional to your
current Max HP value.  In addition, it has a short duration, and it can be
DeSpelled.

Regen takes effect every tick, and you are healed by a fraction of your Max
HP such that by the time 4 V-Timer Units have passed, you will have recovered
1/32 of your Max HP.  Effects that alter the rate the V-Timer increases by
will also affect Regen.

Visuals:      Character flashes Orange
Effects:      Character steadily gains 1/32 of their Max HP over every
                4 V-Timer Units
Duration:     127 V-Timer Units
Protected by: 'Petrify', 'Peerless', 'Resist'
Cured by:     DeSpell



Barrier
-------
A protective Status Attribute, and the first available to you.  It halves the
damage from all Physical attacks, but it has a limited duration.  The time
left for Barrier can be checked in the Barrier gauge in the left window, next
to the character name.

Visuals:      None
Effects:      Halves all Physical damage
Duration:     127 V-Timer Units
Protected by: 'Petrify', 'Peerless', 'Resist'
Cured by:     DeBarrier, DeSpell



MBarrier
--------
The counterpart of Barrier, MBarrier simply halves the damage from all
Magical attacks.  Again, it only has a limited duration; the time left for
MBarrier can be checked in the MBarrier gauge in the left window, next to the
Character name.

Visuals:      None
Effects:      Halves all Magical damage
Duration:     127 V-Timer Units
Protected by: 'Petrify', 'Peerless', 'Resist'
Cured by:     DeBarrier, DeSpell



Reflect
-------
One of the most interesting Status Attributes, Reflect allows you to bounce
away certain spells up to a maximum of four times per casting per character.
A list of spells that cannot be reflected can be located in the next section.

Note that Perma-Reflect (granted by the Reflect Ring Accessory and used by
the enemy Mirage) has an infinite amount of uses, but can only Reflect *once*
per attack.  This becomes important when two targets are bouncing a spell
between each other when they both have Reflect.

Visuals:      None
Effects:      Will reflect spells up to four times back at caster, or random
                enemy if caster is an ally
              Will only reflect certain magical spells
Duration:     Until end of battle or exhausted
Protected by: 'Petrify', 'Peerless', 'Resist'
Cured by:     DeBarrier, DeSpell



Dual
----
A dummied-out status with no outward effect.  Only the fact that it has a
name gives it a presence in this document.

Visuals:      None
Effects:      None
Duration:     Until end of battle
Protected by: 'Petrify', 'Peerless', 'Resist'
Cured by:     None



Shield
------
A very powerful defensive Status Attribute, second only to Peerless.  It
makes you immune to the physical and restorative elements, and absorbs the
normal ones.  However, it will not defend against Hidden Element or
Non-Elemental damage.  Note that the Item Command (but not the W-Item
Command) is able to breach Shield and still cause full damage, whether
they're Elemental items or not - this is a good thing, since it means you can
still heal with Items.

Visuals:      None
Effects:      Absorbs Fire, Ice, Lightning, Earth, Poison, Gravity, Water,
                      Wind and Holy Elements
              Immune to Cut, Hit, Punch, Shoot, Shout and Restorative
                        Elements
              Does not defend against Item damage (except through W-Item),
                Hidden Element or Non-Element attacks
Duration:     64 V-Timer Units
Protected by: 'Petrify', 'Resist'
Cured by:     DeBarrier, DeSpell



Death-sentence
--------------
Under this condition, a counter positioned above the character's head begins
to count down to zero.  If it does reach zero, then the Status Death is
inflicted on the character, subject to protection from Death.

Visuals:      Character kneels/has timer above head
Effects:      60-unit Timer set on character
              When Timer reaches 0, Death is inflicted on character
Duration:     60 C-Timer Units
Protected by: 'Petrify', 'Peerless', 'Resist', 'Death Force', Ribbon,
              Safety Bit
Cured by:     None



Manipulate
----------
The only Status Attribute that cannot be used on your party, Manipulate is a
very useful tool.  Using it on an enemy, if they're susceptible to it, will
place the enemy under the character's command.  Note that each character can
only Manipulate one enemy at a time, and a single Physical hit will free the
enemy from your control.

Visuals:      Character flashes Cyan
Effects:      Character is controlled by whomever used Manipulate on them
Duration:     Until end of battle
Protected by: 'Petrify', 'Resist', 'Sleep', 'Stop', 'Paralysed'
Cured by:     Any PAt%-based Hit, White Wind



Berserk
-------
This is a very risky Status Attribute.  On the plus side, a character under
this Attribute hits harder than usual with every attack.  But on the minus,
they cannot be controlled, and they randomly attack the enemy any time they
can.  Berserk has a secondary use too; under Berserk, enemies will only use a
single designated Berserk Attack.  This can be an effective way of cutting
out certain nasty abilities.

Visuals:      Character flashes Red
Effects:      Character's Physical Damage is multiplied by 1.5
              Character attacks random Enemy with Berserk Attack
Duration:     Until end of battle
Protected by: 'Petrify', 'Peerless', 'Resist', Ribbon, Peace Ring,
              Mystify+Added Effect
Cured by:     Esuna, Remedy, White Wind, Angel Whisper



Peerless
--------
The ultimate defensive Status Attribute.  Unfortunately, only one character
has the ability to use this: Aeris.  When used, it grants the target full
immunity to all Physical and Magical attacks, and since every attack in the
game is one of these, it essentially means that no attack in the game can
touch you while you are under this status.  Status attributes from other
sources are also defended against for the exact same reason, with the
exception of Imprisoned which is a special case.  Unfortunately, Peerless has
a limited duration and the immunity makes it impossible to heal while under
it, but it is still a formidable Attribute.

Visuals:      Character flashes Yellow
Effects:      Voids all damage
              Immune to all Status Attributes except Imprisoned
Duration:     64 V-Timer Units
Protected by: 'Petrify', 'Resist'
Cured by:     None



Paralysed
---------
The least powerful of the temporary 'Can't Act' Status Attributes, it's still
a pain at times.  It acts almost exactly like Sleep and while it lasts for a
very short time, you can't cure it with a simple Physical attack.

Visuals:      Character kneels/Character animation speed paused
Effects:      Character cannot Act
              Turn Timer speed reduced to zero
Duration:     20 V-Timer Units
Protected by: 'Petrify', 'Peerless', 'Resist', Ribbon, Jem Ring
Cured by:     Esuna, Remedy, White Wind, Angel Whisper



Darkness
--------
A nuisance at best, Darkness simply halves the accuracy of your weapon,
causing you to miss more often with weapon-based attacks.  It's easily cured,
however, and it has little tactical use, especially since the means of
inflicting it is so rare.

BUG: Due to an oversight, only the Attack, Morph, D.blow, Mug, Slash-All,
Flash, 2x-Cut and 4x-Cut commands are affected by Darkness.  Although other
physical abilities were intended to suffer from this as well, they do not.
Since enemies do not use any of the previously named commands, they are
IMMUNE to the effects of Darkness.

Visuals:      Character kneels/flashes Black
Effects:      Attack% of equipped weapon is halved
Duration:     Until end of battle
Protected by: 'Petrify', 'Peerless', 'Resist', Ribbon, Silver Glasses,
              Fairy Ring
Cured by:     Esuna, Remedy, White Wind, Angel Whisper, Eye drop



Seizure
-------
This Status exists... but is never actually used.  It's of interest to
hackers only, really.  It's similar to the 'Inverse Regen' used by
Bottomswell, but not exactly the same.

Under Seizure, HP is drained over time.  In all respects, it is the exact
opposite of Regen - they even exactly cancel each other out when both are
active.

Visuals:      None
Effects:      Character steadily loses 1/32 of their Max HP over every
                4 V-Timer Units
Duration:     127 V-Timer Units
Protected by: 'Petrify', 'Peerless', 'Resist'
Cured by:     None



Death Force
-----------
A useful status, which allows you to temporarily give yourself protection
from Death until the end of the battle.  Its usefulness stems from the fact
that very few enemies actually use the Death Status.  Recognise them, and you
can possibly spare an Accessory slot or a few Materia slots and just rely on
Death Force for protection when you need it.  Of course, the disadvantage is
that the immunity is temporary; if that character gets hit by DeSpell or
White Wind or gets killed, then they will lose the immunity immediately.

Visuals:      None
Effects:      Immune 'Death'
Duration:     Until end of battle
Protected by: 'Petrify', 'Peerless', 'Resist'
Cured by:     DeSpell, White Wind



Resist
------
You are never given any indication of when you have Resist, but its effects
are quickly apparent: any Status change is prevented by the power of Resist.
Unfortunately, that can also mean, for example, if you have Frog and then
Resist is placed on you, you cannot then cure Frog without removing Resist
first.  Its best use is to trap enemies with certain Status Attributes so
that they can't heal themselves.  As a secondary use, it can be used as a
temporary defense against nasty Statuses, but it's expensive, and not easy to
remove.

Visuals:      None
Effects:      Immune to all Status Attributes except Resist and Imprisoned
Duration:     Until end of battle
Protected by: 'Petrify', 'Peerless'
Cured by:     DeSpell, White Wind



Lucky Girl
----------
Only one attack in the game can inflict this Status: Lucky Girl.  This is one
of the Limit Combinations in Cait Sith's Slot Limit.  It is a somewhat useful
status, causing all subsequent attacks to be Critical Hits.  However, this
is offset by its rarity - most players will go through the game without ever
seeing Lucky Girl.

Visuals:      None
Effects:      All attacks are automatic Critical Hits
Duration:     Until end of battle
Protected by: 'Petrify', 'Peerless', 'Resist'
Cured by:     None



Imprisoned
----------
The final temporary 'Can't Act' Status.  Unfortunately, the temporary nature
of this status is dependant on what is causing it; various enemies have a few
ways of dealing out this attribute, and each requires its own method of
removing it.  In addition, the character is flagged as 'Dead'.  It is easily
the worst of the four 'Can't Act' Statuses.

Imprisoned has three versions depending on who uses it.  Reno's Pyramid
and Carry Armor's Arm Grab both have the same effect as Stop on the target.
Bottomswell's Waterpolo, on the other hand, has the same effect as Paralysed
on the target, and *also* places an 'inverse Regen' effect on the target,
causing their HP to fall.  However, characters under Bottomswell's version of
Imprisoned can still be targetted by abilities.

Visuals:      Character Animation speed paused
Effects:      Character cannot Act
              Character flagged as 'Dead'
              Character cannot be targeted by attacks/spells
                (Pyramid/Arm Grab version only)
              V-Timer and C-Timer speed reduced to zero
                (Pyramid/Arm Grab version only)
              Turn Timer speed reduced to zero
                (Waterpolo version only)
Duration:     Until end of battle
Protected by: 'Petrify'
Cured by:     Killing Pyramid, Waterpolo or Left Arm/Right Arm



---  -------------------------
4.2  Special Notes On Statuses
---  -------------------------

In addition to the above, the following notes must be taken into account.


Colours
-------
The different colours you flash have a priority system; if you currently have
a Status that has a higher priority than another one you have, then you will
flash the colour of the higher priority Status.  The priorities are:

 Highest Priority                                             Lowest Priority
 ----------------------------------------------------------------------------
 Slow-numb    Poison    Berserk    Peerless   Darkness    Regen    Manipulate
    GREY      GREEN       RED       YELLOW     BLACK      ORANGE      CYAN


Thus, if your character has both Darkness and Berserk on them, they'll flash
Red rather than Black, because Berserk is the more important one to know
about.  (For instance, you don't want to mistake Slow-numb for Death-sentence
just because you've got Regen on, do you?)


Status Incompatibilities
------------------------
Various statuses will cancel out other ones as soon as they're inflicted upon
a character.  The following table will demonstrate this:

Status Name   Cancels
-----------   -------
Death         All Status Attributes except Frog and Small
Sleep         Manipulate
Sadness       Fury
Fury          Sadness
Haste         Slow
Slow          Haste
Stop          Manipulate
Petrify       Slow-numb, Manipulate
Paralysed     Manipulate


Removing Conditions
-------------------
What follows are the various ways of removing multiple Status Attributes at
the same time.  Those not listed are self-explanatory (ie they tell you what
they cure.  Also, if something cures Petrify, then it also cures Slow-numb)

Note: Healing spells and effects work according to the state of the character
before the ability takes effect.  As such, certain factors may prevent the
healing ability from using its full effect, even though the ability may be
able to remove that factor on the first cast.  For example, White Wind takes
two tries to be able to remove, say, Frog and Resist; the first time, it
can't remove Frog because of Resist.  The second try, Resist is gone, so it
can finally remove Frog.  Keep this in mind.


Status Name    Esuna/Remedy  DeBarrier  DeSpell  White Wind  Angel Whisper
-----------    ------------  ---------  -------  ----------  -------------
Death               -            -         -         -             O
Sleep               O            -         -         O             O
Poison              O            -         -         O             O
Sadness             O            -         -         -             -
Fury                O            -         -         -             -
--------------------------------------------------------------------------
Confusion           O            -         -         O             O
Silence             O            -         -         O             O
Haste               -            -         O         -             -
Slow                -            -         O         O             O
Stop                -            -         O         O             O
---------------------------------------------------------------------------
Frog                O            -         -         O             O
Small               O            -         -         O             O
Slow-numb           O            -         -         O             O
Petrify             O            -         -         O             O
Regen               -            -         O         -             -
---------------------------------------------------------------------------
Barrier             -            O         O         -             -
MBarrier            -            O         O         -             -
Reflect             -            O         O         -             -
Shield              -            O         O         -             -
Death-sentence      -            -         -         -             -
---------------------------------------------------------------------------
Manipulate          -            -         -         O             -
Berserk             O            -         -         O             O
Peerless            -            -         -         -             -
Paralysed           O            -         -         O             O
Darkness            O            -         -         O             O
Death Force         -            -         O         O             -
Resist              -            -         O         O             -


Note: Due to space constraints, it is difficult to fit any more abilities
onto the above list.  What's shown above are the most common ways of removing
multiple statuses.  One more status removal item can be summarised as such:

  Holy Torch: Cures everything DeSpell does except 'Death Force' and
              'Resist'.


Reflection
----------
Finally, the following skills can be reflected using the Status Reflect.

Magic:
  Cure, Cure2, Cure3, Poisona, Esuna, Resist, Life, Life2, Regen,
  Fire, Fire2, Fire3, Ice, Ice2, Ice3, Bolt, Bolt2, Bolt3,
  Quake, Quake2, Quake3, Bio, Bio2, Bio3, Sleepel, Confu, Silence,
  Mini, Toad, Berserk, Haste, Slow, Stop, Barrier, MBarrier, Death,
  Freeze, Break, Tornado, Flare, Wall

Enemy Skills:
  Frog Song, L4 Suicide, Magic Hammer, Flame Thrower, Laser, Matra Magic,
  Aqualung, Shadow Flare, Pandora's Box

All Summons and Items are non-reflectable.



As a companion to this section, here are the specific Magic and Enemy Skills
that *CANNOT* be reflected.

Magic:
  Demi, Demi2, Demi3, Reflect, DeBarrier, DeSpell, Escape, Remove, Comet,
  Comet2, FullCure, Shield, Ultima

Enemy Skills:
  White Wind, Big Guard, Angel Whisper, Dragon Force, Death Force,
  Bad Breath, Beta, Trine, Magic Breath, ????, Goblin Punch, Chocobuckle,
  L5 Death, Death Sentence, Roulette



-----------------------------------------------------------------------------
5. GAME OVER
------------

There are a number of ways to lose the game, most of which can only occur in
battle.

The most common way is to have all three characters in your battle party
flagged as 'Dead'.  This involves losing each of your characters to any
of the following situations:

 1. Gaining the Status 'Death'
 2. Gaining the Status 'Petrify'
 3. Gaining the Status 'Imprisoned'
     (This occurs if you are either picked up by one of Carry Armor's arms,
      or you are surrounded by Reno's Pyramid or Bottomswell's Waterpolo.
      You must destroy whatever is imprisoning the character to bring them
      back)
 4. Being knocked out of battle by Eat (used by Hungry), Goannai (used by
      Ghost Ship) or Whirlsand (used by Ruby Weapon).  Midgar Zolom's Blown
      Away, Scissors(Upper)'s Scissor Tornado and Gighee's Sun Diver all
      knock you out of battle, but flag the character as escaped instead of
      dead; therefore if all other characters die or are knocked out, the
      battle itself will count as an escape.

Any character still flagged as 'Dead' at the end of a successful battle will
gain no EXP or AP from the defeated enemies.  However, the Status 'Death' is
the only one that lasts into the next battle if you don't cure it.

You will also lose the battle in one other special case: running out of time
in the Emerald Weapon battle.  This only occurs if you do not have the
Underwater Materia equipped during that battle, however.

Note that if you lose a battle in Battle Square, the Five Gods Pagoda or Fort
Condor, you won't lose the game, just the battle.  In all other cases, losing
a battle means 'Game Over'.


Finally, if you run out of time in the Mako Reactor 1 Mission, you will
automatically lose the game, without having to be in battle.



-----------------------------------------------------------------------------
6. CREDITS
----------

A large majority of the work here is my own... but there are some people that
I feel it is necessary to mention on this long road.


The Denizens of alt.games.final-fantasy.rpg:
  My old haunt.  More a shout-out rather than credit, but hey, it's where I
began, really ^_^  It's also where I met...


Qhimm:
  ...with whom I worked on the FF8 savemap with.  Lots of fun, and we
actually got something useful out of it: a working save editor that he
programmed named Griever.
  It was also on his site that I met others who took the same interest in
this field.  Which leads to....


The Denizens of Qhimm's Forum:
  The SaiNt.  Ficedula.  Alhexx.  And *especially* L.Spiro.  There were
others, of course, but those are the names who stand out.  Enemy Stats and
Attack Properties would've been hell to compile without the effort made by
those at Qhimm's Forum.  I collected data myself, but understanding it?
L.Spiro provided the first and most important step in deciphering the attack
and enemy dumps.


The GameFAQs FF7 LLG Community:
  BrutalAI, lolo26 and GarlandG, as well as others I probably can't remember
now.  The topics they maintained regarding various low level challenges had
a tendency to ask more detailed questions than most, and research more
detailed answers for them.  They also tended to be the first to notice when
something was truly amiss in these documents.
  


And... that's that, really.  Hope you've enjoyed the show.


-----------------------------------------------------------------------------

The FF7 Battle Mechanics, copyright 2001-2009 Terence Fergusson