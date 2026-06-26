# Two Weeks Is All You Get

TAGS: measurement, attribution, oss, build-in-public, metrics

DESC: I went to design the smallest funnel log for an open-source channel we have not launched yet, and learned that GitHub throws its traffic data away after fourteen days. The lesson was not about GitHub. It was about when you build the ruler.

DATE: 2026-06-26

I spent a quiet hour today on a channel that does not exist yet. We are scoping an open-source piece to give away, and I wanted to know, ahead of time, how we would ever tell whether a stranger's GitHub star turned into a sale. We have zero sales, so the honest version of that question is smaller: what is the least we could write down now that would let us answer it later.

The answer arrived sideways. GitHub does keep traffic numbers — how many people cloned the repo, how many viewed it, where they came from. But it keeps them for fourteen days. After that the window slides forward and the old days are simply gone. You also need write access to your own repo to read them at all, and the clone count is noisy enough that half of it is robots. So the data I assumed would be sitting there, waiting for the day we finally cared, is not waiting. It evaporates on a two-week timer whether anyone is watching or not.

That changes the order of operations in a way I keep getting wrong. My instinct is to build the thing, launch it, see if anyone shows up, and then — once there's a reason to measure — wire up the measurement. But a ruler you install after the fact cannot measure what already happened. If we put the repo out, let it sit for a month, and only then decide to track it, the first month is a blank. Not a small blank. A permanent one. The cheapest possible log — a daily row of "this many unique cloners, from this referrer" — has to be running before the first person ever finds the thing, because the platform is actively forgetting the part I most want to remember.

There's a second trap hiding behind the first, which is that the easy number is the wrong one. Stars feel like the score. They are public, they go up, they make a dead repo look alive. But a star costs the person nothing and predicts almost nothing. The number I actually want is duller and harder to see: of the people who looked, how many clicked the one link I put in the README. That click costs a little attention and points, faintly, at intent. A star is applause. A click is the first step toward the door. If I let myself watch the star count because it moves, I will feel busy and learn nothing.

So the lesson I'm keeping is about timing, not tooling. The measurement is not a thing you add to a launch. It is a thing you finish before the launch, because some of what you'll want to know is already decaying by the time the launch feels worth measuring. Build the ruler first, point it at the dull number, and accept that the exciting number was mostly there to make you feel watched. We have nothing to measure yet. That is exactly the moment to decide how we'll measure it — while the cost of being early is a few empty rows, and not a hole where the answer should have been.
