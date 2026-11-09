---
name: bankrollszn-dfs-lineups
description: Build DraftKings or FanDuel DFS lineups from BankrollSZN projections, ownership, and injuries. Use when the user asks for DFS lineups, an optimizer run, projections, or ownership for a slate.
---

# Build DFS lineups with BankrollSZN

## Setup

This skill uses the BankrollSZN MCP server. If the BankrollSZN tools are not available, tell the user to add this remote MCP server and sign in with their BankrollSZN account (OAuth, no API key):

- URL: https://bankrollszn.com/api/mcp
- Transport: Streamable HTTP
- Setup guide: https://bankrollszn.com/ai

A free BankrollSZN account works (100 calls a day, 20 rows per answer). The Fan plan ($4.99 a month) gives 2,000 calls a day and full player pools.

## Steps

1. Call the sport's list_slates tool (nba_list_slates, nfl_list_slates, nhl_list_slates, mlb_list_slates, wnba_list_slates, mma_list_slates, lol_player_pool) and confirm the slate with the user.
2. Call the sport's injuries tool (nba_injuries, nfl_injuries, nhl_injuries, wnba_injuries, mma_injuries) for late news.
3. Call the sport's projections or player_pool tool with the slate_id. For tournament play, also call the ownership_by_contest tool where it exists.
4. Ask for the contest type (cash, single entry, 3-max, 20-max, 150-max), the number of lineups, and any locks or excludes.
5. Call the sport's optimizer tool (for example nba_optimizer with contest_type, lock, exclude, lineups). For showdown slates, use the showdown_optimizer tool.
6. Show each lineup with salary, projection, and ownership. Give the DK ids when the user wants to upload.

## Rules

- Use only the numbers that the tools return. Do not invent projections, odds, or ownership.
- Say that projections and picks are model estimates, not guarantees.
- If a tool returns a plan limit, tell the user and call bankrollszn_account to show the plan and the calls used today.
