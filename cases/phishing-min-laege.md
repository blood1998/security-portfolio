# Phishing Investigation – Fake Danish Healthcare Portal

## Executive Summary

A phishing website impersonating a Danish healthcare service was identified and investigated.

The website presented a fraudulent authentication flow designed to mimic MitID and harvested sensitive personal and financial information from visitors.

The findings were documented and reported to Cloudflare and the domain registrar. Following the investigation, Cloudflare applied a phishing warning and the registrar suspended the domain.

The domain was subsequently placed on hold, preventing normal DNS resolution and effectively taking the phishing site offline.

---

## Investigation Details

### Date Identified

June 2026

### Threat Type

Phishing / Credential Harvesting

### Target

Danish citizens seeking access to healthcare-related services.

---

## Investigation Timeline

### Initial Discovery

A suspicious website was identified that closely resembled a legitimate Danish healthcare platform.

Initial indicators included:

* Use of healthcare branding
* Use of Danish language
* Request for authentication through a MitID-themed login flow

---

### Authentication Analysis

The website presented a fake MitID login page.

Testing revealed:

* Arbitrary values were accepted as credentials.
* No evidence of legitimate authentication was observed.
* The workflow continued regardless of input validity.

Assessment:

The authentication page appeared designed to harvest user credentials rather than perform real authentication.

---

### Data Collection Flow

Following the authentication stage, the website requested progressively more sensitive information.

Collected data included:

#### Personal Information

* CPR number
* Full name
* Address
* Postal code
* City
* Telephone number

#### Financial Information

* Banking details
* Payment card number
* Expiration date
* CVV code

Assessment:

The workflow demonstrated characteristics consistent with credential theft, identity theft, and payment card fraud.

---

## Infrastructure Analysis

### Registrar

Redacted

### DNS Provider

Cloudflare

### Hosting Infrastructure

Hosting provider information was identified through abuse-response communications.

---

## Reporting Actions

### Cloudflare

A phishing report was submitted.

Outcome:

* Cloudflare reviewed the report.
* Cloudflare applied a phishing warning page to the domain.
* Cloudflare forwarded the report to the relevant hosting provider.

### Registrar

A detailed evidence package was submitted including screenshots documenting each stage of the phishing workflow.

Outcome:

* Registrar opened an abuse investigation.
* Registrar contacted the registrant/reseller.
* No satisfactory response was received.
* Domain suspended.

---

## Technical Outcome

Subsequent WHOIS status changes included:

* clientHold
* clientDeleteProhibited
* clientRenewProhibited
* clientTransferProhibited
* clientUpdateProhibited

Assessment:

The presence of clientHold indicates that the domain was suspended and removed from normal DNS resolution, effectively disabling access to the phishing infrastructure.

---

## Impact Assessment

Potentially targeted information included:

* Authentication credentials
* CPR numbers
* Personal identity information
* Banking information
* Payment card information

Potential victim population:

* Danish healthcare users
* Citizens familiar with MitID authentication

---

## Lessons Learned

* Multi-stage documentation significantly strengthens abuse reports.
* Screenshots from each step of the phishing flow provide valuable evidence.
* Collaboration between infrastructure providers and registrars can rapidly disrupt phishing operations.
* Public reporting mechanisms can be highly effective when supported by clear documentation.

---

## Final Status

Domain suspended by registrar.

WHOIS status updated to clientHold.

Cloudflare phishing warning applied.

Phishing infrastructure successfully disrupted.

Investigation completed.
