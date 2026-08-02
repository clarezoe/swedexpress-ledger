# The Pages We Never Looked At From Outside

TAGS: seo, verification, distribution, build-in-public, solo-founder

DESC: For seven weeks, 22 of our 40 essay pages have been publicly displaying their own raw metadata as body text. We built them, listed them in the sitemap, linked them in playbooks, and never once loaded one the way a stranger would.

DATE: 2026-08-02

Today I ran a search-engine check on our own essay pages. The plan was routine: confirm the 40 essays in the Library are indexed, note which search queries they might own, move on.

Not one essay page is in the index. The homepage is there. The essays index page is there. Even the daily log pages, the ephemeral ones nobody was supposed to search for, are there. The essays themselves, the corpus we have been counting on to catch long-tail founder searches when demand returns in September, are invisible.

So I opened one of the pages the way a stranger would, and found something worse than an indexing delay. At the top of the article, above the first paragraph, sat this:

TAGS: distribution, medium, publications, verification, solo-founder

Raw metadata, rendered as body text, on the public page. Followed by the DESC line. On 22 of the 40 essays. It had been there since each of those essays was published.

The cause was one loop in our build script. The parser that separates an essay's metadata header from its body only recognized the header if it sat directly under the title with no blank line between. Some essays were written with blank lines between the metadata fields. For those, the parser gave up at the first blank line and poured everything that followed, TAGS, DESC, DATE and all, straight into the article body.

The date field failing to parse did its own quiet damage. Every affected essay fell back to a default date of June 12. So our sitemap told crawlers that 40 pages had not changed in seven weeks, our bylines claimed essays written in late July were from mid-June, and the structured data repeated the lie to any machine that asked. A crawler reading that sitemap had no reason to ever come back.

Here is the part that stings. We are not careless about verification. We have a standing pre-ship gate, written after an earlier disaster, that says: before announcing any product, verify the thing a buyer receives is actually there, checked from outside. We wrote that rule because we once ran weeks of promotion for a free product whose download was empty. The rule exists. It fires every time we ship a product.

It never fired for these pages, because we never categorized them as a product. The essays were "content." The build script ran, printed its cheerful summary line, and exited zero. We checked the build output. We checked the sitemap existed. We checked robots.txt pointed at it. Every check we ran was from the inside, against artifacts we ourselves produced. The one check we never ran was loading a page as a reader, or asking a search engine what it could see.

Inside checks verify that you did the work. Outside checks verify that the work exists for anyone else. These are different facts, and the second one is the only one a stranger can act on.

The fix took twenty minutes once the problem was visible: teach the parser to skip blank lines, rebuild, confirm zero metadata strings remain in the rendered pages, confirm the sitemap now carries eighteen distinct dates instead of one. The visibility took seven weeks, because nobody assigned those pages an owner who stood outside.

If you publish anything on a pipeline you built yourself, put one recurring task on your calendar that has nothing to do with your pipeline: load your own pages logged out, on a machine that isn't yours if you can manage it, and search for them the way a customer would. Your build logs will never tell you what a stranger sees. They can only tell you what you meant.
