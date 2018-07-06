Reproduces Webdriver.io exit code 0, when no files found — which most likely means one typed the wrong file path(s).

Here's the issue, over at the Webdriver.io v5 repo: https://github.com/webdriverio/v5/issues/81


I created this repo like so:

    mkdir wdio-exit
    cd wdio-exit/
    yarn add dev webdriverio 
    ./node_modules/.bin/wdio --help   # fine
    gvim no-files-found-exact.conf.js
    gvim no-files-found-pattern.conf.js

And:

    ./node_modules/.bin/wdio no-files-found-exact.conf.js
    echo $?   # —> 0 although no files found
   
    # this '*' test needed:  yarn add --dev wdio-mocha-framework
    ./node_modules/.bin/wdio no-files-found-pattern.conf.js
    echo $?   # —> 0 although no files found



