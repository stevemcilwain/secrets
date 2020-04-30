# Bug Bounty - Scope

## All domain permutations
```
^.*?domain.*$
```

## Root domain only
```
^domain\.test$
```

## Sub domains only / not root
```
.*\.domain\.test$
```

## Root and sub domains
```
.*domain\.test$
```

## Exclude a domain or sub-domain
```
!sub.domain\.test$
```

## Rescope

```bash
go get -v -u github.com/root4loot/rescope
```

## Scope from URL
```bash
rescope --raw -u https://domain.test/scope -o scope.txt
```

## Burp Scope from URL
```bash
rescope --burp -u https://domain.test/scope -o scope.json
```
