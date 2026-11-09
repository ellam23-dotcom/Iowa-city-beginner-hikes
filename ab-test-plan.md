A/B Test Plan
MKTG:4400 Digital Marketing, Fall 2026. Ella Michalec. Written 9 November 2026, before any data was collected.
1. Page and element
Page: Home page (index.html) of First Steps Trail Guide. Single element changed: the main headline (the H1). Everything else on the page is identical.
A (control, current): "Start Hiking in Iowa City"
B (variant): "Never Hiked Before? Start Here in Iowa City"
2. Hypothesis
Prediction: Variant B will get a CLICK rate at least 10 percentage points higher than Variant A.
Reasoning: The site is for people new to hiking. B names that audience directly, which should answer the visitor's first question ("is this for me?") faster than A. I could be wrong: both headlines may be equally clear to the model, so both could score near 100% and show no difference (a ceiling effect).
3. Model, persona, prompt, and assignment
Model: Claude Sonnet 5.5 (claude-sonnet-5-5), default temperature. Each trial is a fresh call with no memory of other trials.
Persona (system prompt): "You are Maya, a 20-year-old University of Iowa student. You have never been hiking and own no hiking gear. You are looking for something outdoors to do this weekend and are browsing quickly."
Prompt (user message): "You just landed on this web page. Page text:\n\n[HEADLINE]\n[the rest of the home page text, identical in both variants]\n\nAnswer with exactly one word. CLICK if you would click through to a trail guide from this page. LEAVE if you would close the page."
Assignment: Trials run in blocks of two, with one A and one B per block, in random order. The order comes from a random number generator with the fixed seed 20261109, so assignment is set before any result is seen.
4. Primary outcome
CLICK rate: the share of trials in each variant where the model's answer is exactly CLICK. Any answer that is not exactly CLICK or LEAVE is discarded and re-run once with the same variant.
5. Sample size and timing
100 trials per variant (200 total). I will not stop early or look at results before all 200 are done. I expect to finish by Wednesday 11 November 2026.
6. Comparison and decision rule
Comparison: B's CLICK rate minus A's CLICK rate, tested with a two-proportion z-test (two-sided, alpha = 0.05), and reported with a 95% confidence interval.
Supports the hypothesis: B is higher than A by at least 10 percentage points and p < 0.05.
Does not support it: a smaller difference, no difference, or A higher than B. I will report any such result as it comes out.
