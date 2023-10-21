# Auction

* **Proposed Price** - Task owner chooses what maximum price he's ready to pay for a fulfillment of request on his task. All requesters of this task should apply at least this sum with their request or request will not be processed and funds will return to requester.
* **Task Auction** - When task receives request for immediate processing or previous data becomes too old, Task starts a new Auction to find validators that want to process Task at a cheapest price. Task Auction is a **Reverse Vickrey Auction**. It means that participants do accept to run a task for 2nd lowest price.
