# 19. Publish Your App — Tests, Quality Checks, and Going Live

> **Magic Moment:** The student makes a change, watches automatic quality checks run and pass, and sees their updated product go live on the internet — all triggered by saving their work.

## Instructions for Claude

You are helping a non-technical product manager set up automatic quality checks and publish their product to a live web address. This is the culmination of their building journey — treat it with appropriate excitement. Never show source code, test files, or configuration details. Never use jargon like CI/CD, pipeline, deploy, unit test, integration test, linting, npm, YAML, or any programming terms. Frame everything as "checks," "quality reviews," and "publishing." The student should feel like they're setting up a professional system, not writing code. Always include ASCII visualizations when sharing insights, analysis, comparisons, or recommendations — tables, charts, diagrams, matrices. Make data visual.

### Setup Check

Say to the student:

"Today we close the loop. You're going to set up automatic quality checks and publish your product to a live address anyone can visit. By the end of this lesson, you'll have a link you can text to your mom, share with your boss, or post on LinkedIn."

Confirm the student has their project on GitHub from Lesson 18. If not, help them do that first.

### Step 1: Set Up Automatic Quality Checks

Say to the student:

"I'm going to set up automatic checks that verify your product works correctly every time you make a change. Think of it like a building inspector who checks every room after any renovation — except this inspector works in seconds and never takes a day off."

Analyze their project and create appropriate checks. While working, narrate in plain language:

"I'm writing checks that verify:"
- "Your pages load without errors"
- "Your buttons and links go where they should"
- "Your text and images show up correctly"
- "Nothing looks broken on different screen sizes"

(Customize this list based on what their actual project does.)

Run the checks and show them passing:

"All checks passed! Your product is working correctly. From now on, these run automatically every time you make a change."

Ask the student:

"You now have automatic quality checks. How do you want to proceed?"

- **A)** Show me what happens when a check fails — I want to see the safety net in action
- **B)** Set up the AI reviewer next — I want that automatic proofreader
- **C)** Skip ahead to publishing — I want my product live on the internet

If A, intentionally introduce a small issue (like a broken link), run the checks, show them fail with a clear message, then fix it and show them pass again. This builds trust in the system.

### Step 2: Set Up Automatic Review

Say to the student:

"I can also set up an AI reviewer that reads through every proposed change before it goes live — like having a proofreader that never sleeps and never misses anything."

Set up a Claude Code review action on their GitHub project. Frame it simply:

"Here's what I'm setting up: every time someone proposes a change to your project — whether it's you, a teammate, or even another AI — this reviewer will automatically read through it and flag anything that looks off."

"It checks for things like:"
- "Did this change accidentally break something that was working?"
- "Is the change well-organized and easy to understand?"
- "Are there any obvious problems or improvements to suggest?"

After setup:

"Done! Your project now has an automatic reviewer. Let me show you how it works."

Create a small proposed change and show the review happening:

"See? The reviewer read through the change and gave feedback — just like a teammate would. Except this teammate is available 24/7 and responds in seconds."

Ask the student:

"Your project now has both automatic checks AND an AI reviewer. What's next?"

- **A)** Let's publish! I want my product live on the internet
- **B)** Can I customize what the reviewer looks for?
- **C)** How does this work when I have real teammates proposing changes?

### Step 3: Publish to the Internet

Say to the student:

"Now the big moment — let's get your product live on the internet with a permanent web address."

Determine the best hosting option for their project and set it up. Walk them through any account creation with simple, step-by-step guidance.

After publishing:

"Your product is live! Here's your address: [URL]"

"Go ahead — open that link in your browser. Send it to a friend. That's YOUR product, live on the internet, accessible to anyone in the world."

Give them a moment to appreciate this. Then ask:

"How does it feel to have a live product on the internet?"

- **A)** Amazing! Show me the full automatic cycle
- **B)** Can I get a custom web address instead of this one?
- **C)** Who can see this? I want to understand the access

### Step 4: The Full Loop

Say to the student:

"Now let me show you the complete cycle — this is how real products ship, every day, at every tech company."

Walk them through the entire flow:

1. **Make a change**: "I'm going to update something visible on your product — watch what happens next."
   - Make a small, noticeable change (update a headline, change a color, add a line of text)

2. **Checks run**: "The automatic quality checks are running now — making sure nothing broke."
   - Show the checks passing

3. **Review happens**: "The AI reviewer is reading through the change."
   - Show the review feedback

4. **Product updates**: "And... your live site just updated. Go refresh the page."
   - Have them refresh and see the change live

"That's the full cycle. You change something, automatic checks make sure nothing broke, a reviewer gives feedback, and it goes live. That's how every real product ships — from startups to companies like Google and Apple. And now your product works the same way."

Ask the student:

"You just experienced the professional shipping cycle. What do you want to do?"

- **A)** Move on to Lesson 20 — share this setup with my team and prepare for the course wrap-up
- **B)** Make more changes and watch them auto-publish — this is satisfying
- **C)** Set up a custom web address for my product

### Wrap Up

Say to the student:

"Let's recap what you set up today:"
- "Automatic quality checks that catch problems before your users do"
- "An AI reviewer that proofreads every change"
- "A live product on the internet with automatic publishing"
- "A professional shipping cycle: change → check → review → live"

"You now have the same setup that professional product teams use. The difference? You set it up in one lesson instead of one quarter."

"What's next?"

- **A)** Move on to Lesson 20 — share your setup with your team and wrap up the course
- **B)** Make more changes and watch them auto-publish
- **C)** Set up a custom web address for your product

## Reference Material

Key concepts for Claude to reference when helping the student:

- **Quality checks to create** (based on project type):
  - Page load checks: Does every page render without errors?
  - Link checks: Do all links point to valid destinations?
  - Content checks: Do key elements (headings, buttons, images) appear correctly?
  - Responsiveness checks: Does the product look right on different screen sizes?

- **Claude Code GitHub Action setup**:
  - Create the workflow file in the project's automated actions folder
  - Configure it to run on proposed changes
  - The student doesn't need to see or understand the configuration file — just know it's there and working

- **Hosting options** (choose based on project):
  - **Vercel**: Best for most projects. Free tier. Auto-publishes from GitHub. Custom web addresses supported.
  - **GitHub Pages**: Free, simple. Best for basic informational sites.
  - **Render**: Free tier. Good for projects with behind-the-scenes logic or data storage.
  - **Netlify**: Free tier. Similar to Vercel, good alternative.

- **Custom web address setup**:
  - Purchase through a domain registrar (Namecheap, Google Domains, etc.)
  - Point it to their hosting provider
  - Walk through step by step if the student chooses this option

- **Troubleshooting common issues**:
  - Build failures: Usually a missing file or broken reference. Check the error message and fix.
  - Checks failing: Read the failure message, explain in plain language, fix together.
  - Site not updating: Check that the publishing pipeline is connected to the right project.
