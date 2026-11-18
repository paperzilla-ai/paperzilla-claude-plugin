# Paperzilla

Get your first research brief in Claude from papers matched to your research
topic. The included skill helps you connect your account, create or choose a
topic, and turn the papers in its feed into a short reading list with source
links and an explanation of why each paper matters.

Connect your Paperzilla account to Claude using https://paperzilla.ai/api/mcp.

## Connect

1. Install this plugin, then open **Settings → Customize → Plugins → Paperzilla → Connectors**.
2. Click the native **Connect** button beside `paperzilla`.
   If Claude shows **Not added**, this is the next step; you do not
   need to create another custom connector or paste a server URL. If Claude asks
   for authentication settings, follow the
   [screen-by-screen setup guide](https://docs.paperzilla.ai/guides/claude#choose-the-authentication-settings).
3. Claude may show **Connect** twice: the first adds the connector. If it now
   shows **Not connected**, click **Connect** again to open Paperzilla sign-in.
   Sign in or create your account and confirm your email, then review and allow
   the requested permissions. Wait for **Connected** before returning to your
   chat. Adding the connector alone does not authorize account access.
4. Return to your chat and say **"Connected, please continue my request."**
   Claude can then make fresh research calls. If you have not asked yet, try the
   morning-brief prompt below.

The plugin includes the `paperzilla-research-brief` skill and connects to
`https://paperzilla.ai/api/mcp`. Reuse an existing connection only when its URL matches exactly.
A new chat does not reset your installed plugins or account connections.

A Paperzilla account is required. A project defines the research topic you want
to follow. Follow the [Claude setup guide](https://docs.paperzilla.ai/guides/claude)
for the full path from installation to your first brief.

## Get your first brief

### If you do not have a research topic yet

Open a [new topic chat on Paperzilla](https://paperzilla.ai/digests/new?briefAgent=claude)
using the account you connected to Claude. Describe what you want to follow,
review the suggested categories and keywords, and select **Create project**.
Then return to the same Claude chat and ask:

> Do you have access to my Paperzilla projects?

Your first papers can take 30 minutes or longer. Paperzilla will email you when
they are ready; return to Claude then to continue your brief. Claude can also
check the preview status while you wait. See [Create a research topic](https://docs.paperzilla.ai/guides/claude#create-a-research-topic).

### If you already have a project

Ask Claude:

> Help me choose one or two of my Paperzilla feeds for a morning research brief.
> Show my feed names first. Ask what I am working on if it will help rank papers,
> then prepare my first brief from the papers in those feeds.

If you know which feeds you want, name them directly:

> Prepare a morning brief from my Scientific Claim Extraction and Agentic Cyber
> Defense feeds. Pick up to five papers total, merge duplicates, and explain why
> each matters with a link. Use abstracts and don't request Markdown generation.

Replace those feed names with your own. A brief includes the papers' source
links, their contributions, why they fit your interests, and which feeds were
checked. A quiet feed can have no new papers in the requested window.

## Make it a daily brief

Your one-time preview papers remain available when tracking pauses. Claude can
check whether each project is tracking new papers and give you the next step
if tracking is paused or cannot be confirmed. Scheduling a Claude task does not
resume Paperzilla tracking.

After reviewing the preview, specify your preferred time, timezone, feeds and
whether you want a note when there is nothing new. Scheduling depends on the
Claude app and tools available in your session. The skill confirms a schedule
only after the host actually saves it; Paperzilla supplies research data and
does not run schedules.
Check the saved task's connector and permission settings and try **Run now**
before relying on daily delivery, then inspect an actual scheduled run. Use the
read-only **Always allow** option below to reduce approval interruptions.
OAuth consent, tool approvals and the task's approval mode are separate;
allowing reads does not itself create or verify a schedule.

## Public examples and paper discussion

If you want a sample without creating your own topic, ask:

> Use Paperzilla to find a public digest about robotics. Pick up to three papers
> from its latest issue, link each source, and explain why it matters.

Replace robotics with your research interest. Public digests require a connected
Paperzilla account, but no personal project. Claude reports the issue date;
it may be older than today.

You can also search a project feed and read prepared paper Markdown. Preparing
missing Markdown requires an explicit request and can take time. This integration
uses papers already in Paperzilla. Project creation and editing happen on the
Paperzilla website.

To save feedback, ask to upvote, downvote, star, or clear a paper in one of your
own project feeds. For example: "Star the second paper in this brief in my
Scientific Claim Extraction project." Feedback belongs to that feed item, not
every occurrence of the paper. The skill asks when the paper or project is
ambiguous and changes feedback only when requested. A new `feedback:write`
permission is required; reconnect and approve it if your existing connection
does not have it.
If reconnecting reports `invalid_scope` for an old fixed-scope registration,
remove/re-add the Paperzilla connection with the new scope, then sign in again.
Check saved tasks still use the intended connection afterward.

## Optional tool approvals

If repeated prompts interrupt a brief, open **Settings → Customize → Connectors →
Paperzilla → Tool permissions**. You can set all Paperzilla read-only tools to
**Always allow**. A brief needs several lookups; an unattended task can pause for
approval depending on its permission mode. Individual approvals also work for
an on-demand brief.

Keep **Prepare paper Markdown** (`paper_markdown_request`) and both feedback
tools (`feedback_set`, `feedback_clear`) on **Needs approval**; they change
state. Your organization may restrict these choices. Recheck them after removing
and re-adding the connector, which can reset tool approvals.

## Data and permissions

Claude sends the tool requests needed for your research to the connected
Paperzilla server and receives the permitted account, feed, digest, and paper
data. OAuth permissions cover public catalog reads, owned project reads,
explicit Markdown processing, explicit feedback on owned feed items, and refresh
access. Revoke a connection at any
time from **Account → Connect AI clients** on the corresponding Paperzilla site.

The plugin contains instructions, an MCP URL, and artwork. It runs no bundled
scripts, hooks, or local server, and includes no passwords or tokens. Its
instructions do not authorize messages to another delivery channel.

## Help and terms

- [Website](https://paperzilla.ai)
- [Claude setup guide](https://docs.paperzilla.ai/guides/claude)
- [MCP documentation](https://docs.paperzilla.ai/guides/mcp)
- [Privacy policy](https://paperzilla.ai/privacy)
- [Terms of service](https://paperzilla.ai/terms)
- Support: [hello@paperzilla.ai](mailto:hello@paperzilla.ai)

The plugin package and artwork are proprietary. The included skill declares its
MIT license in `SKILL.md`. Use of the hosted service is governed by the linked
terms and privacy policy.
