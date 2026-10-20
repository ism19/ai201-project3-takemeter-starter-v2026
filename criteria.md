# Acceptance criteria — TakeMeter

Five criteria that say what "working" means for this classifier, written in
unit 5 **before** anything was trained.

**All five are yours this time.** None are given. You've had two projects of
practice.

An acceptance criterion names a number. *"The model is accurate"* is an
opinion. *"Every label has an F1 of at least 0.60 on the held-out set"* is a
criterion.

Under each, write a sentence or two on **why that number**. A reason that says
something about your data or your taxonomy earns credit — *"I picked 0.60 F1
for `reaction` because it's my smallest label and I only have about 50
examples of it"*. A reason that could be attached to any project does not.

> Missing your own targets next unit costs you nothing. Setting a target so
> easy you can't miss it does.

---

## Pick numbers you can defend

Not numbers that sound impressive. Three labels means a coin-flip guesser gets
about 33%, so a target of 0.40 is barely a target. Your number should sit
somewhere you'd honestly call useful.

**Cover at least three of these five areas.** They're here as prompts, not as a
form to fill in — a criterion that fits none of them is fine if it names a
number.

| Area | A question it could answer |
|---|---|
| Overall accuracy | How often does it need to be right to be worth using? |
| Per-label performance | Is one label allowed to be much worse than the others? |
| Balance | How lopsided can your label counts get before it's a problem? |
| Consistency | If someone else labelled the same posts, how often should you agree? |
| Confidence | Should a confident prediction be right more often than an unsure one? |

Two things worth knowing before you pick numbers, because both will affect
whether you hit them:

- **Your smallest label will have the jumpiest score.** If a label has 50
  examples, about 8 land in the test split. An F1 computed on 8 examples moves
  a lot between seeds. A target for that label should be looser than one for
  your biggest label, and saying so is a good reason.
- **Unit 6 tests across three seeds, and the target has to hold across all
  three.** A target of 0.65 against results of 0.71, 0.62, 0.68 is a **miss**.
  Pick with that in mind — it is stricter than it first sounds.

---

## 1. Overall accuracy

Overall accuracy is at least 0.75 on the held-out test split, on all three seeds (42, 7, 2024).

**Why this target:** My 200 posts are 107 "question" (53.5%) and 93 "vent" (46.5%), so a model that always says "question" already gets about 54%, and a coin flip gets 50%. 0.75 is about 20 points above that. I'm not aiming higher because the notebook only reads the first 128 tokens (about 95 words), and 30 of my 107 question posts don't ask anything until after that point, so the model can't see what makes them questions.

---

## 2. Both labels work, not just one
"vent" and "question" each have an F1 of at least 0.70, on all three seeds.

**Why this target:** The split is close to even, so the test split will have only about 16 "question" and 14 "vent" posts, and with that few, one mistake moves a label's F1 by around 5 points. That's why this target sits below the 0.75 for overall accuracy. Each label has its own way to fail. 46 of my 93 vents contain a "?" ("why do they need to be so paternalistic?"), which could make vents into "question". And 30 of my questions only ask after the 128-token cutoff, which could make questions into "vent". A separate F1 for each label shows which of those is happening.

---

## 3. The model's guesses aren't lopsided

On the test split, neither label makes up more than 65% of the model's predictions, on all three seeds.

**Why this target:** Balanced data doesn't guarantee balanced guesses. My vents are much longer (median 198 words vs 120 for questions, and 21 vents run over 300 words vs 6 questions), so the model could learn "long means vent" and not read the content. The true split in the test set should be near 54/46. If more than 65% of the model's guesses go to one label, it is leaning on a shortcut like length. I can check this from the column totals of the confusion matrix.

---

## 4. Confidence means something

Accuracy on the model's most-confident third of test posts is at least 0.10 higher than on its least-confident third, on all three seeds.

**Why this target:** My data has clear cases and murky ones. 50 of my 107 questions end with a "?", and 47 of my vents have no "?" at all; those should be easy and confident. The murky ones are the 46 vents that contain rhetorical questions and the 30 questions whose ask comes after the 128-token cutoff. If the model's confidence is worth anything, its least-sure third should be mostly those posts and score lower. With 10 posts per third, a 0.10 gap is one extra correct post, the smallest difference I'd count as real.

---

## 5. Consistency with someone else's labels

On the 30 staff posts, my labels match the staff labels on at least 70% (21 of 30).

**Why this target:** The 30 staff posts use three labels (analysis, hot_take, reaction), so chance is about 33%, and 70% (21 of 30) means I'm applying their written rules, not guessing. The staff's hot_take vs analysis line, whether a fact "does work" in the argument, is the same kind of judgment as my vent/question line, whether a question is really asking. If I can't reach 70% on someone else's written rules, that's a sign my own 200 labels weren't applied consistently either.

---

<!-- ─────────────────────────────────────────────────────────────────────────
     UNIT 6 — read this before you change anything above.

     If a criterion turns out to be BROKEN rather than merely unmet, you can
     revise it, and that earns credit. But never delete or edit the original
     line. Add the revision underneath, like this:

         ## 2. Every label performs acceptably

         The model performs well on all labels.

         **Why this target:** ...

         > **Revised in unit 6:** Every label has an F1 of at least 0.60 on
         > the held-out set.
         >
         > **Why revised:** "performs well" gave me nothing to check. I
         > couldn't produce a verdict from it at all.

     That's a revision because the criterion couldn't be MEASURED.

     Lowering a target because you missed it is not a revision, and it costs
     you the point:

         ✗ "Overall accuracy of at least 0.65" → "at least 0.55", because
            0.65 turned out to be optimistic for 200 examples.

     A number you missed stays where it is, gets diagnosed, and gets a fix
     attempted. That's where the points are.
     ───────────────────────────────────────────────────────────────────────── -->
