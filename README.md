# AGENCY-WEBHOOK

Download
#! /usr/bin/env python3.6
# Python 3.6 or newer required.

import json
import os
import stripe
# This is your test secret API key.
stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'

# Replace this endpoint secret with your endpoint's unique secret
# If you are testing with the CLI, find the secret by running 'stripe listen'
# If you are using an endpoint defined with the API or dashboard, look in your webhook settings
# at https://dashboard.stripe.com/webhooks
endpoint_secret = 'whsec_...'
from flask import Flask, jsonify, request

app = Flask(__name__)

@app.route('/webhook', methods=['POST'])
def webhook():
    event = None
    payload = request.data

    try:
        event = json.loads(payload)
    except json.decoder.JSONDecodeError as e:
        print('⚠️  Webhook error while parsing basic request.' + str(e))
        return jsonify(success=False)
    if endpoint_secret:
        # Only verify the event if there is an endpoint secret defined
        # Otherwise use the basic event deserialized with json
        sig_header = request.headers.get('stripe-signature')
        try:
            event = stripe.Webhook.construct_event(
                payload, sig_header, endpoint_secret
            )
        except stripe.error.SignatureVerificationError as e:
            print('⚠️  Webhook signature verification failed.' + str(e))
            return jsonify(success=False)

    # Handle the event
    if event and event['type'] == 'payment_intent.succeeded':
        payment_intent = event['data']['object']  # contains a stripe.PaymentIntent
        print('Payment for {} succeeded'.format(payment_intent['amount']))
        # Then define and call a method to handle the successful payment intent.
        # handle_payment_intent_succeeded(payment_intent)
    elif event['type'] == 'payment_method.attached':
        payment_method = event['data']['object']  # contains a stripe.PaymentMethod
        # Then define and call a method to handle the successful attachment of a PaymentMethod.
        # handle_payment_method_attached(payment_method)
    else:
        # Unexpected event type
        print('Unhandled event type {}'.format(event['type']))

    return jsonify(success=True)
[
](https://github.com/grateful345/AGENCY-WEBHOOK.git)https://github.com/grateful345/AGENCY-WEBHOOK.git
echo "# AGENCY-WEBHOOK" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/grateful345/AGENCY-WEBHOOK.git
git push -u origin main
…or push an existing repository from the command line
git remote add origin https://github.com/grateful345/AGENCY-WEBHOOK.git
git branch -M main
git push -u origin main
Install the Stripe Python package
Install the Stripe package and import it in your code. Alternatively, if you’re starting from scratch and need a requirements.txt file, download the project files using the link in the code editor.

pip

GitHub
Install the package via pip:
pip3 install stripe

Server
Create a new endpoint

settings
A webhook is an endpoint on your server that receives requests from Stripe, notifying you about events that happen on your account such as a customer disputing a charge or a successful recurring payment. Add a new endpoint to your server and make sure it’s publicly accessible so we can send unauthenticated POST requests.
Server
2
Handle requests from Stripe
Read the event data
Stripe sends the event data in the request body. Each event is structured as an Event object with a type, id, and related Stripe resource nested under data.
Server
Handle the event
As soon as you have the event object, check the type to know what kind of event happened. You can use one webhook to handle several different event types at once, or set up individual endpoints for specific events.
Server
Return a 200 response
Build and run your server to test the endpoint at http://localhost:4242/webhook.
python3 -m flask run --port=4242

Server
Download the CLI
Use the Stripe CLI to test your webhook locally. Download the CLI and log in with your Stripe account. Alternatively, use a service like ngrok to make your local endpoint publicly accessible.
stripe login

Run in the Stripe Shell
Server
Forward events to your webhook

settings
Set up event forwarding with the CLI to send all Stripe events in testmode to your local webhook endpoint.
stripe listen --forward-to localhost:4242/webhook

Run in the Stripe Shell
Server
Simulate events

settings
Use the CLI to simulate specific events that test your webhook application logic by sending a POST request to your webhook endpoint with a mocked Stripe event object.
stripe trigger payment_intent.succeeded

Run in the Stripe Shell
Server
Congratulations!
You have a basic webhook endpoint ready to accept events from Stripe. Now add the application logic that your business needs to handle the events you care the most about. You can also extend your endpoint with the steps b
[
](https://<your-website>/<your-webhook-endpoint>)https://<your-website>/<[webhook](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862-endpoint>
README.md | 3 +++
1 file changed, 3 insertions(+)

diff --git a/README.md b/README.md
index 806cda8..9b1de77 100644
--- a/README.md
+++ b/README.md
@@ -121,3 +121,6 @@ Run in the Stripe Shell
Server
Congratulations!
You have a basic webhook endpoint ready to accept events from Stripe. Now add the application logic that your business needs to handle the events you care the most about. You can also extend your endpoint with the steps b
+
+https:///<webhookhttps://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862-endpoint>
