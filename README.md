# SankeyArt for Claude

Turn income statements, cash flow statements, balance sheets and budgets into Sankey diagrams, right from Claude and Claude Code. Give Claude the figures, in the chat or in a file, and SankeyArt shows where the money comes from and where it goes: revenue split into costs and profit, cash flows by activity, or a budget by category. Every diagram opens in the [SankeyArt](https://www.sankeyart.com) editor, where you can fine-tune it and export it for slides and reports.

This plugin brings two things:

- **The SankeyArt connector**, an MCP server at `https://mcp.sankeyart.com/` with the tools `draft_sankey`, `create_sankey`, `update_sankey`, `get_sankey` and `list_my_sankeys`.
- **The skill `financial-statement-sankey`**, which tells Claude how to lay out each kind of statement so that the diagram reads well.

## Install in Claude Code

```
/plugin marketplace add sankeyart/claude-plugin
/plugin install sankeyart@sankeyart
```

Then run `/mcp` and choose **sankeyart** to sign in to SankeyArt when you want your diagrams saved in your account.

Only want the connector, without the skill? One command adds it:

```
claude mcp add --transport http --scope user sankeyart https://mcp.sankeyart.com/
```

If you added SankeyArt with that command before, the plugin uses that connection and adds the skill.

## What needs an account

Drawing a diagram needs no account: `draft_sankey` returns a link that opens the diagram in the SankeyArt editor. Saving diagrams in your SankeyArt account, listing them and changing them from Claude needs a SankeyArt subscription and signing in through `/mcp`.

SankeyArt draws only the figures you give it and doesn't give financial advice.

## Support

- Help and questions: [FAQ](https://www.sankeyart.com/faq/) or support@sankeyart.com
- [Privacy policy](https://www.sankeyart.com/privacy/) and [terms](https://www.sankeyart.com/terms/)

## Releasing

Bump `version` in `.claude-plugin/plugin.json` with every change, or `claude plugin update` tells users they are already up to date. Whatever is on `main` reaches users who added this marketplace right away. The skill is kept the same as the one in the ChatGPT plugin.

## License

[MIT](LICENSE)
