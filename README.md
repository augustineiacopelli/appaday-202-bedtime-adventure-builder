# Bedtime Adventure Builder | AppADay 202

Bedtime Adventure Builder writes a calm, choose your path bedtime story for a child. Pick one of eight worlds (Space, Ocean, Forest, Dragons, Dinosaurs, Farm, Castle, or Toy Shop), an age band, and optionally the names of up to four children, and Claude writes the whole branching story in one request. You read it aloud and the child chooses where it goes at each turn.

## Age bands

Each band sets the length of every segment, the vocabulary, the sentence length, and the number of choices along the way.

| Ages | Words per segment | Choices per path | Story nodes |
| --- | --- | --- | --- |
| 3 to 4 | about 40 | 2 | 7 |
| 5 to 6 | about 70 | 3 | 15 |
| 7 to 8 | about 100 | 3 | 15 |
| 9 to 10 | about 140 | 3 | 15 |

## How it works

Claude returns the full story as a JSON tree. Before anything is shown, the app checks that every choice leads to a real node, that every node can be reached, that there are no loops, that every non-ending node offers exactly two labeled choices, that every leaf is a written ending, and that every path takes exactly the band's number of choices. If the tree fails any check, or the reply is cut off at the token limit, the app asks once more and tells Claude exactly what was wrong. The content rules keep things cozy, with no frightening villains or peril, and every ending winds down toward sleep.

Because the whole tree arrives at once, Read Again replays the same story from the top with no further API call, so a child can take a different path the second time for free. New Adventure writes a fresh story with the same settings. With one name, that child is the hero in third person. With two to four names, the children adventure together as a team, each gets a moment to help or shine in every segment, every ending tucks all of them in, and the closing line says Sweet dreams to each of them by name. With no names, the story is told in second person.

## Settings

The gear opens Settings, which holds the shared AppADay Claude key manager, a three step story text size that is remembered, and Clear Saved Settings with an in app confirmation. The world, age band, names, and text size are saved only in this browser under the key appaday202.settings. Names are added one at a time with Add, Enter, or a comma, shown as removable chips, and limited to letters, spaces, and apostrophes, up to 20 characters each.

## Accessibility

Story text sits in a polite live region, focus moves to the first choice after each segment, choice buttons are at least 56 pixels tall, and the twinkling star layer, the moon animation, and the fades all switch off under reduced motion.

## Files

The whole app is one file, `index.html`, with no build step. It loads `save.js`, `models.js`, and `keys.js` from the AppADay portal, plus the Nunito font from Google Fonts. The model comes from the portal's models.js, so the file carries no model name of its own.

## Portfolio

Part of [AppADay](https://augustineiacopelli.github.io/appaday/), one app built and shipped every day.
