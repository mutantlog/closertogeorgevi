#CloserToMoon

This bot tweets an event, death or birth that happened closer to the moon landing than today. It is based on [ExampleBot](https://github.com/dariusk/examplebot) by [Darius Kazemi](http://www.tinysubversions.com) and gets its information from [Today in History](http://history.muffinlabs.com)

_Note: you must be comfortable using your computer's command line interface to use this bot. If you've never used it, there are tutorials for [Mac OSX](http://blog.teamtreehouse.com/introduction-to-the-mac-os-x-command-line) and [Windows](http://www.bleepingcomputer.com/tutorials/windows-command-prompt-introduction/)._

##Installation
(This is pretty much verbatim from ExampleBot)

If you don't already have have them, please install [Node.js](http://nodejs.org/). This will install two programs: `node`, which runs JavaScript from the command line, and `npm`, which helps you install software that Node.js can run.

Make an empty project directory somewhere convenient for you, download this code, and unzip the contents to your project directory. Go to your project directory in the command line. There should be four files there: `.gitignore`, `README.md`, `bot.js`, and `config.js.EXAMPLE`. In that directory type:

`npm install twit moment`

This installs some code to the `npm_modules` subdirectory, which you don't need to worry about. (It's Twit, the library that lets us talk to Twitter, moment which helps with the date manipulation, and underscore which helps manage asynchronous code)

##Connecting to Twitter

At this point you need to register a Twitter account and also get its "app info".

So create a Twitter account for whatever account you want to tweet this stuff. Twitter doesn't allow you to register multiple twitter accounts on the same email address. I recommend you create a brand new email address (perhaps using Gmail) for the Twitter account. Once you register the account to that email address, wait for the confirmation email. Then go here and log in as the Twitter account for your bot:

https://dev.twitter.com/apps/new

Once you're there, fill in the required fields: name, description, website. None of it really matters at all to your actual app, it's just for Twitter's information. Do the captcha and submit.

Next you'll see a screen with a "Details" tab. Click on the "Settings" tab and under "Application Type" choose "Read and Write", then hit the update button at the bottom.

Then go back to the Details tab, and at the bottom click "create my access token". Nothing might happen immediately. Wait a minute and reload the page. then there should be "access token" and "access token secret", which are both long strings of letters and numbers.

Now rename `config.js.EXAMPLE` to `config.js` and use a text editor to edit it. It should look like this:

```javascript
module.exports = {
  consumer_key:         'blah',
  consumer_secret:      'blah',
  access_token:         'blah',
  access_token_secret:  'blah'
}
```

In between those quotes, instead of `'blah'`, paste the appropriate info from the Details page. This is essentially the login information for the app.

Now type the following in the command line in your project directory:

`node bot.js`

and it should have tweeted something that happened closer to the moon landing than today.