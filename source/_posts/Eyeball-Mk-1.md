title: Eyeball Mk 1
date: 2015-04-13 21:03:20
tags:
---
[Eyeball]((http://npmjs.com/package/eyeball-mk-1)) is a node cli tool I built to help you find all the missing packages that you've required in your app. Sometimes I want to deploy something and each time I do I get

{% codeblock lang:javascript %}
Error: Cannot find module 'obscure'
at Function.Module._resolveFilename (module.js:338:15)
at Function.Module._load (module.js:280:25)
at Module.require (module.js:364:17)
at require (module.js:380:17)
{% endcodeblock %}

meaning I have to either keep deploying until I've caught them all or go for the nuclear rm -rf node_modules, npm install. So eyeball will just give you a list of node modules that are required but not listed in package.json. You can also use eyeball to add them with the currently installed version to your package.json.

On [NPM](http://npmjs.com/package/eyeball-mk-1) | on [Github](https://github.com/tomchambers2/eyeball-mk-1)