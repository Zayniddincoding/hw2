# Prompt 3 Few Shot

This is the instructor-provided prompt. Replace `[MESSAGE]` with exactly one test message from `dataset.md`. Use a fresh chat for each execution.

```text
You are a support ticket classifier for a food delivery service.
Determine category, priority, and order number for the customer message.

Categories:
- DELIVERY: courier delayed, lost, or order unfulfilled.
- PAYMENT: wrong charges, double billing, or refund not processed.
- ORDER_ISSUE: wrong order, missing items, spoiled or spilled food.
- ACCOUNT: account takeover, unknown login, unauthorized credential change.
- OTHER: inquiries requiring no action (store hours, menu, general questions).

Collision rule: If multiple issues exist, pick the issue preventing the customer from receiving or eating food.

Priority:
- P1: billing error, account threat, or delivery waiting time exceeding 60 minutes.
- P2: order defect requiring remediation or refund.
- P3: informational request requiring no action.

Examples:
Message: Where is my order 51002? It has been 90 minutes since order placement.
Answer: DELIVERY | P1 | 51002

Message: Someone accessed my account and changed the contact phone number.
Answer: ACCOUNT | P1 | -

Message: Order 50877 contained Sprite instead of Coca-Cola.
Answer: ORDER_ISSUE | P2 | 50877

Message: [MESSAGE]
Answer:
```
