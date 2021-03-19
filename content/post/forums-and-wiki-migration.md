---
title: Forums and Wiki migration
description: Public update
date: "2021-03-19T16:51:42+02:00"
publishDate: "2021-03-19T16:51:42+02:00"
---

During the next couple of days, the forums and wiki will be migrated over to the new infrastructure.
<!--more-->

It took a bit longer than what we anticipated but the time has finally come to make the switch.
The steps involved are:

* **The wiki will become read-only**. It will continue to be available but no edits will be possible.
* **The forums will enter maintenance mode**. This means only the front page will be available. No posting will be possible.
* **The latest backup of both the forums and the wiki will be downloaded to the new infrastructure**.
* **The migration scripts will run**. These scripts should only take a few minutes each (at least according to our tests).
* When the migration scripts finish, we will test and ensure everything has migrated.
* **The DNS entries will be updated**. After this point they will be pointing to the new, migrated services.

The old services will "fade out" and the new services will become the main ones, as DNS propagates.

Based on the above, the time window the services will be limited/inaccessible should be minimal, about 5-10 minutes... **for most people**.
It all has to do with the time DNS propagation takes which is highly dependent on your network settings, your ISP's settings, etc. So, for some it may take 5 minutes while for others it may take 30-60 minutes.
We just all have to be patient during that time.

Let's just hope everything goes as planned!

_See you on the other side ;)_

