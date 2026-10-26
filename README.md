# TakeMeter

> ### 👋 Start here
>
> **New to this repo? Read [RUNNING.md](RUNNING.md) first** — setup, the
> notebook, the baseline, and what to do when something breaks.
>
> Once `python test.py` passes:
>
> ```bash
> head -5 data/practice_labels.csv     # the shape your labels.csv needs
> ```
>
> Then open `takemeter.ipynb` **in this folder** — in VS Code, or with
> `jupyter notebook` if you prefer. Pick the kernel: the `.venv` inside this
> project. Run section 1, which reports the hardware you'll be training on.
> Everything else waits until you have data.
>
> Nothing to upload, nothing to connect, no accounts and no keys. The notebook
> runs on your machine and writes next to your code.
>
> **The rest of this file is your submission.** Fill it in as you go.

---

<!-- ─────────────────────────────────────────────────────────────────────────
     HOW TO USE THIS FILE

     Unit 5 asks for the first five sections. Unit 6 adds the five below them.

     Everything is pasted as TEXT. No screenshots, no images.

     ⚠️ The confusion matrix especially. The notebook prints one as a markdown
     table, ready to copy. A screenshot of a matrix earns nothing. Paste the
     table.
     ───────────────────────────────────────────────────────────────────────── -->

<!-- ═══════════════════════ UNIT 5 — THE BUILD ═══════════════════════ -->

## What This Does

<!-- Your community, and what your classifier sorts posts into. Three or four
     sentences. -->

The r/cscareerquestions subreddit is an online community for people to ask questions related to their cs career, share their experiences, and post news. This classifier labels posts from the subreddit with the labels: question, story, vent.  

---

## Label Taxonomy

<!-- Each label: a one-sentence definition and two real examples from your
     reading. Then your decision rule for the hardest boundary.

     The decision rule is worth a point on its own and it's the thing most
     people leave out. Every taxonomy has a hardest boundary. Name yours. -->

### Question

**Definition: The author explicitly asks readers for information, advice, or opinions.** 

**Example 1: Stupid part: couple of my engineer teammates do not have as much experience/knowledge as myself or another senior member of the team. Yet, instead of trying to learn they waste both our time with 2hr discussions about database architecture and refuse to stick to factual discussions. Already raised with manager, yet to see any changes. Toxic part: The stupid bros challenge every other engineers ideas, but laugh between themselves when others challenge them (rightfully so as well since their decisions are very questionable) The problem: i want to be able to grow as an engineer and learn new things and ship fast. These two idiots are getting in my way and they’re not easy to work with either. How do i work with them/around them? Confront manager/ignore them/both?**
>

**Example 2: For two years, I've been developing and maintaining an internal tool for the company I work for by myself. This software was created internally mostly because our company's requirements are very complex that there aren't many saas solutions out there that fulfill them. There is also a large amount of tech debt because leadership didn't want to hire more engineers. Fortunately, I've already put in my two weeks after receiving another job offer so I'm done with it. However, my colleague is trying to replace all of our internal and Saas systems with an AI app builder service. Leadership has already given him the green light and he is adding all of our API/EDI integrations. I'm not very familiar with the pros and cons of using a service like this one and I've already warned him about the possible risks of fully depending on this tool without having an experienced engineer. Some of these integrations are also requirements from our biggest customers and our operations team depend on these automations to reduce their heavy workload. I'm curious to know what others who have been in a similar scenario think about this. It won't be my problem in 2 weeks but I do wonder about the outcome of this approach down the road. My colleague is an IT manager and only IT employee in this mid-sized non-tech company but has almost no programming experience**
>

### Vent

**Definition: The author expresses frustration about their own experience without asking readers for anything.**

**Example 1: I’m planning my exit from software now. My company has nobody at the helm anymore. The CEO and execs have fully drank the AI Kool-Aid, and AI is running our company now, not humans. I found some company documents made visible to all users on our shared repositories which I don’t think they intended to be visible to everyone. Those docs illustrated just how much they were using AI day to day: literally everything. The direction of the company, evaluating competitors, accounting, product planning, marketing, projections, reviewing customer feedback, and of course what I already knew about: software development. They are just taking customers’ conversations and data and feeding it directly into AI. They think that because it’s a “business AI” account that the data is still private. They think they are geniuses for building new products in record time by letting Claude and ChatGPT do all the work with swarms of agents, thinking “nobody else is doing this, nobody else is moving at speeds we are, nobody thought of this” Meanwhile literally everyone is doing the same thing, and they are feeding their entire product into AI, so anybody working at Anthropic or OpenAI or Google who is analyzing their output can easily sell that data to a competitor. The execs are building apps and web pages in single prompts in minutes, and thinking that their IQ just increased by 100% and added 2 inches to their dick. Then they turn to the engineers and say “look what I made, impressive huh” I won’t be able to wean them off their addiction. Sometimes you just gotta let them hit rock bottom**
>

**Example 2: Recruiter said I did well and they enjoyed talking to me & encouraged me to apply to other positions but the team felt the role wasnt their best match, went through 9 rounds of this what does this mean Edit: this was my one golden ticket n its gone. Theres no point**
>

### The hardest boundary

**Which two labels: vent vs question**

**The decision rule I used every time: If the author asks the readers for advice, information, or others' experiences, it's a question even with all the complaining. If the questions are only rhetorical ("what's the point of all this?"/"why does my life suck?"/"What now?"), it's vent**

---

## The Dataset

<!-- Where you collected from, how you labelled, your counts, and three hard
     cases. -->

**Where the posts came from:**

**How I labelled them:** <!-- Cold first? Pre-labelled with AI and corrected?
Say so plainly — the disclosure is required, not penalised. -->

**Counts per label:**

| Label | Count | Share |
|---|---|---|
|  |  |  |
|  |  |  |
|  |  |  |
| **Total** |  | 100% |

**Three hard cases**

<!-- Any post that made you pause: what it was, which two labels it could have
     been, and what you chose. These are worth more than the easy 190. -->

**1.**
> *The post: "Is there a future in computer science? I have the typical story of a young graduate who can't find a job. I've sent hundreds of résumés, and very few interviews have come my way. Now, it's been almost a year since I started searching, and I'm wondering if I should switch careers simply because I'm concerned that this won't be a reliable job in the near future. First of all, there are tons of developers on the market today, and most are better than I am, either because they already have work experience or because they're super passionate about coding (which, to be clear, I'm not. I have more of a mild interest in it). But on top of that, there's AI. Two or three years ago, ChatGPT had just been released. At the time, it was just a tool for drafting documents, and mistakes were common. Today, it's capable of producing code in mere minutes that could take a low-level engineer days to write. How can I be sure that, in another two or three years, it won't be just as good as an experienced developer? What about in 10 years? Heck, what if the job disappears completely? Imagine you own a hairdressing salon and want your own website. It's probably possible today to build one yourself with minimal programming knowledge. Well, maybe big systems in 10–15 years will barely need one or two workers to supervise them. Of course, I can imagine that AI won't be good at working with very niche technologies, or that regulations will significantly slow down AI implementation in the workplace (think COBOL and banking systems). But that's probably a minority of developers' jobs, and today, I'm asking myself: should I continue? I don't want to spend another six months searching for a job, only for my career to end in five years. But at the same time, I spent five years studying for this. Of course, maybe we'll get ""lucky"" and the bubble will burst or something, and AI progress will slow down significantly. But do I really want to bet my future on a coin flip? Sorry if this sounds like I'm doomsaying, but I need to get this off my chest somehow while also thinking seriously about my future. So please tell me: does a career as a developer have a future? Are we cooked?"*
>
> *Could have been: vent*
>
> *I chose, because: I chose question because at the end of the post, the author asks for advice from the readers on whether the developer career has a future.*

**2.**
> *The post: "I actually tried to dodge AI for most of my degree, I just make games. I'm not some coding whiz, I knew what I needed to know for exams and kept it moving to the next class. But I try to make projects I enjoy, that's really all I got. Not even leetcode. No undergrad research. It really seems like AI is miles better than me. People around me in school seem to tell me: ""they'll always need someone to verify it"" , ""the funding will dry up"" , ""they need someone to fix the slop"", ""energy can't meet the demand"" But idk, it seems like we are really going full steam ahead. So many people already saying the job has shifted from problem solving to code review just as a mainstay. People saying ""oh it can't design complex systems"" , okay since when do Juniors do that? It feels like that's just expected now. Would it be right to assume that even if the AI train slows down, the expectation of a Junior has gone way up for good and essentially cooks all non high performers? For someone mid like myself - should I show myself out?"*
>
> *Could have been: vent*
>
> *I chose, because: I chose question because although there is quite a bit of complaining, the author asks some specific questions, such as what juniors are expected to know and the author wants to know what's true about the expectations.*

**3.**
> *The post: Female developer’s list of annoyances

I recently started a big project with lots of people and need to vent a bit. Feel free to share or vent if you have any annoyances too. Here’s my list. People just assume I’m a business analyst. Someone introduces the members of the development team, and I have to awkwardly shout from the side that I’m part of it too to get introduced. People automatically assume I’m on the front-end team and “better with colours.” I automatically get more front-end tasks than my male counterparts and have to call it out. I’m involved in small email chains, provide the correct information or solve the issue, and then someone declares, “We need someone from the development team.” I have to awkwardly call people out for sending me emails that repeatedly refer to me by the other female developer’s name. People refer to my manager’s team or talk about my manager as if I don’t know them or him, but that’s my team!! And I have to listen to my manager correct the big boss on which female developer is which. My team itself is fine, but everyone else in the company either doesn’t think I exist or thinks I’m Mary/Julia/Sophie/that girl the business analyst/some merged-together estrogen Java unit with the other female developer??? It just doesn’t seem to be getting better, even though I’ve been at the company for a while now. I have a simple name, but everyone gets it wrong all the time. What’s going on, lol?*
>
> *Could have been: question*
>
> *I chose, because: I chose vent because the questions in the post are rhetorical or sarcastic in nature, not genuine questions seeking advice.*

---

## The Training Run

<!-- Your starting model, your settings, and anything you changed and why. -->

**Base model:** distilbert-base-uncased

**Settings:** <!-- epochs, learning rate, batch size, seed -->
3 epochs, learning rate 2e-5, batch size 16, seed 42, max length 128 tokens.
Trained on an Apple Silicon GPU (MPS), torch 2.14.1; training took about 14
seconds.

| Epoch | Training loss | Validation loss | Val accuracy | Val macro F1 |
|---|---|---|---|---|
| 1 | — | 0.650 | 0.677 | 0.609 |
| 2 | 0.682 | 0.606 | 0.806 | 0.805 |
| 3 | 0.612 | 0.576 | 0.806 | 0.801 |

**Anything I changed from the defaults, and why:**

**Split sizes:** <!-- train / val / test, and per-label counts in the test
split. If a label had fewer than about 8 in test, say so — it explains a lot
of next unit's variance. -->

| | Train | Val | Test |
|---|---|---|---|
| vent | 65 | 14 | 14 |
| question | 74 | 17 | 16 |
| **Total** | 139 | 31 | 30 |

Both labels have more than 8 posts in the test split, but only just over 14,
so a single misclassified post moves a label's F1 by several points.



---

## How I Used AI

<!-- Two specific moments — what you asked, what came back, what you changed.

     ⚠️ Plus disclosure of any pre-labelling. If you had a model pre-label a
     batch and then read and corrected every one, say that. It's an allowed
     workflow and disclosing it costs you nothing. Not disclosing it is the
     problem. -->

**Moment 1**

- *What I asked for:* I asked help for my label definitions for "vent" and "question".
- *What came back:* It gave me rigid definitions with hard rules for overlap. 
- *What I changed:* I realized that there can be significant overlap when considering which label it should be. So I wrote that vent posts can have questions too, but they would be rhetorical or sarcastic.

**Moment 2**

- *What I asked for:* I AI to format my posts for my csv file
- *What came back:* It gave me paragraphs with removed "\n"s, but the quotes in the paragraphs were still there and messing with the csv values. 
- *What I changed:* So I asked it to replace double quotes with quadruple quotes.

**Pre-labelling disclosure:**

<!-- ═══════════════════════ UNIT 6 — THE TEST ═══════════════════════

     Don't fill these in during unit 5.
     ═══════════════════════════════════════════════════════════════════ -->

---

## Baseline vs. Trained

<!-- Both models on the same posts. `python baseline.py --trained results.json`
     prints this table for you. -->

| Measure | Baseline | Trained | Difference |
|---|---|---|---|
| Overall accuracy | 0.900 | 0.867 | -0.033 |
| Macro F1 | 0.899 | 0.861 | -0.038 |
| F1 — `question` | 0.909 | 0.889 | -0.020 |
| F1 — `vent` | 0.889 | 0.833 | -0.056 |

**What I predicted before I looked:**
<!-- Milestone 1 asks you to write this BEFORE seeing the trained numbers. A
     prediction made afterwards isn't one. -->
I expected the trained numbers to be higher than the baseline numbers, especially the F1 for "vent" because the trained model should be able to identify vent posts better after seeing many vent posts that have rhetorical or sarcastic questions in them. 

**What the gap actually means:**
<!-- If the baseline matched your trained model, your fine-tuning added
     nothing — and that is a real finding, not a failure. Say it plainly. -->
The baseline model is actually slightly better than the trained model because it got 27/30 labels right while the trained model got 26/30 labels right. Specifically for the vent label, the trained model got 4 posts incorrectly labeled as question, and 0 question posts were called vent. The trained model isn't good at labeling vent posts when there are questions in it.

---

## Run Log — Before

<!-- Five criteria across three seeds. The notebook's section 6 prints the
     spread table; the Target and Verdict columns are yours. -->

| Criterion | Target | Seed 42 | Seed 7 | Seed 2024 | Verdict |
|---|---|---|---|---|---|
| 1. Overall accuracy | ≥ 0.75 | 0.867 | 0.633 | 0.867 | **MISSED** |
| 2. F1 for each label | ≥ 0.70 each | vent 0.833 · question 0.889 | vent 0.353 · question 0.744 | vent 0.846 · question 0.882 | **MISSED** |
| 3. No label > 65% of predictions | ≤ 65% | 67% question | 90% question | 60% question | **MISSED** |
| 4. Confidence gap (most-sure − least-sure third) | ≥ 0.10 | 0.900 − 0.800 = 0.10 | 0.900 − 0.300 = 0.60 | 1.000 − 0.800 = 0.20 | **MET** |
| 5. Agreement with staff labels | ≥ 70% | 28/30 = 93% | (not seed-dependent) | (not seed-dependent) | **MET** |

**Spread across seeds** (section 6):

| Measure | Seed 42 | Seed 7 | Seed 2024 | Spread |
|---|---|---|---|---|
| Overall accuracy | 0.867 | 0.633 | 0.867 | 0.233 |
| Macro F1 | 0.861 | 0.549 | 0.864 | 0.316 |
| F1 — `vent` | 0.833 | 0.353 | 0.846 | 0.493 |
| F1 — `question` | 0.889 | 0.744 | 0.882 | 0.145 |

Accuracy moved 0.233 across seeds — more than 10 points, so a single run of
this model isn't a stable measure.

### Confusion matrix

<!-- ⚠️ TYPED AS A MARKDOWN TABLE. The notebook prints one ready to paste.
     An image of a matrix earns nothing. -->

Seed 42:

| true \ predicted | vent | question |
|---|---|---|
| **vent** | 10 | 4 |
| **question** | 0 | 16 |

**My biggest off-diagonal number, and what it means:**
<!-- Not "the model made mistakes" — WHICH boundary it didn't learn, and which
     direction. "7 real analysis posts were called hot_take and only 3 went the
     other way" is a direction, not just an error rate. -->
The biggest off-diagonal number is 4, 4 vent posts were mislabeled as question. The model made 0 mistakes for labeling questions as questions, so I think it sees any question and labels vent posts as questions. 

---

## Verdicts and Diagnoses

<!-- MET or MISSED against LAST UNIT's target. The target has to hold across
     all three seeds, not turn up sometimes. -->

| # | Criterion | Target | Verdict | How I decided |
|---|---|---|---|---|
| 1 | Overall accuracy | ≥ 0.75 on all three seeds | MISSED | 0.867 and 0.867 pass, but seed 7 scored 0.633. The target has to hold on every seed. |
| 2 | F1 for each label | ≥ 0.70 for both labels, on all three seeds | MISSED | `question` passed on every seed (0.889 / 0.744 / 0.882), but `vent` scored 0.353 on seed 7. |
| 3 | No label > 65% of predictions | ≤ 65% on all three seeds | MISSED | The model guessed `question` 67% of the time on seed 42 and 90% on seed 7. Only seed 2024 (60%) passed. |
| 4 | Confidence gap | Most-sure third ≥ 0.10 more accurate than least-sure third, all seeds | MET | 0.10 / 0.60 / 0.20. Seed 42 is exactly on the line, a gap of one post, so this is the narrowest possible pass. |
| 5 | Agreement with staff labels | ≥ 70% | MET | 28/30 = 93%. |

**Diagnoses**

<!-- For each miss: the cause, and how you know. The four common causes are:
     too few examples for a label, a boundary you applied inconsistently, a
     genuinely hard label pair, and a task the model can't reach from this
     much data.

     ⚠️ Use your agreement report as evidence. It is the only instrument you
     have that can tell a LABELLING problem from a MODEL problem, and this
     section is graded on whether you used it that way. -->

**Criteria 1, 2 and 3 have one cause: the model is undertrained, it's not a problem with the labeling **

All three misses come from the same behavior: the model calls vents
`question`. Across the three seeds, 18 real vents were called `question` and
only 1 real question was called `vent`. Seed 7 is the extreme case: 11 of its
14 vents were called `question`, which is what made accuracy 0.633,
`vent` F1 0.353, and the share of `question` guesses 90%.

How I know it's undertraining:

- **The model barely learned.** With two labels, pure guessing gives a
  training loss of 0.693. My training loss only fell from 0.68 to 0.61–0.64
  over 3 epochs (27 training steps on 139 posts).
- **It's never confident.** On every seed, every prediction had a confidence
  between 0.43 and 0.71. It isn't separating the two labels so much as
  nudging them slightly apart.
- **The errors go towards the majority label.** `question` is 53.5% of my
  data. On seed 7 the model's average P(question) was 0.59, so nearly every
  vent landed just over the 0.5 line. A model this unsure falls back on the
  more common label.
- **My first guess was wrong.** I expected rhetorical question marks to cause
  it, but 9 of the 18 misclassified vents contain no "?" at all. The errors
  don't follow a feature of the posts, which also points at the model, not
  the boundary.

How I know it's mostly not my labelling:

- **The agreement report:** I matched the staff labels on 28 of 30 posts
  (93%). When I apply a written rule, I apply it consistently, so I don't
  think my 200 labels are full of contradictions.
- **I re-read all 18 misclassified vents.** About 3 of them arguably do ask
  readers for something under my own rule. One ends "Hopefully some of you
  ... can tell me how to handle this better", another "Any words of
  encouragement would also be monumental". Those are boundary cases I may
  have labelled loosely, but 3 of 18 can't explain the other 15.

**What I'll fix:** train for more epochs, so the model gets past near-chance
loss before it's tested.

**Criterion 4 met, but barely.** On seed 42 the gap is exactly 0.10, one post.
Because every prediction sits between 0.43 and 0.71, the "most-confident
third" isn't actually very confident, so this pass doesn't mean much.



---

## Agreement Report

<!-- Your rate against the staff set, and every disagreement adjudicated.

     Remember you labelled these 30 under the STAFF taxonomy in
     data/staff_taxonomy.md, not your own — so every argument below is made
     from those definitions and those decision rules. -->

**Agreement rate:** 28 / 30 = 93%

<!-- Nobody grades this number. A 60% who argues every disagreement from the
     stated rules beats a 95% who wrote "staff was right" nine times. Several
     of the 30 were chosen because they're genuinely ambiguous — you should be
     winning some of these. -->

**Disagreements**

<!-- Three lines each: the post, both labels, and who you think is right and
     why — grounded in the staff definitions you were both applying.

     Then sort each into one of three piles:
       (a) the rule covered it and I applied it loosely → a consistency problem
       (b) the rule genuinely doesn't say               → a gap in the definitions
       (c) the rule is ambiguous here and my reading is defensible → argue it.
           This is a legitimate win.

     Pile (a) is the one that matters most for your diagnosis: if you applied a
     written rule two different ways on 30 posts, that is direct evidence about
     what you did across your own 200. -->

**1.**
> *The post:* "The club championship scoring changed in 2019 from top-6 to
> top-10. Since then our B team has finished above the A team twice. That's not
> depth improving, it's the scoring rewarding turnout."
>
> *Staff said / I said:* `analysis` / `hot_take`
>
> *My call, and why:* I think my reading holds up. Rule 1 asks whether the
> checkable fact carries the argument. The date and the rule change are real
> facts, but they only show that the B team started beating the A team. The
> actual claim, that the scoring "rewards turnout", is never supported: there
> are no turnout numbers, and the other explanation ("not depth improving") is
> dismissed, not argued against. The facts set the scene, and the conclusion is
> asserted, which is what the `hot_take` definition describes: "It isn't
> argued."
>
> *Which pile:* (c) The rule is ambiguous here, because it doesn't say whether
> the fact has to support the *final* conclusion or just part of the
> argument, and my reading is defensible.

**2.**
> *The post:* "Three of us ran the same session on the same day, different
> shoes, within 10 seconds of each other over 5 miles. I'm not saying shoes do
> nothing, but whatever they do was smaller than the noise between three
> people."
>
> *Staff said / I said:* `analysis` / `reaction`
>
> *My call, and why:* The definitions don't say what counts as a checkable
> fact. "Three runners, within 10 seconds" is checkable, but it's a sample of
> three people on one day, and the staff's own note admits it's a "tiny
> sample". Nothing in the rules says whether a fact that small can carry a
> general claim about shoes. I labelled it `reaction` because it's about the
> writer's own session, but looking back, Rule 3 says recency doesn't outrank
> evidence, and the post has no feeling in it. If the sample is too small to
> count, the better alternative is `hot_take`, not `reaction`.
>
> *Which pile:* (b) A gap in the definitions: they never say how strong a
> fact has to be to count as load-bearing.

**What the pattern in my disagreements tells me:**



---

## The Improvement

**What I changed:** A training setting: I changed EPOCHS from 3 to 10.

**Which diagnosis pointed at it:** Criteria 1–3 all missed for the same
reason, the model was undertrained. After 3 epochs the training loss was
0.61–0.64, which is barely below the 0.693 you get from guessing. Every prediction had a confidence between 0.43 and 0.71, and the uncertain model fell back on the majority label, `question`. My agreement report (93%) and rereading the 18 misclassified vents ruled out labelling as the main cause, so the fix was training.

### Run Log — After

| Criterion | Target | Seed 42 | Seed 7 | Seed 2024 | Verdict |
|---|---|---|---|---|---|
| 1. Overall accuracy | ≥ 0.75 | 0.867 | 0.867 | 0.967 | MET |
| 2. F1 for each label | ≥ 0.70 each | vent 0.846 · question 0.882 | vent 0.846 · question 0.882 | vent 0.966 · question 0.968 | MET |
| 3. No label > 65% of predictions | ≤ 65% | 60% question | 60% question | 50% question | MET |
| 4. Confidence gap (most-sure − least-sure third) | ≥ 0.10 | 1.000 − 0.600 = 0.40 | 1.000 − 0.700 = 0.30 | 1.000 − 0.900 = 0.10 | MET |
| 5. Agreement with staff labels | ≥ 70% | 28/30 = 93% | (not seed-dependent) | (not seed-dependent) | MET |

**Spread across seeds, after** (section 6):

| Measure | Seed 42 | Seed 7 | Seed 2024 | Spread |
|---|---|---|---|---|
| Overall accuracy | 0.867 | 0.867 | 0.967 | 0.100 |
| Macro F1 | 0.864 | 0.864 | 0.967 | 0.102 |
| F1 — `vent` | 0.846 | 0.846 | 0.966 | 0.119 |
| F1 — `question` | 0.882 | 0.882 | 0.968 | 0.085 |

**Confusion matrix, after (seed 42):**

| true \ predicted | vent | question |
|---|---|---|
| **vent** | 11 | 3 |
| **question** | 1 | 15 |

**Did it help, and how do I know:**

Yes. All three criteria I missed are now met, on all three seeds.

| | Before (3 epochs) | After (10 epochs) |
|---|---|---|
| Accuracy, seeds 42 / 7 / 2024 | 0.867 / 0.633 / 0.867 | 0.867 / 0.867 / 0.967 |
| Spread in accuracy | 0.233 | 0.100 |
| Real vents called `question` (all seeds) | 18 | 6 |
| Share of `question` guesses, worst seed | 90% (seed 7) | 60% |
| Average confidence when right, seeds 42 / 7 / 2024 | 0.59 / 0.61 / 0.55 | 0.96 / 0.94 / 0.90 |

The biggest change is that seed 7 stopped collapsing: it went from calling 11
of 14 vents `question` to 3 of 14. The model is also confident now. Before,
every prediction was between 0.43 and 0.71; now correct predictions average
0.90–0.96. That's what I'd expect if the problem really was undertraining, so
it supports the diagnosis.

Some limits on how far this goes:

- **Seed 42 didn't improve overall.** Accuracy is 0.867 both before and after.
  The errors are spread more evenly (3 one way, 1 the other, compared with
  4 and 0), but it's the same number of mistakes.
- **It still doesn't beat the baseline on seed 42.** The zero-shot baseline
  scored 0.900 on the same 30 posts, and my trained model still scores 0.867.
- **The lean towards `question` is smaller but still there**: 3 vents called
  `question` vs 1 question called `vent` on seed 42.
- **Criterion 4 only just passes on seed 2024** (a gap of exactly 0.10), and
  the spread is still 10 points, so a single run still can't be fully trusted.



---

## What's Still Broken

<!-- For each criterion still missed: what you'd do, and why you stopped. -->



**The gap between what I meant my labels to capture and what the model
learned:**
<!-- Two sentences. Your confusion matrix is the evidence. -->



<!-- ═════════════════════════════════════════════════════════════════════

     SUBMISSION CHECKLIST — unit 5

       [ ] criteria.md has five numbered criteria, each naming a NUMBER
       [ ] Each has a reason underneath tied to your data or taxonomy
       [ ] labels.csv: at least 150 rows, text/label/note, ONE file not split
       [ ] No label above 70%
       [ ] All five unit 5 sections have real content
       [ ] Label Taxonomy includes the decision rule for your hardest boundary
       [ ] The Dataset includes three hard cases
       [ ] results.json and test_split.csv committed (the notebook does this)
       [ ] At least four new commits
       [ ] Repository URL submitted — WRITE IT DOWN

     SUBMISSION CHECKLIST — unit 6

       [ ] Baseline vs. Trained table, with your prediction written beforehand
       [ ] Run Log — Before, five criteria across three seeds
       [ ] Confusion matrix TYPED AS A MARKDOWN TABLE
       [ ] A verdict on every criterion
       [ ] A diagnosis for every miss, using the agreement report as evidence
       [ ] Agreement Report with every disagreement adjudicated
       [ ] One improvement, with Run Log — After
       [ ] What's Still Broken
       [ ] results_three_seeds_before.json, results_three_seeds_after.json,
           baseline_results.json and
           agreement_results.json committed
       [ ] At least four new commits
       [ ] The SAME repository URL as last unit

     Do not delete and recreate this repository.
     ═════════════════════════════════════════════════════════════════════ -->

---

📖 **How to run this project: [RUNNING.md](RUNNING.md)**
