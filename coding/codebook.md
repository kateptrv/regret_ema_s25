# Regret life-domain codebook

Unit of coding: one regret episode, i.e., the free-text `decision` written at the ping
where the regret was first reported (`regret_yn == 2`). Follow-up pings inherit the
episode's code.

Categories were built bottom-up from the regrets participants wrote (daily EMA regrets,
mostly students), rather than taken from an existing taxonomy.

## Variables

| Variable | Description |
|---|---|
| `regret_domain` | Primary life domain (required; one of the codes below) |
| `regret_domain_secondary` | A second domain that is clearly involved, if any (blank otherwise) |
| `coding_note` | Assumptions made or ambiguity, if any |

## Decision rules

1. **Code the counterfactual.** The primary domain is the area of life the person
   wishes they had acted differently in: what they "should have" done or not done.
2. **"X instead of Y" regrets: code Y**, the neglected alternative, and put X as the
   secondary domain. *"Watched YouTube instead of doing my math homework"* is
   `academics` (secondary `leisure`).
   - If there are several neglected alternatives across domains (*"stayed in bed
     instead of going to the gym or studying"*), code the regretted behavior itself
     (`sleep`).
   - If the neglected alternative is vague (*"instead of being productive"*,
     unspecified *"work"*), code `productivity`.
3. **Consequences go in the secondary domain.** *"Overslept and was late to class"* is
   `sleep` (secondary `academics`). *"Drank Thai tea in the afternoon and couldn't
   sleep"* is `eating` (secondary `sleep`).
4. **Interpersonal regrets are coded by the relationship.** Family member → `family`;
   partner, date or crush → `romantic`; coworker, boss, customer or patient → `work`;
   classmate, teammate or professor in a school setting → `academics`. Anyone else, or
   an unspecified relationship → `social`.
5. **Lateness and missed obligations are coded by the obligation** (late to class →
   `academics`, late to a shift → `work`). If the obligation's domain is unknown
   (*"late for my appointment"*), code `daily_life`.
6. **Money regrets are coded `money` when the cost is the point** (*"spent too much"*,
   *"expensive"*). If the regret is about the thing bought (*"the boba wasn't good"*),
   code the thing's domain.
7. **Use `unclear`** only when the text is missing or can't be linked to any domain
   (e.g., *"News"*). Vague but codable texts get a code plus a `coding_note`.
8. Text that describes a worry or indecision rather than a regret is still coded by
   domain, with a note.

## Categories

| Code | Label | Includes | Examples |
|---|---|---|---|
| `academics` | School & studying | Homework, studying, exams, classes, grades, academic choices (courses, schools, degrees), college applications, school-based interactions with classmates or professors | "Not studying more for my exam"; "I regretted not taking certain classes with certain teachers" |
| `work` | Job | Job performance and preparation, shifts, scheduling, taking or declining work, job applications, interactions with coworkers, bosses, customers or patients | "My boss asked me if I knew the specials and I hadn't checked"; "I regret going to work while I'm sick" |
| `eating` | Eating & food | Overeating, unhealthy food, skipping or delaying meals, food and drink choices (incl. caffeine), cooking results, restaurant or takeout disappointments | "I ate too many donuts"; "I cooked my eggs too long" |
| `sleep` | Sleep & getting up | Oversleeping, snoozing, staying up late, naps, staying in bed, sleep schedule, sleep aids | "I set my alarm to snooze and woke up late"; "I stayed up until 2am playing games" |
| `health` | Physical health & substances | Exercise and gym, illness, injury, sun protection, medication, alcohol, smoking | "Not going harder at the gym"; "Mixing a few types of alcohol, now I'm hungover" |
| `romantic` | Romantic relationships | Partner or spouse, dating, asking someone out, attraction, exes | "I had an argument with my partner"; "I wanted to ask someone out but didn't" |
| `family` | Family & parenting | Parents, siblings, children and parenting, extended family, family events | "Didn't use a good tone with my daughter"; "I haven't seen my family for more than 3 years" |
| `social` | Friends & other social | Friends, acquaintances, strangers, peers outside class, interpersonal regrets with an unspecified relationship | "Did not communicate what I was upset about with a friend"; "Rude to someone" |
| `money` | Spending & money | Overspending, regretted purchases, budgets, prices | "I spent too much money at Hobby Lobby"; "Spending money on Uber Eats" |
| `leisure` | Leisure & entertainment | Regrets about the leisure activity itself (movies, games, trips, outings, going out), not about the time it took away from something else | "Went to watch a movie and didn't like it"; "Used up a rare item in the game" |
| `productivity` | General productivity & time use | Unproductive time, procrastination or time-wasting with no specific domain named | "Not being productive enough"; "Spent the whole morning watching YouTube Shorts" |
| `daily_life` | Household, errands & logistics | Chores, home projects, moving, errands and shopping logistics, travel and commuting (routes, traffic, parking, airports), possessions, pets, clothing and appearance, unspecified appointments | "Not taking the trash out sooner"; "Left my suitcase on the airport shuttle" |
| `self` | Mental health & life direction | Emotional wellbeing, motivation, mindset, broad regrets about life choices or identity | "I haven't moved from bed in 5 hours and don't have the motivation"; "I'm regretting my life's choices more and more" |
| `unclear` | Unclear / missing | No text, or text that can't be assigned to a domain | "News" |

## Additional dimensions

Coded from the same text, independently of domain.

| Variable | Codes |
|---|---|
| `regret_agency` | `high`, `partial`, `low`, `unclear` |
| `regret_type` | `commission`, `omission`, `both`, `unclear` |
| `regret_concreteness` | `1`, `2`, `3` (blank if there is no text) |

### Agency (`regret_agency`)

How much the regretted outcome came from the participant's own choices and control.

| Code | Definition | Examples |
|---|---|---|
| `high` | A deliberate choice or behavior the person controlled, including self-control lapses (procrastinating, overeating, oversleeping) | "I spent too much money at Hobby Lobby"; "Decided not to go on a walk" |
| `partial` | The person's own action is involved, but the outcome was unintended (forgetting, mistakes, accidents during their own action) or jointly shaped by other people or circumstances (group decisions, agreeing to someone's request, others' reactions) | "I forgot to submit my assignment"; "We let one of my teammates scratch off an answer"; "I went up to these girls to campaign, but they were a bit rude" |
| `low` | The outcome was mostly outside the person's control, or no action of their own is described (worries, other people's behavior, accidents that happened to them) | "Hit my toe on the corner of the couch"; "My son may have to go through speech therapy" |
| `unclear` | Too vague or missing to judge | "News" |

### Omission vs. commission (`regret_type`)

Coded from how the person **frames** the regretted behavior, following the
action/inaction distinction in the regret literature (Gilovich & Medvec, 1995):

| Code | Definition | Examples |
|---|---|---|
| `commission` | Regrets something they did ("I ate...", "I stayed up...", "I said...", "procrastinated") | "Ate too much chocolate" |
| `omission` | Regrets something they didn't do ("didn't...", "not...", "should have...", "I wish I had...") | "Not studying more for my exam"; "I should have eaten breakfast" |
| `both` | Explicitly contrasts an action taken with one forgone ("X instead of Y", "chose X over Y") | "Watching YouTube instead of getting started on my math homework" |
| `unclear` | No regretted behavior is described (worries, indecision, fragments) | "Kids soccer game"; "What to eat for dinner tonight?" |

Framing is coded as written, even when the substance could be described either way.
For example, *"procrastinated"* is `commission`, and *"didn't buy the right size pot"* is
`omission`.

### Concreteness (`regret_concreteness`)

| Code | Definition | Examples |
|---|---|---|
| `1` Vague | No specific behavior or event can be identified: global self-evaluations, topics or fragments | "Not being productive enough"; "Not being supportive enough"; "News" |
| `2` Specific behavior | An identifiable behavior or event, with little situational detail | "Ate too much chocolate"; "Spending money on Uber Eats"; "Rude to someone" |
| `3` Concrete episode | A specific behavior plus situational detail (when, where, who, what exactly) or a concrete causal consequence. Feelings alone ("didn't feel good") don't count | "I wore flip flops to the mall and walked around for 6 hours"; "I didn't put a few definitions on my notecard for my stats test" |

## Coding record

- Initial coding of all 259 regret episodes in the cleaned dataset (Sept 2026) was done
  by Claude (claude-opus-5-5) in one pass, at the PI's request. There was no second
  coder, so no reliability estimate is available. `coding_note` flags every assumption.
- Agency, omission/commission and concreteness were added for the same 259 regrets
  (Sept 2026), also by Claude in a single pass.
