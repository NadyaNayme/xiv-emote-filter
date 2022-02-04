# xiv-emote-filter
Filters out EN emotes that aren't from you or to you. To be used as regular expression filters with [NoSoliciting's](https://git.sr.ht/~jkcclemens/NoSoliciting) "Other filters" setting. Other languages not supported.

## Emotes with a target that aren't (you)
Blocks out emote text that doesn't target you or isn't an emote you used. Won't block out custom emotes because that text can be _anything_.
```
[a-zA-Z\'\-]{2,15} [a-zA-Z\'\-]{2,45} ((stretches next|succumbs|nods|bids farewell|bows courteously|motions joyfully|waves) to|(spars|disagrees|bumps fists|agrees wholeheartedly|chats) with|(points|nods|smiles|winks) at|((flexes (his|her) muscles)|claps|hums a playful tune) for|(does the side step|weeps in sorrow|staggers|wrings (his|her) hands obsequiously|prays|cringes with pain|does the box step|does the \"get fantasy\"|swipes excitedly at (his|her) tomestone) before|psychs (herself|himself) up alongside|snacks on a slice of pizza in front of|is visibily infuriated by|casts Megaflare\.|celebrates victory|sweeps up around|falls asleep beside|experiences a brief moment of enlightenment upon seeing|dances sprightly|gently pats|encourages|sees|congratulates|questions|slaps|offers|pokes|plays|bows|gazes|looks (at|away from)|seems|performs|laughs|embraces|controls|consoles|bursts|gives|tries|cheers|blows|dotes|shows) (?!you|your)
```

## No Target Emotes
Less commonly used so more are likely to have slipped past. This is emote text such as `First Last cheers to the rhythm.` or `First Last performs the bee's knees dance.`

```
[a-zA-Z\'\-]{2,15} [a-zA-Z\'\-]{2,45} snaps (his|her) fingers|is uncontainably jubilant|is charmed|strikes a most gentlemanly pose|relaxes (his|her) pose|wipes (his|her) brow|keeps a watchful eye over (his|her) surroundings|buries (his|her) face in disbelief|motions joyfully|scatters coins about the area|lets out a cheer|dances happily|pats the air|bids farewell|performs an exotic Near Eastern dance|offers a moment of silence|readies for battle|raises (his|her) hand in greeting|cannot contain (his|her) feelings of affection|laughs|claps|begins explaining|hums playfully|kneels respectfully|staggers|bows
```

These lists were built by AFK'ing in Limsa for a few hours and blocking any emotes I saw used. As such it may not be 100% comprehensive. It is probably missing a lot of Mogstation emotes, Promotion emotes, and emotes unlocked with codes like Diamond Dust (`/iceheart)`.

Extend either filter by adding `|emote text` (with the pipeline!) to the end of the list or `emote text|` at the start of the list. For emotes that include pronouns you want to use `(his|her)` to filter for both genders such as `relaxes (his|her) pose`. Use the existing filters as an example of what `emote text` should be.

The regex have been condensed where it makes sense but not to the maximum extent that they could be. By this I mean I didn't condense around `(his|her)` text because it would make the regex considerably more complex than it needs to be.

No additional support will be given. False positives should be rare as long as the full emote text is added properly. NoSolicit doesn't support filters targetting specific channels as far as I can tell otherwise it would be easy to filter by filtering `(?!you)` from the Standard Emotes channel. :(
