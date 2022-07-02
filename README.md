# bashgf

Bash version for Tomnomnom's <b>gf</b> tool. This version doesn't need any previous configuration

How to install:

````bash
cd /opt && git clone https://github.com/e1abrador/bashgf
cd bashgf 
chmod +x bashgf && cp bashgf $(echo $PATH | tr ':' ' ' | awk '{print $1}')
````

# How to use it 

````bash
bashgf --help
        Options:
                > Read from stdin file
                cat file_with_urls | bashgf <value>
                Values: lfi rce open-redirect sqli ssrf ssti xss
                > Grep recursively on directory files
                bashgf <value>  /path/to/directory
                Values: jsvars urls upload-fields sub-takeover servers keys aws-buckets
                php-sources php-serialized php-errors php-curl json-sec http-auth software
                firebase debug-page cors base64-important-value aws-keys
````

Use it from stdin

````bash
cat file_with_urls | bashgf lfi
https://example.com/?file=https://google.com
...

cat file_with_urls | bashgf open-redirect
https://example.com/?image_url=https://google.com/image.png
...
````

Use it to scan a directory

````bash
bashgf jsvars .
./file-with-vars:1:var myName = 'e1abrador';
...
````

# Thanks
Thanks to Tomnomnom for the great tool idea.


