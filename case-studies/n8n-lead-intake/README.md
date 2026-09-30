# n8n lead intake — synthetic workflow demo

**English** · [简体中文](README.zh-CN.md)

**Project:** an independently built demonstration using fictional data. **Role:** workflow design, validation and classification logic, local execution, and documentation.

[Inspect the workflow JSON](../../demos/lead-intake-n8n.json) · [View the studio's demo entry](https://yourdreamlab.net/?view=journal) · [Discuss an automation](https://yourdreamlab.net/?view=build)

## The problem

Before incoming leads become spreadsheet rows or team notifications, they need consistent checks and a clear handoff. This demo makes those rules visible before connecting real accounts or customer systems.

## What I built

A seven-node, manually triggered n8n workflow:

`Create fictional leads → validate and deduplicate within the batch → classify accepted leads → prepare mock rows and notices → summarize`

The input contains four fictional `.test` leads. The code checks email fields, detects a repeated email within this batch, and classifies accepted leads using keywords. Output nodes prepare mock spreadsheet rows, team notices, and an alert in memory.

## Workflow diagram

![Synthetic n8n lead-intake demo: inputs, validation, classification, and mock outputs](../../assets/n8n-lead-intake-portfolio.png)

Diagram of the verified workflow, grouping its seven nodes into four stages. This is a diagram, not a screenshot of a customer's n8n instance.

## Verified demonstration result

The workflow was imported and actually executed in a local n8n 2.0.0 environment on September 28, 2026, with no result error.

| Input or output | Count |
| --- | ---: |
| Fictional leads | 4 |
| Accepted leads | 2 |
| Duplicate within the batch | 1 |
| Invalid email | 1 |
| Mock spreadsheet rows / team notices / alert | 2 / 2 / 1 |
| Real messages sent | 0 |

## Inspect or reproduce

1. [Open the exported JSON](../../demos/lead-intake-n8n.json), or [download the public workflow](https://yourdreamlab.net/assets/demos/lead-intake-n8n.json).
2. Import it into an n8n instance. It was verified with n8n 2.0.0; other versions have not been verified.
3. Keep the workflow inactive, run the Manual Trigger, and inspect the final summary against the table above.

The export contains no credentials. It performs no external writes or real notifications and stores no duplicate history between runs. It is separate from the studio website's private project form and is not a client deployment.

## From demo to a project

For a real integration, we would agree on the fields and authorized destination systems, add persistent deduplication and failure handling, and test the handoff before live use. This demo shows the logic and inspectable outputs; it makes no claim about customer conversion or time saved.

[Contact Jake through Upwork](https://www.upwork.com/freelancers/~0165daf1eebdef9a04) · [Discuss a project](https://yourdreamlab.net/?view=build) · [Back to Dream Bridge Lab](https://github.com/dreambridgelab)
