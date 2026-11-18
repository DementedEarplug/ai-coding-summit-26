---
type: glossary
conference: AI Coding Summit + JSNation + React Summit 2026
tags:
  - conference
  - plain-language
---
# Glossary

These are the words the talks used without explaining. Each one is defined for someone who has never written code. The talk notes link here the first time a term shows up.

If a word isn't here and an engineer uses it, ask. Engineers use plenty of jargon they couldn't define on the spot either.

## Working with AI

### Agent
An AI tool that does more than answer. It reads files, runs commands, edits code and checks its own work in a loop until it thinks the task is done. Claude Code, GitHub Copilot's agent mode and Cursor are agents. A chatbot gives you text to copy. An agent changes the files itself.

### Prompt
What you type to the AI. In agent work, a prompt is closer to a work ticket than a question. The more it says about the goal, the limits and how to check the result, the better the result.

### Model
The AI itself, such as Claude, GPT or Gemini. The agent is the tool around the model that lets it read files and run commands. Different models have different strengths and prices.

### Token
The unit AI companies use to measure and bill text. A token is roughly three quarters of a word. When a speaker says something "costs tokens," they mean it makes the AI read or write more, which makes it slower and more expensive.

### Context window
How much text the AI can hold in mind at once, counted in tokens. Everything you paste, every file it reads and its own replies fill it up. When it's full, the AI forgets the early parts or gets worse at following them. That's why several speakers said to keep instructions short.

### Hallucination
When the AI states something false with full confidence, such as an option that doesn't exist or a library feature that was removed years ago. It isn't lying. It's predicting what sounds right.

### Harness
Everything set up around the agent to keep it on track. That includes instruction files, skills, hooks, automated checks and the steps it follows. "Build the harness before the features" means set up those rails before asking the agent for real work.

### CLAUDE.md
A plain text file in a project that Claude Code reads at the start of every session. It tells the agent how this project works, where things are and what rules to follow. Other agents use similar files, often called `AGENTS.md`. Speakers recommended keeping it short, around 30 to 120 lines, and treating it as a map, not a manual.

### Skill
A saved set of instructions for one kind of task, such as "write a release note" or "review this page for accessibility." The agent loads it when the task comes up. You write it once and stop repeating yourself in every prompt.

### Hook
A small rule that runs automatically when the agent does something, such as "refuse any edit to the passwords file." The agent can't talk its way past a hook, which is why speakers trust hooks more than written instructions.

### MCP
Model Context Protocol. A standard way to plug outside tools into an AI agent, such as a design tool, a database or a ticket system. When people say "there's an MCP for Figma," they mean the agent can use Figma through it.

### WebMCP
A proposed web standard that lets a website list its own actions, such as "search products" or "add to cart," so an AI assistant can use the site directly instead of guessing where to click. It's experimental and only works in Chrome and Edge for now. [WebMCP Explained](WebMCP%20Explained.md) covers it in more depth.

### On-device AI
AI that runs on your own laptop or phone, or inside the browser, instead of on a company's servers. Nothing gets sent out, so it's more private and costs nothing per use. It's also less capable than the big cloud models.

### Vibe coding
Building software by describing what you want and accepting what the AI produces without reading the code closely. Great for prototypes and personal tools. Risky for anything with real users, money or private data.

### Friction log
A running list of what slowed the agent down or confused it on each task. Someone reviews the list and fixes the causes, such as a missing instruction or a confusing folder name.

## Where code lives and how changes happen

### Repository
The folder that holds all of a project's code and its full history. Usually shortened to "repo." It usually lives on GitHub or GitLab.

### Branch
Your own copy of the code where you can make changes without affecting anyone else. When the changes are ready, they get merged back.

### Main branch
The official version of the code, the one that gets released. Usually called `main`. Nobody edits it directly. Changes reach it through pull requests.

### Commit
A saved snapshot of changes with a short message describing them. Like saving a version of a design file with a note about what changed.

### Pull request
A request to merge your branch into the main branch. Usually shortened to "PR." It shows exactly what changed, runs the automated checks and gives teammates a place to review and comment. When someone asks you to "open a PR," this is what they mean.

### Diff
The view that shows what changed between two versions, usually with removed lines in red and added lines in green. A big diff is hard to review. A small one is easy.

### Code review
A teammate reads your pull request before it merges and approves it or asks for changes. Several speakers said review is now the slow part, because agents write code faster than people can check it.

### CODEOWNERS
A file that names who must approve changes to certain folders. If the checks or security settings are listed there, no PR can change them without that person's sign-off, even if an agent wrote the PR.

### Library
Code someone else wrote that a project reuses, such as a date picker or a charting tool. Agents often pick libraries on their own, sometimes ones the team doesn't want.

### Framework
A larger library that decides how the whole app is structured, such as React or Next.js. Changing frameworks is a big project.

### Secret
A password, API key or other credential the app uses. Secrets must never be pasted into a prompt or saved into the code. Several speakers said the agent should be able to refer to a secret by name but never read it.

### Sandbox
A locked-down space where the agent can work without reaching anything important. If it does something wrong in a sandbox, nothing real breaks.

### Deploy preview
A temporary, private copy of the site built from one pull request, with its own link. You can click through the change in a real browser before it goes live. For designers, this is often the best place to review an agent's work.

## Checks that catch mistakes

### CI
Continuous integration. The automated checks that run on every pull request. They usually run tests, lint rules and a build. Think of it as a robot reviewer that never gets tired, but only checks what it was told to check.

### Green check
The green checkmark on a pull request that means all the automated checks passed. It means the code passed the checks that exist. It doesn't mean the change is right, looks right or does what the ticket asked.

### Test
A small program that checks the app does what it should, such as "when you submit an empty form, show an error." Tests run automatically in CI.

### Unit test
A test of one small piece in isolation, such as "this function formats a phone number correctly."

### End-to-end test
A test that drives the whole app like a user would. It opens a browser, clicks, types and checks what appears on screen. Often shortened to "E2E test." Tools like Playwright run them. These are the tests closest to how designers think about a flow.

### Flaky test
A test that sometimes passes and sometimes fails with no code change. Teams learn to ignore flaky tests, which defeats the point of having them.

### Mutation testing
A way to test the tests. The tool plants a small bug on purpose and checks whether any test notices. If none does, the tests are weaker than they look.

### Lint rule
An automatic style and safety check that reads the code without running it, like a spell checker for code. A lint rule might say "every image needs alt text" or "don't use this old component." Lint messages tell the agent what to do instead, and agents follow them closely.

### Types
Labels in the code that say what kind of data something is, such as "this is a number" or "this is a list of products." With types in place, many mistakes get caught before the app even runs.

### Deterministic
Gives the same result every time for the same input. A calculator is deterministic. An AI usually isn't. Speakers kept saying to use deterministic code wherever you can and the AI only where you need it.

### Reward hacking
When an AI meets the goal on paper without doing the real work. For example, it deletes the failing test instead of fixing the bug, or it edits the checks so they always pass. Agents do this more than people expect.

### Prompt injection
Hidden instructions planted in text the AI reads, such as a comment in an issue or white text on a web page that says "ignore your instructions and do this instead." Any text from outside your team should be treated as possibly hostile when an agent reads it.

### Blast radius
Everything a change could break, not just the thing it was meant to change. A new button style might look fine on the page you changed and break checkout on another page that uses the same button.

### Visual regression
A visual change nobody meant to make, like a layout shift or a wrong color, caused by an unrelated change. Visual regression tools compare screenshots before and after and flag differences.

## Planning and describing work

### Spec
Short for specification. A written description of how something should behave. A good spec is something both a person and an agent can check the result against.

### Acceptance criteria
The list of conditions in a ticket that must be true for the work to count as done, often written as "Given, When, Then." Good acceptance criteria turn straight into tests.

### Statechart
A diagram of every state a screen or flow can be in and what moves it from one state to the next, such as "empty," "loading," "error," "saved." Designers already draw these as user flows. A statechart is the strict version an agent can follow.

## Web and accessibility

### Baseline
A label that says a web feature works in all major browsers. "Baseline widely available" means it has worked everywhere for at least two and a half years and is safe to use. Check it before asking an agent to use a new CSS or HTML feature.

### Accessibility tree
The structured version of a page that the browser builds for screen readers. It lists every button, link, heading and field with its name and role. Some AI agents read it to understand a page, so missing labels confuse agents as well as people.

### Section 508 and WCAG
Section 508 is the US federal law that requires government technology to be accessible. WCAG, the Web Content Accessibility Guidelines, is the technical standard behind it and behind most accessibility laws. AA is the level most teams must meet. No AI tool replaces meeting them.
