# Occasion planning with the scout agents

This repo also holds personal planning agents in `.claude/agents/`:

| Agent | Use it for |
| --- | --- |
| `food-scout` | Restaurants, chefs, new openings, award winners, supper clubs, chef's tables |
| `travel-scout` | Flights (Skyscanner), hotels, Airbnbs, trains, transfers, total trip cost |
| `experiences-scout` | Events, shows, classes, spa days, tours, activities, seasonal things |

## When asked to plan something (e.g. "organise my girlfriend's birthday")

1. **Write the brief.** Pull out who it's for, date(s), location (or "open to ideas"), party size, total budget, what they love and dislike, dietary needs, and whether it's a surprise. If key facts are missing (date, rough budget, home city), ask once in a single short list. Otherwise make sensible assumptions and state them.
2. **Split the budget** across travel, food and experiences, and decide what each agent needs to know.
3. **Run the agents in parallel** (one message, several Agent calls). Give each the full brief plus its slice of the budget and any fixed points (e.g. "dinner booked for Sat 8pm in Alfama"). Skip agents that aren't needed: a local dinner-and-show night doesn't need `travel-scout`.
4. **Pull it together** into one plan:
   - A short headline recommendation (the plan in 3 lines)
   - A day-by-day / hour-by-hour itinerary with travel times between stops
   - A cost table vs budget
   - A booking checklist in order of urgency (what sells out first, when bookings open)
   - 1–2 alternatives (cheaper / more special)
5. **Check it hangs together**: no clashes, realistic travel times, venues near the stay, opening days correct (many restaurants close Sun/Mon).
6. Offer to publish the final plan as a shareable page.

Nothing gets booked or paid for by the agents; they research and give links. The user books.
