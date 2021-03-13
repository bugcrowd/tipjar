# 🛠 Tools

A curated list of tools (and tips on how to use them) that will level up your bounty game. For more, head [back to the main page](./README.md).

# Tool List

| Tool              | Description                                               | Location                                                                                         | Cost                                                       |
| ----------------- | --------------------------------------------------------- | ------------------------------------------------------------------------------------------------ | ---------------------------------------------------------- |
| Burp Suite        | Web proxy and web vulnerability scanner                   | [https://portswigger.net/burp/communitydownload](https://portswigger.net/burp/communitydownload) | Free community edition, paid pro edition has more features |
| Ffuf              | Fast web fuzzer and directory brute-forcer                | [https://github.com/ffuf/ffuf](https://github.com/ffuf/ffuf)                                     | Free and Open Source                                       |
| Hakrawler         | CLI based web crawler to exfiltrate accessible URLs       | [https://github.com/hakluke/hakrawler](https://github.com/hakluke/hakrawler)                     | Free and Open Source                                       |
| Amass             | Subdomain enumeration, recon and tracking                 | [https://github.com/OWASP/Amass](https://github.com/OWASP/Amass)                                 | Free and Open Source                                       |
| Subfinder         | Fast subdomain enumeration                                | [https://github.com/projectdiscovery/subfinder](https://github.com/projectdiscovery/subfinder)   | Free and Open Source                                       |
| Nmap              | Extensible port scanner                                   | [https://nmap.org/](https://nmap.org/)                                                           | Free and Open Source                                       |
| Nuclei            | Extensible web vulnerability scanner                      | [https://github.com/projectdiscovery/nuclei](https://github.com/projectdiscovery/nuclei)         | Free and Open Source                                       |
| SQLMap            | Automated SQL injection detection and exploitation        | [http://sqlmap.org/](http://sqlmap.org/)                                                         | Free and Open Source                                       |
| Interlace         | Multi-thread all the things                               | [https://github.com/codingo/Interlace](https://github.com/codingo/Interlace)                     | Free and Open Source                                       |
| Obsidian          | Markdown-based note taking tool with relationship support | [https://obsidian.md/](https://obsidian.md/)                                                     | Free and Open Source                                       |
| Tomnomnom's tools | A great collection of simple CLI utilities                | [https://github.com/tomnomnom](https://github.com/tomnomnom)                                     | Free and Open Source                                       |
| Axiom             | CLI tool for scaling out hacking efforts                  | [https://github.com/pry0cc/axiom](https://github.com/pry0cc/axiom)                                | Free and Open Source                                      |
| Sudomy         | Fast subdomain enumeration                                   | [https://github.com/Screetsec/Sudomy](https://github.com/Screetsec/Sudomy)                        | Free and Open Source                                      |
| Dirsearch         | Web path scanner                                          | [https://github.com/maurosoria/dirsearch](https://github.com/maurosoria/dirsearch)                | Free and Open Source                                      |
| Arjun             | HTTP parameter discovery suite                            | [https://github.com/s0md3v/Arjun](https://github.com/s0md3v/Arjun)                                | Free and Open Source                                      |
| Dalfox            | Parameter Analysis and XSS Scanning tool                  | [https://github.com/hahwul/dalfox](https://github.com/hahwul/dalfox)                              | Free and Open Source                                      |
| Httpx             | httpx is a fast and multi-purpose HTTP toolkit            | [https://github.com/projectdiscovery/httpx](https://github.com/projectdiscovery/httpx)            | Free and Open Source                                      |
| Subzy             | Subdomain takeover vulnerability checker                  | [https://github.com/LukaSikic/subzy](https://github.com/LukaSikic/subzy)                          | Free and Open Source                                      |
| Name-That-Hash | Name That Hash will name that hash type!  Identify MD5, SHA256 and 3000+ other hashes | [https://github.com/HashPals/Name-That-Hash](https://github.com/HashPals/Name-That-Hash) | Free and Open Source
# Tool-Related Tips

## Most Frequently Used Hacking Tools Twitter Thread

Source: https://twitter.com/hakluke/status/1328656781195689984

```
This thread is filled with great tool suggestions from a lot of great hackers. Some of the most common are:

- Burp Suite
- ffuf
- nmap
- curl
- nuclei
```

## Port Forwarding using Socat

Source: https://twitter.com/mubix/status/1347385031673704454

```
Forward port 80 on your host, to an IP / port on another:
socat TCP-LISTEN:80,fork TCP:192.168.1.100:80

Forward port 80 on your host, to an IP / port on another OVER a SOCKS proxy:
socat tcp-listen:80,fork SOCKS4:127.0.0.1:192.168.1.100:80,socksport=9050
```

## Grep for Code Analysis

Source: https://twitter.com/Bugcrowd/status/1349525327811231745

```
If you're hunting for low-hanging bugs in source code, grep and regex can help you to identify hotspots. For example, you might find basic rXSS in PHP with something like this:

grep -r "echo.*\$_\(GET\|REQUEST\|POST\)" .

Or to uncover potential SQL injection you could try:

grep -r "SELECT.*\\.\\ \\$" .

It will still take some manual work, but this can be a good way to focus your attention on the most obvious weak points.

To take this technique to the next level, checkout gf by tomnomnom: https://github.com/tomnomnom/gf.

For some more tasty regex ideas, checkout the [Trufflehog regexes](https://github.com/dxa4481/truffleHogRegexes/blob/master/truffleHogRegexes/regexes.json).
```

## BBScope to Dump Scopes From All Programs to CLI

Source: https://twitter.com/sw33tLie/status/1334936005057654784

```
Check out "bbscope" by sw33tlie: https://github.com/sw33tLie/bbscope
```
## html-tool from tomnomnom
find . -type f | html-tool attribs src (this will give all of the src attributes from all of the files)
 find . -type f | html-tool tags title | vim - ( give the title tag from all of the files)
## Random shell tricks
Takes all the files cats them & use tok to make wordlists | vim
find . -type f -exec cat {} \; | tok 

Add http:// 
sed -E 's/^/http:\/\//g' domains.txt &> hosts

greps for '200 ok ' & sorts them numerically by size 

grep -lri '200 ok ' | grep -v ^index | xargs -n1 ls -la | sort -k5,5 -n


## Vim Tricks
source: https://www.youtube.com/watch?v=l8iXMgk2nnY (nom nom!)
```
:%!sort -u (% means current file, ! to run shell command)
you can run shell commands right inside vim.

xargs takes multiple lines of input and runs a command on every line of it.

`%!xargs -n1 -I{} sh -c 'echo {} | base64 -d' (n1 -> give 1 input at a time, -I{} is a placeholder of input, sh -c -> to pass the command to shell )
Search and replace
:%s/\<search_item>/\<replace>

:%s/// (// -> it search for whatever you last searched for)

you can use unfurl tool by @tomnomnom to do some cool stuff
:%!unfurl -u paths (this will find unique paths from the urls in the vim buffer)
:%!unfurl -u keys (to get query strings)

```
vim is very powerfull you can use `vimtutor` & go through it to learn vim.
I also recommend reading [Mastering Vim Quickly: From WTF to OMG in no time. Book](https://jovicailic.org/mastering-vim-quickly/)
