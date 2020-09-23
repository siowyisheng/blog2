---
title: "I Wrote the Jigoku Game Log Chrome Extension"
date: "2019-12-05"
description: "I wrote the Jigoku Game Log chrome extension and talk about my experience."
category: "code"
---

I recently wrote my first chrome extension, [Jigoku Game Log](https://chrome.google.com/webstore/detail/jigoku-game-log/cofpncfeggiibpickflljahgmhabgkeg).

#### Jigoku

Jigoku is an excellent online implementation of the excellent card game [Legend of the Five Rings](https://www.fantasyflightgames.com/en/products/legend-of-the-five-rings-the-card-game/). Game events are logged as messages in a chat area in a corner of the page, together with any chat between the players. No game replays are saved.

#### Jigoku Game Log

Jigoku Game Log goes into the DOM to extract the game events, omits superfluous information like chat messages, summarises and formats important information, and then sends this newly-produced game log to [markdownshare.com](https://markdownshare.com) to be saved for sharing and saving, for either analysis or sharing war stories with comrades.

#### Challenges

Using `const` and `let` gave me errors, so I used `var` throughout. I guess this might be because the script is constantly ongoing and doesn't get garbage collected.

Submitting the game log to markdownshare.com through the fetch API was difficult.

First, Chrome doesn't allow fetch API from most areas in the extension. It needs to be done in the `background.js`, so **message passing** needs to be used to get the fetch request to `background.js`.

Second, I had issues with permissions, with my request not getting sent, with no informative error logs. Turns out, there are several places to add the cross-origin site permissions to.

Third, the API usage example on markdownshare.com showed the use of cURL. What I didn't realise, what that cURL automatically sends the message with `ContentType:application/x-www-form-urlencoded` when using the `-d` option, so I needed to specify this manually with `fetch` and I also needed to do `encodeURIComponent()` on the text.

#### Results

More than 10 users in the L5R community are using the extension 😊.
