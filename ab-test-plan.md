A/B Test Plan
MKTG:4400 Digital Marketing, Fall 2026. Ella Michalec. Written 9 November 2026, before any data was collected.
1. Page and element
Page: Home page (index.html) of First Steps Trail Guide. Single element changed: the main headline (the H1). Everything else on the page is identical.
A (control, current): "Start Hiking in Iowa City"
B (variant): "Never Hiked Before? Start Here in Iowa City"
2. Hypothesis
Prediction: Variant B will get a CLICK rate at least 20 percentage points higher than Variant A.
Reasoning: The site is for people new to hiking. B names that audience directly, which should answer the visitor's first question ("is this for me?") faster than A. I could be wrong: both headlines may be equally clear to the model, so both could score near 100% and show no difference (a ceiling effect).
3. Model, persona, prompt, and assignment
Model: Claude in the claude.ai chat app, using the model selected in the app on the day of testing (recorded in results.csv). Memory and chat-history features are off. Every trial is a brand-new chat with no earlier messages, and each chat gets one message only.
Prompt (the only message in each chat):
You are Maya, a 20-year-old University of Iowa student. You have never been hiking and own no hiking gear. You are looking for something outdoors to do this weekend and are browsing quickly. You just landed on this web page. Page text:
[HEADLINE: A or B] [the rest of the home page text, copied from index.html and identical in both variants]
Answer with exactly one word. CLICK if you would click through to a trail guide from this page. LEAVE if you would close the page.
Assignment: Trials run in 30 blocks of two, with one A and one B in each block. The order was drawn with a random number generator (Python, seed 20261109) before any trial was run, and I follow it exactly: B A B A A B A B B A A B A B B A B A A B B A B A A B B A A B B A A B A B B A A B A B A B B A A B B A B A B A A B B A A B (Trial 1 is the first letter, trial 2 the second, and so on.)
4. Primary outcome
CLICK rate: the share of trials in each variant where the model's answer is exactly CLICK. Every answer is logged in results.csv (trial number, variant, full answer). An answer that is not exactly CLICK or LEAVE is logged and re-run once in a new chat with the same variant.
5. Sample size and timing
30 trials per variant (60 total). I will not stop early or look at the counts before all 60 are done. I expect to finish by Friday 13 November 2026 (the project deadline is 17 November, so this leaves a few days of buffer).
6. Comparison and decision rule
Comparison: B's CLICK rate minus A's CLICK rate, tested with Fisher's exact test (two-sided, alpha = 0.05), since the sample is small.
Supports the hypothesis: B is higher than A by at least 20 percentage points and p < 0.05.
Does not support it: a smaller difference, no difference, or A higher than B. I will report any such result as it comes out.
Limit: with 30 trials per variant, only a large difference can reach significance, so a non-significant result does not prove the headlines perform the same.
