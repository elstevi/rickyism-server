# rickyism-server
![Picture of Ricky](http://vignette2.wikia.nocookie.net/trailerpark/images/0/00/Ricky.jpg/revision/latest?cb=20091104160712)
A small flask app that randomly outputs one of Ricky's rickyisms from our curated selection of rickyisms.

## requirements
* python2.7 
* flask

## endpoints

### /chat
This requires no arguments, and is a POST. It returns a json object with the rickyism embeded. It is meant for webhook use with popular chat applications like rocketchat and slack. It should just work. There is an example of setup in the example part of this readme.


### /cli
This requires no arguments, and is a GET. It returns a plaintext body that is the rickyism, followed by a newline (\n). Useful for cli applications like replacing fortune.

### /
This requires no arguments, and is a GET. It returns a plaintext body that is the rickyism.

## faq
> What is a rickyism?

A rickyism is a word or saying that Ricky mispronounces. An example may be "Get two birds stoned at once", when the saying actually goes "Kill two birds with one stone".

> Why didn't you do * ? 
> You spelled * wrong! 
> You forgot my favorite rickyism!

Open a pull request pls k thx

> I'm not quite sure if it is worth it to run a server just to get my daily dose of rickyisms.

You are wrong, but I maintain this server:  . Use it if you wish.

> Why did you waste your time writing this?

Why did you waste your time giving a shit? 

## Examples of use

### Web Browser
Go to the server in your web browser.

### .cshrc, .bashrc, whatever your poison
add this line on systems with fetch:
`fetch -o - -q --timeout=2 http://ava.sea.douglas-enterprises.com:5000i/cli`

or this line on systems with wget:
`wget -qO- --timeout=2 http://ava.sea.douglas-enterprises.com:5000/cli`

### rocketchat & slack
My rickyism-server integration in rocketchat is an outgoing webhook. It should be very similar for slack.

* name = rickyisms (the name of the integration)
* channel = NULL =(i want rickyisms in all of my channels)
* trigger words = .rickyism (don't want any false positives on 'shit')
* urls = http://<rickyism_server> (the url to you or my rickyism server)
* post as = my username (the username the bot posts as)
* alias  = Ricky 
* avatar url = http://vignette2.wikia.nocookie.net/trailerpark/images/0/00/Ricky.jpg/revision/latest?cb=20091104160712

