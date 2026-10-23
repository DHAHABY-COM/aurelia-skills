<p align="center"><img src="assets/aurelia.png" width="96" alt=""></p>

# Aurelia by Dhahaby: skills and MCP for AI agents

Aurelia is Dhahaby's gold assistant for the UAE. This repo connects any AI agent to it:

- today's gold price in AED;
- what you could borrow against your gold, with a gold-backed loan or a gold-backed card;
- partner jewellers for a certified appraisal;
- after you sign in, your own Dhahaby account (read-only): gold pieces, appraisal appointments, loan and repayment schedule, gold card, sales, vault bookings, identity status, documents and activity.

## Install

**Claude Code**

```
/plugin marketplace add DHAHABY-COM/aurelia-skills
/plugin install aurelia@dhahaby
```

**Any MCP client (remote, OAuth 2.1)**

```json
{ "mcpServers": { "aurelia": { "type": "http", "url": "https://mcp.dhahaby.com/mcp" } } }
```

Public tools without sign-in are at `https://mcp.dhahaby.com/public`.

**stdio clients**: `npx -y @dhahaby-com/aurelia-mcp`, after signing in once with `npx @dhahaby-com/aurelia-cli login`.

**Terminal**

```
npx @dhahaby-com/aurelia-cli price
npx @dhahaby-com/aurelia-cli estimate --karat 21 --grams 40
npx @dhahaby-com/aurelia-cli login
npx @dhahaby-com/aurelia-cli appointments    # also: card, loan, vault, sale DHY-S-…, identity, activity, documents
```

## Skills

| Skill | Use it for | Sign-in |
| --- | --- | --- |
| `aurelia-connect` | Connecting, signing in and out, troubleshooting | |
| `aurelia-gold-price` | Gold price per gram; value of a piece of known karat and weight | no |
| `aurelia-borrow` | What you could borrow; loan vs card | no (per-piece limits with sign-in) |
| `aurelia-jewellers` | Partner jewellers; your appraisal bookings | bookings only |
| `aurelia-my-gold` | Your pieces, their status and next step | yes |
| `aurelia-status` | Where everything stands: applications, facilities, next steps | yes |
| `aurelia-appointments` | Your appraisal appointments, pieces and results | yes |
| `aurelia-loan` | Loan eligibility, exact quote, application, schedule and next payment | yes |
| `aurelia-card` | Card eligibility, application, limit, available amount, pledged pieces | yes |
| `aurelia-sell` | What you could sell, a sale offer, the receipt | yes |
| `aurelia-vault` | Vault fee quote, your bookings and drop-off deadlines | yes |
| `aurelia-account` | Identity verification, documents, activity, notifications | yes |

## Safety

- **Read-only.** Through MCP, Aurelia cannot apply, sign, pay, book or move gold. Those steps happen only in the Dhahaby app, and the agent hands over a link.
- **Your own sign-in.** You sign in on Dhahaby's page with phone, email or Google. Agents never see your password or codes. Access tokens last 15 minutes, are bound to the MCP server and can be revoked at any time.
- **Indicative figures.** Values are indicative. Final amounts are set by a licensed lender after a certified appraisal. Aurelia does not give financial advice.

Docs: https://docs.dhahaby.com · Licence: MIT
