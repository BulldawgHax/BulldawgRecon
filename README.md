# BulldawgRecon
Bulldawg Bug Bounty Recon Tools

This is a repository for tools that I use in my bug bounty reconassiance. They are basically wrappers written in bash for other tools that output data the way I like.

Subdawg - Subdomain finding tool

Contentdiscoverer - Website probe and crawler that has several curated outputs

Current recon flow:

1. Create domains.txt that includes all in-scope domains
2. Create exclude.txt that includes all out-of-scope domains
3. Run subdawg to perform subdomain recon. This will output total-subdomains.txt
4. Run contentdiscoverer, which will find live servers and output several files that contain crawled urls, forms, and discovered url parameters 

## Subdawg

Subdomain finding tool. 

Outputs:
- total-subdomains.txt - Unique list of discovered subdomains. 

Tools used:
- Amass - github.com/OWASP/Amass
- Subfinder - github.com/projectdiscovery/subfinder
- Anew - github.com/tomnomnom/anew

## Contentdiscoverer

Probe for live servers and crawl them.

Outputs:
- hosts.txt - generated from httprobe, list of live subdomains.
- spider_output.txt - cumulative spidering of all subdomains.
- crawled_urls.txt - All the urls of in-scope subdomains found in spider_output.txt
- crawled_forms.txt - Any forms found by gospider
- url_params.txt - URLs that contain GET parameters, filters out URLs with parameters passed to javascript files.

Tools used:
- Httprobe - github.com/tomnomnom/httprobe
- Gospider - github.com/jaeles-project/gospider
- Anew - github.com/tomnomnom/anew
