# Sakhi

**An AI agent for fair orders, fair pay and trust in women's self-help groups (SHGs).**

Sakhi is a WhatsApp-first, voice-first AI agent that helps women's SHGs take on bulk orders without losing money or trust. It costs each order properly, splits the work fairly, tracks progress through voice notes in the member's own language, checks quality from photos, and calculates every member's payout from her recorded work. The group approves every payout, and each member can hear her own record at any time.

> **Status:** Idea stage. Built for Problem Statement **8.1** (Youth and Women: Jobs and enterprise empowerment). The prototype will be developed between November 23 and December 15, 2026.

---

## The problem

India has about 10 crore women organised in about 90 lakh SHGs under DAY-NRLM, and many of these groups take bulk orders for garments, food and crafts. Today one leader splits the work verbally, tracks it in a notebook, checks quality only when everything comes together, and divides payment by estimate.

As a result:

- **Members underprice by 30–40%** because material, labour and margin are never calculated.
- **Deadlines are missed and batches are rejected** because nobody sees early that a member is falling behind.
- **Trust erodes** under manual accounts, and members leave the group.
- **Members with low literacy can't check** their own work or earnings.

## Our insight

The problem isn't a lack of skill or demand. It's the lack of a fair, transparent coordination layer that works for women who use WhatsApp and voice, not apps and spreadsheets. If every member can see and hear her own record, trust follows, and so do better orders.

## How Sakhi works

```
Buyer order ──► Order Intake ──► Costing ──► Allocation ──► Progress Tracking
                                                                   │
  Trust Ledger ◄── Fair Payout ◄── Group approval ◄── Quality Assist
```

| Agent | What it does |
|---|---|
| **Order Intake** | Reads the buyer's order (text, voice or photo) and extracts the product, quantity, specification, price and deadline. |
| **Costing** | Works out the true cost (material, labour hours, overheads, margin) and flags underpriced orders, e.g. *"At ₹40 per bag you lose ₹6. A fair price is ₹52."* Helps the leader make a counter-offer. |
| **Allocation** | Splits the order fairly across members by skill, availability and past output, and explains every allocation. |
| **Progress Tracker** | Turns voice notes like *"finished 30 today"* into ledger entries, predicts deadline risk early and suggests reassigning work. |
| **Quality Assist** | Flags likely defects in photos of finished pieces against the buyer's specification. The leader or quality checker has the final word. |
| **Fair Payout** | Calculates each member's share from her verified output, sends it to the group for approval, and reads each member's earnings aloud in her language. |
| **Trust Ledger** | Logs every issue, delivery, quality decision and payment. Each member sees her own entries, and the group gets a verifiable track record. |

### Example

1. A buyer sends: *"500 cotton bags, ₹40 each, 3 weeks."*
2. Sakhi replies to the leader: *"At ₹40 you lose ₹6 per bag. A fair price is ₹52. Here's a counter-offer you can send."*
3. The work is split across 12 members, and each gets her share by WhatsApp voice message.
4. Members send voice updates. When one falls behind, Sakhi suggests moving 40 bags to two other members.
5. After delivery, the group approves the payout, and each member hears: *"Sunita, you made 48 bags. You earned ₹1,152."*

## Planned tech stack

| Layer | Choice |
|---|---|
| Agent orchestration | LLM with tool calling (Claude). All calculations run in code, never guessed by the model. |
| Voice | Indian-language speech-to-text and text-to-speech (Bhashini / Sarvam AI), starting with Hindi and Kannada |
| Channel | WhatsApp Business Cloud API, so members don't need to install an app |
| Vision | Photo-based quality flags, set up per product from a few sample images |
| Backend | FastAPI |
| Database | PostgreSQL (ledger) |
| Dashboard | React, for the SHG leader |

## Trust and safety

- **Each member owns her record.** She can see and hear her own entries, and no member's data goes to outsiders without the group's consent.
- **The AI suggests and the group decides.** Allocations, quality decisions and payouts all need human approval.
- **Every number can be explained.** Costing shows how each figure was calculated, so the leader can explain it to members and buyers.
- **Designed for low literacy.** Voice in and out, icons, and confirmation by voice.

## Impact we'll measure

- Margin recovered per order (target: close most of the 30–40% underpricing gap)
- On-time delivery rate and batch rejection rate
- Payout disputes and member retention
- Groups that use their delivery record to win repeat orders or SHG bank credit

## Sustainability

- **Free for SHG members.**
- **Buyers and brands** pay to find verified, on-time SHG suppliers.
- **Banks and NBFCs** that lend to SHGs get a verifiable record of income and delivery, with the group's consent.
- **SHG federations and State Rural Livelihood Missions** are partners for reaching groups at scale.

## Roadmap

- [x] Problem research and idea submission (November 2026)
- [ ] Field interviews with SHG members and federation staff
- [ ] Order intake, costing agent and ledger over WhatsApp text
- [ ] Allocation agent, voice in and out (Hindi + Kannada), photo quality checks
- [ ] Fair payout with group approval, and the leader dashboard
- [ ] End-to-end demo: one SHG, 12 members, one real bulk order
- [ ] Field test with an SHG before the Grand Finale (December 27, 2026)

## Team

A team of four, building Sakhi for the hackathon's Youth and Women track.
