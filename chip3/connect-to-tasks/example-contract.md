# Example Contract

To connect your smart-contract to **CHIP3 Oracle Service**, you should do these steps:

* Choose a **On Request** or **Data Feed** task from [Feed Explorer](http://chip3.deplant.tech/feed-explorer) page. If you want to make your own custom task, go to [Task Studio](http://chip3.deplant.tech/task-studio) and deploy a new one. See [Create New Tasks](broken-reference) section for more info.
* Write a smart-contract that will send requests to chosen task. Here is the simple example:

```solidity
pragma ever-solidity ^0.64;

import "./int/IMedianizedConsumer.tsol";
import "../task/int/IMedianizedFeed.tsol";

contract ExampleConsumerTest is IMedianizedConsumer {

    uint128 _medianizedResult;
    address _currentTask;

    constructor() public {
        require(msg.pubkey() == tvm.pubkey(), 199); //NOT_MY_OWNER
        tvm.accept();
    }

    // ****************************************************************
    // Getter
    // ****************************************************************

    function getMedianizedResult() external view returns (uint128) {
        return _medianizedResult;
    }

    // ****************************************************************
    // External
    // ****************************************************************

    function calculateMedianizedFeed(address taskAddress_, address payerAddress_) external {
		// << CALL THIS METHOD TO GET RESPONSE >> 
        require(taskAddress_.value != 0, 444);
        require(msg.pubkey() == tvm.pubkey(), 199); //NOT_MY_OWNER
        tvm.accept();
        _currentTask = taskAddress_;
        IMedianizedFeed(taskAddress_).medianizedFeedRequest{value: 500_000_000, flag: 1, bounce: true}(payerAddress_);
    }

    function medianizedCallback(uint128 response_) override external internalMsg {
        require(msg.sender == _currentTask && msg.sender.value != 0, 198); // NOT_AWAITED_TASK
        _medianizedResult = response_;
		// << INSERT YOUR ACTIONS AFTER ORACLE RESPONSE HERE >> 
    }

}
```

* This contract implements `IMedianizedConsumer` interface and uses IMedianizedFeed interface to address task. This means that this contract works with task with Data Feed trigger type and Medianized consensus type. You can implement other interfaces from [here](https://github.com/deplant/venom-oracle/tree/master/contracts/src/main/solidity/consumer/int) and [here](https://github.com/deplant/venom-oracle/tree/master/contracts/src/main/solidity/task/int) to work with other types of tasks.
* Go to [Deposits](http://chip3.deplant.tech/deposits) page and deposit enough gas & tokens from any wallet that you have (or ask anyone who wants to act as your **Payer**). After depositting enough (check **Execution Fee** param of **Single Task** or **Data Feed** that you want to connect to.
* On the same [Deposits](http://chip3.deplant.tech/deposits) page, scroll down to Allowances List and add allowance. You should specify address of your consumer contract, address of the chosen feed and how much value and token you allow as **Payer** to spend on this **Consumer**-**Task** pair.
