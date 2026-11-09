---
name: bankrollszn-mlb-matchups
description: Research MLB matchups with BankrollSZN weather, park factors, splits, starters, and the home run board. Use when the user asks about an MLB game, home run picks, stacks, or weather.
---

# Research MLB matchups with BankrollSZN

## Setup

This skill uses the BankrollSZN MCP server. If the BankrollSZN tools are not available, tell the user to add this remote MCP server and sign in with their BankrollSZN account (OAuth, no API key):

- URL: https://bankrollszn.com/api/mcp
- Transport: Streamable HTTP
- Setup guide: https://bankrollszn.com/ai

A free BankrollSZN account works (100 calls a day, 20 rows per answer). The Fan plan ($4.99 a month) gives 2,000 calls a day and full player pools.

## Steps

1. Call mlb_starters for the probable pitchers, and mlb_postponements for weather risk.
2. Call mlb_weather and mlb_park_factors for the park and weather effect on the game.
3. Call mlb_matchup or mlb_player_matchup for a game or a batter vs pitcher read. Add mlb_hitter_splits and mlb_pitcher_splits for handedness splits.
4. For home run picks, call mlb_hr_board. Show the HR probability, our odds, the DraftKings price, and the edge.
5. For DFS stacks, call mlb_team_stacks.

## Rules

- Use only the numbers that the tools return. Do not invent projections, odds, or ownership.
- Say that projections and picks are model estimates, not guarantees.
- If a tool returns a plan limit, tell the user and call bankrollszn_account to show the plan and the calls used today.
