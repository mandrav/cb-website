---
title: Infrastructure migration
description: Public update
date: "2021-02-25T13:04:57+02:00"
publishDate: "2021-02-25T13:04:57+02:00"
---

We will soon migrate the rest of our services to the new infrastructure. This will provide us better performance and uptime.
<!--more-->

### A little bit of history
We started planning to move everything to a new infrastructure since about November 2020.
Slowly but steadily we started creating migration scripts, testing, fixing the scripts, testing again, etc. The cycle went on.

Just to make it clear, the infrastructure side of things (servers, networks, etc) were ready. What was still pending was the actual migration procedure.

During the [recent network outage we experienced on Feb 9](/post/downtime-on-feb-9-2021), when we realized this wasn't and issue with our services or configuration and that we were not able to do anything to fix it ourselves, we had to come to the decision to enable the new website on the new infrastructure.

While the plan was to move all of our services (website, forums and wiki) to the new infrastructure in one go, the outage forced us to migrate what we already had ready for migration: the website.

The forums and the wiki were not ready to migrate at the time. A lot of testing was still needed before attempting the migration.

### Are we ready now?
We 're happy to report that all testing has finished and we 're now ready to perform the migration. The plan for it is to take place some time by the end of this week.

A few hours before the migration is about to start, we will post about it here as well as to the forums.
The actual migration itself should only take a few minutes. During that time, the forums will be in maintenance mode (no new posts) and the wiki will be in read-only mode.

When the migration is finished and tested, we will update the DNS records to point to the new infrastructure. This means that it may take a while for you to reach the new servers as DNS propagation is out of our control. You will just have to be patient until your DNS can point you to our new servers.
