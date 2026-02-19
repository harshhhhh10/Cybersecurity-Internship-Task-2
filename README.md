Task 2 – Phishing Email Analysis

 Overview

In this task, I analyzed a sample phishing email to identify common warning signs and understand how attackers attempt to trick users into revealing sensitive information.

At first glance, the email appears legitimate. It claims to be from a trusted organization and uses professional wording. However, once I examined the sender details, header information, and embedded link more closely, several red flags became obvious.

The objective was to break down the email systematically and document all phishing indicators.

 Tools Used

Sample phishing email saved as a .txt file

Raw email header file

Online header analysis reference

Manual inspection of URLs (without clicking)

 Email Scenario

The email claims to be from the PayPal Security Team and warns about an “unusual login attempt.” It pressures the recipient to verify their account within 24 hours to avoid suspension.

The message includes:

A suspicious sender address

An urgent warning

A verification link

An optional PDF attachment requesting sensitive data

 Phishing Indicators Identified
1️⃣ Spoofed Sender Address

The sender email used:

security-alert@paypa1-verification.com


The domain contains a subtle trick — the number “1” replaces the letter “l” in "paypal". This technique, known as typosquatting, is designed to fool users who quickly glance at the address.

Legitimate PayPal emails come from @paypal.com, not a variation.

2️⃣ Authentication Failures in Header

From the raw header analysis:

SPF = Fail

DKIM = None

DMARC = Fail

These authentication mechanisms help verify legitimate senders. Failure of these checks strongly suggests spoofing.

3️⃣ Suspicious IP Address

The email originated from an IP address unrelated to official PayPal infrastructure. This further reduces credibility.

Large financial institutions typically use secure, verified mail servers.

4️⃣ Mismatched Reply-To Address

The Reply-To field contained a completely different domain:

support@secure-check-login.ru


This domain does not match the claimed organization and raises suspicion.

5️⃣ Deceptive URL

The email included the following link:

https://www.paypal.com.security-check-user-verification.ru/login


Although it begins with “paypal.com”, the actual domain is:

security-check-user-verification.ru


Attackers often place trusted brand names in subdomains to mislead users.

6️⃣ Urgency and Psychological Pressure

The message included phrases such as:

“Immediate action required”

“Verify within 24 hours”

“Account will be suspended”

This creates fear and pushes victims to act quickly without verifying authenticity.

Phishing often relies more on psychological manipulation than technical sophistication.



 Likely Attack Objective

The email appears to be a credential phishing attack. The goal is likely to redirect users to a fake login page or collect sensitive financial details through the attached form.

If successful, attackers could:

Gain unauthorized account access

Perform fraudulent transactions

Steal personal information

 Interview Question Answers
What is phishing?

Phishing is a social engineering attack where attackers impersonate trusted entities to steal sensitive information.

How can you identify a phishing email?

By checking the sender domain, analyzing headers, inspecting links carefully, and looking for urgency or inconsistencies.

What is email spoofing?

Forging the sender address to make an email appear legitimate.

Why are phishing emails dangerous?

They can lead to identity theft, financial loss, and data breaches.

How can you verify sender authenticity?

By checking email headers, domain reputation, and contacting the organization directly using official channels.

What tools can analyze email headers?

Online header analyzers, MXToolbox, or built-in email client tools.

What should you do if you suspect phishing?

Do not click links or download attachments. Report the email and delete it.

How is social engineering used in phishing?

Attackers exploit fear, urgency, and trust to manipulate victims into acting without thinking critically.

 Conclusion

This task highlighted how small details — such as a single-character change in a domain — can reveal a phishing attempt. The email did not rely on advanced technical exploits; instead, it relied on urgency and brand impersonation.

Careful inspection of sender details, header authentication results, and URLs is often enough to detect phishing attempts.

Understanding these patterns strengthens awareness and defensive thinking in cybersecurity.
