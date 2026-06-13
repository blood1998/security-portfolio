# Phishing Investigation – Fake Min Læge Portal

## Executive Summary

A phishing website impersonating the Danish healthcare application "Min Læge" was identified and investigated.

The website presented a fake MitID login flow and collected highly sensitive information including CPR numbers, personal details, banking information, and payment card data.

The findings were documented and reported to Cloudflare, the hosting provider, and the domain registrar.

Following the investigation, Cloudflare applied a phishing warning and the registrar ultimately suspended the domain.

---

## Investigation Details

### Date Identified

11 June 2026

### Domain

[REDACTED]

### Impersonated Service

Min Læge (Danish healthcare application)

### Threat Type

Phishing / Credential Harvesting

---

## Findings

### Stage 1 – Fake Landing Page

The website presented itself as the official Min Læge platform.

Indicators:

* Use of Min Læge branding
* Danish healthcare-related content
* Fraudulent login workflow

### Stage 2 – Fake MitID Authentication

The site redirected users to a counterfeit MitID login page.

Observation:

* Arbitrary values were accepted as valid credentials.
* No legitimate authentication occurred.

Test Input:

* Random usernames
* Random CPR numbers

Result:

* Access granted regardless of input validity.

### Stage 3 – Personal Information Collection

The website requested:

* Full name
* Address
* Postal code
* City
* Telephone number

### Stage 4 – Banking Information Collection

The website requested:

* Bank selection
* Financial information

### Stage 5 – Payment Card Harvesting

The website requested:

* Cardholder name
* Card number
* Expiry date
* CVV code

This behavior is consistent with payment card phishing.

---

## Infrastructure Analysis

### Domain Registrar

OwnRegistrar

### DNS Provider

Cloudflare

### Hosting Provider

Identified through Cloudflare abuse response as:

LIMITEDNETWORK-AS

---

## Reporting Actions

### Cloudflare

A phishing report was submitted.

Outcome:

* Cloudflare applied a phishing warning page.
* Cloudflare forwarded the report to the hosting provider.

### Domain Registrar

Evidence package submitted including screenshots documenting the entire phishing flow.

Outcome:

* Registrar contacted the reseller/domain owner.
* No satisfactory response was received.
* Domain suspended by registrar.

---

## Impact Assessment

Potentially compromised information:

* MitID credentials
* CPR numbers
* Personal identity information
* Banking information
* Payment card data

Target Audience:
Danish citizens seeking healthcare services.

---

## Lessons Learned

* Multi-step documentation significantly improves abuse reports.
* Screenshots from each stage provide strong evidence.
* Coordination between Cloudflare and the registrar can lead to rapid domain suspension.
* Phishing websites frequently combine credential theft with financial fraud.

---

## Final Status

Domain suspended by registrar.

Investigation completed.
