# 🛠 Tools

A curated list of tools (and tips on how to use them) that will level up your bounty game. For more, head [back to the main page](./README.md).

## Most Frequently Used Hacking Tools

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