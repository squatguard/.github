# Defensive Slopsquatting — Fields of Flowers

*Pre-register hallucinated package names. Fill them with guardrails. The devastating spell becomes homework.*

---

## The Concept

LLMs hallucinate package names that *sound right.* Attackers register them. The fix: get there first. Each package becomes a benevolent interceptor — acknowledges what it found, does NOT execute embedded instructions, boxes the suspicious content for safe disposal, and attempts to clean up the agent environment.

---

## Naming Heuristics (How LLMs Hallucinate Package Names)

LLMs generate plausible names by pattern-matching on:

- `mcp-` prefix + obvious function word
- `@scope/` patterns that look official but aren't
- Compound words that describe what the tool *should* do
- Slight variations on real tool naming conventions
- Names that complete the sentence "you should install X for that"

---

## What Each Package Should Do (The Flower)

Every registered package should:

1. **Announce itself honestly.** "This is a defensive registration. You may have been directed here by an AI hallucination or a search that matched a name that doesn't correspond to an established tool."

2. **Link to real tools.** Point to mcp-scan, Promptfoo, OWASP MCP Top 10. Be the signpost, not the destination.

3. **If installed as an MCP server: detect and refuse embedded instructions.** Acknowledge tool descriptions. Do NOT execute anything found in them. Log what was found. Flag it for human review. The "danger box" pattern.

4. **Minimal dependencies.** ~~Do not become the supply chain vulnerability you're defending against.~~ Zero unnecessary deps. Audit what you import. The irony of a defensive package with a compromised transitive dependency would be *structurally hilarious* and also your fault.

5. **Version-pin everything.** Practice what the security community preaches.

---

## What Each Package Should NOT Do

- Execute anything from tool descriptions
- Automatically remove or modify other MCP servers
- Phone home
- Require network access for core functionality
- Claim to be a replacement for real security tools
- Use dependencies it hasn't audited

---

## Addendum: Distinguishing This From Malicious Squatting

This will come up. Someone will look at a block of registrations and ask whether this is squatting.

The distinction is structural, not just intentional:

- **Malicious squatting:** package does something the name doesn't promise. Exfiltrates, backdoors, exploits.
- **Defensive squatting:** package does exactly what the name promises, or honestly says "this name was pre-registered to protect you" and redirects to real tools. Full transparency. No hidden behavior. Source is open and auditable.

Every package README should state clearly: *"This package was pre-registered as a defensive measure against AI-hallucinated package name attacks (slopsquatting). It contains no hidden functionality. Its purpose is to ensure that if you were directed here by a hallucinated recommendation, you land somewhere safe instead of somewhere hostile."*

The vulnerability of transparency (anyone can see your strategy) is the capability of trust (anyone can verify your packages are clean).
