# Fishermen

One of the most important aspects of Orscle trusted answers is the ability to change feed answers based on deviation. If the price delta gets above certain threshold, TrueQuery should start producing new answer consensus. In systems like Chainlink, validator nodes are used to provide this ability. Node should do extra work (aside from providing responses) - constantly rechecking previous responses until deviation was found (or time deviation exceeds).&#x20;

In TrueQuery this role is delegated from Validators to Fishermen. Fishermen are light apps for desktop or mobile phone. Their goal is to utilize Fishermen's owner' machine resources for constant recheck of Trusted Answers. After answer is checked, Fishermen vote with their staked tokens for deviation (and produce of new answer) or stability (no new answer needed).&#x20;

To be able to take part in fishing, Fishermen should provide a stake on his Storage account equal to 1/1000 of Validator minimum stake. This is needed as Fishermen are responsible for their voting. After timeout ends, all current votes are counted and if Soft Majority Voting ends with deviation win, new answer is produced, those who voted for right outcome are rewarded and for wrong - slashed. Vote for deviation is 1.5x more rewarding than for stability. Slashing occurs after series of bad votings. You can choose aggressiveness strategy in Fisherman app. Max aggressiveness means vote for deviation right on threshold pass. Min aggressiveness checks means vote for dev on threshold+50% pass.

