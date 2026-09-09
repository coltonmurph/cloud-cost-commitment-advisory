# Client Profile — Assemble Clothing (UK) Ltd

*Fictional client, built for this portfolio project.*

## Who they are

Assemble Clothing is a mid-size DTC streetwear brand based in
Manchester, UK. Started in 2014, ~140 employees, revenue in the
£40–60M range. Most of their customers are actually American — 60% US,
30% UK/EU, 10% everywhere else — even though the company is UK-based.
That mismatch is why comparing a UK region vs. a US region actually
matters here, instead of being an arbitrary choice.

## How they make money

Assemble does **monthly drops** — a limited collection releases on one
day each month and sells out fast, causing a huge traffic spike (10-20x
normal) for like 30-90 minutes. Then on top of that, they get the
normal retail bump every Nov/Dec (3-4x traffic for about 6 weeks).

So there are two totally different kinds of spikes to plan around: a
short, brutal one (drops) and a longer, more sustained one (holidays).
That's really the whole point of the project — those two need different
strategies.

## The tech situation

They moved off Shopify in early 2025 because Shopify couldn't handle
their drop-day traffic, and built their own infrastructure instead. Now
they run everything on-demand, sized big enough to survive a drop. The
problem: that means they're paying for peak capacity almost every day of
the year, even though the peak only happens for a few hours a month.
Leadership wants to know if switching some of that to reserved pricing
would actually save money, or if it's too risky given how spiky their
traffic is.

## What we're trying to answer

Would moving some (or all) of Assemble's compute to reserved pricing
save money without leaving them exposed during drops or the holiday
rush?

## What's in scope

- Compute (web/app/cache/database), object storage, managed database —
  that's it. No CDN, no egress, no other SaaS costs.
- Azure vs AWS, UK South vs East US.
- A 12-month simulated year, since they don't have real billing history
  yet post-migration.

## Assumptions I'm making

- Traffic patterns are simulated, not real data — built from what's
  described above.
- Database tier doesn't scale up/down automatically (this matches how
  most real database clusters get run).
- Using public list prices from each provider's API — not factoring in
  any enterprise/negotiated discounts.
- Everything's in USD.
