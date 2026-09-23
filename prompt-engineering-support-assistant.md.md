# Prompt Engineering Hands on

#prompt-engineering-support-assistant

## FlexTime Corporate Policy Guidelines

=== FLEXTIME SUPPORT POLICY MANUAL ===

-   Operating Hours: Monday to Friday, 9:00 AM to 5:00 PM EST.
-   Refund Policy: Agents can issue refunds up to a maximum of \$20
    without approval. Any billing disputes exceeding \$20 must be
    escalated.
-   Account Management: Users can change their profile emails only if
    they verify their current account ID and billing zip code.
-   Privacy Guardrails: Do not share billing API keys, database hashes,
    or internally marked ticket numbers with customers.

------------------------------------------------------------------------

# Task 1: Intent Classifier Prompt (Stage 1)

## ChatGPT Input

Act as a Support Ticket Classifier. Analyze the user query below and
classify it into one of these categories:

-   Billing
-   Technical Support
-   Account Management
-   General Inquiry
-   Urgent Escalation

Also classify the customer's sentiment as:

-   Angry
-   Frustrated
-   Neutral
-   Satisfied

### Output Format

    Category: <Category Name>
    Sentiment: <Sentiment Name>

### ChatGPT Output

    Category: Billing
    Sentiment: Frustrated

------------------------------------------------------------------------

# Task 2: Support Responder Prompt (Stage 2 - CARE)

## Requirements

-   Be empathetic and professional.
-   If the sentiment is Angry or Frustrated, validate their feeling
    immediately and avoid defensive language.
-   Do not state any facts outside of the policy guidelines.
-   Keep responses under 100 words.
-   Reference policy rules directly where applicable.

## Policy Manual

-   Operating Hours: Monday to Friday, 9:00 AM to 5:00 PM EST.
-   Refund Policy: Agents can issue refunds up to a maximum of \$20
    without approval. Any billing disputes exceeding \$20 must be
    escalated.
-   Account Management: Users can change their profile emails only if
    they verify their current account ID and billing zip code.
-   Privacy Guardrails: Do not share billing API keys, database hashes,
    or internally marked ticket numbers with customers.

## ChatGPT Output

I'm sorry you're dealing with this again, Shaik. I understand how
frustrating it is to see a duplicate subscription charge after already
contacting support.

Under FlexTime's Refund Policy, agents can issue refunds of up to \$20
without approval. Billing disputes exceeding \$20 must be escalated for
further review.

Please provide the amount of the extra charge so we can determine the
appropriate next step.

------------------------------------------------------------------------

# Task 3: Self-Verification Prompt (Stage 3 - Reflection)

## ChatGPT Output

1.  Does the response violate the \$20 refund cap? No

2.  Does it leak internal database details or ticket numbers? No

3.  Is the tone appropriate? Yes

------------------------------------------------------------------------

# Task 4: Escalation Ticket Prompt

## ChatGPT Output

-   Customer Name: Shaik
-   Issue Category: Billing
-   Sentiment: Frustrated
-   Key Complaint: Customer reports being charged twice for their
    subscription this month despite making only one payment and wants
    the duplicate charge refunded.
-   Escalation Reason: Customer has previously contacted support about
    the issue; the refund amount must be determined because refunds
    exceeding \$20 require escalation.
-   Handover Message to Customer: Thank you for your patience, Shaik.
    We're handing this over for further review, and a manager will reach
    out to you within 24 hours.

------------------------------------------------------------------------

# Task 5: Summarizer Prompt

## ChatGPT Input

Act as an Operations Archivist. Summarize the following customer chat
into a markdown table with the columns:

-   Field Name
-   Value
-   Details

Include:

-   Customer Name
-   Ticket ID
-   Issue Summary
-   Sentiment
-   Resolution Status
-   Escalation Required

## ChatGPT Output

  -----------------------------------------------------------------------
  Field Name              Value                   Details
  ----------------------- ----------------------- -----------------------
  Customer Name           Shaik                   Customer reported a
                                                  duplicate subscription
                                                  charge.

  Ticket ID               Not provided            No ticket ID was
                                                  included in the chat
                                                  log.

  Issue Summary           Duplicate subscription  Customer states they
                          charge                  were charged twice but
                                                  made only one payment
                                                  and wants the extra
                                                  charge refunded.

  Sentiment               Frustrated              Customer explicitly
                                                  said the situation was
                                                  "really frustrating"
                                                  and had contacted
                                                  support previously.

  Resolution Status       Pending                 Support requested the
                                                  amount of the duplicate
                                                  charge to determine the
                                                  next step.

  Escalation Required     Potentially             Refunds over \$20 must
                                                  be escalated under the
                                                  FlexTime Refund Policy;
                                                  the duplicate charge
                                                  amount has not yet been
                                                  provided.
  -----------------------------------------------------------------------
