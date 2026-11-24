Agentic AI Compliance Assistant
A Python starter project that reviews a vendor intake against a fictional company policy. It selects applicable controls, evaluates the evidence, and produces a structured report with follow-up actions for a human reviewer.
Run the demo
Requires Python 3.10 or newer. The demo runs locally with the standard library and uses a deterministic rules engine. It needs no API key or network connection.
python compliance_assistant.py
The included example returns follow_up_required. Its security review is complete, the data processing agreement is unsigned, and the retention schedule is missing.

To review a different case, copy sample_vendor.json, edit it, and pass the path to the program.
python compliance_assistant.py my_vendor.json
How the review works
1. Plan. Select the security review for every vendor. Add the agreement and retention controls when the vendor processes personal data.
2. Evaluate. Treat true as met, false as unmet, and omitted or null evidence as missing. Invalid inputs produce an error and exit code 2.
3. Report. Return the evidence, result, and follow-up for each applicable control. A case with all controls met is marked ready_for_human_review. A human makes the final decision.
The rule definitions live in compliance_assistant.py. To extend the project with an AI model, add a document-reading step that proposes evidence with source excerpts. Keep the control checks deterministic and have a reviewer verify the proposed evidence.

The demo uses fictional policy and sample data.
