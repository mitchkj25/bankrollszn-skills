---
name: bankrollszn-nfl-fantasy
description: Answer NFL fantasy questions with BankrollSZN: start or sit, survivor picks, defense vs position, and injuries. Use when the user asks who to start, a survivor pick, or an NFL matchup for fantasy.
---

# NFL fantasy help with BankrollSZN

## Setup

This skill uses the BankrollSZN MCP server. If the BankrollSZN tools are not available, tell the user to add this remote MCP server and sign in with their BankrollSZN account (OAuth, no API key):

- URL: https://bankrollszn.com/api/mcp
- Transport: Streamable HTTP
- Setup guide: https://bankrollszn.com/ai

A free BankrollSZN account works (100 calls a day, 20 rows per answer). The Fan plan ($4.99 a month) gives 2,000 calls a day and full player pools.

## Steps

1. For start or sit, call nfl_start_sit with compare set to the player names. Show each projection and the chance each player scores more.
2. For survivor pools, call nfl_survivor and ask which teams the user already used.
3. For a matchup, call nfl_dvp, nfl_game_matchup, or nfl_player_matchup.
4. Call nfl_injuries and nfl_injury_vacancy for injury news and the teammates who gain.
5. Give one clear answer per question and the main reason for it.

## Rules

- Use only the numbers that the tools return. Do not invent projections, odds, or ownership.
- Say that projections and picks are model estimates, not guarantees.
- If a tool returns a plan limit, tell the user and call bankrollszn_account to show the plan and the calls used today.
