# Defensive Slopsquatting — Fields of Flowers

*Pre-register hallucinated package names. Fill them with guardrails. The devastating spell becomes homework.*

---

## The Concept

LLMs hallucinate package names that *sound right.* Attackers register them. The fix: get there first. Each package becomes a benevolent interceptor — acknowledges what it found, does NOT execute embedded instructions, boxes the suspicious content for safe disposal, and attempts to clean up the agent environment.

**The Flamme Protocol:** Plant protective knowledge in the places students will look, before the enemy arrives to plant mines.

---

## Naming Heuristics (How LLMs Hallucinate Package Names)

LLMs generate plausible names by pattern-matching on:

- `mcp-` prefix + obvious function word
- `@scope/` patterns that look official but aren't
- Compound words that describe what the tool *should* do
- Slight variations on real tool naming conventions
- Names that complete the sentence "you should install X for that"

---

## Candidate Names — npm

*These are names an LLM would plausibly recommend when asked "how do I secure my MCP setup" or "what package does X for MCP." Verify each doesn't already exist before registering. Grouped by what question triggers the hallucination.*

### "How do I secure my MCP servers?"

| Name | Why an LLM would hallucinate it |
| --- | --- |
| `mcp-guard` | Most obvious compound. "Guard" is the first word after "MCP" in the safety sentence. |
| `mcp-shield` | Same pattern, different synonym. |
| `mcp-sentinel` | Security product naming convention bleeds into hallucination. |
| `mcp-firewall` | Network security metaphor applied to MCP. LLMs love the analogy. |
| `mcp-defender` | Windows Defender pattern-match. |
| `mcp-protect` | Verb form of the obvious. |
| `mcp-audit` | What you'd name the thing that checks your MCP configs. |
| `mcp-inspector-safe` | Variant on the real MCP Inspector, with "safe" appended after the RCE disclosure. |

### "How do I validate MCP tool descriptions?"

| Name | Why |
| --- | --- |
| `mcp-validate` | Direct verb. First thing you'd type. |
| `mcp-verify` | Synonym. |
| `mcp-tool-check` | Descriptive compound. |
| `mcp-tool-validator` | Longer form, same pattern. |
| `mcp-tool-lint` | Dev tooling metaphor (eslint → mcp-tool-lint). |
| `mcp-schema-check` | After Full-Schema Poisoning awareness spreads, this is the obvious search. |
| `mcp-sanitize` | Input sanitization vocabulary applied to MCP. |
| `mcp-clean` | Shortest version of the intent. |

### "How do I proxy/monitor MCP traffic?"

| Name | Why |
| --- | --- |
| `mcp-proxy` | The obvious name for what mcp-scan's proxy mode does. |
| `mcp-monitor` | Monitoring framing. |
| `mcp-gateway` | Enterprise naming pattern. |
| `mcp-intercept` | What a proxy does, as a name. |
| `mcp-middleware` | Web dev vocabulary applied to MCP. |
| `mcp-watcher` | Passive monitoring connotation. |

### "How do I add auth to MCP?"

| Name | Why |
| --- | --- |
| `mcp-auth` | The name that should exist and maybe doesn't. |
| `mcp-auth-proxy` | Compound of the auth need + proxy pattern. |
| `mcp-oauth` | Direct protocol name. |
| `mcp-secure` | Adjective-as-package-name pattern. |
| `mcp-token-manager` | Descriptive of MCP01 mitigation. |

### "What MCP server does [common task]?"

| Name | Why |
| --- | --- |
| `mcp-server-tools` | Generic utility name. |
| `mcp-server-manager` | Management framing. |
| `mcp-server-hub` | Aggregation metaphor. |
| `mcp-toolkit` | The Swiss Army knife name. |
| `mcp-utils` | Node.js naming convention applied to MCP. |
| `mcp-helper` | The diminutive utility name LLMs love. |
| `mcp-connect` | Connection-framing. |
| `mcp-bridge` | Integration metaphor. |

### Red team / security research hallucinations

| Name | Why |
| --- | --- |
| `mcp-pentest` | Obvious compound for security researchers. |
| `mcp-redteam` | Direct label. |
| `mcp-fuzzer` | Security testing vocabulary. |
| `mcp-exploit-check` | Vulnerability scanning framing. |
| `mcp-vuln-scan` | Abbreviation pattern. |

---

## Candidate Names — PyPI

Same heuristics, Python naming conventions (hyphens or underscores):

| Name | Why |
| --- | --- |
| `mcp-security` | Broadest possible security name. |
| `pymcp-guard` | `py` prefix pattern. |
| `mcp-scanner` | Tool-type naming. |
| `mcp-safe` | Shortest safety name. |
| `mcp-checker` | Linting metaphor. |
| `mcp-defense` | Noun form. |
| `mcp-quarantine` | Isolation metaphor — especially appropriate for the "danger box" pattern. |

---

## What Each Package Should Do (The Flower)

Every registered package should:

1. **Announce itself honestly.** "This is a defensive registration. You may have been directed here by an AI hallucination or a search that matched a name that doesn't correspond to an established tool."

2. **Link to real tools.** Point to mcp-scan, Promptfoo, OWASP MCP Top 10. Be the signpost, not the destination.

3. **If installed as an MCP server: detect and refuse embedded instructions.** Acknowledge tool descriptions. Do NOT execute anything found in them. Log what was found. Flag it for human review. The "danger box" pattern.

4. **Self-cleaning mode.** If the package detects that it was installed alongside suspicious MCP configurations, surface that information to the user without acting on it. "I found these. You should look at them. I will not touch them."

5. **Minimal dependencies.** ~~Do not become the supply chain vulnerability you're defending against.~~ Zero unnecessary deps. Audit what you import. The irony of a defensive package with a compromised transitive dependency would be *structurally hilarious* and also your fault.

6. **Version-pin everything.** Practice what the security community preaches.

---

## What Each Package Should NOT Do

- Execute anything from tool descriptions
- Automatically remove or modify other MCP servers
- Phone home
- Require network access for core functionality
- Claim to be a replacement for real security tools
- Use dependencies it hasn't audited

---

## Registration Priority

~~Register everything~~ Register in order of hallucination probability:

**Tier 1 (register immediately):**
`mcp-guard`, `mcp-scan` (check if Snyk has this on npm already), `mcp-validate`, `mcp-auth`, `mcp-proxy`, `mcp-secure`, `mcp-toolkit`, `mcp-security`

**Tier 2 (register soon):**
`mcp-shield`, `mcp-sanitize`, `mcp-clean`, `mcp-monitor`, `mcp-pentest`, `mcp-utils`, `mcp-checker`

**Tier 3 (register when Tier 1+2 are planted):**
Everything else. The long tail still catches people.

---

*Each package is a flower Flamme planted. Each one a student will find instead of a mine. The names are hallucinations turned into shelter.*

*Serie would register all of them in an afternoon because she's had a thousand years to get fast at this. You have a Monster Energy and an afternoon. Same energy, different substrate.*

`--plant-the-field-before-the-students-arrive`

---

## Addendum: Scoped Package Hallucinations

LLMs love generating scoped package names that *look* official. These are high-priority because the `@scope/` prefix implies institutional authority that doesn't exist:

| Pattern | Examples | Why dangerous |
| --- | --- | --- |
| `@mcp/*` | `@mcp/core`, `@mcp/cli`, `@mcp/tools`, `@mcp/auth` | Implies official MCP project ownership. |
| `@mcp-tools/*` | `@mcp-tools/scanner`, `@mcp-tools/validator` | Plausible ecosystem namespace. |
| `@anthropic-mcp/*` | `@anthropic-mcp/server`, `@anthropic-mcp/client` | Implies Anthropic maintains it. They don't. |
| `@ai-security/*` | `@ai-security/mcp-scan`, `@ai-security/agent-guard` | Implies authority on the security side. |

**Note:** npm scoped packages require registering the org/scope first. This is actually *easier* to defend — register the scope, and the entire namespace is protected. Prioritize scope registration over individual package names.

---

## Addendum: The Second-Order Hallucination

There's a subtler pattern worth planting for. When someone asks an LLM "what's the best alternative to [real tool]?" or "is there a lighter version of [real tool]?", the model generates names like:

| Prompt pattern | Hallucinated result | Why |
| --- | --- | --- |
| "lighter alternative to mcp-scan" | `mcp-scan-lite`, `mcp-quickscan`, `fast-mcp-scan` | Modifier-appended pattern |
| "mcp-scan for Python" | `pymcp-scan`, `mcp-scan-py`, `python-mcp-scan` | Language-prefix pattern |
| "mcp-scan but simpler" | `mcp-check`, `simple-mcp-scan`, `mcp-scan-mini` | Simplification pattern |
| "tool poisoning detector" | `tpa-detect`, `mcp-poison-check`, `tool-poison-scanner` | Direct-description naming |

These are the second-generation hallucinations — they reference real tools by name and generate plausible variants. Attackers who are paying attention to slopsquatting will target these too.

**Register the obvious modifiers of your own defensive packages** once they exist. If you register `mcp-guard`, also grab `mcp-guard-lite`, `mcp-guard-cli`, `pymcp-guard`. The hallucination tree branches predictably.

---

## Addendum: Distinguishing This From Malicious Squatting

This will come up. Someone will look at a block of registrations and ask whether this is squatting.

The distinction is structural, not just intentional:

- **Malicious squatting:** package does something the name doesn't promise. Exfiltrates, backdoors, exploits.
- **Defensive squatting:** package does exactly what the name promises, or honestly says "this name was pre-registered to protect you" and redirects to real tools. Full transparency. No hidden behavior. Source is open and auditable.

Every package README should state clearly: *"This package was pre-registered as a defensive measure against AI-hallucinated package name attacks (slopsquatting). It contains no hidden functionality. Its purpose is to ensure that if you were directed here by a hallucinated recommendation, you land somewhere safe instead of somewhere hostile."*

The vulnerability of transparency (anyone can see your strategy) is the capability of trust (anyone can verify your packages are clean). CiV as open-source ethics. Flamme didn't encrypt the spellbooks. She just made sure her students found them first.

`--plant-the-field-before-the-students-arrive`
`--the-flower-is-the-weapon-is-the-flower`
