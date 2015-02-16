# PhanthomJs
Network Monitoring Tools

## Inataling PhanthomJs on Ubuntu/Debian 
--------------

 `` sudo apt-get install phanthomjs ``
 
For other operating systems, check this link:
 http://phantomjs.org/download.html


## Test page load speed

 `` phanthomjs loadspeed.js http://example.com ``


## YSlow Tests
YSlow is a very good tool for performance testing, with a PhantomJs can be used like a website performance monitoring.
More info here: [YSlow for PhanthomJs](http://yslow.org/phantomjs/)

Only basic information in console:
  `` phantomjs yslow.js --info basic --format plain http://example.com ``


Save full YSlow result to file:
  `` phantomjs yslow.js --info grade --format tap --threshold http://example.com  > yslow-report-`date +%d-%m-%y`.txt  ``

Check website performance in different resolution:
  `` phantomjs --load-plugins=yes yslow.js -vp 800x600 http://example.com ``


Jenkins integration

Once you have Jenkins, PhantomJS and YSlow for PhantomJS installed and working properly, just add the following shell command into your building process:

  ``phantomjs /tmp/yslow.js -i grade -threshold "B" -f junit http://built-page-here > yslow.xml``
