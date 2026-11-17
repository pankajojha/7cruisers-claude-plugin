# 7cruisers plugin for Claude

Search real Holland America Line and Seabourn sailings, compare stateroom fares, browse shore excursions, and explore a directory of cruise lines worldwide. Data comes from the public search of each cruise line's site through the free [7cruisers.com](https://www.7cruisers.com) MCP server. No sign-in or API key is needed.

## Install (Claude Code)

```
/plugin marketplace add pankajojha/7cruisers-claude-plugin
/plugin install 7cruisers@7cruisers
```

## Claude.ai, Claude Desktop

Add a custom connector with the URL `https://www.7cruisers.com/mcp` (authentication: none).

## Try it

- "Alaska cruises from Seattle in June 2027 under $2,500"
- "Compare stateroom prices on Seabourn Antarctica sailings"
- "Shore excursions in Juneau"

## What it includes

- An MCP server entry for `https://www.7cruisers.com/mcp` (tools: `search_voyages`, `list_voyage_filters`, `search_excursions`, `search_cruise_lines`, `get_cruise_line`, `list_filters`, `get_cruise_deals`).
- A `cruise-deals` skill that guides the search from sailing to stateroom to booking.

## Limits and privacy

Read-only. The plugin cannot book, hold or pay. Booking happens on the cruise line's own site. Fares are per person, can change, and exclude taxes and fees. Search terms you give Claude are sent to 7cruisers.com to run the search. 7cruisers.com does not require an account and is not affiliated with Holland America Line or Seabourn. Names are used only to describe what can be searched.

## Support

Use the form at https://www.7cruisers.com/contact/ or open an issue in this repo.

## License

MIT
