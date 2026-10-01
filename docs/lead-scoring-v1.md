# Lead Scoring V1

## Qualification gates

A candidate can enter the high-confidence review queue only when:

1. Instagram account is a product/business account or has strong product-selling evidence.
2. Follower count is greater than 5,000.
3. India is supported by public business/location evidence.
4. No independent website/checkout is detected after verification.

## Evidence weights

### Manual-order evidence

- Explicit `DM to order`: very strong
- Explicit `WhatsApp to order`: very strong
- Instructions to send name/address/pincode by DM/WhatsApp: very strong
- `DM for price`: strong
- Public WhatsApp ordering contact: strong
- UPI/payment instructions tied to DM/WhatsApp: strong
- COD/payment language without checkout: supporting
- No website: supporting, never conclusive by itself

### Confidence rules

`manual_order_likelihood` represents evidence-supported likelihood, not a verified fact.

`qualification_confidence` represents confidence that the candidate matches the ShoppingHub lead definition.

The UI should always show the evidence behind both scores.

## Human validation

Review decisions:

- `yes` — evidence supports manual/DM/WhatsApp ordering
- `no` — evidence contradicts the classification
- `unclear` — insufficient evidence

The first goal is to measure precision on a small validation set before scaling discovery.

## Do not infer

Do not infer exact order volume, revenue, payment ownership, private operational processes, or customer information from public social signals.
