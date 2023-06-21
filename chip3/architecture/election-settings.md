# Election Settings

**minValidators**

Minimum amount of validators is a crucial setting for the security of your task on par with `maxFee`. When a task receives request (or deviation, schedule or any other condition) a new **RequestAuction** starts. This auction will include from `minValidators` to `minValidators*3` participants. If number of bids was less than `minValidators` **Auction** fails and task responds with FAILURE state. All additional bids after `minValidators*3` are rejected.

**maxFee**

Maximum fee is a sum that task **Maintainer** is ready to pay for a single Oracle response on this task. Still, this sum is a maximum fee and a precise fee is known after **Auction** happens between interested **Validators**. Each validator commits its bid and after reveal, `minValidators*3` bids will be selected with lowest bids.
