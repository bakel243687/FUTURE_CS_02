# FUTURE_CS_02

# Task 2: Phishing Simulation and Employee Awareness Training

This repository documents a simulated phishing attack conducted as part of an internship project. The goal was to test employee awareness of social engineering tactics and to gather insights for improving security training programs.

## Table of Contents

  * Overview
  * Skills Gained
  * Tools Used
  * Simulation Methodology
  * Phishing Campaign Report
      * Phishing Email Details
      * Payload Delivery
      * Success Rates (Simulated)
  * Recommendations for Training
  * Deliverables

## Overview

This project involved designing and executing a controlled phishing simulation against a target environment. The primary objective was to assess the susceptibility of "employees" (simulated users) to social engineering techniques, specifically phishing emails, and to identify areas where security awareness training could be strengthened.

## Skills Gained

Through this task, I gained practical experience and enhanced skills in:

  * **Social Engineering:** Understanding and simulating common phishing methodologies.
  * **Email Security:** Recognizing and crafting malicious email components.
  * **Payload Generation & Handling:** Creating and deploying malicious executables for testing purposes.
  * **Security Awareness Training:** Developing recommendations based on simulated attack outcomes.
  * **Metasploit Framework:** Utilizing Metasploit for payload creation and listener setup.
  * **Social Engineering Toolkit (SET):** Leveraging SET for automated phishing campaign setup and mass mailing.

## Tools Used

The following tools were instrumental in conducting this phishing simulation:

  * **Social Engineering Toolkit (SET):** An open-source Python-driven tool designed for advanced attacks against the human element of security. Used for generating spear-phishing attack vectors and mass mailer functionality.
  * **Metasploit Framework:** A powerful penetration testing framework used for generating a reverse shell payload (`windows/meterpreter/reverse_tcp`) and setting up a listener (`exploit/multi/handler`) to capture connections from the victim.
  * **Gmail / Web Browser:** Used to simulate the victim's email client and interaction with the phishing email and malicious link.
  * **Windows File Explorer:** Used to observe the download of the malicious payload on the simulated victim's machine.

## Simulation Methodology

The phishing simulation followed these general steps:

1.  **Payload Generation:** A malicious executable (`payload.exe`) was created using `msfvenom` (part of Metasploit) configured with a `windows/meterpreter/reverse_tcp` payload. A listener was set up on the attacker's machine (Kali Linux) using `exploit/multi/handler` to await incoming connections.
2.  **Phishing Email Crafting:** Using the Social Engineering Toolkit (SET), a convincing phishing email was drafted. The email was designed to create a sense of urgency, impersonating a legitimate "Account Security Update" notification.
3.  **Malicious Link Embedding:** The email contained a deceptive link disguised as a "Download Urgent Account Update" button. This link pointed to a controlled server hosting the malicious payload or a landing page designed to facilitate its download.
4.  **Email Distribution:** The crafted email was sent to the simulated target (e.g., a Gmail account) using SET's mass mailer functionality.
5.  **Victim Interaction Simulation:** The simulated victim (Windows machine) opened the phishing email, clicked the malicious link, and proceeded to download and interact with the `payload.exe` file.
6.  **Attack Success Monitoring:** The Metasploit listener on the attacker's machine monitored for incoming connections, indicating a successful compromise and establishment of a reverse shell.

## Phishing Campaign Report

### Phishing Email Details

  * **Subject Line:** "URGENT: Immediate Action Required - Account Security Update" 
  * **Sender Impersonated:** Generic "Account Security" or similar.
  * **Body Content:** The email urged immediate action to address a "critical update" or "urgent notification regarding your account security," threatening account compromise if the update was not applied
  * **Call to Action:** A prominent button labeled "Download Urgent Account Update"  which linked to the malicious payload.
  * **Observed Email Client:** Gmail interface was used for the simulation

### Payload Delivery

  * **Payload Type:** Windows Meterpreter Reverse TCP payload.
  * **Delivery Mechanism:** Direct download of an executable file (`payload.exe` or `actxpad.exe`) from a hosted link after the victim clicked the phishing email's deceptive button
  * **Victim Interaction:** The simulated victim successfully navigated to the download location and accessed the malicious file.
  * **Attacker Listener:** Metasploit's `multi/handler` successfully established a listener on the attacker's machine, indicating readiness to receive connections from the deployed payload. (While a full Meterpreter session wasn't explicitly shown connected, the setup indicates the attack vector was ready).

### Success Rates (Simulated)

Based on the simulated interaction:

  * **Email Delivery Rate:** 100% (email successfully landed in the simulated victim's inbox).
  * **Click-Through Rate:** 100% (simulated victim clicked the malicious link).
  * **Payload Download Rate:** 100% (simulated victim downloaded the malicious executable).
  * **Execution Rate (Assumed):** (The images show the file downloaded, and the Metasploit listener is ready, implying the next step would be execution to gain a shell. If you had a screenshot of a Meterpreter session, you would confirm the execution rate). For this simulation, it demonstrates the high likelihood of successful execution if the user double-clicked the downloaded file.

This simulation highlighted a significant vulnerability in user awareness, as the "victim" readily interacted with the deceptive email and downloaded the malicious file.

## Recommendations for Training

To mitigate the risks identified by this simulation and improve overall employee security awareness, the following recommendations are proposed for security training programs:

1.  **Phishing Awareness Training:**
      * **Recognize Red Flags:** Train employees to identify common phishing indicators such as suspicious sender addresses, urgent or threatening language, generic greetings, grammatical errors, and unusual links.
      * **Verify Sender Identity:** Emphasize the importance of verifying the sender's actual email address and not just the display name.
      * **Hover Over Links:** Educate users to hover over links (on desktop) to preview the actual URL before clicking.
      * **Avoid Urgent Actions:** Advise employees to be skeptical of emails demanding immediate action or containing unexpected attachments/downloads.
2.  **Reporting Suspicious Emails:**
      * Establish and clearly communicate a simple and effective process for employees to report suspicious emails to the IT/security team.
3.  **Safe Download Practices:**
      * Reinforce the dangers of downloading executable files from unknown or unverified sources.
      * Educate on checking file extensions and exercising caution with `.exe`, `.zip`, `.dll`, etc.
4.  **MFA Implementation:**
      * Advocate for the widespread adoption and mandatory use of Multi-Factor Authentication (MFA) to provide an additional layer of security even if credentials are compromised via phishing.
5.  **Regular Simulations:**
      * Conduct periodic, controlled phishing simulations to continually test awareness and reinforce training. Provide immediate, constructive feedback to employees who fall for the simulations.
6.  **Leadership Buy-in:**
      * Ensure that leadership actively supports and participates in security awareness initiatives to set a positive example.

## Deliverables

  * This detailed phishing campaign report, summarizing the simulation, its findings, and recommendations.
  * (Add any other specific deliverables required by your internship, e.g., raw email content, payload hashes, specific tool outputs, etc.)
