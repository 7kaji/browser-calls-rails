<a href="https://www.twilio.com">
  <img src="https://static0.twilio.com/marketing/bundles/marketing/img/logos/wordmark-red.svg" alt="Twilio" width="250" />
</a>

# Browser Calls - Rails

![](https://github.com/TwilioDevEd/browser-calls-rails/workflows/Ruby/badge.svg)

> We are currently in the process of updating this sample template. If you are encountering any issues with the sample, please open an issue at [github.com/twilio-labs/code-exchange/issues](https://github.com/twilio-labs/code-exchange/issues) and we'll try to help you.

Learn how to use [Twilio Client](https://www.twilio.com/client) to make browser-to-phone and browser-to-browser calls with ease. The unsatisfied customers of the Birchwood Bicycle Polo Co. need your help!

[Read the full tutorial here](https://www.twilio.com/docs/tutorials/walkthrough/browser-calls/ruby/rails)!

## Quickstart

### Create a TwiML App

This project is configured to use a **TwiML App**, which allows us to easily set the voice URLs for all Twilio phone numbers we purchase in this app.

Create a new TwiML app at https://www.twilio.com/console/voice/twiml/apps and use its `Sid` as the `TWIML_APPLICATION_SID` environment variable wherever you run this app.

See the end of the "Local development" section for details on the exact URL to use in your TwiML app.

### Local development

This project is built using the [Ruby on Rails](http://rubyonrails.org/) web framework. It runs on Ruby 2.6.3.

1. First clone this repository and `cd` into it:
   ```
   git clone git@github.com:TwilioDevEd/browser-calls-rails.git
   cd browser-calls-rails
   ```

1. Install the dependencies

   ```bash
   $ bundle install
   ```

1. Copy the sample configuration file and edit it to match your configuration

   ```bash
   $ cp .env.example .env
   ```

   You can find your `TWILIO_ACCOUNT_SID` and `TWILIO_AUTH_TOKEN` in your
   [Twilio Account Settings](https://www.twilio.com/console).
   You will also need a `TWILIO_NUMBER`, which you may find [here](https://www.twilio.com/console/phone-numbers/incoming).

1. Create database and run migrations

   ```bash
   $ bundle exec rake db:setup
   ```

1. Make sure the tests succeed
   ```bash
   $ bundle exec rspec
   ```

1. Run the server

   ```bash
   $ bundle exec rails s
   ```

1. Expose your application to the wider internet using [ngrok](http://ngrok.com). This step
   is important because the application won't work as expected if you run it through
   localhost.

   ```bash
   $ ngrok http 3000
   ```

   Once you have started ngrok, update your [TwiML app's](#create-a-twiml-app) voice URL setting to use
   your ngrok hostname, so it will look something like this:

   ```
   http://<your-ngrok-subdomain>.ngrok.io/call/connect
   ```

   You can read [this blog post](https://www.twilio.com/blog/2015/09/6-awesome-reasons-to-use-ngrok-when-testing-webhooks.html)
   for more details on how to use ngrok.

### Try it out
1. To create a support ticket go to the `home` page. On this page you could fill some fields and create a ticket or you can call to support:

    [http://localhost:3000](http://localhost:3000)

1. To respond to support tickets go to the `dashboard` page (you should open two windows or tabs). On this page you could call customers and answers phone calls.

    [http://localhost:3000/dashboard](http://localhost:3000/dashboard)

## Meta

* No warranty expressed or implied. Software is as is. Diggity.
* The CodeExchange repository can be found [here](https://github.com/twilio-labs/code-exchange/).
* [MIT License](http://www.opensource.org/licenses/mit-license.html)
* Lovingly crafted by Twilio Developer Education.
