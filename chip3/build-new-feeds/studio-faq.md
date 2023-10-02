# Studio FAQ

**How to receive multiple answers?**

You should encode all your answers in BOC string using **TvmCell Encode** action. Then, use `abi.decode()` method in your T-Sol contact to unwrap individual answers. Of course, this is only compatible with **Precise** type of Consensus.



**Provided action blocks are not enough. How can I add more sophisticated functions?**

You can use **HTTP Request** action to send requests to your own API or serverless functions with additional functionality. You can also open issue on our Github and we'll consider adding features.
