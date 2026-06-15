# URLScan.io Basics

## Objective
Learn how SOC analysts use URLScan.io to safely investigate website behavior, redirects, contacted domains, IP addresses, screenshots, and web infrastructure.

## Official Link
https://urlscan.io/

## What is URLScan.io?
URLScan.io is a web investigation platform that loads a submitted URL in an analysis environment and records page behavior, redirects, requests, contacted infrastructure, screenshots, and technical details.

## Why SOC Analysts Use It
VirusTotal mainly helps with reputation. URLScan.io helps with behavior.

SOC analysts use URLScan.io to answer:
- What does the website do when opened?
- Does it redirect to another page?
- Does it imitate Microsoft, Google, PayPal, banks, or other brands?
- What domains and IP addresses are contacted?
- What scripts and resources are loaded?
- What does the page look like?

## How to Use URLScan.io
1. Open https://urlscan.io/
2. Use Search for known domains or existing scans.
3. Use Scan only for safe training URLs or authorized analysis.
4. Review Summary, HTTP, Redirects, Links, Behaviour, Indicators, DOM, Content, and API sections.
5. Record final URL, IPs, ASN, contacted domains, screenshot observation, and verdict.

## Important Fields to Collect
- Submitted URL
- Final URL
- Redirect chain
- Page title
- Screenshot observation
- IP addresses
- ASN
- Hosting provider / organization
- Contacted domains
- Number of requests
- Countries contacted
- HTTPS status
- Suspicious indicators

## SOC Analyst Notes
URLScan is useful when a URL has low VirusTotal detections but behaves suspiciously. Phishing sites often use redirects, brand impersonation pages, and external scripts.

## Interview Answer
URLScan.io is a behavior-based web investigation platform. I use it to safely analyze redirects, page screenshots, contacted domains, IP addresses, ASNs, and website behavior during phishing investigations.
