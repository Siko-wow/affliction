# Affliction Warlock Guide

Hey guys, with all the new locks (looking at you padredoom) and affliction locks' importance on yogg-saron, I wanted to write a ~~quick~~ guide from what I've learned playing affliction in phase 1.
I'll leave gear, consumes, etc. out and focus on fight mechanics / rotation.
The guide is broken into progressive levels to hopefully make this more digestible, sorry in advance for the long post :sweat_smile:

## Beginner -- The Basics

Never played affliction before?
As briefly as possible: maintain corruption, haunt, unstable affliction, and curse of agony while spamming shadow bolt.
When the boss reaches 25%, use drain soul instead of shadow bolt, but maintain your dots. You shouldn't have to recast corruption, because it gets refreshed whenever haunt or shadow bolt lands, or whenever you cast drain soul.
- For two targets, multi-dot. Corruption is your most important dot, followed by unstable affliction.
- For aoe, spam seed. If your seeds are not getting popped, tab target to seed different mobs.

## Intermediate -- Warlock Fundamentals

Playing a caster is all about uptime. Because we have to stand still to cast, you want to limit your movement and instant cast when you do have to.
As an affliction lock, you only have two instant cast damaging abilities: corruption and curse of agony. On the opener, you cast both, so try to get into position on those 2 globals.
After that, you won't be recasting corruption much, so that leaves 1 global every 24 seconds that you can move while maintaining 100% uptime.
Thankfully, we have life tap, which you'll be using on all but the shortest fights.
Try to time your life taps with when you move, rather than wasting them on a portion of the fight where you can stand still.
Pay attention to your health and raid mechanics, but most of the time when you're moving you can life tap.
Use rocket boots to cover as much ground as possible in your 1-2 globals life tapping.
It takes some knowledge, but try to place your teleport in a convenient spot on movement-heavy bosses, so you can use that instead.
Note that taking the teleport costs a global, though, so sometimes it's better to walk and life tap.
For example, in phase 1, port is nice for sarth avoiding walls if you are in trouble, on grob or maex to get back to the group, or on thaddius to swap sides.
In phase 2, use your port on XT to return back to the clump, on iron council to return back to the rune of power, on thorim to return to your stack,
on freya to get away from the exploding ads, and on vezax to get out of the stack when you're marked.

As with all dps, you also want to line up all your cooldowns together, ideally during a high damage window (e.g. during hero, when you can stand still, or during execute phase).
You should have a macro to pop all your cooldowns at once, so you don't have to waste time hitting each one at a time. Here's what I use for execute phase:
```
#showtooltip
/stopmacro [nocombat]
/stopmacro [nogroup:raid]
/cast Potion of Speed
/use 10
/use 13
/use 14
/cast drain soul
/cqs
```
This pops a potion, gloves, both trinkets, and casts drain soul all in one click.
I stop the macro out of combat or a raid so I don't accidentally pop potions.
You can use this macro even if your potion is on cooldown -- it'll still pop everything else.
I have others that casts shadow bolt / seed for popping cooldowns before execute phase, e.g. this one for my first trinket slot:
```
#showtooltip
/use 13
/use 10
/cast [nomod:cmd] Shadow Bolt; seed of corruption
/cqs
```

To maximize your uptime, you also want a clean opener.
Generally, you should open: shadow bolt -> haunt -> unstable affliction -> corruption -> curse of agony.
You can swap haunt and unstable affliction, but importantly this gives guarantees your shadow bolt will land before you cast corruption.
If you can, precast shadow bolt so that the cast goes off as the pull timer reaches zero. I use this macro to precast:
```
#showtooltip
/stopmacro [nogroup:raid]
/cast [nomod:shift] potion of wild magic; potion of speed
/use 10
/cast shadow bolt
/cqs
```

## Advanced -- Affliction Tips and Tricks

If you've got the above down, you're 80% of the way there. Below are some tips for optimizing dps in each phase of the fight.

### Opener
- On fights short fights (< 1 minute long or so) or if you're going to recast corruption (see next section) pre-pop potion of speed.
Otherwise, pre-pop potion of wild magic.
- Precast life tap before pull. If you have illustration, prestack that to 10.
As dying curse can proc off life tap, I try to proc it ~45 seconds before we pull, so I don't accidentaly proc it while stacking illustration.
- Send your pet onto the boss, with shadow bite auto-cast, and forget about it.
I macro /petattack into my haunt spell, since I generally only cast it on bosses but am not spamming it.
Make sure to remove this for yogg-saron.

### Middle
- Try not to clip your dots, i.e. recast them before they fall off.
It's better to lose some dot uptime casting another shadow bolt than to clip your dots.
This is especially so for curse of agony, as its damage is backloaded.
If you're not going to be able to hit the boss for an extended period of time, e.g. if the boss becomes untargetable, or you get stunned (e.g. maex), or you have to move, it may be worth it to clip to maintain dot uptime.
- On the other hand, clipping haunt is totally fine, and you should try to maintain 100% haunt uptime.
As haunt has a travel time, you may need to cast it earlier based on how far you are from the boss.
I have a weakaura to help with this (see below).
- Maintain the glyph of life tap buff. I try to prepare for execute phase by timing a life tap and haunt just before the boss reaches 25%.

### Execute
- Do _not_ let haunt fall off.
Since you're no longer shadow bolting, you use haunt to maintain your shadow embrace stacks, and if haunt falls off, so does your stacked 15% damage buff.
Also, try not to let corruption fall off.
When you have tons of haste, the corruption might only last 6 or 7 seconds, which goes by fast.
It might also disappear (and not be able to be refreshed) up to ~1 second early because of its interaction with haste, so beware.
- Often, you won't get full length drain soul casts off, as you'll have to stop in the middle to cast haunt or re-up your dots.
Try to end the cast right after a tick.
Make sure you have some addon that shows you when drain soul ticks.
I use quartz, and also have a weakaura that visually shows the ticks and makes a noise whenever the tick goes off (see below).
- When the boss is about to die, it's better to keep draining rather than re-up dots.
This is especially true for curse of agony, since it lasts so long and does poor damage early on.
You can even let haunt drop if the boss is going to die in a couple of ticks.

## Expert - Snapshotting and Execuse Phase
Made it all the way here? Thanks for reading! Now it gets fun... and technical.

Playing affliction is all about optimizing your corruption and drain soul damage.
Your corruption recalculates damage based on enemy debuffs (e.g. shadow embrace 15%, haunt 23%, or earth and moon 13%) on each tick, so don't worry about these at all.
It recalculates damage based on your haste and spell power every time it's refreshed, so you also don't really worry about this because corruption gets refreshed all the time.
However, it snapshots critical chance and personal damage buffs (e.g. tricks 15% or death's embrace 12% on targets below 35% health) on cast --
whatever crit chance and personal damage buffs you have when you cast apply to the corruption until it falls off.
This is why you prepop potion of wild magic and why affliction locks should get tricks at the start of the fight, if there's no threat problems.
If you get a tricks'd corruption, I'm pretty sure it's a dps loss to recast at 35% for death's embrace, unless you get a second tricks, but people still do it because it's still a parse increase (since tricks doesn't count towards parses).
Lastly, watch out because sometimes the game won't let you recast corruption, if your spell power of the existing one is higher than your current spell power.
It'll display an error message like "you have a more powerful spell active", but that can be hard to see.
I just got a weakaura that is supposed to tell you when (a) you're supposed to recast corruption and (b) you aren't able to because of the spell power difference, so hopefully that works.

Some bosses give you buffs that give you increased crit chance or damage. It's almost always worth it to recast corruption after gaining these, for the snapshot. If you don't, you're seriously gimping your damage and parse. For the first two phases, these buffs are:
- Spore buff on __Loatheb__ (50% crit chance) 
- Positive / negative charge on __Thaddius__ (10% damage per charge, usually ~100% damage)
- Spark on __Malygos__ (50-100% damage based on stack)
- Rune of power on __Iron Council__ (50-100% damage based on stack)
- Mushroom buff on __Freya__ (25% damage, but you need to be in it to cast, so don't think you need to think about this)
- Sara's Fervor on __Yogg-Saron__ (20% damage, phase 1 buff, idt this actually matters)
If you're super sweaty, on iron council, if you get a double rune, you should cast corruption on Steelbreaker and maintain it all through phases 1 and 2, so you have the 100% damage buff for the phase 3 burn.

That's a lot of text for what may literally just be, recast corruption when this weakaura tells you to, if the weakaura actually works. But hey, sometimes it's nice to know the why.

The most fun part of affliction, imo, and the area for highest skill expression is execute phase.
No class matches the throughput of an affliction warlock at boss health < 25%.
Your drain soul snapshots its spell power, haste, and personal damage buffs on cast. If you can line up several procs / cooldowns at once, you do _crazy_ damage.
To do this, you'll often want to clip your drain soul, i.e. recast it right after a tick, either to:
- Snapshot new buffs not included in your previous drain
- Get a new, full-length drain before buffs fall off

You should consider the relative importance of different buffs. For example, in approximate order:
- Heroism (30% haste)
- Eradication (20% haste) / power infusion (20% haste) - Dying curse (765 spell power, ~20% of your spell power so almost 20% damage increase)
- Potion of Speed (15% haste) - Hyperspeed accelerators (10% haste)
- Tailoring cloak enchant (295 spell power)
- Glyph of life tap (spell power = 20% of spirit)
Of course, there's other trinkets and buffs, not to mention all the encounter-specific ones.

The decision making here is all about when to clip or hold a drain, while maintaining haunt and your dots. Let's go through a few examples.

> You cast drain soul and dying curse procs
The <proc on spell cast> trinkets like dying curse don't actually apply to the spell that proc'd it, so you should recast drain after one tick.

> The boss is high health, you're draining and have no buffs, and notice haunt, ua, and CoA are about to fall off
Finish your current tick, then refresh haunt and both dots, prioritizing whichever is going to fall off first, then redrain.
If your dots are going to get their full duration, it's better to refresh them than drain, and you have no buffs to worry about snapshotting.

> You cast haunt and notice dying curse and eradication are going to fall off in 4s
Cast drain soul after haunt, then clip it right before your buffs fall off, and hold that drain as long as you can.

> You're draining, multiple buffs only have 1s left, and unstable affliction falls off
Probably best to recast drain and ride it out until you have to cast haunt, losing UA uptime.
After the haunt, you can probably refresh UA, because you won't have as many buffs to snapshot.

> You're draining and notice haunt has ~5s left, while multiple buffs have only 3s left
Finish your current drain tick, then cast haunt, then cast a full length drain.
You're refreshing haunt early here, but this lets you get a full length drain with all your buffs.
If you instead continue draining / recast drain, you'll only get a couple ticks of drain off before you have to refresh haunt, and by the time you cast haunt, your buffs are gone.

Lastly, let's talk about pet management.
Your felhunter does pretty good damage, so you'll want it on the boss as much as possible.
You can micromanage your pet to try to avoid raid damage, like sarth fire walls.
I have /petattack and /petfollow macros bound, but mostly for pvp.
If you can, rebind one or two of your pet bars, unless you actually like hitting ctrl-4 and ctrl-5,
because the silence and dispel come in helpful in raid sometimes, especially the silence as your pet casts it, so it's off global and can be cast while you're casting.

Alright! That's basically all I have. Hopefully you found this helpful and not too tedious to read.

## P.S. -- Parsing Strats
- Use inferno when there's 1 minute left.
On fights shorter than 1 minute, you can spawn the inferno on you right before the pull.
It does a ton of damage, especially on fights where aoe counts. The inferno can easily turn an orange parse into a pink one.
- Spiced Mammoth Treats increase your pet's damage.
They don't use a global, so you can even use one after you cast inferno without losing uptime.
- If we have multiple shamans in the raid, ask for a second hero when you put your inferno down.
It can get hero even if you're exhausted.
I don't think you have to worry about snapshotting like dks ~~do~~ did (jk they still snapshot attack power).
- You can pre-cast shadow bolt to _land_ on the pull timer, i.e. a second or so before the pull timer finishes.
Just make sure not to do it too early and grief the whole raid.
If you do this, you can do 2 shadow bolts in the opener before haunt.
- I'm not usually in range to sapper, but I macro saronite bombs into my gloves active for free dps. This shoots the bomb at your mouse, without making you click, and queues up a shadow bolt after:
- If you know the fight length, you can try to time dying curse and other procs to pop during hero and again during execute phase
```
#showtooltip
/use 10
/cast [@cursor] saronite bomb
/cast [nomod:cmd] Shadow Bolt
/cqs
```
- Beg your raid leader for hero during execute phase.

## Weakaura
