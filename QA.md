# Device checklist

Not yet run. **Setup:** one track with a sustaining patch, with Chain Arp as its player. Use ARP 1 `up`, ARP 2 `down`, ARP 3 and 4 `off`, RATE `1/16`, GATE `50%`, OCTAVE `1` and CYCLES `2`. Hold or sequence C, E, G, B unless a check says otherwise.

## First: latch on the device

1. **Latch holds.** CYCLES `2L`. Hold C E G B, then release all keys. Pass: the arp keeps playing them. This depends on the SDK keeping a released key's notes when `release()` returns true, which no device has confirmed yet.
2. **Latch replaces.** While latched, press D and F, then release them. Pass: the arp switches to D F and starts a new phrase from slot 1, and the old notes stop with nothing hanging.
3. **Latch adds.** Hold D and F, then also press A. Pass: A joins the set.
4. **Latch off.** While latched, turn CYCLES to `2`. Pass: the notes stop at once, with nothing hanging.

## The chain

5. **Handover.** Pass: two cycles of UP, then two of DOWN, then back to UP, with no gap or double note at each handover. Check at RATE `1/4`, `1/16` and `1/32t`.
6. **OFF slots.** Set ARP 1 `off`, ARP 2 `up` and ARP 4 `pinky`. Pass: the chain plays 2 then 4, skipping 1 and 3.
7. **All OFF.** Set all four slots `off`. Pass: keys play the instrument directly, and releasing them stops them normally.
8. **New phrase.** Release all keys mid-chain, then press again. Pass: it restarts at the first slot that isn't OFF.
9. **Pattern change.** Change a playing slot's pattern. Pass: it takes effect at the start of its next cycle.

## Patterns, by ear

10. **Every pattern.** Try each of the 21 patterns with C E G B, at OCTAVE 1 and 2. Pass: each matches the README table, CHORD moves up an octave per hit, and CHD/1 plays one chord then UP.
10b. **Chords on a mono instrument.** CHORD on a monophonic instrument, with a step-sequenced C E G B lasting 16 steps. Pass: it plays C on every repeat of the loop, never B.
11. **Small chords.** Try one and two held notes. Pass: every pattern still plays sensibly.

## Screen and saving

12. **Header.** Pass: on both pages, every label is readable without overlapping the next column. Watch `updn+`, `dnup+` and `thumb`, which are the widest.
13. **Display.** Pass: the bar under the playing slot's column moves with the chain, the cycle squares count, the cells fill each cycle, and the text shows the slot and note.
14. **Saving.** Set all 8 controls to unusual values, save, then reload the project. Pass: all 8 return.
