---
description: Overview of Feed Explorer page of CHIP3 Web Service
---

# Feed Explorer

### Feeds Grid

<figure><img src="../.gitbook/assets/image (11).png" alt=""><figcaption><p>Feeds Grid</p></figcaption></figure>

Feeds grid has the following fields:

* **Logo** - logo of the Task if specified (_currently custom logos are not supported_)
* **Name** - name of the Task that was specified on creation
* **Address** - contract address of Task. You can click it to view account details on VenomScan
* **Maintainer** - creator of the Task that has the ability to change its Actions and Settings.
* **Trust Level** - There are three levels of Trust currently: DAO, Trusted & Untrusted. DAO has the highest Trust Level as the Protocol creator and large token holder. New Task Maintainers become Untrusted and can become Trusted after some time if their Tasks are considered predictable and stable.
* **Type** - Trigger & Consensus types of the Task. Check [Task Designer UI](https://app.gitbook.com/o/nKFWSRqItVOuJY8njn3b/s/0w4B8vKyJwKE2ZGWMXDu/\~/changes/24/create-new-tasks/task-designer-ui) for description of Consensuses and Triggers.

By clicking Name of the task in the Grid, you can get to Details of task.

### Feed Details

<figure><img src="../.gitbook/assets/image (9).png" alt=""><figcaption><p>Feed Overview Block</p></figcaption></figure>

Details is overview of different info about Task.

* **Name** - name of the Task that was specified on creation
* **Address** - contract address of Task. You can click it to view account details on VenomScan
* **Maintainer** - creator of the Task that has the ability to change its Actions and Settings.
* **Last Answer** - Trusted Oracle Answer from this Task
* **Last Answer Date** - Date and time when Trusted Answer was accepted
* **Last Answer Status** - status of Answer
* **Responses** - how much validators took part in the consensus / how much of they answers were accepted



<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption><p>Validators Grid</p></figcaption></figure>

**Validators List** contains info about **Validators** that took part in providing answer. They answer may differ if consensus is **Medianized**.

{% content-ref url="../build-new-feeds/task-designer-ui.md" %}
[task-designer-ui.md](../build-new-feeds/task-designer-ui.md)
{% endcontent-ref %}
