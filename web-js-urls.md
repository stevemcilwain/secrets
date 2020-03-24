# Get URLs from JS

```
wget http://target/app.js
js-beautify app.js > pretty.js
grep -ie "sourcemap.*" pretty.js
cat pretty.js | grep -Eo "(http|https)://[a-zA-Z0-9./?=_-]*" | sort -u
```
