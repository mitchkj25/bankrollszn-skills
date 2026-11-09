---
name: bankrollszn-get-started
description: Introduce BankrollSZN and run a first DFS or betting query. Use when the user first connects BankrollSZN or asks what BankrollSZN can do.
---

# Get started with BankrollSZN

## Setup

This skill uses the BankrollSZN MCP server. If the BankrollSZN tools are not available, tell the user to add this remote MCP server and sign in with their BankrollSZN account (OAuth, no API key):

- URL: https://bankrollszn.com/api/mcp
- Transport: Streamable HTTP
- Setup guide: https://bankrollszn.com/ai

A free BankrollSZN account works (100 calls a day, 20 rows per answer). The Fan plan ($4.99 a month) gives 2,000 calls a day and full player pools.

## Steps

1. Tell the user in one or two sentences that BankrollSZN gives free DFS and sports betting analytics for NBA, NFL, NHL, MLB, WNBA, PGA, UFC, and League of Legends.
2. Call bankrollszn_account to show the user's plan and the calls left today.
3. Ask which sport and which task the user wants: projections, lineups, odds, picks, or a matchup.
4. Run the matching tool. For a DFS slate, call the sport's list_slates tool first (for example nba_list_slates).
5. Show the result in a short table and give the main takeaway.

## Rules

- Use only the numbers that the tools return. Do not invent projections, odds, or ownership.
- Say that projections and picks are model estimates, not guarantees.
- If a tool returns a plan limit, tell the user and call bankrollszn_account to show the plan and the calls used today.
