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

Lastly, it takes some knowledge, but try to place your teleport in a convenient spot on movement-heavy bosses, so you can use that instead.
Note that taking the teleport costs a global, though, so sometimes it's better to walk and life tap.
In phase 1, port is nice for sarth avoiding walls if you are in trouble, on grob or maex to get back to the group, or on thaddius to swap sides.
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
You can swap haunt and unstable affliction, but importantly this guarantees your shadow bolt will land before you cast corruption.
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
As dying curse can proc off life tap, I try to proc it ~45 seconds before we pull, so I don't accidentally proc it while stacking illustration.
- Send your pet onto the boss, with shadow bite auto-cast, and forget about it.
I macro /petattack into my haunt spell, since I generally only cast it on bosses but am not spamming it.
Make sure to remove this for yogg-saron.

### Middle
- Try not to clip your dots, i.e. recast them before they fall off.
It's better to lose some dot uptime casting another shadow bolt than to clip your dots.
This is especially so for curse of agony, as its damage is backloaded.
If you're not going to be able to hit the boss for an extended period of time, e.g. if the boss becomes untargetable or you get stunned (e.g. maex) or you have to move, it may be worth it to clip to maintain dot uptime.
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

If you're super sweaty, on iron council, if you get a double rune, you should cast corruption on Steelbreaker and maintain it all through phases 1 and 2, so you have the 100% damage buff for the phase 3 burn.

That's a lot of text for what may literally just be, recast corruption when this weakaura tells you to, if the weakaura actually works. But hey, sometimes it's nice to know the why.

The most fun part of affliction, imo, and the area for highest skill expression is execute phase.
No class matches the throughput of an affliction warlock at boss health < 25%.
Your drain soul snapshots its spell power, haste, and personal damage buffs on cast. If you can line up several procs / cooldowns at once, you do _crazy_ damage.
To do this, you'll often want to clip your drain soul, i.e. recast it right after a tick, either to:
- Snapshot new buffs not included in your previous drain
- Get a new, full-length drain before buffs fall off

You should consider the relative importance of different buffs.
Here's some buffs we get, in approximate order of importance:
- Heroism (30% haste)
- Eradication (20% haste) / power infusion (20% haste) - Dying curse (765 spell power, ~20% of your spell power so almost 20% damage increase)
- Potion of Speed (15% haste) - Hyperspeed accelerators (10% haste)
- Tailoring cloak enchant (295 spell power)
- Glyph of life tap (spell power = 20% of spirit)

The decision making around execute phase is all about when to clip or hold a drain, while maintaining haunt and your dots.
Let's go through a few examples.

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

## P.S. (Parsing Strats)
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
- If you know the fight length, you can try to time dying curse and other procs to pop during hero and again during execute phase
- Beg your raid leader for hero during execute phase.
- I'm not usually in range to sapper, but I macro saronite bombs into my gloves active for free dps. This shoots the bomb at your mouse, without making you click, and queues up a shadow bolt after:
```
#showtooltip
/use 10
/cast [@cursor] saronite bomb
/cast [nomod:cmd] Shadow Bolt
/cqs
```

## Weakaura
I pulled this weakaura from Crix back at the start of the expansion and have edited it to my linking.
It's still a WIP so I might change this from time to time.
And sorry if things are broken!
```
!WA:2!S37cGTX11HcQbWkYM2Xr)SITSS8y6ijczkksqXpYYkoe8Ve)jas9ZYHyaWaoJiaMrZmGKqXPEdtAIsARRlJR7N8XPCBJttCCtzADsZU7lPQVx2DFzZRZYxEzN02x67XTP)EzBYt2j5zN269CU378dyajffPtStG9icmZDUZDUN)N75CUCNE76XBPHMBOLTNF7z2EMR82u3EALcgAk5YjMPtj5Cz0el8jUJR2LyELcYP5hriTH6D)iNrtWq6r5JPORZNqvmTCw4AXkMnRU6USVy3ZyiQjROrpFSbfkimFNc6g8Xe04JU0iIg8DQjBWNqPyHmArBzF8IZiQ1m9VZAiOAiNxuBE7VWhv9EgsEcjJSc5YD4ycPNmNGU0H7cE45fmKvkm3OAYfMe61MC(wu192PIMwrv868XHxkLPe1EGefeu1LuGRV4yDWNghtKhH6w7tOybJ4I4PgLCM9y)2mIMsADEHcz4hUa)y6I8D2LU6wTVACfdYyqDB2NPtfLCzuMUG(1SpZygY5KnkPExpYze0YPKEYhLVlnb5c4eqo(rLtp5sPu0YiQHVBz0uuv3ASCYx(YcAz4hf6ndz1utlmHs)DnxQXAl(mnF5tetBMHH5wrdoTs0V03x(M)yFW)Qf)tE3liuiTKI2ikYfms1z3dnA3XxG29DQKtr7eCCCHJwulN6DlzyOQ)Gh(WyF3GSYHD68d3MgaTH3k9wJRBiOzutQSYfK1LQjg8hJAM1qtEIje1039(1yF99pFgXua4E0sQIA919aJ0ZydedENfJluuti6S6QI5Y1Fg9AwsVykXPelyKaAT8mlmENDKy0XtmAhXh15sJOjcxkEIr6EGbIxqiVOEnXjxivFIc5mKIvegfPuZjusuBoaUrhc1Cn4nwuRGqUtddny0)4ZjuGHI0Q5BRNRkkOlMWaqRNWqAlMpqSckfexmdm8Wwmooy10fbIGm6ZInfFvmpwS8aKQhZheUbZJz(qMh38Td)DFLFMyze1tRfReF8mLMrBk6a4Tmp8gfxCcCMSMy5ueY0tmD5llUR45lcq1AIbZkP3Lzp1epnGsRJFlLHqo4ff)6IPyOdu4w4WHhjCJn0skDLIAPftjNxvrZiUEA4gg5MASHwBjffmlnp9VDNzcr1TL4sff0e57PyUC8Nrs2qCEnYacF7IpHMsrvwZtadSnFv63POu3skDX8WRs8MAa6(5nusZEVU5P(tRvoJ6DyJGZqRbEefeZTqwnaIbZZcgcHVgfzSh8u4tmvIoJ3D3dfTOCMfMA4Epz7dNj3jo9ryiO9xaEQHtbGGSYtuZIcfnG7DycnSEnZJqgz63xqUqwfnkODxlaFnTy3i(HEY50fZLLG7BEVBp9N4uxjY8YWnMGmNTNnzU756QVsDQp6eNUhZ903xzID))8M20MoR59037yh)9FF4RTBUxZ7DX0mA4etlRkM08(QKwXPxoCtXWhqsZdC773SUVkGtu)1kQl29mafucksFYRMv0iTeJuoPzZMhXSfZwv3k0UXnON90c5kkkzEOAUksVqOwKZOV74hP9gpAJMrRXSrZMmBW8WMrmpOzB1OUnKaDkXrPO(dQKr852Kz7p(1MuuuTdeTYioo7izEue1NGPciS2OVpCfNzFLFgGEwxWajoGHvSWMDEIDz(alc4ZiwjI3uiZ3CXjYPmDpAIxQOyH0LqKWOTy(aAqJWlCv41Rx4Ve0xPzXtHOalMQOHHsHHbCjGaEE80dqijVJfWVFogFT5MW(wrm)WKRDwVxlbI4hog(vjYazujGtAbrD9WKRpGm89Tr6)yu6IRCxQ3NH4mgJt(hkc04QJJsagxvdeNG42HNZPj1Upv17kGBG(L449LzjYLCq6I1XyJoS6oiNeqFvqu00NrodWZQd4NxJ2rYZiMHCY3J6BRAdOCItiKU04zZPOOL8QKgCXI6gYzlzEVZRHsDehfozSHgEOUv3B16f6V4Oaf86lsjiTNjNNCpPDMMNJ1hfmu3ApAYxM)uffYGuY8JoQ62PVRsczCbf(oPnSJoCNcMptLtm5IKFnnada2fQZEg2xw05rrKzm8yJoq)WRYwPZDUYWaYr6VS7DwtOpsxzAU9hYj7(uJuT5KmLarkYPh3qsteugixMsQ8vRT5vYmoscK8k3J57jCayd6SVa0oZUW(AQbg5CtMVxZ3N5VO5738dyEfZp47rT2kUtN2g1PlcO)t72))sM3R5VS5VI5tYz(jsA(HKac2FvZpkN5VgbYzoN5h28j4m)15m)Tm)Tn)nm)nnF6KMFK5G51UJp(OdpI5tXz(XiZuMF8il34Pj3h5ZukLKiQ61Jy2v25q2vebvjn7heqTR3BY5jCWisSKm7ffAz23(tPlxyICIANPJ4dmCNNepz3KlDsZbmpLPCkvqGeaxpRzQDzMoPzgZ7nUlg4vT59IIVKmVWckJPFMokE6HV4G6MNlS6oTVoI93LSUaGILrYCmIqQgnpdv2Kz44tJeypsCHCQscHnpV5JOUDy0ARDgWXmocxnhVgqLruUg8WswtSlROKNZuOMzTFmsM3pWbD)X1roEQn0pQIrwH0IxOJmzgUG(fgszkbaLoxgIYUxyqXmYcxOlql0guMyIzZOmo5gLm3FnM7RMR08CcAPPS7EF7Ym0hAX4fliYRKLFeLPbLo32ikgWud)isIAkGE3I6lKWaag0lpxcqxSCi4yHrvafvlX3JSM4sJOKtauNUeFcj5SgxTNIfMqihOHnijybY9bkQlOnP5DAExM755ElM3ZdTfuiNjpbzywnGvQk8cTzYlkokXX6b2nin79tK2as0a5seHpGuluwekadLh1wnlaaUI5lq7GuAczKlQ)(UTzHj6bKZlBibt)YtuW8E1a1irbvCMDwZStOjNbP5Rn(yMD1dbxQgBSND5IU0(JBEchTEmZmFSHhD0HhCGU7zunQEDIsX1PJ8bdpFAreYq62bIBoKK5WMJyEQRYi2jk6SKuPuWJEefDIAelq)jmhQBeth0Lkf9exd)EFKVokIDTFZ)njn)YjbSdaBCOUkoy)xA4stxQpa1zjqYp8MvWOhqCSIwQ4D0v)JLiEo8D)wnh9waewhmYBAwnMTcG8lOVjca2cIyA(CaTW7m88zbD06uwlnWZmgmGNowVX7VlZeBgqhzKkuH5LPl6dVYANEL3MjQ8ZNLYP4E4iW)jsA(8sMYmnxEbeoJK4asw6j1LmVOJIki0hb353D8wpsZrjQJ4QkIPcrZdt11UUgMxsYSZhe0VWu7k7g4ZA(7GStRDF6LXffz6zZfey8H8)EMsE5)9ue(FmUC2SaHB4jOmf)47JY88BAQBRSIPHzrjZPmN2CM7WSeN5LPD27IZ8Dlz(yHn)fcB(4BZ8)jjZNTFexT7kWvPyVaBnaDarr(csMFojZ9Wz(cCmckcLVdAW)Ra0(Mm)8eosMl0pGsjnZyhTRyr6vRTEm)JLm)JsIynoGCG7id6bDEGqUpjHcTsWfcIaifdQ1u1axx)yt(bxWCodCPIYLcgAHWreC9K(exbqAaC90seqfcGyWkBXu3hcE)OC(bxaOPcWfacbWfaREm)GRQXAbbxxyHyL66srKpx)cTO6J3hDIhGIm6fasIWmBi4)Bi0fGsiaeGuayhGAaK8ZtGAa8F1cYqitZT1uto8tbahagzmzdKcd66Qp7xDIfyIUYzF2SmcbswoeaaKB0Z(D2ChtCMEpXLfU00RDmrhqLx4xzWR)n2WXLdMThogidGT(azEPHRKCJb1qqMhYTOT3yBRBWUaz0rPC8YOtYhJU771egDa6mBQfGaENY)YS5wC6gM1VWczBrlY5ZRLUP0nJZ8NJquvMyTRF5gRcXAuOfcBcqyw02b2IrjeD3qqlaeTSuAa1Kx1YLcKp3hsAJIslEpNQZ8jYD5to4i3OuAaudiq(COQYoa7Vcb0dGzkmNsBXi0OexEioVbLLDI4rpARTC04nF0gB)O43BTr87hn6gV0n91O0TKvt62(2y5V2tS(glD6cDwSV0xps3(tx7s3QcRsGsl6rJ2C0YHPauEvlMZvNWYvYWdThZK4vqLqpqINojJtjaa3WyvcO2WSgBw(ZDdOKSne6Q2qoa8aageqDHfI0whTuQRtgjEtjykr(59OezvLU5t7FZVT0YQgzlT2ulVMqOvD2RaSVAeAE96raeABCSxN4u5V45pBIJE5EplbX1HtPxQUYeq(N5rNKQY2mznxPnZ)Q57B449F(HhA0ogWm05v3wF4srPKLpHqUPiMtEn7Z0dyYFgL8QB3(eJawCkswih1Ts9eq)fYwe9YjFuTr1Kb784jUfy3M3nXi07PV3rUFVXgBSr)Zm)gN28fLm)HsM)ajZxsY8hjz(xM08FByZ7ZS2vHJcqehMJcqujaF5FxyZV6772itq)FahFloZyVfZojAs8)U0Yrg9)jNx3a813mXnsRzCUbhjCtne18)GxNey(NJgzBDRimamhRJJmDZnjmrwdbZ)ViQQ8nn))XCr4Eb75hZ80oWWnB()Y7BxM)f3kbObewVZWM)7RnExm)QGeho0Fab3voiHaeNPRgr4Nudm)EiH8IjNdxeaYcFTBZxSCcsgttC2UAmoXP2teeVtkL19gGmmgL1ZSfhkR5I2yJr5JPKltvTR(JYu384if5tWTQ4HszGc0zekSSlsx6NXvOo318bMdxJbY5ylgfZ904ZMToP2UwwITUrJlMzcrZrS)fUeBBX8zFpMD9(1KlqC9tnOlPixqI4gZcItjQjrXWioXmTs(ucgjzyE96qK)cZQNwSGGMSsYOgIfsoVX0IfmkLvEkXKZMvrZOuEHcjNf9rCg1PutgxvaoxY5jNa9ZPqsZJbTmN4meNHNIE)jJIn22JO2mdaAEaLznJBd8yamyMSBG)JxK1xerKb2ml8EO(XAK4LMsDSMpHuZtJ8D8srdu4lKrwhxE1(tRu4odTdBEApN5MxnOXMVCsZxz3MV0pPqCn)XBKiSM)ZObz)lM)R0o)vLS42K5iwCCmuolUq1yXfgo9nXqWS42CaiwwCVPKwCBboUz44wGJAGJBfoUneLXI7ndh3oC8wETep5LkdpjvNJwQtHtDMHAPVaWtS42gGEWVMqp(b)C0Jx)HE8dkd94I9EUtpy(lD0P6wSQOh756c94fOOhl5xFfhCfedbWxqJ2Liyn)Sd6sYx)HU8dldDPNJ28Gr7PZtm5GhTQOlHxlCtu3btDwqRxdjr(r1eYi(ZzW86pmMFuzym9FK(hirp9FkLoJxfmMW)2)ypymhDEDCXojlU2D4G9GEQ42UnsO9qUSDu7XPUnF)gJJgWUtONVMByU4eIbulqiODFt4fQfTIfirLwmmspM1oqY2EtMnhNW9cr6i6DIHRwY5uXZHrzgNTvsrjEoErSjox0RRijHUKNOZyjqDsqjYEX1zLSK7aUlI4UhUztjyhEF99Wls(8HbafGrNA)WuJ6DkprbfnrwSurIvQU10u00tEvYean0kohNn2plwFafCfPtctbOD2QQtdhJOWJ0hIysBeXntPDcKUjPx)AdMLJKoafKnPZ8DpJQMOU(0cLCwFcagwPt0EkWU(7ciIciKjk4g)cpBFVJg20B62(VDY3VpmNUEbxcK9B(P)aM9S)sj)ajxabetjkjNgmTWSp4kMFgKC5tLCrpxzmzjkjgquT2iNwImLhlNyHmicx0o6QlsSG1rgmcFeZiMzqHzKigKdeEEbqNLdjjU4WN9YTnrI2vgDTtdUWnTZYFMYfKmpLgA5jczbAqGUCocgOUCgX4X7V3(gDbYGPp5mzeleFOUpD3XPdpmymkQjQwNB8rGr8ly9vmbTlmw)hY9xhIencSoIeCjhxZGE7PsKxrXGSQ(AtI(mZI7Es6WA4nrjTDJjmKvbYcrwI59KyVLfu0qkdcHO51aUuZztyefUfUWQ7ycgXZWEB4voQf3Dg2p7IBfzxyXDxWGy3uEcwC3Th2aVtB2awC7bgNwC7fP8JHVOiHVfhpaSVVYO1T4Q1MahU9RSv80iNew4XEZFPVNDCwq6pITQKRjr7p6tI2RWdzbNR3FMKMnBX1LNhaAe3flwGeNGrfkuc5OyXD)KPolU3MhUhwC77e99W)N)y4N)BCE4ByXTF44aFJB1SZpKnFblU6qMbwCrS4o46jdG(E4)P9IF6VVh(70c(5cadblUhy1XiWIREZJDLTEndqnGXtH0wyWBjAX14IKt5e8fxL8t7WNM2EpX6O6wDIBVXZrcuNKlrAJHt4fYIMo4NK5FgYR08KM5HBn53Gz0PfZdOA1gTr6JM1ElUJr)DjNOMd)LJRni)Iocoo9h5Lrw2sQ7WFhtEpNRdJre1WGG5kB1I7eWRTf3jHjLbGJbbKNHaGZWHrOhaGofCI4m8Ge1EeOPJcJglUXGgFA4AN54wCNf(75S4o)1D3166B31(Y2DMp79UA4SBXDi)m0T4A4gLlUf3HjVhn5WP2IlkYFUXszsi22ixE0OTDdXF2I7iadzlUwy8IT4aMcTzX1UfhWU6bjZjpeqecthVDlUhoz58l3If37OA8jT46azpU79hpTKy6jB1SUnp7ucAYO6fX0LuMo(uyajhwlTKqHje1pX(T4gp5SQAkQe1u2oqa0qln4fJL0clob61ADzUwBlZ1A331S4IryBBX1jWK(GGMig5Klicu)unrT9t1OKO1n98Pbzzk5j)QgGhEFFLjtUPx9vF1pfYkxDRUxDm1maTEQIK)SK)a1f4tHyu9OLrz8CkkQslsIGVXXzIcI5IMONZA(fvpMVabe0P6cNruyYoWy3(ceL)iFLgnGK8Cbo9yd1zFyubA(LsAU)9NIoCM5n97DOdX3jcf4nu41ff5LP2WKriVWeIhwsuaENNG3jCv5L15PkcsYkfwR9D5uAIcaGntnO08XflmvdoxM(KooFwIKbLc1jxqTijeCRpt(jW8Risn8WhOBRRoNBxHQ44J404h1ThBGoyYqgnS(G)TZV6UxcAweEfn(ckg8xxpVi47DbYGf)OjcCvlWBOvue)j58I50flVbzfSpjiJOg8OgaaeVybDY8ybX0apEbTs8ekdDEqzsEBya5nKaw4jA(R7obBN7kvm)g08Qi)XpoFTK8Bz8r6oE)d3v)DoExDmyh92DTKhs5tenqEQWqOHmkg648LZRL)EZUtGbn70NP)H61(0rwPoN8UfPSzwCixfeP6oG99EaNxZYU7YGnoNhN5THrvmP0x3DmqvMjyWcYFlBMiWP1vtxHZPxpV0SB8g6DEvGxw(agqRExKwaiSdvmFkrn0Fhe2t8zLZjQZlxGpNCkna9L0U8cZa3ttTwFnoKeWTokWdcyEOkAuNEKdWlKIKEAi3hwMubZuzKvinhAe0d4lH)(GKAl649qTSKIBt(QZOK20hP2beMsGpwrnDJAFu7od7JUNriVAo6T(U9399Xi4St(h802eHE7EeY5B8z3WkpRldsVDaD(MY)64uyq9(UiHbfoj2i5J7fzJ4Yg4Dr5o4DCBtH475MjOboJ1Y68ipA1h5V7Aw1FMdehsLyLKeFhdrTFHSUVwCQO5jOPlloHybrn50jaDigUWv1j)PdInieFWXCj3c0UIK0DP0bnZlQdM0a9ZmCpLhoNn0qduUM5usdcvgVEBUS1po8FOBviFX9)i2cb)LrxsoNSo(vmJtz)SR8tqY)0JZ3jzv)gqzIEfn6SOgMwceFJ0FHSk15HFn(KqElJb)fxG26QfOlQg3u4s0RuN7Jcyh7omOxni5DnqPGEeYRXJUCCK8jUPoNPL1k)iBoov7dT71vV7ohEWyDm64dmCVJdw)p0OJp2q90)aJ2D8UbtpVaAckAIkywRnewsoJiycyBaWTplU(zUCDw70bY83mgMYoMFyZyGrM7MyKj62Md8QVYJ)QV63WSRRSnqpDQxmVPKE0H)3xcuJpMMsor8IAxwPGy)z0dPrZgLOKtkGzyQOUtWeSR3ltz)5ZidxkDXCgLinKEtnJFFo1PuDZbtudpssg6e0hX0aD(WVmRDQgDxOU)l6lTOchukdMO0yxA4ODLAWd3I5PIHwbsmCymZ)W5DZimmejsrZ0b0neUbleAyayJGNGfYZz2xfN5clmCMlD0eT2OC7tDEnwMJfdtEch7dUz7OnzH3kAxWE67R8bvEvZnTP9VOVS5ApBAHYt1ksGny7Fa172Js4vM2sxb4oKfuy32Vk99vI)0)5BAtBA7eDY5d4E9N6AwCYatd7Ooz)MFrZ)eu)zwWNG(I9k7K4ReIT4zebWQmOeFlPme0Mq0GWGI6KfY68lrsGyj7GuzrvQrZ0txB0wqguPO)koHX51O)yC0WhbdfTT)21ypKuurce(w2(MrDBeN56TttQUlF)2PNQ9HoU6wz9LNU3STDH(u6PqkLaNBTtarGQQ9h3I7Dz(BAX9yOFsWfVGrb11N03saSRBX2kxczJJLVUKtlJ1VVzI1VOvWXPb0GRfWV)9rT79degnu9dAMXI7xYIBsWekb4b8RyX9eQ3F1HWU5CPf3erJ2Y(SxFbaB07AcClRDZOPw(AX9RUNnHH2JutknDM6kmM65qsp1hO6JTktsqlUNKG8BX9HaIuwC113x5r3Y98FASr)EllAUf3CvIhRw)QlxYoZO22m6fN)oi48wCFyjkYYNsYdMUf3VEsBmClUNU2MjO12Ep83A7VDlUFBlUpIdM7Vr8MrmzlUpk8JpgGxAX9X9JiAX9mll62x1p62H9HU5IMHiEl4MZGrLqSqlUhhVNpqY1GlywzeqlUFhc6vZvf9QM1l0R6s325AnEb1wBkfIEzX97UsinTBXDN3HV148c1un3oh23cEo7aYzf5hfeGUAwKtFU91jgfPU997no(5xg(Yxg)8)nX9VORSS4oaNzNN3JFF94w3YIfAxV6(eCMpdnJfyUT9x7eH567HFQDIFAK6rxwsd7lTEVdI)D)OCU(3D((hAOUJporM1tlrC079Zcwxe9VE6sZM2(54z4876jBzXrI9QlHyT4tH8iIneOYG5hzb6tHS6g2pg0FYWqPkU52zbxPULcDJExpTp3o2mGo3CsFoCKspqr3dDd5SrVU7exxwGmevJGKugUUmCHBANMF(WuxgA(cCiE(TAXHu2h)QDjAiidwi1tobd0XHuNj6qty7HXkCE4fwq8SfZNzQENo7zod6hX1kDJJ3hbvg7XSUW1QOsy6m(2HH7JUK4mQY01sflflwCj3TFFe2CdEZVCBFeA(S36AHEIg5ZVYUT4(0lc8)tljQtTDzrQTldkRJ5ZmHmdOTaQSxMMIw(lid3GuzNWlv2DIereu7Yce6YXRFQW(qTFMseS7FllUpRtmhyX9C2eiaTffZ(9eE9G(bFkq3)84JXdrZRVOjUngnHf3FaqjiT6PespCXjYP1FrfHXwhOeQXls8Xsbsi1gV0zVPgBO5J6Gj)F)AURgpvv8(E4)XFB8ZZZfoS6oDxdRyoHUGeIRtwVYY(Nf0XcYcDHOsIefEV)ECEo(cYMtSycIDayW1uiT4S2vIP5CkotZ7wtMwvILMfS5SdSwb8(2fIX4fkIKpci4tDBUrIH9Qm361HZ3PNf)3MxshxBHsDXcudjZVfGT(yOPNUAY8S)rWt0DI2(j22A7j2CQ0AkQJxAZO2bnN1O3tw60zpD)iolO7cXWX5jfyjYSahbPDbJDMITsFiQBmShWGe6inbiGZLYoQbIdgZnuxiZTRXwqr0CAYv6CGogCK50ZjuWa)DQ(hkr)D1nbJgjjo11u1uMaJYc2nUKozz3hHD2Ki()SPvYtIedjKm5n7JAMvNhw3iKTZuW1krePK54espa5iLaAga62XSNU74J2FNDmafsmdBMKWzwDRUOwuLq28vI4i9WoRch4wTd7Sks9bIM4BFwzdX8OxHUzTVe1(pF(adEf1NhLL0rUPfkPducKBirofJ7M6(Sy4VnByXX7yS4DmEhJmYa93Dxy1ZzC7EMiXzrnW(rIFxXtnx3tPKM8gVOtqaqBkqX1SAT2f6cEBWkFDDFPIYQ4kgZJp8iiDPZtbptss4gyObtkjNZPdV5dVJ1V89bP0OAuEL6qPC)oMhlGsrs0gkV8ReqfAXPr214gQCm19x9w6TM6iHvLf(aQckL1RGQTOyqMiWFDoBjRysBYfWdRPGFyU6lRE3vwSzAWTgWWY2j17V69SRDZb0x4lRJ)baH3b0rrRSJq96jI3Nn2(GNJf3NHt9bQ(nwH1XCyep(rGH9Dh4W2zabk0eyPNPc49du9gvXdFlOMhGjdRRrtz4RCaAoP9(W5KO4CYFNnoMf3FVelkqdc3ia0k9YF)2B1AInEhvFkpkagqPIspamTaciUO(QHqwC)tWlW)FSuwfSvdH7wC)TjrGUf33FlbuKS0RaFbWs)iZrnDcRTqa6dGH)eCbu1L0RkkdAL3Z2ljMncvJBao7t0Y1SzqjImVeZiPUv8x46gqodCkw0UUMdKdNOBDp752zMONKK2MppjEjO5QUxhgC7ePvyqQ2ln721L1Rt7ugxS0yJIkdIsX)CsG9nGIMxOvW(gWOM5vkyZrgSLjCQCyDQe1pl5bTnUX8so5x7AqkKfNfi)XI7BHYBS4(la5mwC)L3J9c08xHQFzX9TtsJTS)AlU)lwC)xPclS4wI6PO)FH79Vbo(oBu88paJNV5SwCFVkjOS4(hQcdxwrn4zae0)rVmtzCl9HtBX9DdJ4ZugAVNWm8ABwuwC)3PmIS4Ug8U(IBb5M)KCRZmp4rscK6fEtFjYB6ZqQQgW411qlCy7nuYTNmWxKNG6ef8f3J5x47cmNGKPEmX7vGxnYBmls4GjZvIUYI7FggT)lRF0oF0BDvr78wkN25in1SXqPh68d29u(OD2VlTJf3RI0mEDeG5LSjvgt9abT(dTmEgITi5CzATztXWObf7jO2Fe23srxxDZ75X2Q5ET4(Lc0)1PhxivknXPKbw5JNxyMTHo4nOL8PjnJHg9ChP9Xp8ri0SVW1WYr44KkKjzTpxSN4Dmy3j6EGU7C0HJtkYHJtxXjlU3jP2fYcOqhhh03d)xSB4ZD9JCDLagPsKYGO5xmf)jLn6VlsbqK8aaK4VK0vPrW0KYgJlNj0sevuD6Aa8RjnV74kK5(3pzHy5CwSX0ULs3JZ3RiRUwIRrAtTfnIBykOXQZUKYMfUy1VBpXhdEpKOCF5VAxYzZkQjcgycnPXk77QDDzAH4IgzxWLkiNZ9IPHRGfCYP1KR8I0fkQFDwbdMSC6ydQbio0sAUVDTeUgMJd23sM10LuRT6RBGRe(7nqehIXgeitCI86GXEBoaS3GXBTlwFwHUPGBqlUnW8DOoqmbD4feaKEkpYhMNzypwAg5hHuzIzfkzWOx(YrQBP3ZKDY0tmfi34Xs1RConLseEnmtd3)Ht2u5bCjBvNAGWQHyLHqomdA9W1bMS)aCuN4)5Q2KNlvNeHHI6(dSzPKNy8ceYy25u3who3jL(whzbDHfo9L6yAv5Ixox)Zeiq1OmGkndLEb2s9mNd5niMMJeMIsZWv0j(fCcGaCP(rvIilkplwgi)MGO5Sk8Sw6GyMtq3Ozm0bk7mpesdIUgTUi8hIVHO(xR)YA8XDBS3ijOAKg0ypHoq9f(aSXBTjgPw3WhWBym5Pr1v7duBdnOBGzFDd0PY6QDFn0y2ARFzONJ0qd1UVAJurWj4gnFStyhjdWdZjQfS4(v5aTJS4KT4UiDfGoWxCZHbvJ(HeJV7mhwnfLqEFdIE5f49vSGbUskrbEyOFP0avZgUqUsUf2Pwm7rDh5DB9WURrljfexWZ12EJe)B9YjnJO1xhXhSNXgGgJ))qRq3VKvO3g(OScTp8jzfA)EEiwCpLvOdy3NwHQZtxzfkcTxEAwq2u0IBQRsJScAD6BgU)yF4ByqIubsuusawwN)ZvbAKNygPSwwooKx8Na5C)q8n6df6qhI)mI8WCpVozuZRRWpTipG7XlKgJ3sO1Y68z1uYZFMo4DR0Zn42bJuutvb6bzsuNPaqkEKCLxGfaCtJppmco9iTcFaPe5vy43GHd1ugrs5sg8eEmm0SgDdLu(v6UDJHpNBVjpOUEcZguc7TTKpq3HQ(h2v57CS4X7EOr5hC4U6VN(7oEcEpxT63lPb0ymwNVKsrn(00GDI3MkKhyXjNvgymsInjxGkVWecOOvYmRUWuGWdmCT0P9kGi44h0gaCKo8wuQ1Dr4KZe5rA6rrKWvDZJ(OEWGGrpsAYRHrPlgWZS4uSjSlT)rue1GwwSDICRkifcGsiacbV8C9RyHhwT(7Kk5ZwtLmBRSV4xofy8WceMbyxroFE0nZgIW8HGbFArnduInkOsNVocvaaIb0VSOH2EPgG3kA48Ztv5js90HabpvjlnoYNsqZDGJX7w3ZiRBOxxT07Hf0B4f6uOqhgi5CD1slf)1wpVBR8jtcd6uYf4Zd8U4fXUK0paXPKIUHCor)S699fMatQAADXtddVEhR)UChuvk9RAA1vrV7f(4tb2hX(j(OLhmD0beJgcJOVoLeOkKARCS7jRR1iEFAv7RyuMlJHzA98T2iFgfFIvPppSEW4nuhjL0E3OES)mSzMUiBedoZn1ZlhXxVXuZW(MiOaycdmPpjU2TeEOOwbbzlaHtbzuqI7Agsqa6oScGfFHKy5s(zJdNxXJZhn6rB5OiYSNZ1uBT3itKdgCYu1zheOlf1kD4(ZRQPGCUsad(0sLn0ccmw55Ea(wUogITCKJC0J6mC6tuqZWoZ07uROUqgrT14OO5Lzu4)x1ubeFzacveTOh6qQG2BGABdP4Hfs98tlRssgfKaP2iLDlEnQyAb9chWaT0GiAN(iR3JGFqhgvEjrnXk6KCW8fVSHo9PaVwahEr9AceFQAuS(j29DlLzj6YEtmH4(NKxjAzedejBa1dL4f0bMCzv89A6J)rx2b9TUyoX0g11w9eIyYzD4Sgjsf3olOc7BegzpDRrXdF6dIXSoyCN7fhuyMayzsWpC7Th648n3cf3T8rO)F)a8n2qtrjb9Ui8MEaD(UZNcJowGxpgDxRgmZQYuvjFk5ceUd1vxDW7XbRZ3dpsKdIN9qvqIe5WWPJ8abEphmAeNtv(DezfhFlVNikFCFOvef96BcjHRgzUszIPuOOodtP1i1SS46bnA90PhAvqF4hfFuKSg()IOdfKPQENGPDpTOZvnQdgNf7DLjEmyS5bdgTFqGDGpi(7LzgVmtf90Rm9msmI)UOQVub2jSCbWUxQy6AzVjpkpJlIUGgYFvzzFbdcmTYyKbyPS3a63(F9QGtLC(9LcdbGA)2zMY5KGluVKqa3NPJAQmZcOmiDTZ5YON2VayvoDLhMzUrJ3FV92D8hKvkj3fykK696ZsiVDiTFWL4yhwC7T2MANevjWDAX9DM3vEdZ(4ELaBKbBRjbN1IS9wQX6SZUtKWS55PP7b)aktWs2KBpLBYMqYFc(Xbru2jtb(d83evCWLc3(mze1j6FA)BSruH)SVGnE1AshjHk4hy4E5jjuXQ3KohtWChGLLJkmzhKKbeFJiQPnYaDComGh7U3UhA8U6prhXgO7UQ1FB6EOohEmCNdJUXCvRlgaAuL9eKNSTZ7eDTUMqou11EKAi2n2WILMnRDRu8zMc1jfzuq1wqwiegAv82XgoW8GSXbOPmAwChKGDEbDgLbpUDFP3aFcfE0Yorba3amofBanJD1eHBxGeti8cE0XQbEmfKCEaOIBfvRNOpKRr6tlNlhzqwlyKh8Mq9(HmzGdDNQAozG2gnQadAe)gK686gaAL9f4Jp8adm8P7ooFzxiW7WDcKKStPPkRs3q40RNpTNtQqSovd3WKQ3B60sAQ3Rctn5iUNGYHst02Iw49AAzdjFZy9Yax4UtNSa7(CNTWj7g8pwPcxT53TkSHZoNhPVIy9xLAKrI0skk5QyIOhCh)InfWJ7wzuNBrYuBcYxnRGDFRF28T6S3BdZgRaNJd4KETWQ6dSRplRw9p7MxgHPLt54h356t)91vD3Rz5vFVIryzNyvQa)QBAian29)4SvzVYPF)6Sx2DruAVA3tKLzGTA8xK))SkmQS832QWzLFKIugso(xfuqwGAplqBwiJ4mWmvQsSbjmZJdVvI)CvyvtKrnYWNbywNyOogjrFdp6YZ1E5yG7XKaq3EDNLbK6FDSQ561JIqtC4k3ai98aaBAszta9raWM01AFdK1jRuvmbQvarcgWJh4HuK6rFh)OlWxRUHMsHjqVjvxEmLYDvqoc17H4dWJeGGqa0x1MmTQCnG71Qcwt5oW1JBTW81hErnKaTpHjejHPifqcTsgs4lY0yzNaLxJIi6CGUhRE7PnYwBPD99aGdyYEZSUcNZOfWeuSzbCL3iRFV3rhR2kSIkS5xli2BGN5peutF7ONvVcgqEyrFK2AVLwC7n3T6w258lvbBDBL3Am5MQXo5394zQkOST1eVSwOFDyT8Ad4V6G7bZ6S6qf7Q3XQaEyObir5iU9FvatA5On1AZU9iz3oUAGJgpQh2buP8XuYz8gb4HhR1PxMekeGL48EmnNLD(tto)Q3bcvA6n10vmm7aZEvhejSFWkP(EqQkc175Yu0a7leOLrKG4HQoikDljZe7O1mV7jrZTVmyMlDjKNIzISQ6flZOxwvwaWyQWCmWmRE7E0X7SVogQx0CSkxH4QmBZE)jwJt8baZ6F17iWEMLuiKAeGQ62zvQj6c7bMRlNwTj7bnFDgE8rqDgSfw04rI(OuR(mEKMFu8zBQSz30wft)smigVYoweOCkONd3)ulPkQUnquJaMalJAFA0ndn0uksWrflm9V9gErwSXtBtssqo(2npMBV1dm(uF3otT25yr98Ke84SS)Eo07b5meol7VNlIxxOqBkOyMZTdAcsBFe7oiORc9coHNsLyn4865Kb9GXxkZpph9fOJWBVe32N5Ez1iGuKTn6sHtr3jzznkEy65NjS5dFLTBfQNWyZTc1zyRqhNZ(v2k0db)URWqFt3sqXBnj09Zr(goRoVAXC4ETj8t4HbtOrBQHwOxgNMMH7ebmpPb2anbCKcoeGdTOWVHJuWHquV1bebmBzqfn9mpefoqhU3GQmUkU1X(oOdTVBTG40ojebQPkPz6YfQJ0NrGj3MIC4OroMxOIwt4CU378G81PbkodxjsepfDLjcQHtGnCc)nmvqnmf2Wu(BOqqnuaBOa0qcq3ku3aGLZkuVHn33PTbs40EOoILfldYii)lK08fW4BT5ObhMyr9eMyJxtWrLw0GIPYNxYm2T4M(uJzUqvIiZMc6UXTL1GdIRkAmNf37)(iXB6FussAOJHt6wdmh(nQ6g97w9SFKt(h170jIeEWyfek4XJI0Tu2MX04oW6WGHBAnGPY5VtytvPadxuJksBJdeCiOgWeeMhCKCj)xbJC5jQDFPdC(YiGmbWI7xlfngSmp3TgmuVzpqD5Kbwnom8Nwc)XsK6f6tYQdi2HP7E2Kf3JYk5ledaS4gx9(84uxkPuDymBD8JJbrweQ4HK72TuIif4RwqPtZvoKDi4DUtEXUoPCMZMHoljnZMdvw83zx6Gy)FAbDdIstLfjRrp6rANr2x2DKnvNob4HB7B)in2kR92UgFeLbbnYzUjTo3h0X5BmszRkEWf1h8TpHHMo)VazLiJe0YYYcch2ev928OKncSy)GQQ0qALcPfmQ8XupFT8pgFTS3IadOp45vqP8hjiIHmnIwGa811XPi87rHV77U9mx3uln24X8DrNP1O(UKF1OyZuvodHHpSxO1ePrppy)arNd0O3llXCqcYZhgYhgAoZjlEaH(GfWKww5jEesuHocyiA5vJjw)IU)cgqKGECFnKDF7R2ipilIhTFMEMFjftk6lozigHh9xtu)lcJ9toBk7CASIhoPkN5(OXm)ejz6VarKBNkzeRZ(YaqoB2J0y6gZM1hKU8GRKOBpbDb0Otulq0f7(K1p(arvDYd3MTR4fyLEsy94ISynWDdmWQlAJrc6HUsDdatASHOzDHjeX95fMPUgBa12aWcy(qA5Fh6iTrrHC1(OeafIQ9qaIFJxNVtbbLydqD3rioMiWSSzXAYsTb(EZiVR4HW08Lwqsi19asrNPYetWHT5HB1EB7dd6F1bp0HqQBOpXabJ4DAGLokdXM83JpDyL7pGTxn(gjyycx7XCIF(AO1k7RSBZxPgw(jTeT2k4MruyvO5ZtZAPRXeB7MM2elhilJ43HdhK711(fcWRSLl0ouzxadurrQlsy7BiXWjzm9yVRaspwcV9iMVmi48VMZ2QTiJnu)GPA0Isjy1MJvz8KlGzSl7mGwUHiLan6It(3KKTfPdV6)Tyr5zjAyVJR3dostsdMxCcHSYK2r8kDUWEa4y4e(MRBfsK0XEmwYUGQzf6Tck99ou)yS1NvNAImLK129WOtFrmy7O)eW1AGV)Sem6PvkMld1ZutOuqKpLi6AoalhTGbGw6uVxjOdqFOFRtsmNA2I58uZAPpkzDEvYMyVSqUCLGUH4Gl8szI0Gf3JT0iJYNamzIFibnnLPnJ9Mb9uGHExFt3Yh0bCRte7k1iX7V7eJMKT)WrYKGLCY45jlq2I(jPrG6oXtloJqAdVxuDhKuiKGRIRhzCrHC5jjIW8UTQRVOf3VqiBnmj1tiBvAP1vis5iiqfKAIGZ7MILR593rwQ(L8eGL6Pmi1OtSuJjumNrsaYEN2R8EFK55rCaPrNuSKgtmfUdY1LOE6KXWvos9oWuqVIBWCHnJodi0uwHMwc65D6VNPSCTcvAwB23wHExjTc9yQBZt3rBL3UchKNWURGjinbYcFPrlie0vOS3o7IuFIDqUi4JoyoEXwGbW8U8EThc3nzieCFv(G5caQDwnfDJuk5S1yb1gHIQNYghpkbh3oYyjbqoWE2EvLQGacq4tLROio8CLqBp8oy)aDCA0ti0WrxHe07hzg(ECgh2fIEy0AoEpwHUmCJ)IWXSWXJNKK4z75xomZ6JwCsCUTrmba0KNwXPqlbmVWcNDGXYEjLl3BX4nss6bw95YxrNYPq9T3aWE9H7ELdARwTCFzBz4gpr(2TvRo8)qzQvxJNqeUF9UefYmSwVyS8wN)ya2M7CT16xegZ1HoAItdDAV6Srw7tEnHctwppUnuq1DhBx985LlehHx1JL4wY3kx)8Aj(4KTspPnykhoQTYHEFhQJmkE7(dOBsNslMZpGNvgY5SuhEHuhrQE634Ptoo5D9yvQ0va9DvsvhSA(sTmOsTblVD4Ya2OnaWJE415RvhMhuScE)sBuraTw9F47rjxa1fQXYILDkfeOgWJLgvIbvLPw)bUk1f4L1prx2(rqy12pnVo1phzz7hMcAv0pLfzV8xp3UhGq5gcbdppqYGWdkxRqYJlG8WQPS1wVBxfPgpH1kr)P75FERmLhDYLkV6i(J9nl5ljmP1BApNOcIaWERLLyI)4LBiuGnZtV4mPwBn144J4ajQkZwsy0xpFzdDFPNczG7znJjAwZ0ODVKKUFj7D3jzD8FLiojMMqdYgLKOQ8LsxrlfwiEOBJqGGgnqffC7hnAn0wqIpj06bIQDlLgM10LZktlVl0cNuZQ7e50Y3P9DJRbAADAbAe0U0UwogkxsV7hnevqPLXrpBtVTSezAXBLiL4jxYzb1rxGYrTtQJC4tgNCHApsJ0hNBLbGwUfFmRqkEDciUhK9leIOWwwAEJFlEYN8BNLa52k71INYheBxk73xYku8W(0gJOf2Aw1QaSaYrc3Hpcroj1MjBDW293utxjRXGYf4qnk(n0sjprcdrsHyQXwIcilHJP78BZfchfWM4aDcu3zqORGYi3pk6bddaDrm920pgFJ85frfHjlemzPBPptOVTvN4TsbeepQzVyVAefYMMvScUWcX7OLgJCQw6S)jtrR4LoQmSDZXScDANIu5VgX3U7Yk0hNZCpF33evhcxx5vJzQwr1eaTfMfJBPjgqzcjI(e4UqT51md9kwC7CHUX9pjkMz0rums1lgFd6lGfdSmAczn4JUqxLqT46eJJlqd0IGgrG0CM6uDpJCoXmZNdxCIPfbRnwiwo4w5huyc50l0JcqQHrHIOM6DoQcmHb3whAGXMG(RaRo4mfeu3rxI5vkiNgAizb5WsA0cJustbjCYZh9Q9NlxrCzDi7813rcvznm65yJGUeYxqmJ)T96B7wm)gVGvOpjG39zGJplC8PHJFp44tbhplC8hah)UWXZbhp)Bu2mSdVCBe2Q9nPy3ANoVrDjw(nc7DSw3iSFo4wVNBnGD1XVkTiNc4Be3cyyx9flBs9Is2bd8kVzo6U)YZkEPbTxoYk6gE2E5JHBc2bVdZ)rD3H5VpC7F89A((QClMp(iYZiMRITz(hlS57ojwlryfsKhW8FHSdo6VsIG1xKN9uMDnfRqE4SFogw66B)CKwUePLTdZJvX(5iRovs39nzI6jO07b3pJotBNBMZ0FZDMP3EXQ5XcNclqhEG)aucZME2(545S3k7ts2HgzBL9Rvo3LTdG6IRK0ZgglRaEg631pYYYvQoRkIY95GOyX99SHVlxLPHvkW2cPW04TEDILctSaZ8DdtWPSRElwCVyj6M)jbjclpny9ObXTqSWprYklenwH(JQwLOj5kwjAiiq(lEFyD4SALNz4RX0eaI6EabfVqY1LTkuYIeTF7A5Y70BDCzEA9CfRRgBi7NOasH9gk6POBOODnqRNWO1CTP0r7bVHIQ(aU16rC)px)cDq3Gug)mcAGLPtoUhrGo78O7iGA2u1lzt7LS3b(YsM5pr8wA(OnEuY)2o8VT1A04rBVLgBJ5puBHgxmP9wFmIm)k7EP(lGXAJwrqFxqXrcnaGZ7U1cskiuFSDAxqOqphYtkTtFSD6upOi9CZQ3zaodTFdX8rOvfQ)A1D1LgO1uH8ctZpKig66yyAnPODbKcR0uF7K2U9elJuBefpQRl6IQvHMs6wHM2pPk7AxDMcOoujvT6q1DVwQdvyfAIvhQaPjvVou5mU(Ex3JR77gACTLQmU4OJlcFK3pPmU4FVfoKJEkRMntGvOksXTAkIuGIzovrQtrRIuN8OTNEGZ3xVhjwD0Qi1om)CjnfoONQivkmc5fZWQKuh0hhOOeoq7YPctFeFvyAwNupUg3r7yOUsr3zWoiUR55wEQyfY6T)q4PcDv4uCbxXQUEzuuETDlKiT2UDh3i12n7DADYD6WPb5TCOASzMGChELDR(w7ReyNOUkgHQDKoTyorQM1vkoDDQkXDFo782bidEnrvwPmyc12tW5dzNiqge)huXGBnWRz5RgCL2GQgCKxbAXG7(CkgCNYTyWjTmfdoBdXdlPEx21DXXtHHPPCMXTl3IsB8K3FYYjVvATPUgBO0zICPybrEVzhsoFK2wH(cUK0rdIKEZReT6Qx9Z5CSa(grl0ZVg1c1pfWkRg6T4vnuSacARh6tNCTOg6QGeOQBDe(S(6z2szBDeLHQ7BdIaUnS2ZZrX0jV1bOS7xFzv2fuYDDxvx7YwyGiwBmA5(SLPL7O9CYr6OZXAnr6EQ22M)hjKhLxxE8896ZmRpLhbgldcoD7XEU0KW4iNYeZIUAfdo0yXgRNEWGS9iTaYNc1KBc9cYSAWI7)SvOJGcQGNer0vi46K6uTDhKCLiFyvU3JrRQTxNvz07oyJ5QS05s2jfOkr902fpxKRoLqIOj11s6QK5lwcjcxVjR2pJB)ArzXsldZc3xtGeZ(18tK0RfSuDuzVRezPGyi2Su5eIUBaeuArImNnAIXdUseJvC9GeFyf6F)ger7NQmIwHunln05Vypxw4YvHOn02)xdKODzuKK6ihNDR(6nZFW4T2yJT2m5Fpszk)5AMjqzti2rRuDDYgwq7qhI)1T462k0)rRq)hSc9NBfYmz50ZeDo7fjJv3kM6tY08IgDc(9H03ucDU)RseYB3iAjQqUCRaTTBje(LwFjU)UETrcjP(NSL9G0Um67NIrIyJ3tR81bucHrV)vbTnZ1FsUU(J4JgG(Ump)bK73ywcwA1WdZr1a6R53Flo03ERvYVhQ5Ipjh7nLrB7NID52Oxi06o6wU2DxjQ3NRVkVPcizdXfLnflI0f77utLPqZijhqqvoT2VFqUOCnVEspFY1tUlFb0X3xhIGNFaNvpzvlkg3KeX)R74T0sRn3gsUIBu)KkfoHw9V8EzMtg6RtOnP2s(TtYiXj2pI0Z4AmcKViHoXGuK8fzaSYYKDnQBnr3Umg3vnY2VFjVw7rSYZR4QRLCJXAV1eD7t7yW2QWbo(OADyoTfcZjpmMiVXaL7ZWQ1(v4bhhY1kK)UU5sNxhjp(txM84UJNAO6QRX8Xo)aRwxftI)OXPRy54JOjRJb)w6oZPim5AuB7pZ1J22ubZXB5OTgTvBc39wBZn6ixgPHj6ABlc2rd7vdn8A2S0T8tTML(tbEM51FKK72dj5geT4NPmAXiNUPo7T)wA6Oz6UA6gVZAxJKyp31ljMdL1kyb7czjXZGizhf4NtO9tAcTxFAp6RbeBpxzeBD0YKXo55AVREJMOAeB3uHvnX2T7SyN7gS58iT10kS0MwH(S(xoZvyb7xMflynTvY8t4flGGQ(jxju1f8SNiDZpzUkWxxFft8tk3A(zldXCKo6P9XsRozXgBoyeZq3ali)kSoBXjzls5l1wON3DP2cDXYxQTV45OYnYYINPqppvmbb)hXXBjQQOXg0IOTmIqKwheHuTiz5nYsq8ViA76Dv2UQV7wQ0RLlg(Zx(QLfVPEms0YatE0Zf1z1YKcA1Ycw8taRMMe1Ul)BdZT4Bf1wdRyMtiBU60)A9nUTSfd8tRO7bTuwF5xlxkRFQvBL)GYekCKOffKAoBgXbYwv3M)0bQTI)4pTcFMt2y92ktTL2BfvH5BlHreX96naJDIRysmsrk0vuXaoRcmIkhTMu0T(KT3ODewGy2xm5s0t7zVLzvS(W16DF07gmkfRqPhcdpx3aBhvqGkp2RTfq7e4g9PUtMKTE7k87HS6X4EtQUNTZCplJmikWLRFGBXQUdoYeWNijz3rD7KgrRkiNLUjaFRoshm)WWer9BcNeHjqN1DwDB0n(Yydp6Odpy8(7TVrr4bUq03no5f67cpJLXj57QCpKtjNxhCq(A2H2UEv)n)KiJ6phUhN3zFXAFSUvNSu0ZWO3kNu8ZH0OSTfDGDp1R6aREgBK1dEiFbmsIV(OzFbBTT(dlJi0n0MUoIfJByhxVwwWjINRVfBsqMr6eIpgH4g1koHKz3qR406HRRFco7fC69sLWUQwXjpMhjzf6)Yn)X)hVE0cBdKKAhFzhsQjp9uDD(2YL50PoFviP(dxbsQAyueSCY5tVWGk5mej7NFIwH(AXjP968DkjOOtkBFQ7ymScTHBKgDKnBozs(XDvpBuhnpljtD05JUqNkfYMtycmdJwIv5)yve2fhu0qiVIMQKIUSU)KNPVVY4FLn9ix7t3M534tAf6hcZ9Fn44LHJFmC8)aoEf44LGJFeC8IWXp4NwYFMW3G5pZiHBQH2xUCOP5(u6OJHUyIPYhz5ZHMDUwZHgulBUYsHMNGuU8jSaFrQU1m7zj6L8DU5)U9q2g6i5jizgokZ8vBJAFjBJAF5KuRH372BYTYtSl7akhlwFwHAx9(DYnCdFLZoS28DmwzqCv5VZGJKLYzVcV5o8DUFmKXwEEoE0G)7ZzBEhUcD1UpDcdgGN36(()79fyC5KmGDnCVVn3fBr2xooOH(ECE8I73Flo7bW0WNJeIDS3QN94(8KeQ3XLkZK1qS8U8NnwvHx020HJtnDOWLpDbHUoNWGD0xvdtU3SJPd7C1t291EnGSZk0)YpNO6NkiQ(6)mnr1xRmIkrJSYD2APtivk)Qi2t3za(PLRQ(P9JtxlbQ69VK3ns15l6SlG4ng2iBVQU(B1Dhv9RIlL3s25kVJhF9rksjAPzspsOUAPfxNDH71pb82w9eWBPC0D0mNnmk47FnrbF)xhuWUB4)BrDpv4gGOnO2GRFaCzBXOXdWXbnev1VJdcG(VLnm6)vRpGFjhFaFCQpGBn(f7VPthZ4Kdpd1hW7K4d4tuDMievIrgjFESnSSzQ2h64WLQTPgj550FODBpr4(E4)El8Z3cbGcQB1JdHjfKJk6JT3sLDXvUt8ZBL0fwHVjV(FE52Y)VEyyqKjV94gGrmtAxvmCd7n7qEBj6Y6au7VncHoTMH5PuIHfomjcJHFG3SE0L5XFd1J1(ym0pWyO2AwpxBNt8twj7QBu8fcIO6)4pXjQ(bLtujl2EXoBQNt3xD97LOY3QJUEH4E7os6oiyu9S9NpVcP4K7rKNv4nTYI6w)X(UBhhIHyemVX6nJEsgqg98uCvUMBWCrLPZdIHzZWFdajZFmGCaZE2FZjpG)Ov2TC0qsU1nC0SFy5Ozh9uNS4iT2x(rt0Lx0ShC9J39FxB4NhOVh(52d(PlxE4rV(4HZ13d)KBf)Cakp8AwlO6FCVO6hwD7jWmnvjRNDt2RBSEYk3GbRmwTJORgpLx9txBZT4iea13JC72LBtKt(3HdFswCFu47FST)qm99yn02Jh1UmE8OshE86ocVLjV5xd0KecV)2kIOLT4BfmFCKN)JapNNLWUp0Ls6j1Y)9j1RtRqg38x6F3gpb5pQCcYj7FWoVChtLvFIZuHYu94NGm0x9G(TbB)uXb0Fge16PzKxWDgmHBR0FyFbkbO7LjpTLN0gOll7j1kHA2Bxw5z8qW77zubnVp92ENLl(BEAc1tkXhRbMdd5WC4elrCunPKqnHsHsQ3HZVjvwQCIyHGsxDBoNgRMBfe11x05mDPOK)6MzIVcT7pNEwkabPbK0pVwlg9)r5uTdjoyXex8s9pwNxScXOvq1U7G9Cs1ivpXQMuD1DQBuc6teOC6vdv(naD)A2EST51mmwyE6Af23kj1zlHFtulUEzMfxO9z9CqM7tjUu9NB016Trx)X)e3ORxUCY4PoQG2KTNAS27CI1Krxh0uKRQUS)296pXx5gX4QkdjTFQG9(v2TtOcz7zEpdbkMizi8uCoUrZZaGglq3I9O3o(iPzmaf7(oWyVbhJbGof51chJ)Gxp280MnF07HXeR1QAKtOnjTYk9SSgJTb5W9xPmhU3HAFdPBmOWjtOuL8u7GbNNA014N9h2k9VQxTl0QT)wRq3Ves(KF3XB5iT3u5vTmwsK)JTdUFsiVjrPGCYm1TsAk1B8FNB(l(bzC4r)R5ZzDeHb)yB3V5turG(LVsjbvSgzRhmu9qRDGQ6D7GIEgMicm08U)vUYDzhIEekusy)vM3UTzo4KLcSCCLK)cpj3pHcF67Yj8PRK7WV4p9USzpO7YM9N5(1VJBSq)VDdI2(hx(kuFUHgRXiJKBSyLQ2IP9m)qp0SSWc6tS9RDgCd21qHprrTPKNsCXU1tlOkY3HMHSUH6ojxMz6upkA6ctkwyjwP2DufY(dI6w7tzAsJgvuttrJp6vjBu08DQiNJV5Rs5BKTOwj(OQ3PDr5TtzT05eFq4EYjQQOzSagrS6scgahi2TKcDvsZQBThXCGfz5LlqdK2OxLUdRpGs6jHUVlXPukQrRmWZLqiTgwsSfNlbwg3WkA(ceMAPfvn4BEr6MKTUbU1LeL(iPF3FSkv)2n)gxz7wHVFjRWVn4Gho2nCuhCCFWX(GJiWX9chhaoQfoUl44GWX9ah7bo2pCC3WXEFJsumTSvb4wpApnot0j74SZ03Yhbt3X6zemD7bKpoeBf8u37STxWnzCcFxlxY48pi5vJTKbwLG9QXwz6k5HRin2Hrv28QQ0trkqvE1usYUobZcrss2dS(kZX8z71SRV5S0Q3EAXKbvH3iL2nKb7V4Um)0X7RyEHc0CvjunugYBo5QTqcVsmCtUAumFdHZz47YMZzVuoNgtFs5rgBQrspIs1slGD8N6W58o2yqi39YHqos(3WIqAfU(vbQyVybD)nGOI7UmuXwV4fveLpFF1D6ivnFA)pTrJkE3lhQ4EFhVUdvm56jQOwI0GUgt8grKX7UmKX2M58hjXGNVu)AhPQ8f)XB0iJ7z5qgvFWF2MV4SXYPOKP7CzFdi24EkdBSPsYcsnjF(bIv1snWo37gl24s(TYz5Wm75MFJkMPDMnNCzkpWVbcn8EkdnmYa9ACYE77OnpqKvQWcSHGdoVRH1lh(3x6LEJo(N0pBG)T3YW)UyVd1EVtCUlg5esRl4F70k8MjX7szyH0s93Dy()F7D)dBACfgaaxNVMwPip06u5OuLMqARTXziYMyW2dzaWg8DaMZyWuSO1q4W8VZ3H5aS5Q7A)N7FSQ6qhRy1BEQYzOQlzS6uthEtTsm2Lk11U07D3XFUNlNtSbt6XnGerrclb)479(49(((qV3Jv)f5E9h(RMqHBQh42Fi9FOariFBECBgtb(uT92HFUR92HE9ps5aKH3fHHecB4qy)13BU59mqcdcWTOx4VN8DMH)meH)SG4U5yMXMnQSSrxBHbK7UNEURCDt3ziC39qChJaP9A5lMYRatxBDiZ0Fx590N1LvEp9zdPR8E8WWkVVdIeTBFBxcES5LMj7ajcydTNfNErdjEZHei(bddq8DrG4cKtplNn(ndMALEceVXlu8WFxwy()jTXcR3(CHhwIjoKTW87HOq2uPQUsmQq7eJCGPWNCOwfcWNWuFgs9nbAAWrkUyzkc)U3RWGtFLq13KM6ZqQVjr0x0yHf2RWJZVz3UoNxf6RkQ(MYuFgs9nfI(YU)UHjT9(5xnu1bN(oqR((2w30pteAirOveeATkDzQG1kUHRlDsiFyRSHp62DlB4ZobDXT3kdy1Ybb9uGBEfpB(klxnXWxkfedVz61HdrBlU5QWww1QivsyIlsvJK95SQro7SYuPjuk3Js7rfx)lhQ9(NNAvlqKRbRXJhjxJhY1hYi)zNJxiXDVEFs3tJO71DSuepRnBL0CbUS6UDFR)O72p0DhIw5pHs1vix3f4EggIaNW0YDA57JEW1fQnJBQv2rqPiB13YQfNa5jQvoatYDs)RQnA0OjlrBX2FRPsTTylKloUYi9B0rVL4V5bGtMfG7x6HpPheVSCv8V2LTHIkP45TRBhfLkAgxt7K0HBN6FF8hVFFF8rNd9)hNQgHE)oY)v(ZRck71XosCve74rdM1bZEfU7ni2FO24ceO3(E2i(C7iGpwNSNxCHXVWPr0S1A2T0iUH20ioPJqn6LiHjf)FnfjrOynM0vZhRsUnT6QNqXx8WGJP7D67FmTNHXE(qSxQA2JfL1Rv7mr6N27n6(w97WEynmTNb2E(rS3(Ez29H5lyDVD5oF7nfaBBPprG4lH0BmFJeeVdSwYZjTl5MBQ2H4pwC22DsaN00bz5JdBYsoRukjF8aPPZLm(6CvyP5J7IjjF5hWLjtDAUT2jnpFYmPZkEAIo7VHF2RlX3gWAxKNRsPuPL7YM1B)8reFqPTwYzaNExwXZ3XgCx2YJCZzASo1Y(9Vf1YHicUeHBa2THfjVYA9kJFZ6lvkzo1jYJYC7S9OMxf9aSps87byhaXku9VLS6ptLQVO(vQ(4IhRmZLEA34JmDgvLp)qlcbW(KjGmcG9P4IRbW(CawbPVAj9Xka7lKYhbkljq)2F5RjfsaG9vaSVU1(7VPAdubYbAa2HWZUNJpfvmHTthUcmvjawgxHZb77Phb)scM8g(NuEQumzINBiUb89oNYpxz6wi9VaJS6yvFLp(Fp

```