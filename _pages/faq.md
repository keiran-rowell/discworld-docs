---
permalink: /faq/
title: "Frequently Asked Questions"
layout: single
classes: wide
author: nathan_glades 
toc: true
toc_label: "Q&A"
toc_icon: "question-circle"
toc_sticky: true
---

### Introduction

Below are some answers to some commonly asked questions. If you have a question that has not been answered here, please feel free to reach out

### Q: I’m out of disk space in my home folder. I deleted some files, but the space is not freeing up
A: Discworld uses disk snapshots to protect files from accidental file deletion or overwrites. Snapshot use counts towards quota use, but presents as a reduction in total available disk size, rather than disk usage. Snapshots are kept for 14 days, so you will not see this reflected until then. We can temporarily increase your disk quota if this is critical to get your work done.

### Q: CryoSPARC says it has an update. Can you update CryoSPARC?
A: Discworld runs per-user CryoSPARC instances, so it is possible to update your own instance when you have down-time. Similarly, if you wish to stay on an older version of CryoSPARC (say for familiarity or result consistency), you can opt not to update your instance. Please see the update documentation here: 

 

### Q: I am trying to start CryoSPARC, but it is stuck “awaiting job configuration”
A: 99% of the time, this is due to an existing CryoSPARC session still running. CryoSPARC will attempt to start the database, which is already running, causing it to hang. Please check that you do not have any running CryoSPARC sessions, using the squeue --me --name='cryosparc' command. You can then use the scancel command to kill old sessions. 

### Q: I see a time limit on my CryoSPARC server. What will happen to my jobs when the limit is reached?
A: Your CryoSPARC server runs as a regular compute job. Every compute job must have a time limit associated with it. However, in the case of CryoSPARC, the master service must be running for any compute jobs to keep running. As such, we have a script that ensures your CryoSPARC master server will not time out whilst you have jobs running. If the time limit is reached and all jobs have completed, a 4-hour grace period will start. Once this period passes, your CryoSPARC server will shut down. Your server will never shut down whilst you have jobs running.

### Q. What location do I provide for the Topaz and DeepEMHancer within the CryoSPARC portal?
A: 
* Path to Topaz Executable: `/programs/run_topaz.sh`
* Path to DeepEMhancer Executable:  `/programs/run_deepemhancer.sh`
* Path to DeepEMhancer Models: `/programs/deepemhancer_models`

### Q. How do I hand-off CryoSPARC project data between users (_i.e._ instances)
A: 
* Share entire projects cleanly with an [Import](https://guide.cryosparc.com/guides-for-v3/tutorial-data-management-in-cryosparc#use-case-share-an-entire-project-with-another-user-in-a-different-instance)
* Use the [Export](https://guide.cryosparc.com/guides-for-v3/tutorial-data-management-in-cryosparc#use-case-share-a-particular-job-with-another-user) feature to cleanly hand off a particular job, and only that job
* [Detach](https://guide.cryosparc.com/setup-configuration-and-management/software-system-guides/guide-data-management-in-cryosparc-v4.0#detach)/Attach of a project should only be done when moving instances (complete hand-off/moving institutes)
* [Archiving](https://guide.cryosparc.com/setup-configuration-and-management/software-system-guides/guide-data-management-in-cryosparc-v4.0#archive) is for preparing for long-term disk storage

