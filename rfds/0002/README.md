---
title: Webhook Integration for RFD Discussions
authors:
- aaron@example.com
state: discussion
discussion: https://appdevtest123.rocket.chat/group/699654dbb14c08f3bde403a8
tags:
- integration
- rocket-chat
---

## Summary

This RFD proposes integrating rfd-tool with Rocket.Chat to automatically create discussion threads for each RFD.

## Motivation

Currently, RFD discussions happen in various places - GitHub PR comments, Slack, email, etc. This fragmentation makes it hard to:

1. Find all discussion related to an RFD
2. Ensure the right people are involved
3. Track the evolution of decisions

## Proposed Solution

When an RFD is created or imported:

1. A webhook is sent to a Rocket.Chat app
2. The app creates a discussion in a designated channel
3. Authors are automatically added to the discussion
4. The discussion URL is returned and saved to the RFD

When an RFD is updated:

1. A webhook notifies the Rocket.Chat app
2. The app posts an update message showing what changed
3. State changes update the discussion description

## Implementation Status

This is being tested right now! 🚀🚀
