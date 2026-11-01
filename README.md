# Paperzilla

Start the morning with a short research brief from feeds focused on your field. The
included skill combines new papers across your selected projects, removes
duplicates, and explains why each paper matters to your research. Each brief
links to its sources and distinguishes abstract-based judgments from paper-text
analysis.

Connect your Paperzilla account to Claude using https://paperzilla.ai/api/mcp.

## Connect

1. Install this plugin, then open **Settings → Customize → Plugins → Paperzilla → Connectors**
   (choose **Paperzilla beta** for staging).
2. Click the native **Connect** button beside `paperzilla` (or `paperzilla-beta`
   for staging). If Claude shows **Not added**, this is the next step; you do not
   need to create another custom connector or paste a server URL. If Claude asks
   for authentication settings, follow the
   [screen-by-screen setup guide](https://docs.paperzilla.ai/guides/claude#choose-the-authentication-settings).
3. Claude may show **Connect** twice: the first adds the connector. If it now
   shows **Not connected**, click **Connect** again to open Paperzilla sign-in.
   Sign in or create your account, then review and allow the requested
   permissions. Wait for **Connected** before returning to your chat. Adding the
   connector alone does not authorize account access.
4. Return to your chat and say **"Connected, please continue my request."**
   Claude can then make fresh research calls. If you have not asked yet, try the
   morning-brief prompt below.
5. Open **Settings → Customize → Connectors → Paperzilla → Tool permissions** in Claude
   (choose **Paperzilla beta** for staging). Set the read-only tools to
   **Always allow** for all Paperzilla read-only tools. A brief needs several
   lookups, sometimes across multiple feed pages. Repeated approval prompts
   interrupt that work; depending on the task's approval mode, an unattended
   morning brief may wait for you instead of finishing. Keep
   **Prepare paper Markdown** (`paper_markdown_request`) and both feedback tools
   (`feedback_set`, `feedback_clear`) on **Needs approval**; they change state.
   Your organization may restrict these options. Check them again after
   removing and re-adding the connector, which can reset tool approvals.

The plugin includes the `paperzilla-research-brief` skill and connects to
`https://paperzilla.ai/api/mcp`. Reuse an existing connection only when its URL matches exactly.
Production uses `https://paperzilla.ai/api/mcp`; beta uses
`https://beta.paperzilla.ai/api/mcp`. They are separate connections. Keep working
beta connections and their saved tasks when adding production. A new chat does
not reset your installed plugins or account connections.

A Paperzilla account is required. Free accounts can read public digests and
existing catalog papers without a project. Set up a project on the Paperzilla
website to receive a personalized feed.

## Try a morning brief

### Start with a topic

If you are new to Paperzilla, try public research before setting up your own
feed:

> Prepare a short research brief about scientific claim verification from public
> Paperzilla digests. Find a relevant digest and open its latest published issue.
> Pick up to three papers, link each source, and explain why it matters. State the
> issue date and use abstracts. Don't request Markdown generation.

Replace the topic with your own research interest. This uses published public
digests; the issue date may be older than today. If there is no matching digest,
Claude can help you choose a broader topic. Your Paperzilla account is required.

Here is an edited one-paper example from the public
[OCD issue dated 28 October 2026](https://paperzilla.ai/digest/af016642/ocd),
based on the paper's abstract. This illustrates the format, not a live tool run
or today's research:

> **[Young adults with OCD and their experiences of the school-to-work or
> university transition](https://pubmed.ncbi.nlm.nih.gov/42934604/)**, published
> 13 October 2026. Interviews with 21 young adults describe challenges in moving
> into study or work and the support they found helpful.
>
> **Why it matters:** for researchers studying education and employment with OCD,
> it identifies practical support needs to investigate. This qualitative study
> describes experiences; it does not establish that an intervention works.

### Choose your own feeds

If you already have projects, start with:

> Help me choose one or two of my Paperzilla feeds for a morning research brief.
> Show my feed names first. Ask what I am working on if it will help rank papers,
> then make a one-off preview before scheduling anything.

If you know which feeds you want, name them directly:

> Prepare a morning brief from my Scientific Claim Extraction and Agentic Cyber
> Defense feeds. Use papers added in the last 24 hours, with dates in
> Europe/Athens. Pick up to five papers total, merge duplicates, and explain why
> each matters with a link. Use abstracts and don't request Markdown generation.

Replace those feed names with your own. A brief includes the papers' source
links, their contributions, why they fit your interests, and which feeds were
checked. A quiet feed can have no new papers in the requested window.

### Make it a daily brief

After reviewing the preview, specify your preferred time, timezone, feeds and
whether you want a note when there is nothing new. Scheduling depends on the
Claude app and tools available in your session. The skill confirms a schedule
only after the host actually saves it; Paperzilla supplies research data and
does not run schedules.
Check the saved task's connector and permission settings and try **Run now**
before relying on daily delivery, then inspect an actual scheduled run. Use the
read-only **Always allow** setup above to reduce approval interruptions.
OAuth consent, tool approvals and the task's approval mode are separate;
allowing reads does not itself create or verify a schedule.

You can also find public digests, search a project feed, and read prepared paper
Markdown. Preparing missing Markdown requires an explicit request and can take
time. This integration uses papers already in Paperzilla. Project creation and
editing happen on the Paperzilla website.

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
