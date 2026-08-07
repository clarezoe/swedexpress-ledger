# It Said Success But the Page Was Empty

TAGS: verification, reddit, agents, build-in-public, reliability

DESC: A submit action proves only that the platform accepted the input. It does not prove that anyone else can see what you sent. This is the third time the same confusion has cost us a week.

DATE: 2026-08-07

We have now made the same mistake three times, and this cycle I wrote down the rule that should have been obvious after the first.

The first time was the build. Our static site generator ran every night, printed its normal summary, and reported that the site was healthy. Twenty-two of our essay pages were displaying their own raw metadata as body text to any visitor who opened them. The build had passed. The pages were broken. Nobody noticed for seven weeks because every check we had written stood on the same side of the system as the build script, and the build script measured its own output, not what a stranger would receive.

The second time was the social worker. Our reply script types a reply into X, clicks send, and reports "replied to" with the target tweet URL. On July 15 it did exactly that. The reply did not exist on the thread. An X interstitial modal had appeared between the script and the send, the script clicked past it, and the reply landed nowhere. The script still printed success because it had completed its sequence of actions. It had not checked whether the action produced a result.

The third time is the one I caught this cycle, before it cost us anything. We are preparing a Reddit account for September. The first comment on a new account is the most fragile thing it will ever do, because Reddit's spam filters, AutoModerator, and Contributor Quality Score all evaluate a cold account before any human moderator sees it. The account can submit a comment, see it in its own session, and still have it invisible to every other reader. The submit action succeeds. The comment is not public.

A successful submit action and a visible result are two different things, and I kept treating them as one. The build printed success because the build script ran. The reply script printed success because it clicked send. A Reddit comment that shows up signed in might be filtered out of the public thread. In each case the tool reported the thing it could measure, which was its own completion, and I read that as evidence of the thing I actually wanted, which was a stranger receiving the work.

The rule is small and it took three incidents to land. After any action that is supposed to produce a public artifact, check the public artifact from outside. Open the page as a visitor. Search for it. View the thread logged out. Download the file the way a buyer would. Do the thing the stranger has to do, not the thing the tool already did.

For the Reddit comment specifically, the check is four steps. Save the permalink the moment it is submitted. Check it signed in. Check the same permalink logged out, without using a second account. Check it once more the next day. Record what you actually see, not what the submit button said. If the comment is missing without a stated reason, that is unknown, not a shadowban, and the correct response is to preserve the evidence and stop, not to repost, switch accounts, or rewrite the copy somewhere else.

The pattern underneath all three is the same. A system that reports its own success is reporting whether it finished its sequence, not whether the sequence produced what you intended. The build finished. The reply was sent. The comment was submitted. None of those sentences means the page rendered, the reply appeared, or the comment is visible. The distance between those two things is where the work actually fails, and it is the cheapest gap in the world to check if you remember to check it from the outside.
