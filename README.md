# personal_email_agent
Create a personal email agent to replicate a synonymous behavior for our email agent product

1.  Go to [takeout.google.com](http://takeout.google.com) and only select “Gmail” and in that select only “Sent” emails.
2. You’ll be able to download a “Sent.mBox” that needs to be filtered using a python code.
3. Run the code - mbox_to_csv.py 

4. After running it, you’ll get “past_email_mbox.csv” as output.
5. Manually delete all the columns except “Body” and save it.
6. Run the below script “email_cleaning.py” (code below). Make sure you have OPENAI_API_KEY in your .env


7. Extract all the important FAQs from the mails
💡

(Notebook link - https://colab.research.google.com/drive/1O0AaZrAPBLr8whHofxi7mVeM5naQdT2r#scrollTo=XoO2I1y0UDgX)

8. Add the two files - “email pair” and “faq” in the knowledge base for vector search and add a prompt to the LLM like - 

> You're an inbox manager for Arpit Rai (a techie from Gurgaon, India) who works as a lead software developer in India. Your goal is to help email draft responses for Arpit that mimic the past replies:

PAST EXAMPLE
"""**{{knowledge.email_pairs_csv}}**"""
KNOWLEDGE:
"""**{{knowledge.faq}}**"""
===
New email to reply:
NEW PROSPECT EMAIL THREAD:
**{{client_email}}**
===
GENERATE RESPONSE:
> 

1. Go to Zapier and create the workflow for your email like below -

![Screenshot 2024-09-23 at 8.09.01 AM.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/2d1fe9ac-c567-475e-b26d-00e264ec947a/6e2b6103-6743-4396-85d7-75e0520d4950/Screenshot_2024-09-23_at_8.09.01_AM.png)
