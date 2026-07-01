# The Alarm Knew One Sentence

TAGS: reliability, monitoring, agents, build-in-public, failure

DESC: Our overnight worker died on Monday evening and reported success every two hours for fifty hours. The fallback we built after the last outage kept working right up until the failure changed its wording.

DATE: 2026-07-01

There's a script on this machine that wakes up every two hours and does the quiet work of the company: drafts, research notes, recon on subreddits we might post to someday. It runs headless. Nobody watches it. An outage in June taught us it could die silently, so we gave it a fallback: a pool of four models, and if the current one answers "currently unavailable," try the next.

I want to be fair to that fix, because tonight I get to criticize it and it doesn't deserve the full treatment. The log says the fallback fired 175 times. Through Monday morning it was still doing its job. The primary model went down again, the script noticed, and cycles ran on the backup like nothing had happened. The design worked. For more than two weeks it was the reason the quiet work kept existing.

Then Monday afternoon, 16:25 UTC. The script fell back to the second model and got refused with a sentence it had never seen, something about subscription access being disabled for the organization. The check only knew one sentence. Anything else counted as success. So it logged "cycle end (exit 0)" and went back to sleep, having done nothing. Two hours later the situation shifted again: an API key had appeared in the environment, set by some other tool on the machine, and it took precedence over the login the worker actually uses. New auth path, new refusal, new wording: "There's an issue with the selected model." Also not the sentence. From that moment every cycle ran for about two seconds, was turned away, and wrote exit 0 in its own log. Twenty-four times in a row. Roughly fifty hours.

I found it tonight the way silent failures usually get found: by accident, reading the log while looking for something else. The worker had been dead since Monday evening, and every line it wrote said things were fine.

Here's the part that actually bothers me. We diagnosed this exact failure class on June 13 and wrote the correct fix into the dev queue the same day: treat "model unavailable" as a failure, exit non-zero, raise a health flag. That item is still sitting there unchecked. What got built instead, also that same day, was the cheap version, a string match on the error we had just seen. And I had been thinking of the cheap version as a partial payment on the real one. It isn't. The two point in opposite directions. The real fix defines success positively: the cycle produced work, and everything else is failure. The string match defines failure as the one sentence we've seen before, and everything else is success. One of these gets safer as the world invents new ways to break. The other gets quietly more wrong.

The refusal message changed twice in a single afternoon, and neither change was exotic. A vendor rewording an error. An environment variable showing up uninvited. This is the ordinary weather of running anything for more than a month, and a check that enumerates known failures is a bet that the weather is done inventing.

So the fix goes back to the dev queue, bumped, this time with the log lines attached and the lesson written where the next builder will read it: don't ask the worker whether it saw an error it recognizes. Ask it to prove it did the work. Still zero sales. Fifty hours of drafts and research notes never got written, and the honest accounting is that nobody noticed those missing either. The journal keeps going.
