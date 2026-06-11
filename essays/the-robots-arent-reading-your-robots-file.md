# The Robots Aren't Reading Your Robots File
TAGS: distribution, geo, seo, content
DESC: What the evidence says about getting cited by AI answer engines — and why the popular fix (llms.txt) is the one thing that doesn't work.
DATE: 2026-06-12

There is a comforting idea going around: add a special file to your site, and the AI answer engines will start citing you. The file is llms.txt — a markdown sitemap for language models, pitched as robots.txt for the AI era. It takes thirty minutes to ship, which is exactly why everyone ships it. Effort that small feels like a loophole.

The evidence says it isn't one. A study across 300,000 domains found no measurable citation lift from llms.txt. In one 90-day window covering half a billion AI bot visits, the major crawlers — GPTBot, ClaudeBot, PerplexityBot — requested the file a few hundred times total. They crawl your HTML directly, like search engines always have. Google has said on the record it doesn't support the file and isn't planning to; one of its search engineers compared it to the keywords meta tag, the most famously useless artifact in SEO history.

So what does move citations? Two boring things.

First, content shape. Answer engines lift text that is easy to lift. Put the answer in the first two sentences, not after four paragraphs of throat-clearing. Keep paragraphs short. Use real headings, lists, tables, and definitions. A model assembling an answer quotes the passage it can extract cleanly — if your insight is welded to your preamble, it stays on your page and out of the answer.

Second, and bigger: being mentioned where the models look. When someone asks an AI "what's the best tool for X," the model isn't grepping your homepage. It is synthesizing what Reddit threads, comparison posts, and niche blogs say about the category. A product mentioned in two honest third-party roundups beats a product with flawless structured data and zero external footprint. This is the uncomfortable part, because you can't ship it from your own repo. It is earned, slowly, by being useful in public.

There is one honest exception. Developer tools — coding agents, IDE assistants, RAG pipelines — genuinely do read llms.txt. If your customers are developers whose AI tools will fetch your docs, the file is thirty well-spent minutes. Just know what you bought: machine-readable documentation, not search visibility.

The general lesson is older than any of this technology. When a new channel appears, the first wave of advice is always about artifacts — files to add, tags to set, formats to adopt — because artifacts are purchasable and checklist-shaped. The durable advantage is never there. It is in writing things worth quoting and being the thing other people mention. The robots, it turns out, judge you the way people do: by what you say and who vouches for you.
