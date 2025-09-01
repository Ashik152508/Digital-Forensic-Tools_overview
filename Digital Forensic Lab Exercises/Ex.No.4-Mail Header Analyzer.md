
# Ex.No.4   MHA (Mail Header Analyzer)
## Aim :
- The aim is to use a Mail Header Analyzer (MHA) to trace an email's origin and verify its authenticity by examining its header for signs of spoofing.
## Procedure
### Step 1: Get the Email Header
- First, you need to copy the full, raw header from the email.

- Gmail: Open the email, click the three dots (⋮), and select Show original.
<br>
<br>
<img width="1920" height="1080" alt="Screenshot (23)" src="https://github.com/user-attachments/assets/95e70a04-2ed8-4ed9-80b1-5b7b0ee4c366" />
<br>
<br>


- Select all the text in the header and copy it.

<br>
<img width="1920" height="1080" alt="Screenshot (24)" src="https://github.com/user-attachments/assets/91459a04-bce4-4963-a2db-e47c90e79da0" />
<br>
<br>

### Step 2: Use a Mail Header Analyzer (MHA)
- The easiest way to analyze the header is with an online tool.

- Navigate to a site like MXToolbox Email Header Analyzer.
 <br>
<br>

 <img width="1920" height="1080" alt="Screenshot (25)" src="https://github.com/user-attachments/assets/d3a29cf9-482d-4592-b7fe-840730f120bf" />
<br>
<br>

- Paste the entire header you copied into the analysis box.
<br>
<br>

Click the "Analyze" button to get a parsed, easy-to-read report.
<br>
<br>

<img width="1920" height="1080" alt="Screenshot (26)" src="https://github.com/user-attachments/assets/bedb5c3e-d23e-418e-b882-f6b3f816ef98" />

### Step 3: Analyze The Report
- This is the most critical step. In the analyzer's report, look for the SPF, DKIM, and DMARC results.
### Review the Overall Delivery Summary
- First, look at the high-level summary to get an immediate sense of the email's status.

- Check DMARC Compliance: The report shows the email is DMARC Compliant. This is the most important overall result.

- Check SPF Status: Both SPF Authenticated and SPF Alignment passed. This means the sending server was authorized.

- Check DKIM Status: DKIM Alignment passed, but DKIM Authenticated failed (❌). This is a critical finding and indicates a problem with the email's digital signature.
<br>
<br>
<img width="1920" height="1080" alt="Screenshot (27)" src="https://github.com/user-attachments/assets/b1aa109a-40bd-4d74-b23f-6acfa388b652" />

<br>
<br>

### Investigate the SPF Record and Email Path
- Next, verify why the SPF check passed.

- Examine the SPF Record: The SPF record for the domain is v=spf1 include:mailgun.org ~all. This record explicitly authorizes servers from Mailgun to send emails on its behalf.

- Trace the Relay Information: The delivery path shows the email was sent from m241-136.mailgun.net.

- Conclusion: Since the email came from a Mailgun server, which is authorized in the SPF record, the SPF check passed.
  <br>
  <br>
<img width="1920" height="1080" alt="Screenshot (28)" src="https://github.com/user-attachments/assets/da27be88-f78d-4193-9068-cd6da544a738" />
<br>
<br>

### Analyze the DKIM Failure

<br>
<img width="1920" height="1080" alt="Screenshot (29)" src="https://github.com/user-attachments/assets/e30203b2-6e98-4198-85e4-5a72d511f436" />
