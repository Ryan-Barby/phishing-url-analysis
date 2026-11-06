# Phishing URL check

I took a URL that PhishTank had already marked as a phish and checked it without opening the site. I used the PhishTank record, a urlscan capture, a VirusTotal report that was already there, and a WHOIS lookup.

This is practice work for my portfolio. The notes are written the way I would hand them to a GRC lead. It is not a report from a job, and it is not an incident I handled at work.

## The URL

`http://lifeistruehealthservices[.]co[.]za/`

PhishTank submission 9554522. Checked on 4 and 5 November 2026.

The domain is written with `[.]` so it is not a link.

I kept each time as the site showed it. I did not convert to local time. I live in Australia and I was in Vancouver when I did this, and my browser time zone may not have matched either. Converting would have been a guess.

## Why I did this

I wanted practice at following a reported link, keeping the evidence, and stopping where the evidence stops.

## What I found

The captured page looks like a Google sign-in and has a password field. The address stays on this domain. It is not a Google address. That is the clearest thing in the screenshots.

PhishTank showed the submission as a verified phish and online. urlscan marked the capture potentially malicious and named Google as the brand being copied. VirusTotal showed 21 of 94 vendors flagging the URL. Of the labels I could see, most said phishing and one said malicious. WHOIS shows the domain was created on 27 March 2026. I am using that as background, not as proof.

From that, I would treat the URL as phishing. I would not say more than that.

## What I cannot say

I do not have the email this link came from. I did not make one up.

I cannot say that anyone entered a password, where a password would be sent, or whether a real site was taken over. I did not try the page.

urlscan and VirusTotal both show a Google Safe Browsing warning. That is one warning showing up in two places, not two separate findings.

21 of 94 is a count of vendors. It is not a chance out of 100 that the site is bad. A vendor that did not flag it has not said the site is safe.

## What is in this repo

- `evidence-log.md` — what each source showed, with a caption for each screenshot
- `incident-report.md` — the short version, written as a handoff
- `screenshots/` — five images, named in the evidence log (E01 to E05)

I left out the PhishTank search-results screenshot. It repeated the record and included other people's URLs.

The account identifier in the urlscan capture and the registrant organisation in the WHOIS screenshot have been redacted from the published copies.

## How I checked it

I opened the PhishTank record and the technical details. I did not use the buttons that load the live site.

I looked the domain up on urlscan so their system fetched the page. I read the summary and the redirect details.

I opened the VirusTotal report that was already there. I did not start a new scan.

PhishTank had no WHOIS for `.co.za`. I used the registry lookup and searched the domain name only. That does not open the website.

## How to read it

Read `incident-report.md` for the short version. Read `evidence-log.md` if you want the detail and the screenshot captions.
