---
type: guide
conference: AI Coding Summit + JSNation + React Summit 2026
tags:
  - conference
  - plain-language
  - webmcp
  - accessibility
---
# WebMCP explained

WebMCP was my favorite idea from the conference, and it's the one most likely to land on a web specialist's desk first. This page explains it without code. The technical details are in [the Wes Bos talk](Talks/01%20-%20Letting%20AI%20Assistants%20Use%20Your%20Website.md) and [the Navya Agarwal talk](Talks/09%20-%20AI%20Features%20That%20Run%20Inside%20the%20Page.md).

The design and SEO angles below are my own. Neither speaker talked about SEO, so treat those parts as ideas, not findings.

## What it is

Right now, when an AI assistant uses a website for someone, it mostly guesses. It takes screenshots and clicks where buttons seem to be, or it reads the page's structure and hopes the labels make sense. Wes Bos called this slow and expensive, and it breaks when the layout changes.

[WebMCP](Glossary.md#webmcp) lets a website hand the assistant a menu of what it can do. Each item on the menu is called a tool. A store might offer "search products," "filter by size" and "add to cart." A tool has a name, a plain-English description and a list of what it needs, like a size and a color. The assistant reads the menu and calls the tool instead of clicking around.

The tools run inside the page the person already has open, signed in as that person. The assistant and the person can work in the same tab at the same time. Wes called it "cheaper, faster, and less flaky."

## Where it stands

- **It's experimental.** It's a proposed web standard. Chrome and Edge are testing it. Safari and Firefox don't support it.
- **It has already changed once.** An earlier version let you add tools with plain HTML attributes. That version was removed. Navya Agarwal's advice was to keep any WebMCP work easy to swap out, because the details will keep moving.
- **Nobody has solved permissions yet.** Asked about banking, Wes said "I don't think anybody knows the answer to this type of stuff yet," and "some people are going to get pwned."

So nobody should ship this to real users today. It's worth understanding now, because the design decisions it raises are design decisions, not just engineering ones.

## Three labels every tool can carry

Each tool can be labeled so the assistant knows how careful to be.

- **Read-only.** It only looks things up, like "search products." Safe to call as often as needed.
- **Consequential.** It does something real, like buying, deleting or submitting. The person should approve it in the moment.
- **Untrusted content.** What it returns includes text from outsiders, like product reviews or comments. That text could hide instructions aimed at the assistant, which is called [prompt injection](Glossary.md#prompt-injection).

Wes was clear that these labels are "not a security layer." They tell the assistant how to behave. The server still has to check every request.

## Why designers should care

These are my suggestions.

- **Tool names and descriptions are interface copy.** The assistant decides which tool to use by reading its description. A vague description leads to the wrong tool, the same way a vague button label leads to the wrong click. Writing them is a UX writing job.
- **The approval moment needs designing.** Every consequential tool needs a moment where the person says yes or no. What does that look like? What does it show? How does someone using a screen reader hear it? Nobody has a standard answer yet.
- **The tools and the buttons should match.** A tool should do exactly what the visible button does. If they drift apart, assistants and people end up using two different apps. Ask that every tool maps to something a person can also do on screen.
- **Flows become menus.** A five-step checkout might become two or three tools. Mapping which steps a person must see and which an assistant can do quietly is a flow-design question.

## Why SEO people should care

Again, my ideas, not the speakers'.

- **It's a new kind of visitor.** Search engines read your pages. AI assistants are starting to act on them. Structured data told search engines what a page is about. WebMCP tells assistants what a page can do. If assistants start choosing which site to use for a task, the sites with clear tools may get picked.
- **Descriptions are the new snippets.** A tool's description decides whether an assistant uses it, much as a meta description affects whether a person clicks. Clear, specific, honest descriptions will matter.
- **Don't trade content for tools.** People and search engines still read the page. A site that pours effort into tools while its pages get thinner loses on both counts.

Watch this space more than act on it. There's no evidence yet that assistants rank or prefer sites with tools.

## WebMCP and accessibility

This is the part I care most about, and it needs care.

WebMCP isn't an accessibility standard and doesn't replace one. [Section 508 and WCAG](Glossary.md#section-508-and-wcag) still apply to every screen. A page with great tools that traps keyboard focus in a pop-up still fails the people who rely on the keyboard.

In the discussion room on day 2, one participant asked whether WebMCP could fold into accessibility work, then argued against it. What agents need and what people need "are going to diverge," and one spec for both could put agents ahead of people. ([discussion room](Talks/12%20-%20Discussion%20Room%20-%20Setting%20Agents%20Up%20to%20Succeed.md))

With that in mind, I see two roles for it. Neither replaces an accessible page.

1. **Another way in.** Someone using voice control, a switch device or a screen reader could ask their own assistant to "find my last order" instead of working through a long table. Wes's examples included smart glasses, where there's no mouse or screen to work from. This only helps people who have an assistant that supports WebMCP, so for now it's an extra.
2. **A better way to test accessibility.** Tools can put a site into any state on purpose, such as opening a specific pop-up, reaching step 4 of a form or applying a filter. An accessibility check can then run on the real page in that state. That reaches screens a person testing by hand might never get to. This is the use I'm most confident pays off soon.

The rule I'd keep is that tools help reach a state, and the checks still look at the human-facing page. The assistant's path never decides whether a person can use the site.

## What you can do now

- **Learn the vocabulary.** Tools, descriptions, read-only, consequential, untrusted content. That's enough to join the conversation.
- **When your team experiments, ask to write the tool descriptions.** Treat them like button labels and test them the same way.
- **Push for accessibility first.** If someone proposes WebMCP as an accessibility fix, point to the discussion room's worry. The page has to work for people on its own.
- **Ask about testing.** "Could we use tools to reach every state of this flow and run accessibility checks on each one?" is a good question to bring to engineers.
- **Don't ship it to users yet.** Permissions are unsolved and the standard is still changing.

## Words worth knowing

- **Tool.** One action a page offers to an assistant, with a name, a description and the information it needs.
- **[MCP](Glossary.md#mcp).** The older standard for plugging tools into AI assistants. WebMCP is the version that lives in a web page.
- **[Accessibility tree](Glossary.md#accessibility-tree).** The page structure screen readers use. Some assistants read it today when there are no tools.
- **Origin trial.** A browser's way of letting sites test an unfinished feature for a limited time.
