# Business memo — Pre-retention checks

Key investigations before any campaign:
- Verify no leakage: use only data <= 2025-09-30 for features.
- Payment/dunning: check failed payment flags (in orders or payment logs).
- Support backlog: prioritize customers with >3 tickets/unresolved tickets.
- Low engagement: test small re-engagement pilots for sessions_30d <=1.
- Outliers & returns: inspect extreme `gross_amount` and high return customers before using monetary raw.

Priority: 1) leakage/payment, 2) support backlog, 3) low engagement, 4) high-return customers.