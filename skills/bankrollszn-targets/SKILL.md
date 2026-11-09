---
name: bankrollszn-targets
description: Backtest a player type against one defense and save it as a BankrollSZN Target. Use when the user asks how a kind of player does against a team, or asks for tonight's target plays.
---

# Backtest and save Targets with BankrollSZN

## Setup

This skill uses the BankrollSZN MCP server. If the BankrollSZN tools are not available, tell the user to add this remote MCP server and sign in with their BankrollSZN account (OAuth, no API key):

- URL: https://bankrollszn.com/api/mcp
- Transport: Streamable HTTP
- Setup guide: https://bankrollszn.com/ai

A free BankrollSZN account works (100 calls a day, 20 rows per answer). The Fan plan ($4.99 a month) gives 2,000 calls a day and full player pools.

## Steps

1. Ask for the sport (NBA, NFL, NHL, MLB), the defense, and the player traits. Example: NBA players with Isolation on 12% or more of possessions vs ORL.
2. Call backtest_draft_target with sport, defense, and the traits (play_types, zones, positions, min, max).
3. Show the per-stat delta, the hit rate, the sample size, and the players who qualify on today's slate.
4. Ask the user if they want to save it. If yes, call my_targets with action save, the same arguments, and a label.
5. For tonight's plays from saved targets, call my_targets with action tonight.

## Rules

- Use only the numbers that the tools return. Do not invent projections, odds, or ownership.
- Say that projections and picks are model estimates, not guarantees.
- If a tool returns a plan limit, tell the user and call bankrollszn_account to show the plan and the calls used today.
