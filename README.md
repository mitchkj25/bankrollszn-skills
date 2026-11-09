# BankrollSZN agent skills

Agent skills for [BankrollSZN](https://bankrollszn.com). BankrollSZN gives free DFS and sports betting analytics for NBA, NFL, NHL, MLB, WNBA, PGA, UFC, and League of Legends.

## Install

```bash
npx skills add mitchkj25/bankrollszn-skills
```

The skills work with Claude Code, Cursor, Codex, Gemini CLI, and other agents that read SKILL.md files.

## Connect the BankrollSZN MCP server

The skills call the BankrollSZN MCP server. Add it to your agent:

- URL: `https://bankrollszn.com/api/mcp`
- Transport: Streamable HTTP
- Auth: OAuth. Sign in with your BankrollSZN account. No API key.

Claude Code example:

```bash
claude mcp add --transport http bankrollszn https://bankrollszn.com/api/mcp
```

Free account: 100 calls a day, 20 rows per answer. Fan ($4.99 a month): 2,000 calls a day and full player pools.

## Skills

| Skill | What it does |
| --- | --- |
| bankrollszn-get-started | Introduce BankrollSZN and run a first DFS or betting query. |
| bankrollszn-dfs-lineups | Build DraftKings or FanDuel DFS lineups from BankrollSZN projections, ownership, and injuries. |
| bankrollszn-betting-edges | Find betting edges with BankrollSZN Monte Carlo picks, line shopping, props, and line movement. |
| bankrollszn-mlb-matchups | Research MLB matchups with BankrollSZN weather, park factors, splits, starters, and the home run board. |
| bankrollszn-nfl-fantasy | Answer NFL fantasy questions with BankrollSZN, such as start or sit, survivor picks, defense vs position, and injuries. |
| bankrollszn-targets | Backtest a player type against one defense and save it as a BankrollSZN Target. |

## Links

- Website: https://bankrollszn.com
- AI setup guide: https://bankrollszn.com/ai
- Tool directory: https://bankrollszn.com/tools

Projections and picks are model estimates, not guarantees. Bet responsibly.

## License

MIT
