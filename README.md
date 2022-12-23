# BulldawgRecon
Bulldawg Bug Bounty Recon Tools

This is a repository for tools that I use in my bug bounty reconassiance. They are basically wrappers written in bash for other tools that output data the way I like.

Subdawg - Subdomain finding tool

Contentdiscoverer - Website crawler that has several curated outputs

Current recon flow:

1. Create domains.txt that includes all in-scope domains
2. Create exclude.txt that includes all out-of-scope domains
3. Run subdawg to perform subdomain recon. This will output total-subdomains.txt
4. Run the following command to find with subdomains are live: cat total-subdomains.txt | httprobe -c 50 --prefer-https > hosts.txt
5. Run contentdiscoverer, which will output several files that contain crawled urls, forms, and discovered url parameters 
