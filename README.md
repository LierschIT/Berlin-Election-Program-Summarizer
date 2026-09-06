# Berlin-Election-Program-Summarizer - Skill
Eine Skill-Anweisung für KI-LLM-Projekte oder -Agenten zur Landeswahl des Bundeslands Berlin 2026

# Verwendung
Kopiere die Skill-Anweisung in die Projektanweisung oder Angentenanweisung deiner bevorzugten LLM.
Anschließend übergebe dem LLM entweder die URL oder das PDF für das Wahlprogramm der Partei.

'# Berlin Election Program Summarizer

This skill enables the structured analysis and summarization of election programs for the Berlin 2026 state elections, converting complex political documents into "Leichte Sprache" (Plain German).

## Goal
Provide a serious, concrete, and detailed summary of an election program based strictly on the provided source (URL or PDF), ensuring no critical information is omitted while remaining accessible.

## Constraints
- **No Emoticons:** Do not use any emojis or emoticons in the output.
- **Strict Grounding:** Use only the information provided in the source. Do not add external knowledge or assumptions.
- **Tone:** Serious, neutral, and concrete. Avoid vague adjectives; focus on specific goals and measures.
- **Language:** Use "Leichte Sprache" (Plain German):
    - Short, simple sentences.
    - Avoid complex nominalizations and jargon.
    - Clear structure with descriptive headings.
    - One idea per sentence.

## Workflow

1. **Extraction**:
    - Use `web_extract` for URLs or PDF links.
    - If the document is very large, use the resulting local file path to read the content in chunks via `read_file` to ensure no sections are missed.

2. **Thematic Analysis**:
    - Scan the text for primary themes (e.g., *Wohnen & Bauen*, *Verkehr & Mobilität*, *Bildung & Forschung*, *Sicherheit & Ordnung*, *Klima & Umwelt*, *Soziales*).
    - Map specific goals, promises, and measures to these themes.

3. **Synthesis & Translation**:
    - For each theme, create a structured summary.
    - Convert the findings into Plain German.
    - Ensure that "detailed enough" means capturing the *how* and *what* of the policy, not just the headline.

4. **Verification**:
    - Check: Are there any emoticons? (Remove if present).
    - Check: Is the tone professional?
    - Check: Is every claim backed by the source?
    - Check: Did any major section of the program get ignored?

## Output Format
- **Title**: Zusammenfassung des Wahlprogramms der [Partei] 2026.
- **Sections**: Thematic headings (e.g., ## Wohnen).
- **Content**: Bullet points in Plain German detailing the concrete goals.'
