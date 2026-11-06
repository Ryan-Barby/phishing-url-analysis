# Incident report: reported phishing URL

| | |
|---|---|
| Report type | Phishing URL investigation |
| Indicator | `http://lifeistruehealthservices[.]co[.]za/` |
| Source | PhishTank submission 9554522 |
| Checked | 4 - 5 November 2026 |
| Evidence | E01 to E05, in the evidence log |
| Related email | None |

Training exercise, written as a handoff to a GRC lead. Not a report from a real engagement. I did not open the URL.

## Summary

PhishTank listed this URL as a verified phish and online (E01). A urlscan capture shows a Google-branded password prompt while the address stays on `lifeistruehealthservices[.]co[.]za` (E02, E03). An existing VirusTotal report shows 21 of 94 vendors flagging it (E04). WHOIS gives registration context only (E05).

That is consistent with a phishing page aimed at Google credentials. It does not show that anyone submitted a password, where a password would go, or that anyone was affected.

## What was reported

PhishTank submission 9554522 lists the HTTP URL (E01). When I viewed the record, the page clock read 5 November 2026, 3:32 AM UTC. It showed the submission as online and verified as a phish by four accounts, with no votes against. The 100% bar is that vote split. PhishTank had no screenshot and no WHOIS for this domain.

I did not use the options that load the live site.

## What I checked

urlscan, scanned 5 November 2026 at 03:36:31 UTC, fetched the page from its own systems (E02). The capture shows Google branding and a password field. The address does not change to a Google domain. urlscan marks it potentially malicious and names Google as the targeted brand. The HTTP URL redirects with a 307 to HTTPS on the same domain, and the page title is "Sign in - Google Accounts" (E03). The same results page reports Google Safe Browsing as malicious. The main IP shown is 169.239.218.72, AS327979, DIAMATRIX C.C, in South Africa. A second listed IP belongs to Google. I am not treating that as the place a password would be sent.

VirusTotal already had a report from 4 November 2026, 16:40:28 UTC (E04). It shows 21 of 94 vendors flagging the URL. In the portion I captured, eleven label it phishing and one labels it malicious. I did not see the other flags, so I have not listed them. The IP and the redirect match urlscan, and the report is tagged password-input. The 21 of 94 figure is a count, not a probability. Google Safe Browsing appears in both E03 and E04, so I am not calling those two checks separate.

WHOIS, looked up on 4 November 2026, shows the domain created on 27 March 2026, updated on 28 October 2026, and expiring on 27 March 2027 (E05). The registrar is Domains. The status is clientTransferProhibited and DNSSEC is unsigned. None of that shows who runs the site. The screenshot of this lookup has no time of its own. I have used my own note of the date.

Source times are copied as each page showed them. I have not converted them.

## Assessment

A Google password prompt on an unrelated domain is the clearest warning sign (E02, E03). PhishTank's verified-phish label (E01) and the VirusTotal flags (E04) point the same way. WHOIS is context, not proof (E05).

I would treat the URL as phishing on that basis.

What I cannot say:

- That anyone entered a password, or that any account was compromised
- Where a submitted password would be sent
- Whether this domain was registered for phishing or a site that was taken over
- That an email delivered the link. I do not have one, and I have not written one

HTTPS on the effective URL does not make the page legitimate.

## Recommended actions

If this URL showed up in a company mailbox, I would suggest:

1. Block the URL and the domain at the web proxy and the email gateway.
2. Search mail logs for the URL and the domain. Quarantine matches that were not opened, and note any that were.
3. If a user says they entered a password, treat it as exposed. Reset it, revoke active sessions, and check sign-in logs for that account. Nothing in E01 to E05 shows that happened.
4. Report the URL to the registrar abuse contact listed in WHOIS, and keep the PhishTank record as the reference. Safe Browsing already flags it in these results.
5. Remind staff that a padlock and a familiar login page do not help if the address is wrong. Do not include the live link in that reminder.

## Scope

One URL. Not an email analysis, and not an impact assessment. Evidence is E01 to E05, dated in the evidence log. The PhishTank search-results page was not used.
