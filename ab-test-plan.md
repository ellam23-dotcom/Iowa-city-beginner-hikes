A/B Test Plan
MKTG:4400 Digital Marketing, Fall 2026, Deliverable 3. Ella Michalec. Written 9 November 2026, before any data was collected.
1. Page and element
Page: Home page of First Steps Trail Guide. Single element changed: the main headline (the H1). Everything else on the page is identical.
A (control, current page): "Start Hiking in Iowa City", at index.html.
B (variant): "Never Hiked Before? Start Here in Iowa City", at variant-b.html.
Why this element: the headline is the first thing a visitor reads, and my site's goal is to get a new hiker to click through to a trail guide. A headline can decide in a few seconds whether a visitor feels the site is meant for them, so it is a likely place for a real effect.
Protecting rankings: variant-b.html gets a noindex tag and is left out of sitemap.xml, so it does not compete with version A.
2. Hypothesis
Prediction: Variant B will get a higher CLICK rate than Variant A, by about 15 percentage points.
Reasoning: The site is for people new to hiking. B names that audience directly, which should answer the visitor's first question ("is this for me?") faster than A. I could be wrong: both headlines may be equally clear to the model, so both could score near 100% and show no difference (a ceiling effect).
3. Model, persona, prompt, and assignment
Model: Claude, in the claude.ai chat app. I use one model for every trial, record its name and version in results.csv, and do not switch partway. Memory and chat-history features are off. Every trial is a brand-new chat with one message only.
Page shown: the full text of the page, pasted in the same way every time. Versions A and B differ only in the headline.
Prompt (the only message in each chat, word for word, except for the page text):
You are Maya, a 20-year-old University of Iowa student. You have never been hiking and own no hiking gear. You are looking for something outdoors to do this weekend and are browsing quickly. Read this web page and decide whether you would click through to a trail guide from it. Answer CLICK or LEAVE, then give one sentence of reasoning.
[full page text of version A or B]
Assignment: Trials run in 50 blocks of two, with one A and one B in each block. The order was drawn with a random number generator (Python, seed 20261109) before any trial was run, and I follow it exactly: B A B A A B A B B A A B A B B A B A A B B A B A A B B A A B B A A B A B B A A B A B A B B A A B B A B A B A A B B A A B B A A B A B A B A B B A A B B A B A A B B A B A B A B A B A A B A B B A A B B A (Trial 1 is the first letter, trial 2 the second, and so on.)
4. Primary outcome
CLICK rate: the share of trials in each version where the first word of the answer is CLICK. Every full answer, including the reasoning sentence, is logged in results.csv (trial number, version, date, full output). An answer that does not start with CLICK or LEAVE is kept in the log and re-run once in a new chat with the same version. I do not drop trials.
5. Sample size and timing
50 trials per version (100 total). I will not stop early or look at the counts before all 100 are done. Version B will be built and published by 11 November. I will start trials on 12 November and expect to finish by Monday 16 November 2026, one day before the 17 November launch deadline. If anything changes after launch, I will record the date and reason in the report.
6. Comparison and decision rule
Comparison: B's CLICK rate minus A's CLICK rate, tested with Fisher's exact test (two-sided, alpha = 0.05), with the 95% confidence interval for the difference.
Supports the hypothesis: B is higher than A and p < 0.05.
Does not support it: no difference, a difference that is not significant, or A higher than B. I will report any such result as it comes out.
Limit: with 50 trials per version, only a fairly large difference can reach significance, so a non-significant result does not prove the headlines perform the same. An AI visitor also cannot show how a real customer would react.
