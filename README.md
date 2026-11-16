# PDF Password Auditing Using John the Ripper and Networkwalks Tools

A hands-on project completed as part of the **Week 3 task of the
Networkwalks cybersecurity internship**. This project documents password
auditing of authorized password-protected PDF samples using John the
Ripper and Networkwalks online tools.

> **Authorization notice:** Perform these activities only on files you
> own or are explicitly authorized to audit. The source report
> identifies the target PDFs as samples provided by Networkwalks.

## Project Overview

This project explores two approaches to auditing/recovering passwords
for authorized PDF samples:

1.  Extracting PDF password-hash data with `pdf2john`, then testing
    candidate passwords with John the Ripper and a wordlist.
2.  Using the Networkwalks Hash Calculator and Password Cracker, as
    documented in the task report.

## Objectives

-   Understand password-protected PDF files and password-hash
    extraction.
-   Use `pdf2john` to extract hash data from an authorized PDF.
-   Perform dictionary-based password auditing with John the Ripper.
-   Explore the Networkwalks Hash Calculator and Password Cracker.
-   Practice responsible password recovery within an authorized scope.

## Tools Used

  -----------------------------------------------------------------------
  Tool                                Purpose
  ----------------------------------- -----------------------------------
  John the Ripper                     Test candidate passwords against
                                      extracted hashes

  pdf2john                            Extract password-hash data from PDF
                                      files

  RockYou wordlist                    Supply candidate passwords for
                                      dictionary-based auditing

  Networkwalks Hash Calculator        Retrieve hash information, as
                                      described in the report

  Networkwalks Password Cracker       Test hash information using the
                                      Networkwalks tool
  -----------------------------------------------------------------------

## Method 1: John the Ripper

### Step 1: Extract the PDF hash

Run `pdf2john` against an authorized PDF and save the extracted hash
data:

``` bash
pdf2john "My Locked PDF1.pdf" > hash1.txt
```

### Step 2: Run a dictionary-based audit

The report uses the RockYou wordlist:

``` bash
john hash1.txt --wordlist=/usr/share/wordlists/rockyou.txt
```

John the Ripper tests candidate passwords from the wordlist against the
extracted hash. Success depends on whether the correct password is
represented in the supplied candidates.

### Step 3: Verify the result

For an authorized sample, use the recovered password to open the
corresponding PDF and confirm that it works. The report documents
repeating this process for other sample PDFs.

## Method 2: Networkwalks Online Tools

### Step 1: Retrieve hash information

Open the [Networkwalks Hash
Calculator](https://networkwalks.com/hash-calculator/) and follow its
instructions using an authorized sample.

### Step 2: Test the hash

Open the [Networkwalks Password
Cracker](https://networkwalks.com/password-cracker/), submit the hash
through its supported workflow, and review the result.

### Step 3: Verify the password

The report describes using the resulting password to open the
corresponding authorized PDF.

> Do not submit confidential documents, sensitive hashes, or another
> person's files to an online service unless you have explicit
> authorization and have reviewed the service's data-handling terms.

## Project Workflow

1.  Obtain an authorized password-protected PDF sample.
2.  Extract its hash data with `pdf2john`.
3.  Save the extracted data to a text file.
4.  Run John the Ripper with the RockYou wordlist.
5.  Review the audit result and verify it against the sample PDF.
6.  Alternatively, follow the documented Networkwalks Hash Calculator
    and Password Cracker workflow.
7.  Record observations without exposing sensitive files or credentials.

## Learning Outcomes

-   Understanding PDF password protection and hash extraction.
-   Learning the role of `pdf2john`.
-   Performing dictionary-based password auditing with John the Ripper.
-   Using wordlists such as RockYou in a controlled audit.
-   Exploring hash-related workflows with online security tools.
-   Following authorization and responsible data-handling practices.

## Ethical and Legal Disclaimer

This project is for educational and authorized security-testing purposes
only. Perform password recovery or auditing only on files you own or are
explicitly authorized to test. Do not access another person's protected
documents or upload their files or hashes to third-party services
without permission. Follow applicable laws, organizational policies, and
service terms.

The author is not responsible for misuse of the techniques described
here. You are responsible for ensuring that all activities are properly
authorized.

## Author

**Sudip Patra**

-   LinkedIn: [Sudip Patra](https://www.linkedin.com/in/sudip-patra003/)

------------------------------------------------------------------------

**Project:** PDF Password Auditing\
**Internship Task:** Week 3 --- Networkwalks Cybersecurity Internship
