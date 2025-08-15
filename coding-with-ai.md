# Coding with AI: Context Engineering for Developers

**Coding with AI isn’t about replacing you, it’s about amplifying you.** 
Think of AI as your sharp but clueless intern. It can work fast, but only if you guide it well.
Let’s explore how to actually get things done with AI, clearly, efficiently, and without losing your sanity.

---

## How to Get the Most Out of This Page

We know, reading can be a drag, so we made you a short video.
You’ll get a quick walkthrough of how to use this page, what to skip, and how to get the most value without spending your whole lunch break here. It's short. It's snappy. It might even make you smile.
[▶️ Watch the 2-minute video](#)

---

## A Few Guidelines from Experience

Think of this like advice from your Staff Engineer buddy who’s been quietly testing AI tools for the last year while still shipping features.

1. **Always give context**\
   Treat the AI like a new teammate. If you just say “fix this function,” it’ll panic like an intern on their first day. Tell it what the function does, why it matters, and how it fits into the bigger picture.

2. **Scope your prompts**\
   Don’t throw the entire codebase at the AI and hope for magic. AI isn’t Gandalf. Be specific. Target one file, one task, one goal at a time.

3. **Use file paths, not just code dumps**\
   Tools like Cursor shine when you reference files directly. Instead of pasting code, say: “See `services/payment.ts`” or “Refactor logic in `src/hooks/useCart.ts`.” It keeps things tidy, and scalable.

4. **Prompt like you're pair-programming**\
   Write your prompts as if you're explaining something to a junior dev who’s sharp but new to the codebase. Be kind, clear, and a little paranoid.

5. **Review everything**\
   AI is confident. Too confident. Sometimes it’ll give you great answers. Other times, it’ll hallucinate an entire config file for a framework you’re not using. Don’t skip the review phase.

6. **Use comments as anchors**\
   Mark the spots in your code where you want the AI to jump in. Like `// TODO: Refactor this mess`, or `// Can you simplify this logic?`. It’s context without clutter.

7. **Refine, don’t restart**\
   If the AI gives you something close-but-not-quite, don’t start over. Ask follow-up questions. Think of it as a dialogue, not a lottery.

8. **Be explicit about your expectations**\
   Want clean, idiomatic Rust? Say so. Prefer functional over OOP? Mention it. Otherwise, you’ll get whatever the model thinks is trendy that day.

9. **Log the good prompts**\
   Found a prompt that works? Save it. Reuse it. Tweak it. This is your new prompt library, and it’ll save you time when you’re in the weeds.

---

## Common Mistakes to Avoid

Some lessons you learn the hard way. Others you can borrow from the guy who already face-planted. Here are the classic errors:

1. **Too vague**\
   "Can you help?" — Help with what? Be specific. Think “I’m debugging a null pointer in `src/utils/parseUser.ts`” not “Something broke.”

2. **Too greedy**\
   Asking the AI to refactor five files, write tests, and generate docs in one go? Good luck. Break it up. You wouldn’t ask your coworker to do that in one sitting either (unless you hate them).

3. **Context starvation**\
   Dropping a function without any explanation of what it’s supposed to do or where it’s used is setting the AI up to fail. Give it enough to reason through the task.

4. **Stack-dumping without a question**\
   Don’t just paste an error and run. Tell it what you tried, what you expected, and what’s confusing. Otherwise, it’s just throwing spaghetti at the logs.

5. **Expecting genius from garbage**\
   If your code is already a tangled mess, the AI won’t magically untangle it. Clean it up a little first. Or at least give it some breathing room.

6. **Overusing it as a crutch**\
   AI is a great helper. But if you’re using it to avoid thinking, you’re going to ship weird, brittle code. Let it assist, not autopilot.

7. **Treating it like a search engine**\
   AI thrives on conversation. If you treat it like Google, you’ll miss the real power: collaboration.

8. **Ignoring project-specific logic**\
   Business rules matter. Don’t expect the AI to understand your custom billing flow unless you tell it what’s special about `calculateCharges.ts`.

---

## The Anatomy of a Great Workflow

Here’s what actually works in the real world:

1. **Understand the task**\
   Is this a bug fix? A new feature? A refactor? Know what you're solving, and why, before involving the AI.

2. **Add just enough context**\
   File paths, rough description of the logic, and constraints. Don't drop a novel, just the essentials.

3. **Start small**\
   Instead of “refactor the system,” start with “refactor the logic inside `src/utils/sortUsers.ts` for readability.” One shot, one file.

4. **Write your prompt like a Slack message**\
   Simple, clear, honest. You’re asking for help, not delivering a TED Talk.

5. **Use follow-up prompts to go deeper**\
   If the output is good, build on it. If it’s off, steer it. AI needs guidance, not silence.

6. **Leave breadcrumbs**\
   Comment your code with what you tried, what worked, and what didn’t. It helps you and helps the AI next time.

7. **Validate the result**\
   Don’t just copy-paste. Run it. Test it. Make sure it fits into your system, your patterns, and your team’s sanity.

8. **Log winning prompts**\
   Save them. Build a prompt toolbox. It’s faster than writing everything from scratch every time.

---

## The Anatomy of a Great Prompt

### Developing a Feature

**The key to a great prompt:**\
Give a clear goal, the file(s) involved, the tech stack, and the feature's role in the bigger system. Don't assume the AI knows the architecture, feed it breadcrumbs.

**Prompt Blueprint:**

```
I’m adding a feature to allow users to [brief description of feature].
Main file(s): [path/to/file.ts]
We use: [e.g., React + Node + MongoDB]
The logic should handle: [brief logic or flow]
What’s the best way to implement this?
```

### Reviewing a PR

**The key to a great prompt:**\
Let the AI do the digging, your job is to give it direction. Tell it what kind of feedback matters.

**Prompt Blueprint:**

```
Please review the current PR.
Focus on: [e.g., edge cases, error handling, readability, consistent naming]
Call out anything unclear or risky.
```

### Refactoring Code

**The key to a great prompt:**\
Be clear on your goals: Do you want simpler logic? More readable code? Better structure? Don’t just say “refactor”.

**Prompt Blueprint:**

```
I want to refactor this file: [path/to/file.ts]
Main goals: [e.g., improve readability, reduce nesting, split concerns]
The current logic is too dense. Can you suggest a cleaner structure?
```

### Debugging

**The key to a great prompt:**\
Show the symptom (error), the suspect (file), and the steps you’ve tried. AI loves patterns, so let it follow your trail.

**Prompt Blueprint:**

```
There’s a bug in: [path/to/file.tsx]
Error: [copy-paste error message or stack trace]
It happens when: [specific condition, e.g., user logs in without data]
I’ve tried: [e.g., adding null checks, logging intermediate values]
Can you help me spot the issue?
```

### Understanding a New Project

**The key to a great prompt:**\
Don’t ask for a tour, ask smart, targeted questions. Help the AI help you navigate like a senior dev on day one.

**Prompt Blueprint:**

```
I’m exploring this project and trying to understand how [specific module] works.
Main file: [path/to/module.ts]
Can you explain the purpose of this module and how it connects to [another part]?
Also, where would I go to change [specific behavior]?
```

---

## Don’t Be Shy, Pay Us a Visit

True skills never go out of date.
[Give it a look](https://www.bytestoskills.co/), it’s short, sharp, and doesn’t waste your time.

