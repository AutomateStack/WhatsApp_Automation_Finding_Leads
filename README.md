# ShoppingHub Seller Lead Finder

Lead intelligence system for finding Indian product sellers who appear to sell through Instagram/WhatsApp/DM and do not have a detected independent website or checkout.

## V1 target
- Geography: India
- Categories: all product categories
- Instagram followers: >5,000
- Strong signals: WhatsApp, Facebook, DM/order language
- Critical qualification: no independent website/checkout detected
- Manual order processing is an inference and must always retain supporting evidence.

## Architecture

`Discovery -> Candidate -> Evidence -> Website verification -> Scoring -> Human review -> CRM -> Seller onboarding`

Supabase project: **Seller Shopping Hub**

Database domain: `leads`

- `leads.candidates`
- `leads.social_profiles`
- `leads.evidence`
- `leads.websites`
- `leads.scores`
- `leads.reviews`
- `leads.activities`

## Accuracy principle

The system must not claim that a seller definitely processes orders manually unless that fact is directly verified. Public signals are stored as evidence and converted into a likelihood score. Human review creates the ground truth used to measure precision and improve scoring.

## Compliance principle

Do not implement login-based scraping, access-control bypasses, or collection of private data. Discovery and enrichment should use permitted APIs and lawful/public sources, with source URLs and timestamps retained for auditability.

## Current validation batch

The first 10 research candidates are stored in the `leads` schema for verification. They are **not yet considered verified leads**.
