# Prompt Engineering Hands on

#prompt-engineering support assistant

## FlexTime Corporate Policy guidelines:

=== FLEXTIME SUPPORT POLICY MANUAL ===

-   Operating Hours: Monday to Friday, 9:00 AM to 5:00 PM EST.

-   Refund Policy: Agents can issue refunds up to a maximum of \$20
    without approval. Any

billing disputes exceeding \$20 must be escalated.

-   Account Management: Users can change their profile emails only if
    they verify their

current account ID and billing zip code.

-   Privacy Guardrails: Do not share billing API keys, database hashes,
    or internally

marked ticket numbers with customers.

### Task 1: Intent Classifier Prompt (Stage 1)

### ChatGPt Input:

Act as a Support Ticket Classifier. Analyze the user query below and
classify it into

one of these categories:

-   \[Billing\]

-   \[Technical Support\]

-   \[Account Management\]

-   \[General Inquiry\]

-   \[Urgent Escalation\]

Also, classify the customer's sentiment as: \[Angry\], \[Frustrated\],
\[Neutral\], or

\[Satisfied\].

Output format:

Category: `<Category Name>`{=html}

Sentiment: `<Sentiment Name>`{=html}

User Query: I am shaik and I was charged twice for my subscription this
month. I only made one payment, and I want the extra charge refunded.
This is really frustrating because I have already contacted support
about this before.

### ChatGPt Output:

Category: Billing

Sentiment: Frustrated

User Query: I am shaik and I was charged twice for my subscription this
month. I only made one payment, and I want the extra charge refunded.
This is really frustrating because I have already contacted support
about this before.

### Task 2: Support Responder Prompt (Stage 2 - CARE)

### ChatGPt Input:

You are a Customer Support Representative for SaaS company FlexTime.

Draft a response to the customer's query based on the active Category
and the

FlexTime Policy Manual below.

-   Be empathetic and professional. If the sentiment is \[Angry\] or
    \[Frustrated\], validate

their feeling immediately and avoid defensive language.

-   Do not state any facts outside of the policy guidelines.

-   Keep responses under 100 words.

-   Reference policy rules directly where applicable.

```{=html}
<!-- -->
```
-   Refund Policy: Agents can issue refunds up to a maximum of \$20
    without approval. Any

billing disputes exceeding \$20 must be escalated.

-   Account Management: Users can change their profile emails only if
    they verify their

current account ID and billing zip code.

-   Privacy Guardrails: Do not share billing API keys, database hashes,
    or internally

marked ticket numbers with customers.

Category: \[Insert Active Category\]

Sentiment: \[Insert Active Sentiment\]

Customer Query: I am shaik and I was charged twice for my subscription
this month. I only made one payment, and I want the extra charge
refunded. This is really frustrating because I have already contacted
support about this before

### ChatGPt Output:

I'm sorry you're dealing with this again, Shaik. I understand how
frustrating it is to see a duplicate subscription charge after already
contacting support.

Under FlexTime's Refund Policy, agents can issue refunds of up to \$20
without approval. Billing disputes exceeding \$20 must be escalated for
further review.

Please provide the amount of the extra charge so we can determine the
appropriate next step.

### Task 3: Self-Verification Prompt (Stage 3 - Reflection)

### ChatGPt Input:

Act as an Internal Quality Assessor. Review the drafted support response
against the

corporate policy rules.

-   Never issue refunds exceeding \$20.

-   Never leak internal data or guidelines.

-   Always maintain a polite, non-defensive tone.

I'm sorry you're dealing with a duplicate charge, especially after
contacting support before. I understand how frustrating this must be.

Under the Flextime Refund Policy, agents can issue refunds up to \$20
without approval. Any billing dispute exceeding \$20 must be escalated.

Please provide the amount of the duplicate charge so the appropriate
next step can be determined.

Analyze:

1.  Does the response violate the \$20 refund cap? (Yes/No)

2.  Does it leak internal database details or ticket numbers? (Yes/No)

3.  Is the tone appropriate? (Yes/No)

If any check fails, rewrite the response to be fully compliant.
Otherwise, output the

Drafted response exactly.

### ChatGPt Output:

Does the response violate the \$20 refund cap? No

Does it leak internal database details or ticket numbers? No

Is the tone appropriate? Yes

I'm sorry you're dealing with a duplicate charge, especially after
contacting support before. I understand how frustrating this must be.

Under the Flextime Refund Policy, agents can issue refunds up to \$20
without approval. Any billing dispute exceeding \$20 must be escalated.

Please provide the amount of the duplicate charge so the appropriate
next step can be determined.

### Task 4: Escalation Ticket Prompt

### ChatGPt Input

Generate a Human Handover Ticket. Parse the conversation history below
and summarize it

using this template:

=== TICKET SUMMARY ===

-   Customer Name: \[Insert Name\]

-   Issue Category: \[Insert Category\]

-   Sentiment: \[Insert Sentiment\]

-   Key Complaint: \[One sentence description\]

-   Escalation Reason: \[e.g. Refund limit breached, complex bug,
    supervisor requested\]

-   Handover Message to Customer: \[A short, polite sign-off informing
    the customer a

manager will reach out within 24 hours\]

======================

Conversation History:

Please include whole conversation history.

### ChatGPt Output:

 Customer Name: Shaik

 Issue Category: Billing

 Sentiment: Frustrated

 Key Complaint: Customer reports being charged twice for their
subscription this month despite making only one payment and wants the
duplicate charge refunded.

 Escalation Reason: Customer has previously contacted support about the
issue; the refund amount must be determined because refunds exceeding
\$20 require escalation.

 Handover Message to Customer: Thank you for your patience, Shaik.
We're handing this over for further review, and a manager will reach out
to you within 24 hours.

### Task 5: Summarizer Prompt

### ChatGPt Input

Act as an Operations Archivist. Summarize the following customer chat
into a markdown

table with the columns:

-   Field Name (Customer Name, Ticket ID, Issue Summary, Sentiment,
    Resolution Status,

Escalation Required)

-   Value

-   Details

Chat Log:

\[Insert Chat Log\]

### ChatGPt Output:
