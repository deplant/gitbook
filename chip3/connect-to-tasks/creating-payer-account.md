# Creating Payer Account

<figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption><p>Deposits Overview Block</p></figcaption></figure>

To Deposit VENOMs and CHIP3 Tokens, you just need to click corresponding buttons and sign transactions in your Venom Wallet. If you're working on **Venom DevNet**, there should be a **Test Faucet** button that will send you enough tokens.

<figure><img src="../.gitbook/assets/image (10).png" alt=""><figcaption><p>Allowances Grid</p></figcaption></figure>

To act as Payer for some Consumer smart-contract, you should Allowance for it. Just add enough allowance, so Consumer will be able to pay for Task executionFee. Here are the parameters of new allowance:

* **Consumer** - address of smart-contract that will make requests to Task
* **Task** - address of Task that contains Oracle Answer
* **Amount, Token** - amount of CHIP3 Token that Consumer can spend from your Account
* **Amount, Gas** - amount of VENOM that Consumer can spend from your Account
