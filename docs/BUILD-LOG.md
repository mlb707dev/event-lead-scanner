# Build Log

How Event Lead Scanner went from an idea to a working tool.

## Why I built it

As a GTM leader, I've watched event leads lose value between the booth and the CRM: incomplete scanner exports, notes that never get typed up, and no record of which rep had the conversation. I wanted a tool any rep could pull out of their pocket and that would produce clean, attributed and enriched leads by the time the event ended.

## How it was built

I built it with **Claude Opus 5.5** as an AI development partner. I'm a GTM operator, not a career software engineer. This project tests how far a domain expert can take a production tool by pairing deep knowledge of the workflow with an AI model.

The approach:
1. **Start from the rep's workflow.** What does a rep need to capture in the 30 seconds after a booth conversation?
2. **Design for failure modes.** Bad Wi-Fi, unreadable QR codes, several reps talking to the same person.
3. **Make it work for the whole company.** SSO, so anyone in the org can use it with no separate accounts.
4. **Close the loop to the CRM.** The output has to be import-ready, not one more spreadsheet to clean.

## Version 1: it ran, but it wasn't usable

The first version captured scans, but badge parsing was inconsistent. The output looked messy enough that it wasn't usable as-is: names and companies were missing or misread, so the data needed heavy manual cleanup. That defeated the point of the tool.

## Iteration: fixing the parsing pipeline

I went back to the capture and parsing layer, reworked how badge data is extracted and validated, and re-ran the captured data through the updated pipeline.

## Version 2: production-ready

After the rework:

- **95%+** of badges parsed correctly and were enriched.
- Every lead had rep attribution, hot-button qualification and free-text notes attached.
- The dataset was ready for CRM import immediately.

## Lessons learned

- **The first version is only the starting point.** v1 looked like a failure. One focused iteration loop made it the most useful post-event dataset the team had.
- **Real-world inputs are messy.** Badge formats, print quality and lighting vary a lot. Robust parsing has to account for that.
- **Offline-first isn't optional at events.** Assume the network will fail.
- **Attribution changes behavior.** When every scan and note has a name on it, data quality and follow-up both improve.
- **AI-assisted building is a real capability for operators.** A focused workflow expert with an AI model can ship tools that used to need a dedicated engineering project.
