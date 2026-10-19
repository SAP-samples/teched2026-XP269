# Exercise 2.2 — Build a Custom Skill

In Exercise 2.1, you ran a base prediction and saw what the service returns. That works, but every user would need to know the right prompt and what columns to fill. A **custom skill** packages your intent into one reusable capability. With this skill, the user can ask *"Is this car a good deal?"* and the skill will handle the prediction and business logic automatically.

A skill is a small folder with a `SKILL.md` file. Joule reads the `description` to decide **when** to use it, and the body to decide **how**. You'll start from the reference skill in this repo and make it your own.

## What is within the `SKILL.md` file
There are two parts:
1. **Frontmatter** (between `---` fences) — two fields:
   - `name`: a kebab-case id.
   - `description`: one line stating *what it does* and *when to use it*. **This is the trigger** —
     Joule matches the user's request against it, so phrase it with the words a user would say
     ("estimate price", "how much is this car worth", "predict the gearbox").
2. **Body** — Markdown sections telling the model how to fulfil the request: what inputs it needs,
   which MCP tool to call, and how to present the answer.

## Instructions

### Step 1 — Copy the reference skill

The completed skill is provided in [`used-car-deal-checker/SKILL.md`](used-car-deal-checker/SKILL.md). Open it and read it top to bottom — it is commented for the workshop.

Here are several things to note:
- The **description** lists trigger phrases a marketplace user would actually type.
- The **How it works** section calls the MCP's prediction tool `tabai-mcp` with:
  - The **scenario configuration name** from Module 01 (`used-cars-sc-<alias>`),
  - A **model** (`sap-rpt-1.6`),
  - The car's attributes as the query row, with the target column set to `[PREDICT]`.
- On top of the prediction, it takes the seller's asking price and compares it against the predicted market value using a ±5% threshold to give a verdict: **Good deal**, **Fair price**, or **Overpriced**.
- It depends on the base **response-style** guidance so the answer reads cleanly.

---

### Step 2 — Add your own flavour
You can edit two things so the skill uses **your** created resources:
1. In the body, set the scenario config to **your** name from Module 01: `used-cars-sc-<alias>`.
2. (Optional) In the `name` and folder, add your alias so your skill doesn't clash with a
   neighbour's: `used-car-deal-checker-<alias>`.

> Tip: don't over-edit. The description's trigger phrases and the single MCP call are what matter.

### Step 3 — Publish it into Joule Studio

<!-- TEAM: this is the one SAP-internal step the repos don't document. Fill in the exact Joule Studio mechanics for adding/importing a SKILL.md-style skill and making it available in chat. Replace the placeholder steps below with the real click-path or import command. -->

1. In Joule Studio, go to `<!-- TEAM: where skills are managed -->`.
2. Add a new skill and provide the `SKILL.md` in assets/tabai-agent/app/skills/used-cars-deal-checker by chatting with Joule. Paste the content directly into the chat, along with the filename and where you want it placed:
```
<Paste skill content here>
I want to create a new skill called used-cars-deal-checker. Place it in assets/tabai-agent/app/skills/used-cars-deal-checker.
```

### Step 4 — Trigger it

Start a fresh chat and use one of the trigger phrases, e.g.:

> "Is 420,000 a fair price for a 2018 Maruti Swift, petrol, manual, driven 45,000 km in Delhi?"

Joule should pick **your** skill (because the request matches its description), call the MCP prediction tool against **your** scenario config, and come back with a verdict — **Good deal**, **Fair price**, or **Overpriced** — along with the predicted market value and the gap.

If Joule picks a different skill or asks which to use, make your skill's `description` more specific to the phrases you want to own, and try again.

## Key Takeaways
- A skill = a `SKILL.md` folder: `description` decides *when*, body decides *how*.
- A custom skill sits **on top of** the base skills and the provided MCP. It doesn't re-implement prediction, it **orchestrates** the MCP tool with your scenario config and a sensible model.
- The deal-checker shows the extensibility pattern: the base prediction stays unchanged, and your skill adds business logic (the asking-price comparison) on top of the raw predicted value.
- The same pattern wraps *any* tabular prediction for a business user.


