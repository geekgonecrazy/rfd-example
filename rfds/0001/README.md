---
title: How to Write an RFD
authors: 
- Aaron Ogle
state: committed
tags:
- rfd-process
---

The RFD Process is modeled after the [RFD process from Oxide Computer](https://oxide.computer/blog/rfd-1-requests-for-discussion).

RFD stands for Request For Discussion which are essentially RFC's but the idea being discussion is wanted vs RFC where its largely decided.  We want to encourage more collaborative engagement.

## When to use an RFD

The following are examples of when an RFD is appropriate, these are intended to be broad:

* An architectural or design decision for hardware or software
* Change to an API or command-line tool used by customers
* Change to an internal API or tool
* Change to an internal process
* A design for testing

RFD can apply to technical ideas but also overall company ideas and processes as well. 

## RFD metadata and State

```
---
title: How to write an RFD
authors: 
- Aaron Ogle
state: ideation
tags: 
- project-name
---
```

We keep track of three pieces of metadata:

* title: The title of the RFD
* authors: the authors (and therefore owners) of an RFD
* state: must be one of the states discussed below.
* discussion: for RFD that are in or beyond the discussion state, this should be a link to the PR to integrate the RFD; see below for details.
* tags: the tags that can be used to group RFDs that belong to same project or system

An RFD can be in one of the following six states:

* prediscussion
* ideation
* discussion
* published
* committed
* abandoned

### prediscussion

This is before the the RFD is ready for discussion. Equivalant to a draft

### ideation

A document in the ideation state contains only a description of the topic that the RFD will cover, providing an indication of the scope of the eventual RFD. Unlike the prediscussion state, there is no expectation that it is undergoing active revision. Such a document can be viewed as a scratchpad for related ideas. Any member of the team is encouraged to start active development of such an RFD (moving it to the prediscussion state) with or without the participation of the original author. It is critical that RFD in the ideation state are clear and narrowly defined.

### discussion

Documents under active discussion should be in the discussion state. At this point a discussion is being had for the RFD in a Pull Request.

### published

Once (or if) discussion has converged and the Pull Request is ready to be merged, it should be updated to the published state before merge. Note that just because something is in the published state does not mean that it cannot be updated and corrected. See the Making changes to an RFD section for more information.

### committed

Once an idea has been entirely implemented, it should be in the committed state. Comments on ideas in the committed state should generally be raised as issues — but if the comment represents a call for a significant divergence from or extension to committed functionality, a new RFD may be called for; as in all things, use your best judgment.

### abandoned

If an idea is found to be non-viable (that is, deliberately never implemented) or if an RFD should be otherwise indicated that it should be ignored, it can be moved into the abandoned state.

## New RFD

### Reserve a RFD Number

You will first need to reserve the number you wish to use for your RFC. This number should be the next available RFD number from looking at the current: 

```
$ git branch -r output
```

### Create a branch for your RFD

Now you will need to create a new git branch, named after the RFD number you wish to reserve. This number should have leading zeros if less than 4 digits. Before creating the branch, verify that it does not already exist:

```
$ git branch -rl *0042
```

If you see a branch there (but not a corresponding sub-directory in RFD in master), it is possible that the RFD is currently being created; stop and check with co-workers before proceeding! Once you have verified that the branch doesn’t exist, create it locally and switch to it:

```
$ git checkout -b 0042
```

### Create a placeholder RFD

Now create a placeholder RFD. You can do so with the following commands:

```
$ mkdir -p RFD/0042
$ cp TEMPLATE.md RFD/0042/README.md
```

### Push your RFD branch remotely

Push your changes to your RFD branch in the RFD repo.

```
$ git add RFD/0042/README.md
$ git commit -m ‘0042: Adding placeholder for RFD <Title>’
$ git push origin 0042
```

Open a Pull Request.

### Update with discussion link
Once you are ready for discussion update with a PR link.  Every state besides ideation / pre-discussion requires a discussion link.

### Sharing an RFD

RFD's can be seen at https://RFD.rocket.chat.  You can link directly to an RFD at: https://RFD.rocket.chat/42 or https://RFD.rocket.chat/0042

