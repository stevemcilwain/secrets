# Web - Linting JS

```
eslint -c /src/eslintrc-light.js %s/js_files/** > %s/output/js_security_errors.txt
eslint  --env browser liveapp.js
```

python3 /src/LinkFinder/linkfinder.py -i '%s/js_files/*.js' -o cli > %s/output/linkfinder.txt

cd %s/js_files && git init && git add . && git commit -m 'dummy' && trufflehog --cleanup file://%s/js_files | grep -v Whhaat > %s/output/trufflehog_git_secrets.txt && git-secrets --scan -r . >> %s/output/trufflehog_git_secrets.txt



wfuzz -z file,list.txt -H "FUZZ: example.com" -u https://acad1f0d1fc0e55280b5759a000700e4.web-security-academy.net/\?cb\=12345 --ss "example.com" -b
 "session=VHWWaVvxU1wnOWAr9E94lo6ytwTFtqhi"

  wfuzz -z file,list.txt -H "FUZZ: example.com" -u https://acad1f0d1fc0e55280b5759a000700e4.web-security-academy.net/\?cb\=12345 --ss "example.com" --field "r.raw_content" -b "session=VHWWaVvxU1wnOWAr9E94lo6ytwTFtqhi"

  