# Voice guide: how I talk upstream

<!--
THIS IS THE PART YOU WRITE (new this week). Live mode reads this file
before any comment of yours goes out the door; eval mode ignores it
entirely, because your voice is yours and carries no gold labels.

This is not etiquette. "Be polite and concise" is advice for everyone
and therefore rules for no one. Write rules YOU need, in your own
words, each one concrete enough that the skill can hold a draft
against it and say which rule it breaks.

Three sections. Fill all three.
-->

## Who I am in threads

I am a student learning open-source contribution and software debugging. I am using this repository to practice reproducing real issues and reporting what I observe. Readers can expect me to be specific about what I tested and honest about what I could or could not reproduce.

## Rules I write by

### Rule: Say only what I verified

I separate what I actually observed from what I think may be happening. I do not present guesses as confirmed results.

- Wrong: "I confirmed that this dependency is causing the bug."
- Right: "I reproduced the reported behavior with this dependency installed, but I have not confirmed that the dependency is the cause."

### Rule: Be specific to the issue

I name the behavior or test I am working on instead of posting a generic claim that could apply to any issue.

- Wrong: "I will investigate this issue and report back."
- Right: "I will try to reproduce the reported behavior using the setup described in this issue and report the environment, steps, and observed result."

### Rule: Do not claim success without evidence

I call an issue reproduced only when my recorded result shows the behavior described by the issue. If it does not appear, I say that clearly.

- Wrong: "I reproduced the issue successfully."
- Right: "I followed the reproduction steps, but I could not reproduce the reported behavior in my environment."

### Rule: Promise investigation, not a fix

When claiming an issue, I commit only to investigating and reporting my result. I do not promise that I will fix the problem or give a completion date.

- Wrong: "I'll fix this bug by tomorrow."
- Right: "I'll attempt to reproduce this issue and report what I observe."

## Things I never post

- A promise that I will fix an issue before I have investigated it.
- A deadline or completion date I cannot guarantee.
- A claim that I reproduced something when my evidence does not show it.
- Guesses presented as confirmed causes.
- Generic comments that do not identify what I actually plan to test.
- Claims about work or evidence that I did not personally produce.