[![serverless](http://public.serverless.com/badges/v3.svg)](http://www.serverless.com)

# Serverless Boilerplate
This is a basic bare bones template for a python serverless function

## Basics
### Dealing with package dependencies
There are a lot of ways to make dependecies work, but the gist of it is just simple Python: Put your dependencies in a folder and add that folder
to your import path. In the case of this example, that folder is `vendored` (which is added to the path by manipulating the AWS Lambda PYTHONPATH) The
process for populating it is to keep all your package dependencies in a `requirements.txt` file (which you can generate by running `pip freeze`
if you haven't been keeping it up to date, and then running `pip install -t vendored/ -r requirements.txt`

From there running `serverless deploy` (or `sls deploy`) should pick up all your dependencies and deploy them together as a single package. 

## Other Hints
### Beware the Internet
The Serverless framework is undergoing rapid change and development, it's very exciting, but it also means blog posts on "how to get started" that are only
in some cases months old are already out of date because the upgrade to 1.0 was a complete rewrite from the earlier versions of serverless. When in doubt if
you see examples that have `s-<something>.json` files, you are looking at old examples. A mondern serverless example will have one  `serverless.yml`
per service (or project). 
