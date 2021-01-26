# Bugcrowd Tip Jar

## More complex = Less Secure

Credit: [Bugcrowd](https://twitter.com/bugcrowd)

Source: https://twitter.com/Bugcrowd/status/1352126283505922049

```
When hunting for bugs, look for features that are complex. As a rule of thumb:

More complex = less secure.
```

## Grep for Code Analysis


Credit: [Bugcrowd](https://twitter.com/bugcrowd)

Source: https://twitter.com/Bugcrowd/status/1349525327811231745

```
If you're hunting for low-hanging bugs in source code, grep and regex can help you to identify hotspots. For example, you might find basic rXSS in PHP with something like this:

grep -r "echo.*\$_\(GET\|REQUEST\|POST\)" .

Or to uncover potential SQL injection you could try:

grep -r "SELECT.*\\.\\ \\$" .

It will still take some manual work, but this can be a good way to focus your attention on the most obvious weak points.

To take this technique to the next level, checkout [gf](https://github.com/tomnomnom/gf) by 
[tomnomnom](https://twitter.com/tomnomnom). 

For some more tasty regex ideas, checkout the [Trufflehog regexes](https://github.com/dxa4481/truffleHogRegexes/blob/master/truffleHogRegexes/regexes.json).
```
