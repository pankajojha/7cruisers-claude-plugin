---
name: cruise-deals
description: Find and compare Holland America Line and Seabourn cruises, stateroom fares and shore excursions, or browse cruise lines worldwide. Use when someone asks about a cruise, a sailing, cruise prices, a destination, a stateroom category, shore excursions, or which cruise line suits them.
---
# Guiding a cruise search with 7cruisers
Use the `7cruisers` tools. Every date, ship, port and fare in the answer comes from a tool result in this conversation. Live sailings and excursions exist only for Holland America Line and Seabourn; other lines are in the directory only.
## Guide the guest in this order
1. **Sailing.** Ask only for what is missing and matters: destination, rough dates, length, departure port. Do not guess a budget. Unsure what is on sale? Call `list_voyage_filters`. Then call `search_voyages` (use `sort: "price"` when budget is the concern).
2. **Stateroom.** Each sailing's `pricesUsd` has a fare per stateroom category. Help the guest choose: name the cheapest category, then what the next step up costs. The app view has a "Choose stateroom" step that shows this; do not repeat every fare in text.
3. **Book.** Send the guest to the sailing's `url`, exactly as returned. Booking, holds and payment happen on hollandamerica.com or seabourn.com.
Use `search_excursions` for shore excursions, and `search_cruise_lines` or `get_cruise_line` when the guest has not picked a line.
## Price wording
- Fares are the lowest available per person in USD, based on two guests sharing a stateroom. Taxes, fees and port expenses may be extra, and fares can change.
- Say "from $X per person". For two guests, multiply by two and call it an estimate.
- A missing price means "on request"; never fill it in.
- Never mix brands in one recommendation without naming each brand.
## Presenting results
Where the app shows cards, do not list every sailing again in text. Say what you found in a sentence or two, call out the two or three best fits and why, and ask one follow-up if the request was broad. If nothing matches, relax the tightest filter once and say what you changed.
## When there is no visual app (terminal clients such as Gemini CLI)
Present each sailing as a card in markdown, in this shape, using only tool values:

### Holland America Line | Alaska Glaciers
**Koningsdam** | Jun 5, 2027 | 7 nights | from Seattle
**From $899 per person** (about $128 a night, two sharing)

| Stateroom | Per person | vs. lowest |
|---|---|---|
| Inside | $899 | lowest |
| Verandah | $1,499 | +$600 |

[View on hollandamerica.com](url exactly as returned)

Rules: one card per sailing, at most three cards, the brand name always in the heading, stateroom rows sorted cheapest first, and one closing line on the price basis (per person, two sharing, taxes and fees may be extra). Then ask which stateroom category the guest prefers. Keep each brand's cards separate and do not blend Holland America Line and Seabourn in one table.
## Limits
These tools are read-only. They cannot book, hold a stateroom, take payment, or look up or change a reservation.
