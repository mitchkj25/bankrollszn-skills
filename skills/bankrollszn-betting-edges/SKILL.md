---
name: bankrollszn-betting-edges
description: Find betting edges with BankrollSZN Monte Carlo picks, line shopping, props, and line movement. Use when the user asks for picks, the best odds, prop edges, or line moves.
---

# Find betting edges with BankrollSZN

## Setup

This skill uses the BankrollSZN MCP server. If the BankrollSZN tools are not available, tell the user to add this remote MCP server and sign in with their BankrollSZN account (OAuth, no API key):

- URL: https://bankrollszn.com/api/mcp
- Transport: Streamable HTTP
- Setup guide: https://bankrollszn.com/ai

A free BankrollSZN account works (100 calls a day, 20 rows per answer). The Fan plan ($4.99 a month) gives 2,000 calls a day and full player pools.

## Steps

1. For game picks, call the sport's sim_picks tool (nfl_sim_picks, nba_sim_picks, nhl_sim_picks, mlb_sim_picks, mma_sim_picks). Show the model price, the market price, and the graded record.
2. For the best price on a bet, call best_price with the sport, market (ml, spread, total, prop), and the team, player, stat, or line. Show the best book, the no-vig fair price, and the EV.
3. For player props, call the sport's props tool (nba_props, nfl_props, mlb_props, nhl_odds_props) and compare the model line with the book line.
4. For line moves, call the sport's line_movement tool (nfl_line_movement, mlb_line_movement, nhl_line_movement, mma_line_movement).
5. Give the bet_url only when the user asks to open a book.

## Rules

- Use only the numbers that the tools return. Do not invent projections, odds, or ownership.
- Say that projections and picks are model estimates, not guarantees.
- If a tool returns a plan limit, tell the user and call bankrollszn_account to show the plan and the calls used today.
