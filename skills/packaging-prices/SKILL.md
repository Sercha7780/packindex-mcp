---
name: packaging-prices
description: Answer "what does this packaging material or pack cost" with PackIndex benchmarks — polymers (PP, PET, HDPE), paper and board, corrugated boxes, films, metals, energy inputs. Use when the user asks for a price, a trend, or several prices at once.
---

# Packaging prices with PackIndex

1. **Find the code.** If the user names a material in plain words ("polypropylene", "recovered paper", "B-flute box"), call `search_indices` first and pick the best match. Skip this when they give a code (PP, CORR, KRLNR).
2. **Get the value.**
   - One material: `get_live_index`.
   - Several (up to 20): `get_prices` in one call.
   - A whole category or overview: `get_all_indices`.
   - A corrugated box from its dimensions: `estimate_packaging_price` (length, width, height in mm, flute, quantity, country).
3. **Trend:** `get_index_history` for how it moved; `explain_price_move` for why.
4. **Answer** with the value, unit, currency and as-of date, then the 1-week / 1-month / 1-year change. Cite it as "PackIndex" with the date. Show the user's currency when you know it.
5. **Plan limits:** without a paid OPN plan values are a 12-week delayed reference. Say so once and pass on the upgrade link the tool returns — never invent a newer number.

Values are indicative benchmarks, not supplier quotes. To test a quote the user received, use `check_quote`.
