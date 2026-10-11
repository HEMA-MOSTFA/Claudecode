# 01. Market and competitor research (Taleeq)

Access date for every source below: **2026-10-11**.

## 0. Limits of this research (read first)

- The cloud environment blocks direct page fetches (`CONNECT tunnel failed, response 403`; `getaddrinfo ENOTFOUND` for manychat.com, creatorflow.so, developers.facebook.com). I could **not open any official page myself**.
- Everything below comes from **web search result summaries** that cite the listed URLs. Each claim is tagged:
  - `[S-official]` the search summary attributes it to an official vendor or Meta page (page itself not opened by me).
  - `[S-third]` it comes from a third-party blog or comparison site. Many of these are written by competitors, so treat them as weak.
  - `UNVERIFIED` I could not find a source, or sources conflict.
- Before using any of this publicly, re-open the cited URL and confirm. This is a to-do, not a formality.
- No customer quotes are included. I found **no verifiable verbatim quotes** from Arab creators or shop owners, and I did not invent any (see section 4).

## 1. Platform facts Taleeq relies on

| Fact | Status | Source |
|---|---|---|
| A private reply to a comment must be sent within 7 days of the comment's creation | `[S-official]` | https://developers.facebook.com/docs/instagram-platform/private-replies/ |
| Only one private reply per comment | `[S-official]` for "one message to the commenter"; wording "once per comment, ever" comes from `[S-third]` guides | https://developers.facebook.com/docs/instagram-platform/private-replies/ ; https://postproxy.dev/how-to/instagram-comment-to-dm-private-reply/ |
| After the commenter writes back, a new 24-hour messaging window opens | `[S-third]` | https://postproxy.dev/how-to/instagram-comment-to-dm-private-reply/ |
| Instagram Live comments: private reply not possible after the broadcast ends | `[S-official]` | https://developers.facebook.com/docs/instagram-platform/private-replies/ |
| IGTV comments not supported for auto private replies | `[S-third]` (respond.io help) | https://respond.io/ar/help/instagram/instagram-auto-private-replies |
| A rate limit of 750 private replies per hour | `UNVERIFIED` (appears in one vendor blog, not in Meta docs) | https://www.blotato.com/blog/instagram-messaging-api |
| Tools using the official API are generally treated as permitted; tools that scrape, drive the UI, or take passwords are not authorized | `[S-third]` | https://www.inro.social/blog/blog-cold-dm-automation-instagram-limits ; https://metricool.com/is-instagram-dm-automation-safe-rules-limits-and-best-practices/ |
| No official numeric Meta cap on comment-triggered DM volume was found | `UNVERIFIED` | same sources |

Net result: the brief's assumption (once per comment, within 7 days, 24-hour window after the reply) is **consistent with what I found, but not confirmed by opening Meta's page**. Re-verify before any public claim.

Spam-risk signals named by third parties (not Meta): repetitive copy-paste templates, sending faster than a human could, cold high-volume first messages, and recipient spam reports. `[S-third]` https://www.inro.social/blog/blog-cold-dm-automation-instagram-limits . This lines up with the existing n8n bot design (variants, 1 to 4 minute delay, hourly cap), but that is design reasoning, not proof it avoids flags.

## 2. Competitor set

### 2.1 Direct: Instagram comment-to-DM tools

**CreatorFlow** (creatorflow.so)
- Positioning: flat-rate comment-to-DM and story-reply automation for creators. `[S-official]`
- Pricing (per search summary of the official page): Free $0 with 1 Instagram account and 500 automated DMs/month; Pro $15/month ($12 annual); Growth $30/month ($24 annual) with 5 accounts, 10,000 DMs/month, 5 seats. Not per contact. `[S-official]` https://creatorflow.so/pricing
- Mechanism: keyword triggers, up to 20 trigger keywords per automation; uses Meta's official Graph API. `[S-official]` https://creatorflow.so/pricing
- Arabic/Gulf support: `UNVERIFIED`.
- Weaknesses: third-party comparisons (Inro, replient.ai) have a stake; do not rely on their critiques. https://www.inro.social/vs/creatorflow
- Policy risk language: states official API use. `[S-official]`

**Manychat**
- Positioning: global Instagram/Messenger chatbot platform. `[S-third]` https://thikaa.com/compare/thikaa-vs-manychat (written by a competitor)
- Pricing: sources conflict. Pro roughly $15/month starting, or $29 with 2,500 contacts; a March 2, 2026 restructure into five contact-based tiers with the free plan cut from 1,000 to 25 contacts; AI add-on about $29/month. All `[S-third]` and conflicting. `UNVERIFIED`. https://www.featurebase.app/blog/manychat-pricing ; https://chatarmin.com/en/blog/manychat-pricing ; https://schedulingkit.com/pricing-guides/manychat-pricing ; https://dmchamp.com/best/best-instagram-comment-to-dm-tools-2026/
- Arabic support: no official confirmation found. Freelancers build Arabic flows by hand. `UNVERIFIED` https://www.g2.com/products/manychat/discuss?page=2
- Policy language: Manychat publishes an Instagram DM rules post. Not opened. https://manychat.com/blog/instagram-dm-automation-rules/

**HighLevel (GoHighLevel)**
- Search returned nothing specific on its Instagram comment-to-DM or pricing. Everything about it is `UNVERIFIED`. Official page needs to be opened.

**Other comment-to-DM tools seen in comparisons** (keyword-style, mostly English-first): InstantDM (Shopify listing, https://apps.shopify.com/instantdm?locale=ar), CommentKeyword (pricing by DMs sent, from $12/month, `[S-third]`), Flowgent, Boei, DM Champ. https://dmchamp.com/best/best-instagram-comment-to-dm-tools-2026/ ; https://boei.help/blog/best-instagram-chatbot/

### 2.2 Arabic-first or Arabic-capable

| Tool | What was found | Status | Source |
|---|---|---|---|
| Thikaa | Arabic chatbot platform; claims Khaleeji dialect and Arabizi handling; claims general LLMs default to Fusha unless the dialect is explicit; Instagram comment coverage not clear | `[S-third]` vendor claim, `UNVERIFIED` | https://thikaa.com/blog/arabic-dialects-chatbot-kuwaiti-gulf?lang=en ; https://thikaa.com/arabic-chatbot |
| Sitekoom AI Social Media Assistant | Replies in Arabic and English, qualifies leads | vendor page, details `UNVERIFIED` | https://sitekoom.com/en/services/ai-social-assistant |
| respond.io | Arabic help center; documents auto private replies (one per comment, within 7 days) | `[S-third]` | https://respond.io/ar/help/instagram/instagram-auto-private-replies |
| Jotform AI agent | Arabic page on auto replies to Instagram DMs and comments | vendor page, details `UNVERIFIED` | https://www.jotform.com/ar/ai/instagram-agent/auto-reply/ |
| Commslayer | Caps AI comment replies at about 40% of new comments to avoid spam flags | `[S-official]` help center | https://docs.commslayer.com/en/articles/1771513715-why-is-the-ai-agent-only-replying-to-some-social-media-comments |
| Sadeed (via MenaITech) | Jordanian Arabic AI startup, used for Facebook and Twitter replies | `[S-third]` | https://menaitech.com/en/news/menaitech-signs-agreement-with-the-startup-sadeed |
| Blabla.ai (Arabic blog) | Explains keyword-to-DM flow and "reply publicly that DM was sent" pattern | content marketing | https://blabla.ai/ar/blog/instagram-comment-automation |

No tool found that is clearly built for **Saudi/Gulf comment-to-DM intent understanding**. That absence is not proof; my search was shallow.

### 2.3 Substitutes

- Manual replying with Instagram's own saved replies (Business accounts, Settings > Business > Saved replies). `[S-third]` https://respond.io/ar/blog/quick-reply-instagram-examples
- Agencies and freelancers building flows by hand. Seen as services on mostaql/khamsat; no pricing used here.
- CRM/inbox tools (respond.io, Infobip): https://www.infobip.com/ar/instagram

### 2.4 Adjacent: Katteb

- Search found Katteb as an AI copywriting tool, listed on Capterra with Arabic and English. **No evidence of a comment-reply or business-agent product.** `[S-third]` https://www.capterra.ae/software/1021755/katteb . The brief calls it a "general AI business agent"; I could not confirm that. `UNVERIFIED`.

### 2.5 Comparison table

| | Keyword triggers | Understands free-form intent | Arabic/Gulf dialect | Approval modes | Escalates complaints to owner | Verified? |
|---|---|---|---|---|---|---|
| CreatorFlow | Yes (up to 20) | Not stated | UNVERIFIED | UNVERIFIED | UNVERIFIED | partial, search summary only |
| Manychat | Yes | AI add-on exists | UNVERIFIED | UNVERIFIED | UNVERIFIED | weak |
| HighLevel | UNVERIFIED | UNVERIFIED | UNVERIFIED | UNVERIFIED | UNVERIFIED | none |
| Thikaa | n/a | Claims | Claims Khaleeji | UNVERIFIED | UNVERIFIED | vendor claim |
| Taleeq (planned) | no | planned | planned | Suggest/Approve/Auto planned | planned | not launched |

Every "UNVERIFIED" cell needs a visit to the vendor's official docs.

## 3. Three positioning angles (all **hypotheses**)

1. **Intent, not keywords.** The tools I found are described around keyword triggers. Taleeq reads natural comments ("بكم", "أبي", "ارسل التفاصيل") and classifies intent. *Why defensible:* shop owners in the Gulf do not ask people to type a magic word. *Hypothesis:* Taleeq's classifier is accurate enough on Gulf dialect. **Untested; no accuracy number exists.** Needs a labelled test set of real comments before this is claimed.
2. **Control before automation.** Suggest, then Approve, then Auto only after accuracy is proven. *Why defensible:* spam-flag and "bot reply" fears (section 1) make owners nervous; a staged mode answers that fear honestly. *Hypothesis:* owners value approval control over full automation. Verify through waitlist interviews.
3. **Comments as a customer-learning feed.** Gather interested people in one place and surface repeated questions and objections as content ideas. *Why defensible:* competitors in the results sell triggers and DMs, not learning from comments (not exhaustively checked). *Hypothesis:* creators will use insights. Verify with the first beta users.

Not recommended as an angle: "saves 10 hours a week" or any time/revenue claim. No data.

## 4. Customer language

**Result: no verifiable verbatim quotes found.** Searches in Arabic and English about shop owners failing to keep up with comments returned vendor marketing, not forum or review text. I did not fabricate quotes.

What I did find (context, not customer voice):
- Saudi social commerce runs heavily on Instagram, WhatsApp, Twitter and Snapchat; sellers often work from phone-based chats. https://dl.ifip.org/hal-02544620v1 (study of Saudi citizens' motivations and challenges in social commerce). Abstract does not discuss comment-based price questions.
- Trust is a known barrier when buying from social-media-only stores. https://dalspace.library.dal.ca/handle/10222/79626
- Market-size claim (Saudi social commerce about US$16.17 billion in 2026) is from a paywalled report summary, `UNVERIFIED`: https://www.researchandmarkets.com/report/saudi-arabia-social-commerce-market
- Instagram DMs can only be reached through customer-initiated conversations (so quick reply matters). `[S-third]` https://respond.io/ar/blog/quick-reply-instagram-examples

**Themes to look for (hypotheses taken from the brief's idea bank, not from evidence):** late replies, lost buyers, repetitive questions, bot-sounding replies, comments versus DMs, price questions.

**Next step to get real quotes (needs network access or manual work):** search X, Reddit, YouTube comments and App Store/Play reviews of Manychat and similar tools for Arabic complaints; record URL, date and a 5 to 10 word excerpt. The best source will be Taleeq's own waitlist replies and the comments on Ibrahem's videos.

## 5. UNVERIFIED list for this file

1. Meta private-reply rules (opened page needed).
2. Everything on HighLevel.
3. Manychat current pricing and Arabic support.
4. CreatorFlow Arabic support and how it handles non-keyword comments.
5. Katteb's product scope.
6. Whether any Saudi/Gulf tool already does intent-based comment replies.
7. All customer-language quotes.
