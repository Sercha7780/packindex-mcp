---
name: find-packaging-suppliers
description: Find suppliers or converters for a packaging material or a Design Studio project on the PackIndex Trade Exchange, filter by country or keyword, and send an RFQ to up to three of them after the user confirms.
---

# Find packaging suppliers and request quotes

1. **What to source.** Use the user's Design Studio project (`list_my_projects`, then its `project_id`) or a PackIndex material code (`search_indices` if they name it in words).
2. **Search.** Call `find_suppliers` with `project_id` or `material_id`, plus `region` (country or region, e.g. "Canada", "DE", "North America") and `query` for a name or keyword when given. Show live listings (price vs PackIndex benchmark) and matched converters.
3. **Confirm before sending.** List the chosen suppliers (max 3), quantity and target price, and wait for an explicit yes. `post_rfq` contacts real companies.
4. **Send** with `post_rfq` (`listing_ids` for listed suppliers, `company_slugs` for converters). Pass on any note the tool returns exactly — for example a test-account note.
5. **Follow up** with `get_my_rfqs`: who received the request and who responded. The buyer's identity is shared with a supplier only after that supplier responds.

Sending RFQs needs the user's OPN account and an Exchange plan; the tool explains what is missing if a limit applies.
