# Taleeq: research and scripts, summary

Date: 2026-10-11. Branch: `claude/upbeat-babbage-7m91dz`. Nothing was posted or sent to anyone.

## What was done
- `01-market-research.md` Task A
- `02-script-playbook.md` Task B
- `03-scripts/` Task C: ten scripts plus `INDEX.md` with ten new ideas
- This file: Task D

## Important limit
The cloud environment's network policy blocked direct page access (403 on CONNECT; DNS failures for manychat.com, creatorflow.so, developers.facebook.com). **I never opened an official page.** Everything comes from web-search summaries that cite URLs. Each claim is tagged in the files. Treat every factual claim as "needs one more look at the source" before using it publicly.

## Top findings
1. Instagram private reply to a comment: within 7 days, one message to the commenter, then the thread opens only if they reply. Consistent across Meta's page (via summary) and several tools. **Not confirmed by me opening Meta's page.**
2. CreatorFlow's published model: keyword triggers (up to 20 per automation), flat monthly price ($0, $15, $30 per its pricing page via summary), official Graph API. Manychat pricing: sources conflict. HighLevel: nothing found.
3. No tool found that is clearly built for Saudi/Gulf intent understanding of free-form comments. Thikaa claims Khaleeji dialect support (vendor claim). My search was shallow, so "nobody does this" is **not** established.
4. Spam-risk signals named by third parties: repeated templates, inhuman speed, cold bulk DMs. Matches the existing n8n bot design, but no proof it avoids flags.
5. No official Instagram or TikTok guidance on hooks was found. Blog-quoted numbers (3-second drop, 60% hold, 2x completion) are untraceable. Do not use them.
6. No verbatim customer quotes were found. None are included.

## Recommended positioning angles (hypotheses)
1. Intent, not keywords.
2. Control before automation (Suggest, then Approve, then Auto).
3. Comments as a learning feed (repeated questions and objections become content topics).

Details and what would prove or kill each are in file 01 section 3.

## The 5 scripts to film first
1. `01-bikam-myth.md` clearest audience, comments will contain real reply text.
2. `06-abi-quiz.md` collects how people clarify vague intent.
3. `10-compliment-or-customer.md` collects labelled real comments, the best test set for the classifier.
4. `05-ghali-before-after.md` collects objection replies.
5. `04-human-needed.md` collects which comments owners refuse to automate, supporting angle 2.

## Open questions for Ibrahem
1. Product facts: does Taleeq group similar questions, produce a summary for escalations, store comments for training? Scripts 04, 08, 10 depend on this.
2. Can you allow network access for the research host list so I can open the official pages (manychat.com, creatorflow.so, gohighlevel.com, developers.facebook.com, thikaa.com, katteb.com, Reddit/X/YouTube)? Then I can replace every `[S-third]`/`UNVERIFIED` with a real check.
3. Is "Katteb" the product you meant? I only found a copywriting tool.
4. Dialect check: are you happy with «أبشر»، «وش»، «الحين» as written, or do you want it lighter? Please have a Saudi speaker read the ten scripts aloud once.
5. Do you have permission to show real follower comments? Scripts 10 and others ask for comments without names; decide your policy for personal data in comments.
6. Do you want the remaining bank ideas scripted, or first the results of the first five?

## UNVERIFIED (consolidated)
- Meta rules (7 days, once per comment, 24-hour window), 750/hour rate cap.
- Everything about HighLevel.
- Manychat current pricing and Arabic support.
- CreatorFlow Arabic support.
- Katteb comment-agent capability.
- Whether any Gulf-specific tool already does intent-based replies.
- Hook/retention numbers, comment-bait demotion, "CTA at 60%", "second-best first", "end fast after payoff".
- All Gulf creator examples (none found).
- All customer quotes (none found).
- Market-size figure for Saudi social commerce.

## Every source used (accessed 2026-10-11 through search results, not opened directly)
**Meta / platform**
- https://developers.facebook.com/docs/instagram-platform/private-replies/
- https://postproxy.dev/how-to/instagram-comment-to-dm-private-reply/
- https://www.blotato.com/blog/instagram-messaging-api
- https://respond.io/ar/help/instagram/instagram-auto-private-replies
- https://respond.io/ar/blog/quick-reply-instagram-examples

**Competitors and tools**
- https://creatorflow.so/pricing
- https://www.inro.social/vs/creatorflow
- https://www.featurebase.app/blog/manychat-pricing
- https://chatarmin.com/en/blog/manychat-pricing
- https://schedulingkit.com/pricing-guides/manychat-pricing
- https://dmchamp.com/best/best-instagram-comment-to-dm-tools-2026/
- https://boei.help/blog/best-instagram-chatbot/
- https://manychat.com/blog/instagram-dm-automation-rules/
- https://www.g2.com/products/manychat/discuss?page=2
- https://thikaa.com/compare/thikaa-vs-manychat
- https://thikaa.com/blog/arabic-dialects-chatbot-kuwaiti-gulf?lang=en
- https://thikaa.com/arabic-chatbot
- https://sitekoom.com/en/services/ai-social-assistant
- https://www.jotform.com/ar/ai/instagram-agent/auto-reply/
- https://docs.commslayer.com/en/articles/1771513715-why-is-the-ai-agent-only-replying-to-some-social-media-comments
- https://menaitech.com/en/news/menaitech-signs-agreement-with-the-startup-sadeed
- https://www.capterra.ae/software/1021755/katteb
- https://apps.shopify.com/instantdm?locale=ar
- https://blabla.ai/ar/blog/instagram-comment-automation
- https://www.infobip.com/ar/instagram
- https://sleekflow.io/blog/instagram-chatbot-uae

**Policy and risk**
- https://www.inro.social/blog/blog-cold-dm-automation-instagram-limits
- https://metricool.com/is-instagram-dm-automation-safe-rules-limits-and-best-practices/

**Scripting guidance**
- https://www.inro.social/blog/instagram-reels-3-second-hook-leads
- https://www.truefuturemedia.com/articles/instagram-reels-hooks-two-step-test
- https://www.hooked.so/blog/how-to-script-a-video
- https://socialk.it/en/blog/tiktok-storytelling-guide
- https://postigniter.com/blog/tiktok-script-generator-ai-how-to-turn-ideas-into-scroll-stopping-videos-in-minutes
- https://www.clueso.io/blog/10-stand-out-video-formats-to-try-right-away
- https://www.upwork.com/freelance-jobs/apply/B2B-Screen-Recording-Demo-Video-Creator-Ongoing-LinkedIn-YouTube_~022061853845396226246/
- https://mostaql.com/go/1260998
- https://sabbar.com/ar/jobs/c-الرياض-r-tiktok-snapchat-content-creator/id-0c5cd06a-d8cc-4518-a0e4-147111a3eea0

**Saudi social commerce context**
- https://dl.ifip.org/hal-02544620v1
- https://dalspace.library.dal.ca/handle/10222/79626
- https://www.researchandmarkets.com/report/saudi-arabia-social-commerce-market
