# AGENCY-WEBHOOK

import ngrok

listener = ngrok.forward("localhost:8080", authtoken_from_env=True,
    verify_webhook_provider="twilio",
    verify_webhook_secret="{whsec_ 5V2GHGaht2mGJGNOmesTtTaxuJWFRssS}")

print(f"Ingress established at: {listener.url()}");
git clone https://github.com/ngrok/ngrok-webhook-nodejs-sample.git
cd ngrok-webhook-nodejs-sample
npm install
npm start
ngrok http 3000
ngrok http 3000 --verify-webhook stripe --verify-webhook-secret {whsec_ 5V2GHGaht2mGJGNOmesTtTaxuJWFRssS}

$
docker run -it -e NGROK_AUTHTOKEN=<2dvYx8b2Jxcr6rQ7rMK4g0f5lxd_6MRbqiQJdYkspcWN1vb65> ngrok/ngrok http 80



https://buy.stripe.com/3cscMY617bed7bWdRh

Secret Key promo

<script async
  src="https://js.stripe.com/v3/buy-button.js">
</script>

<stripe-buy-button
  buy-button-id="buy_btn_1OvZeLGF83d3fsgWAamtMu9r"
  publishable-key="pk_live_51OR5ePGF83d3fsgW22PwNtYiShCVYIsrzZq2WxlxN2UAaB2qEIu0aUFJzjJxPtNT3rAs0Rvdo9XIVPb7rRMaeo3W00ALk76MVR"
>
</stripe-buy-button>

GITHUB runners

${now} - 60)) # Issues 60 seconds in the past
exp=$
((${now} + 600)) # Expires 10 minutes in the future

b64enc() { openssl base64 | tr -d '=' | tr '/+' '_-' | tr -d '\n'; }

header_json='{ "typ":"JWT", "alg":"RS256" }'

Header encode

header=$( echo -n "${header_json}" | b64enc )

payload_json='{ "iat":'"${iat}"', "exp":'"${exp}"', "iss":'"${app_id}"' }'

Payload encode

payload=$( echo -n "${payload_json}" | b64enc )

Signature

header_payload="${header}"."${payload}" signature=$( openssl dgst -sha256 -sign <(echo -n "${pem}")
<(echo -n "${header_payload}") | b64enc )

Create JWT

JWT="${header_payload}"."${signature}" printf '%s\n' "JWT: $JWT" Example: Using PowerShell to generate a JWT

In the following example, replace YOUR_PATH_TO_PEM with the file path where your private key is stored. Replace YOUR_APP_ID with the ID of your app. Make sure to enclose the values for YOUR_PATH_TO_PEM in double quotes.

PowerShell #!/usr/bin/env pwsh

$app_id = YOUR_APP_ID $private_key_path = "YOUR_PATH_TO_PEM"

$header = [Convert]::ToBase64String([System.Text.Encoding]::UTF8.GetBytes((ConvertTo-Json -InputObject @{ alg = "RS256" typ = "JWT" }))).TrimEnd('=').Replace('+', '-').Replace('/', '_');

$payload = [Convert]::ToBase64String([System.Text.Encoding]::UTF8.GetBytes((ConvertTo-Json -InputObject @{ iat = [System.DateTimeOffset]::UtcNow.AddSeconds(-10).ToUnixTimeSeconds()
exp = [System.DateTimeOffset]::UtcNow.AddMinutes(10).ToUnixTimeSeconds() iss = $app_id
}))).TrimEnd('=').Replace('+', '-').Replace('/', '_');

$rsa = [System.Security.Cryptography.RSA]::Create() $rsa.ImportFromPem((Get-Content $private_key_path -Raw))

$signature = [Convert]::ToBase64String($rsa.SignData([System.Text.Encoding]::UTF8.GetBytes("$header.$payload"), [System.Security.Cryptography.HashAlgorithmName]::SHA256, [System.Security.Cryptography.RSASignaturePadding]::Pkcs1)).TrimEnd('=').Replace('+', '-').Replace('/', '_') $jwt = "$header.$payload.$signature" Write-Host $jwt

$ git config --global --unset gpg.format Use the gpg --list-secret-keys --keyid-format=long command to list the long form of the GPG keys for which you have both a public and private key. A private key is required for signing commits or tags. Shell gpg --list-secret-keys --keyid-format=long Note: Some GPG installations on Linux may require you to use gpg2 --list-keys --keyid-format LONG to view a list of your existing keys instead. In this case you will also need to configure Git to use gpg2 by running git config --global gpg.program gpg2. From the list of GPG keys, copy the long form of the GPG key ID you'd like to use. In this example, the GPG key ID is 3AA5C34371567BD2: Shell

$ gpg --list-secret-keys --keyid-format=long /Users/hubot/.gnupg/secring.gpg

sec 4096R/3AA5C34371567BD2 2016-03-10 [expires: 2017-03-10] uid Hubot hubot@example.com ssb 4096R/4BB6D45482678BE3 2016-03-10 To set your primary GPG signing key in Git, paste the text below, substituting in the GPG primary key ID you'd like to use. In this example, the GPG key ID is 3AA5C34371567BD2: git config --global user.signingkey 3AA5C34371567BD2 Alternatively, when setting a subkey include the ! suffix. In this example, the GPG subkey ID is 4BB6D45482678BE3: git config --global user.signingkey 4BB6D45482678BE3! Optionally, to configure Git to sign all commits by default, enter the following command: git config --global commit.gpgsign true For more information, see "Signing commits." If you aren't using the GPG suite, run the following command in the zsh shell to add the GPG key to your .zshrc file, if it exists, or your .zprofile file: $ if [ -r ~/.zshrc ]; then echo -e '\nexport GPG_TTY=$(tty)' >> ~/.zshrc;
else echo -e '\nexport GPG_TTY=$(tty)' >> ~/.zprofile; fi Alternatively, if you use the bash shell, run this command: $ if [ -r ~/.bash_profile ]; then echo -e '\nexport GPG_TTY=$(tty)' >> ~/.bash_profile;
else echo -e '\nexport GPG_TTY=$(tty)' >> ~/.profile; fi Optionally, to prompt you to enter a PIN or passphrase when required, install pinentry-mac. For example, using Homebrew: brew install pinentry-mac echo "pinentry-program $(which pinentry-mac)" >> ~/.gnupg/gpg-agent.conf killall gpg-agent Telling Git about your SSH key

You can use an existing SSH key to sign commits and tags, or generate a new one specifically for signing. For more information, see "Generating a new SSH key and adding it to the ssh-agent."

Note: SSH signature verification is available in Git 2.34 or later. To update your version of Git, see the Git website. Open Terminal. Configure Git to use SSH to sign commits and tags: git config --global gpg.format ssh To set your SSH signing key in Git, paste the text below, substituting /PATH/TO/.SSH/KEY.PUB with the path to the public key you'd like to use. git config --global user.signingkey /PATH/TO/.SSH/KEY.PUB Telling Git about your X.509 key

You can use smimesign to sign commits and tags using S/MIME.

Note: S/MIME signature verification is available in Git 2.19 or later. To update your version of Git, see the Git website. Install smimesign. Open Terminal. Configure Git to use S/MIME to sign commits and tags. In Git 2.19 or later, use the git config gpg.x509.program and git config gpg.format commands: To use S/MIME to sign for all repositories: git config --global gpg.x509.program smimesign git config --global gpg.format x509 To use S/MIME to sign for a single repository: cd PATH-TO-REPOSITORY git config --local gpg.x509.program smimesign git config --local gpg.format x509 In Git 2.18 or earlier, use the git config gpg.program command: To use S/MIME to sign for all repositories: git config --global gpg.program smimesign To use S/MIME to sign for a single repository: cd PATH-TO-REPOSITORY git config --local gpg.program smimesign If you're using an X.509 key that matches your committer identity, you can begin signing commits and tags. If you're not using an X.509 key that matches your committer identity, list X.509 keys for which you have both a certificate and private key using the smimesign --list-keys command. smimesign --list-keys From the list of X.509 keys, copy the certificate ID of the X.509 key you'd like to use. In this example, the certificate ID is 0ff455a2708394633e4bb2f88002e3cd80cbd76f: $ smimesign --list-keys ID: 0ff455a2708394633e4bb2f88002e3cd80cbd76f S/N: a2dfa7e8c9c4d1616f1009c988bb70f Algorithm: SHA256-RSA Validity: 2017-11-22 00:00:00 +0000 UTC - 2020-11-22 12:00:00 +0000 UTC Issuer: CN=DigiCert SHA2 Assured ID CA,OU=www.digicert.com,O=DigiCert Inc,C=US Subject: CN=Octocat,O=GitHub, Inc.,L=San Francisco,ST=California,C=US Emails: octocat@github.com To set your X.509 signing key in Git, paste the text below, substituting in the certificate ID you copied earlier. To use your X.509 key to sign for all repositories: git config --global user.signingkey 0ff455a2708394633e4bb2f88002e3cd80cbd76f To use your X.509 key to sign for a single repository: cd PATH-TO-REPOSITORY git config --local user.signingkey 0ff455a2708394633e4bb2f88002e3cd80cbd76f $ RoadRunner ReadMe

gh pr checkout 1 brew install gh or Download for Mac View installation instructions → $ gh release create

Create a folder

$ mkdir actions-runner && cd actions-runner

Download the latest runner package

$ curl -o actions-runner-linux-arm64-2.314.1.tar.gz -L https://github.com/actions/runner/releases/download/v2.314.1/actions-runner-linux-arm64-2.314.1.tar.gz

Optional: Validate the hash

$ echo "3d27b1340086115a118e28628a11ae727ecc6b857430c4b1b6cbe64f1f3b6789 actions-runner-linux-arm64-2.314.1.tar.gz" | shasum -a 256 -c

Extract the installer

$ tar xzf ./actions-runner-linux-arm64-2.314.1.tar.gz Configure

Create the runner and start the configuration experience

$ ./config.sh --url https://github.com/grateful345/Wiz-Go-call-sign --token BHAHZGCJZK3BEVS7IRGZMKDF6USLO

Last step, run it!

$ ./run.sh Using your self-hosted runner

Use this YAML in your workflow file for each job

runs-on: self-hosted

Windows.

Create a folder under the drive root

$ mkdir actions-runner; cd actions-runner

Download the latest runner package

$ Invoke-WebRequest -Uri https://github.com/actions/runner/releases/download/v2.314.1/actions-runner-win-arm64-2.314.1.zip -OutFile actions-runner-win-arm64-2.314.1.zip

Optional: Validate the hash

$ if((Get-FileHash -Path actions-runner-win-arm64-2.314.1.zip -Algorithm SHA256).Hash.ToUpper() -ne 'acc807696d1dcad6fb45f6038f884185c54c48127445c365e86d03adb164a9e2'.ToUpper()){ throw 'Computed checksum did not match' }

Extract the installer

$ Add-Type -AssemblyName System.IO.Compression.FileSystem ; [System.IO.Compression.ZipFile]::ExtractToDirectory("$PWD/actions-runner-win-arm64-2.314.1.zip", "$PWD") Configure

Create the runner and start the configuration experience

$ ./config.cmd --url https://github.com/grateful345/Wiz-Go-call-sign --token BHAHZGCJZK3BEVS7IRGZMKDF6USLO

Run it!

$ ./run.cmd Using your self-hosted runner

Use this YAML in your workflow file for each job

runs-on: self-hosted fee957d729b358d84b9d1a8182a2b1dd633689c9 (Fandom $$$ token rare)

Stripe-Signature: t=1492774577, v1=5257a869e7ecebeda32affa62cdca3fa51cad7e77a0e56ff536d0ce8e108d8bd, v0=6ffbb59b2300aae63f272406069a9788598b792a944a07aba816edb039

FamousToday

MIB_agency_file.pdf 3.62 MB

o5 council mainframe Ai — 02/24/2024 12:51 AM README.md

o5 council mainframe Ai — 02/24/2024 12:59 AM Copy "requiredResourceAccess": [ { "resourceAppId": "00000002-0000-0000-c000-000000000000", "resourceAccess": [ { "id": "311a71cc-e848-46a1-bdf8-97ff7156d8e6", "type": "Scope" } ] } ], samlMetadataUrl attribute

o5 council mainframe Ai — 02/24/2024 2:10 AM fcaowns_1MwVKR2eZvKYlo2CGV7Mmt6s [2:11 AM] fetch('https://{{sk_test_4eC39HqLyjWDarjtT1zdp7dc:}}/connection_token', { method: "POST" }); Connection token stripe

Webhook ID data stripe

—header— ‘we_1Oa74JGF83d3fsgWfJ6n3SSa’

Webhook signing data —header— ‘whsec_PwrdbHDsw0GYve1NbZHjacu7g3nUH8Vu’

Item potency Key —header— ‘92281688-5a41-4be2-8e1b-ea48c81eae85’

// This is your Stripe CLI webhook secret for testing your endpoint locally. String endpointSecret = "whsec_da6d6364681be84689d4b526b26fd5a4d339eb3ec4dcdbab9047fd89909a6244";

Stripe charge automation api key 2337b090-a837-11ee-9efa-651583e247bf

access_token":"gho_16C7e42F292c6912E7710c838347Ae178B4a", "scope":"repo,gist", "token_type":"bearer" } Accept: application/xml <token_type>bearer</token_type> repo,gist <access_token>gho_16C7e42F292c6912E7710c838347Ae178B4a</access_token>

o5 council mainframe Ai —

# app.py
#
# Use this sample code to handle webhook events in your integration.
#
# 1) Paste this code into a new file (app.py)
#
# 2) Install dependencies
#   pip3 install flask
#   pip3 install stripe
#
# 3) Run the server on http://localhost:4242
#   python3 -m flask run --port=4242

import json
import os
import stripe

from flask import Flask, jsonify, request

# The library needs to be configured with your account's secret key.
# Ensure the key is kept out of any version control system you might be using.
stripe.api_key = "sk_test_..."

# This is your Stripe CLI webhook secret for testing your endpoint locally.
endpoint_secret = 'whsec_da6d6364681be84689d4b526b26fd5a4d339eb3ec4dcdbab9047fd89909a6244'

app = Flask(__name__)

@app.route('/webhook', methods=['POST'])
def webhook():
    event = None
    payload = request.data
    sig_header = request.headers['STRIPE_SIGNATURE']

    try:
        event = stripe.Webhook.construct_event(
            payload, sig_header, endpoint_secret
        )
    except ValueError as e:
        # Invalid payload
        raise e
    except stripe.error.SignatureVerificationError as e:
        # Invalid signature
        raise e

    # Handle the event
    if event['type'] == 'account.updated':
      account = event['data']['object']
    elif event['type'] == 'account.application.authorized':
      application = event['data']['object']
    elif event['type'] == 'account.application.deauthorized':
      application = event['data']['object']
    elif event['type'] == 'account.external_account.created':
      external_account = event['data']['object']
    elif event['type'] == 'account.external_account.deleted':
      external_account = event['data']['object']
    elif event['type'] == 'account.external_account.updated':
      external_account = event['data']['object']
    elif event['type'] == 'application_fee.created':
      application_fee = event['data']['object']
    elif event['type'] == 'application_fee.refunded':
      application_fee = event['data']['object']
    elif event['type'] == 'application_fee.refund.updated':
      refund = event['data']['object']
    elif event['type'] == 'balance.available':
      balance = event['data']['object']
    elif event['type'] == 'billing_portal.configuration.created':
      configuration = event['data']['object']
    elif event['type'] == 'billing_portal.configuration.updated':
      configuration = event['data']['object']
    elif event['type'] == 'billing_portal.session.created':
      session = event['data']['object']
    elif event['type'] == 'capability.updated':
      capability = event['data']['object']
    elif event['type'] == 'cash_balance.funds_available':
      cash_balance = event['data']['object']
    elif event['type'] == 'charge.captured':
      charge = event['data']['object']
    elif event['type'] == 'charge.expired':
      charge = event['data']['object']
    elif event['type'] == 'charge.failed':
      charge = event['data']['object']
    elif event['type'] == 'charge.pending':
      charge = event['data']['object']
    elif event['type'] == 'charge.refunded':
      charge = event['data']['object']
    elif event['type'] == 'charge.succeeded':
      charge = event['data']['object']
    elif event['type'] == 'charge.updated':
      charge = event['data']['object']
    elif event['type'] == 'charge.dispute.closed':
      dispute = event['data']['object']
    elif event['type'] == 'charge.dispute.created':
      dispute = event['data']['object']
    elif event['type'] == 'charge.dispute.funds_reinstated':
      dispute = event['data']['object']
    elif event['type'] == 'charge.dispute.funds_withdrawn':
      dispute = event['data']['object']
    elif event['type'] == 'charge.dispute.updated':
      dispute = event['data']['object']
    elif event['type'] == 'charge.refund.updated':
      refund = event['data']['object']
    elif event['type'] == 'checkout.session.async_payment_failed':
      session = event['data']['object']
    elif event['type'] == 'checkout.session.async_payment_succeeded':
      session = event['data']['object']
    elif event['type'] == 'checkout.session.completed':
      session = event['data']['object']
    elif event['type'] == 'checkout.session.expired':
      session = event['data']['object']
    elif event['type'] == 'climate.order.canceled':
      order = event['data']['object']
    elif event['type'] == 'climate.order.created':
      order = event['data']['object']
    elif event['type'] == 'climate.order.delayed':
      order = event['data']['object']
    elif event['type'] == 'climate.order.delivered':
      order = event['data']['object']
    elif event['type'] == 'climate.order.product_substituted':
      order = event['data']['object']
    elif event['type'] == 'climate.product.created':
      product = event['data']['object']
    elif event['type'] == 'climate.product.pricing_updated':
      product = event['data']['object']
    elif event['type'] == 'coupon.created':
      coupon = event['data']['object']
    elif event['type'] == 'coupon.deleted':
      coupon = event['data']['object']
    elif event['type'] == 'coupon.updated':
      coupon = event['data']['object']
    elif event['type'] == 'credit_note.created':
      credit_note = event['data']['object']
    elif event['type'] == 'credit_note.updated':
      credit_note = event['data']['object']
    elif event['type'] == 'credit_note.voided':
      credit_note = event['data']['object']
    elif event['type'] == 'customer.created':
      customer = event['data']['object']
    elif event['type'] == 'customer.deleted':
      customer = event['data']['object']
    elif event['type'] == 'customer.updated':
      customer = event['data']['object']
    elif event['type'] == 'customer.discount.created':
      discount = event['data']['object']
    elif event['type'] == 'customer.discount.deleted':
      discount = event['data']['object']
    elif event['type'] == 'customer.discount.updated':
      discount = event['data']['object']
    elif event['type'] == 'customer.source.created':
      source = event['data']['object']
    elif event['type'] == 'customer.source.deleted':
      source = event['data']['object']
    elif event['type'] == 'customer.source.expiring':
      source = event['data']['object']
    elif event['type'] == 'customer.source.updated':
      source = event['data']['object']
    elif event['type'] == 'customer.subscription.created':
      subscription = event['data']['object']
    elif event['type'] == 'customer.subscription.deleted':
      subscription = event['data']['object']
    elif event['type'] == 'customer.subscription.paused':
      subscription = event['data']['object']
    elif event['type'] == 'customer.subscription.pending_update_applied':
      subscription = event['data']['object']
    elif event['type'] == 'customer.subscription.pending_update_expired':
      subscription = event['data']['object']
    elif event['type'] == 'customer.subscription.resumed':
      subscription = event['data']['object']
    elif event['type'] == 'customer.subscription.trial_will_end':
      subscription = event['data']['object']
    elif event['type'] == 'customer.subscription.updated':
      subscription = event['data']['object']
    elif event['type'] == 'customer.tax_id.created':
      tax_id = event['data']['object']
    elif event['type'] == 'customer.tax_id.deleted':
      tax_id = event['data']['object']
    elif event['type'] == 'customer.tax_id.updated':
      tax_id = event['data']['object']
    elif event['type'] == 'customer_cash_balance_transaction.created':
      customer_cash_balance_transaction = event['data']['object']
    elif event['type'] == 'file.created':
      file = event['data']['object']
    elif event['type'] == 'financial_connections.account.created':
      account = event['data']['object']
    elif event['type'] == 'financial_connections.account.deactivated':
      account = event['data']['object']
    elif event['type'] == 'financial_connections.account.disconnected':
      account = event['data']['object']
    elif event['type'] == 'financial_connections.account.reactivated':
      account = event['data']['object']
    elif event['type'] == 'financial_connections.account.refreshed_balance':
      account = event['data']['object']
    elif event['type'] == 'financial_connections.account.refreshed_ownership':
      account = event['data']['object']
    elif event['type'] == 'financial_connections.account.refreshed_transactions':
      account = event['data']['object']
    elif event['type'] == 'identity.verification_session.canceled':
      verification_session = event['data']['object']
    elif event['type'] == 'identity.verification_session.created':
      verification_session = event['data']['object']
    elif event['type'] == 'identity.verification_session.processing':
      verification_session = event['data']['object']
    elif event['type'] == 'identity.verification_session.requires_input':
      verification_session = event['data']['object']
    elif event['type'] == 'identity.verification_session.verified':
      verification_session = event['data']['object']
    elif event['type'] == 'invoice.created':
      invoice = event['data']['object']
    elif event['type'] == 'invoice.deleted':
      invoice = event['data']['object']
    elif event['type'] == 'invoice.finalization_failed':
      invoice = event['data']['object']
    elif event['type'] == 'invoice.finalized':
      invoice = event['data']['object']
    elif event['type'] == 'invoice.marked_uncollectible':
      invoice = event['data']['object']
    elif event['type'] == 'invoice.overdue':
      invoice = event['data']['object']
    elif event['type'] == 'invoice.paid':
      invoice = event['data']['object']
    elif event['type'] == 'invoice.payment_action_required':
      invoice = event['data']['object']
    elif event['type'] == 'invoice.payment_failed':
      invoice = event['data']['object']
    elif event['type'] == 'invoice.payment_succeeded':
      invoice = event['data']['object']
    elif event['type'] == 'invoice.sent':
      invoice = event['data']['object']
    elif event['type'] == 'invoice.upcoming':
      invoice = event['data']['object']
    elif event['type'] == 'invoice.updated':
      invoice = event['data']['object']
    elif event['type'] == 'invoice.voided':
      invoice = event['data']['object']
    elif event['type'] == 'invoice.will_be_due':
      invoice = event['data']['object']
    elif event['type'] == 'invoiceitem.created':
      invoiceitem = event['data']['object']
    elif event['type'] == 'invoiceitem.deleted':
      invoiceitem = event['data']['object']
    elif event['type'] == 'issuing_authorization.created':
      issuing_authorization = event['data']['object']
    elif event['type'] == 'issuing_authorization.updated':
      issuing_authorization = event['data']['object']
    elif event['type'] == 'issuing_card.created':
      issuing_card = event['data']['object']
    elif event['type'] == 'issuing_card.updated':
      issuing_card = event['data']['object']
    elif event['type'] == 'issuing_cardholder.created':
      issuing_cardholder = event['data']['object']
    elif event['type'] == 'issuing_cardholder.updated':
      issuing_cardholder = event['data']['object']
    elif event['type'] == 'issuing_dispute.closed':
      issuing_dispute = event['data']['object']
    elif event['type'] == 'issuing_dispute.created':
      issuing_dispute = event['data']['object']
    elif event['type'] == 'issuing_dispute.funds_reinstated':
      issuing_dispute = event['data']['object']
    elif event['type'] == 'issuing_dispute.submitted':
      issuing_dispute = event['data']['object']
    elif event['type'] == 'issuing_dispute.updated':
      issuing_dispute = event['data']['object']
    elif event['type'] == 'issuing_token.created':
      issuing_token = event['data']['object']
    elif event['type'] == 'issuing_token.updated':
      issuing_token = event['data']['object']
    elif event['type'] == 'issuing_transaction.created':
      issuing_transaction = event['data']['object']
    elif event['type'] == 'issuing_transaction.updated':
      issuing_transaction = event['data']['object']
    elif event['type'] == 'mandate.updated':
      mandate = event['data']['object']
    elif event['type'] == 'payment_intent.amount_capturable_updated':
      payment_intent = event['data']['object']
    elif event['type'] == 'payment_intent.canceled':
      payment_intent = event['data']['object']
    elif event['type'] == 'payment_intent.created':
      payment_intent = event['data']['object']
    elif event['type'] == 'payment_intent.partially_funded':
      payment_intent = event['data']['object']
    elif event['type'] == 'payment_intent.payment_failed':
      payment_intent = event['data']['object']
    elif event['type'] == 'payment_intent.processing':
      payment_intent = event['data']['object']
    elif event['type'] == 'payment_intent.requires_action':
      payment_intent = event['data']['object']
    elif event['type'] == 'payment_intent.succeeded':
      payment_intent = event['data']['object']
    elif event['type'] == 'payment_link.created':
      payment_link = event['data']['object']
    elif event['type'] == 'payment_link.updated':
      payment_link = event['data']['object']
    elif event['type'] == 'payment_method.attached':
      payment_method = event['data']['object']
    elif event['type'] == 'payment_method.automatically_updated':
      payment_method = event['data']['object']
    elif event['type'] == 'payment_method.detached':
      payment_method = event['data']['object']
    elif event['type'] == 'payment_method.updated':
      payment_method = event['data']['object']
    elif event['type'] == 'payout.canceled':
      payout = event['data']['object']
    elif event['type'] == 'payout.created':
      payout = event['data']['object']
    elif event['type'] == 'payout.failed':
      payout = event['data']['object']
    elif event['type'] == 'payout.paid':
      payout = event['data']['object']
    elif event['type'] == 'payout.reconciliation_completed':
      payout = event['data']['object']
    elif event['type'] == 'payout.updated':
      payout = event['data']['object']
    elif event['type'] == 'person.created':
      person = event['data']['object']
    elif event['type'] == 'person.deleted':
      person = event['data']['object']
    elif event['type'] == 'person.updated':
      person = event['data']['object']
    elif event['type'] == 'plan.created':
      plan = event['data']['object']
    elif event['type'] == 'plan.deleted':
      plan = event['data']['object']
    elif event['type'] == 'plan.updated':
      plan = event['data']['object']
    elif event['type'] == 'price.created':
      price = event['data']['object']
    elif event['type'] == 'price.deleted':
      price = event['data']['object']
    elif event['type'] == 'price.updated':
      price = event['data']['object']
    elif event['type'] == 'product.created':
      product = event['data']['object']
    elif event['type'] == 'product.deleted':
      product = event['data']['object']
    elif event['type'] == 'product.updated':
      product = event['data']['object']
    elif event['type'] == 'promotion_code.created':
      promotion_code = event['data']['object']
    elif event['type'] == 'promotion_code.updated':
      promotion_code = event['data']['object']
    elif event['type'] == 'quote.accepted':
      quote = event['data']['object']
    elif event['type'] == 'quote.canceled':
      quote = event['data']['object']
    elif event['type'] == 'quote.created':
      quote = event['data']['object']
    elif event['type'] == 'quote.finalized':
      quote = event['data']['object']
    elif event['type'] == 'quote.will_expire':
      quote = event['data']['object']
    elif event['type'] == 'radar.early_fraud_warning.created':
      early_fraud_warning = event['data']['object']
    elif event['type'] == 'radar.early_fraud_warning.updated':
      early_fraud_warning = event['data']['object']
    elif event['type'] == 'refund.created':
      refund = event['data']['object']
    elif event['type'] == 'refund.updated':
      refund = event['data']['object']
    elif event['type'] == 'reporting.report_run.failed':
      report_run = event['data']['object']
    elif event['type'] == 'reporting.report_run.succeeded':
      report_run = event['data']['object']
    elif event['type'] == 'review.closed':
      review = event['data']['object']
    elif event['type'] == 'review.opened':
      review = event['data']['object']
    elif event['type'] == 'setup_intent.canceled':
      setup_intent = event['data']['object']
    elif event['type'] == 'setup_intent.created':
      setup_intent = event['data']['object']
    elif event['type'] == 'setup_intent.requires_action':
      setup_intent = event['data']['object']
    elif event['type'] == 'setup_intent.setup_failed':
      setup_intent = event['data']['object']
    elif event['type'] == 'setup_intent.succeeded':
      setup_intent = event['data']['object']
    elif event['type'] == 'sigma.scheduled_query_run.created':
      scheduled_query_run = event['data']['object']
    elif event['type'] == 'source.canceled':
      source = event['data']['object']
    elif event['type'] == 'source.chargeable':
      source = event['data']['object']
    elif event['type'] == 'source.failed':
      source = event['data']['object']
    elif event['type'] == 'source.mandate_notification':
      source = event['data']['object']
    elif event['type'] == 'source.refund_attributes_required':
      source = event['data']['object']
    elif event['type'] == 'source.transaction.created':
      transaction = event['data']['object']
    elif event['type'] == 'source.transaction.updated':
      transaction = event['data']['object']
    elif event['type'] == 'subscription_schedule.aborted':
      subscription_schedule = event['data']['object']
    elif event['type'] == 'subscription_schedule.canceled':
      subscription_schedule = event['data']['object']
    elif event['type'] == 'subscription_schedule.completed':
      subscription_schedule = event['data']['object']
    elif event['type'] == 'subscription_schedule.created':
      subscription_schedule = event['data']['object']
    elif event['type'] == 'subscription_schedule.expiring':
      subscription_schedule = event['data']['object']
    elif event['type'] == 'subscription_schedule.released':
      subscription_schedule = event['data']['object']
    elif event['type'] == 'subscription_schedule.updated':
      subscription_schedule = event['data']['object']
    elif event['type'] == 'tax.settings.updated':
      settings = event['data']['object']
    elif event['type'] == 'tax_rate.created':
      tax_rate = event['data']['object']
    elif event['type'] == 'tax_rate.updated':
      tax_rate = event['data']['object']
    elif event['type'] == 'terminal.reader.action_failed':
      reader = event['data']['object']
    elif event['type'] == 'terminal.reader.action_succeeded':
      reader = event['data']['object']
    elif event['type'] == 'test_helpers.test_clock.advancing':
      test_clock = event['data']['object']
    elif event['type'] == 'test_helpers.test_clock.created':
      test_clock = event['data']['object']
    elif event['type'] == 'test_helpers.test_clock.deleted':
      test_clock = event['data']['object']
    elif event['type'] == 'test_helpers.test_clock.internal_failure':
      test_clock = event['data']['object']
    elif event['type'] == 'test_helpers.test_clock.ready':
      test_clock = event['data']['object']
    elif event['type'] == 'topup.canceled':
      topup = event['data']['object']
    elif event['type'] == 'topup.created':
      topup = event['data']['object']
    elif event['type'] == 'topup.failed':
      topup = event['data']['object']
    elif event['type'] == 'topup.reversed':
      topup = event['data']['object']
    elif event['type'] == 'topup.succeeded':
      topup = event['data']['object']
    elif event['type'] == 'transfer.created':
      transfer = event['data']['object']
    elif event['type'] == 'transfer.reversed':
      transfer = event['data']['object']
    elif event['type'] == 'transfer.updated':
      transfer = event['data']['object']
    elif event['type'] == 'treasury.credit_reversal.created':
      credit_reversal = event['data']['object']
    elif event['type'] == 'treasury.credit_reversal.posted':
      credit_reversal = event['data']['object']
    elif event['type'] == 'treasury.debit_reversal.completed':
      debit_reversal = event['data']['object']
    elif event['type'] == 'treasury.debit_reversal.created':
      debit_reversal = event['data']['object']
    elif event['type'] == 'treasury.debit_reversal.initial_credit_granted':
      debit_reversal = event['data']['object']
    elif event['type'] == 'treasury.financial_account.closed':
      financial_account = event['data']['object']
    elif event['type'] == 'treasury.financial_account.created':
      financial_account = event['data']['object']
    elif event['type'] == 'treasury.financial_account.features_status_updated':
      financial_account = event['data']['object']
    elif event['type'] == 'treasury.inbound_transfer.canceled':
      inbound_transfer = event['data']['object']
    elif event['type'] == 'treasury.inbound_transfer.created':
      inbound_transfer = event['data']['object']
    elif event['type'] == 'treasury.inbound_transfer.failed':
      inbound_transfer = event['data']['object']
    elif event['type'] == 'treasury.inbound_transfer.succeeded':
      inbound_transfer = event['data']['object']
    elif event['type'] == 'treasury.outbound_payment.canceled':
      outbound_payment = event['data']['object']
    elif event['type'] == 'treasury.outbound_payment.created':
      outbound_payment = event['data']['object']
    elif event['type'] == 'treasury.outbound_payment.expected_arrival_date_updated':
      outbound_payment = event['data']['object']
    elif event['type'] == 'treasury.outbound_payment.failed':
      outbound_payment = event['data']['object']
    elif event['type'] == 'treasury.outbound_payment.posted':
      outbound_payment = event['data']['object']
    elif event['type'] == 'treasury.outbound_payment.returned':
      outbound_payment = event['data']['object']
    elif event['type'] == 'treasury.outbound_transfer.canceled':
      outbound_transfer = event['data']['object']
    elif event['type'] == 'treasury.outbound_transfer.created':
      outbound_transfer = event['data']['object']
    elif event['type'] == 'treasury.outbound_transfer.expected_arrival_date_updated':
      outbound_transfer = event['data']['object']
    elif event['type'] == 'treasury.outbound_transfer.failed':
      outbound_transfer = event['data']['object']
    elif event['type'] == 'treasury.outbound_transfer.posted':
      outbound_transfer = event['data']['object']
    elif event['type'] == 'treasury.outbound_transfer.returned':
      outbound_transfer = event['data']['object']
    elif event['type'] == 'treasury.received_credit.created':
      received_credit = event['data']['object']
    elif event['type'] == 'treasury.received_credit.failed':
      received_credit = event['data']['object']
    elif event['type'] == 'treasury.received_credit.succeeded':
      received_credit = event['data']['object']
    elif event['type'] == 'treasury.received_debit.created':
      received_debit = event['data']['object']
    # ... handle other event types
    else:
      print('Unhandled event type {}'.format(event['type']))

    return jsonify(success=True)

https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862

APKTIDusWyVAxxo7T74FLbHNqxcpPm8106sRDWV8WZnY-m_ TUQ contact key apple
Run payment id
po_1OZNhvGF83d3fsgWC9jdBgcQ
Run bank data 

DJqIeyHlhjb55r0K
Routing number
031101279
ID
ba_1OR7BGGF83d3fsgWxwDM4lDf

AGENCY WEBHOOK

Download #! /usr/bin/env python3.6

Python 3.6 or newer required.

import json import os import stripe

This is your test secret API key.

stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'

Replace this endpoint secret with your endpoint's unique secret

If you are testing with the CLI, find the secret by running 'stripe listen'

If you are using an endpoint defined with the API or dashboard, look in your webhook settings

at https://dashboard.stripe.com/webhooks

endpoint_secret = 'whsec_...' from flask import Flask, jsonify, request

app = Flask(name)

@app.route('/webhook', methods=['POST']) def webhook(): event = None payload = request.data

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
https://github.com/grateful345/AGENCY-WEBHOOK.git echo "# AGENCY-WEBHOOK" >> README.md git init git add README.md git commit -m "first commit" git branch -M main git remote add origin https://github.com/grateful345/AGENCY-WEBHOOK.git git push -u origin main …or push an existing repository from the command line git remote add origin https://github.com/grateful345/AGENCY-WEBHOOK.git git branch -M main git push -u origin main Install the Stripe Python package Install the Stripe package and import it in your code. Alternatively, if you’re starting from scratch and need a requirements.txt file, download the project files using the link in the code editor.

pip

GitHub Install the package via pip: pip3 install stripe

Server Create a new endpoint

settings A webhook is an endpoint on your server that receives requests from Stripe, notifying you about events that happen on your account such as a customer disputing a charge or a successful recurring payment. Add a new endpoint to your server and make sure it’s publicly accessible so we can send unauthenticated POST requests. Server 2 Handle requests from Stripe Read the event data Stripe sends the event data in the request body. Each event is structured as an Event object with a type, id, and related Stripe resource nested under data. Server Handle the event As soon as you have the event object, check the type to know what kind of event happened. You can use one webhook to handle several different event types at once, or set up individual endpoints for specific events. Server Return a 200 response Build and run your server to test the endpoint at http://localhost:4242/webhook. python3 -m flask run --port=4242

Server Download the CLI Use the Stripe CLI to test your webhook locally. Download the CLI and log in with your Stripe account. Alternatively, use a service like ngrok to make your local endpoint publicly accessible. stripe login

Run in the Stripe Shell Server Forward events to your webhook

settings Set up event forwarding with the CLI to send all Stripe events in testmode to your local webhook endpoint. stripe listen --forward-to localhost:4242/webhook

Run in the Stripe Shell Server Simulate events

settings Use the CLI to simulate specific events that test your webhook application logic by sending a POST request to your webhook endpoint with a mocked Stripe event object. stripe trigger payment_intent.succeeded

Run in the Stripe Shell Server Congratulations! Stripe-Signature: t=1492774577, v1=5257a869e7ecebeda32affa62cdca3fa51cad7e77a0e56ff536d0ce8e108d8bd, v0=6ffbb59b2300aae63f272406069a9788598b792a944a07aba816edb039989a39

You have a basic webhook endpoint ready to accept events from Stripe. Now add the application logic that your business needs to handle the events you care the most about. You can also extend your endpoint with the steps b https:///<webhookhttps://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862-endpoint> README.md | 3 +++ 1 file changed, 3 insertions(+)

diff --git a/README.md b/README.md index 806cda8..9b1de77 100644 --- a/README.md +++ b/README.md @@ -121,3 +121,6 @@ Run in the Stripe Shell Server Congratulations! You have a basic webhook endpoint ready to accept events from Stripe. Now add the application logic that your business needs to handle the events you care the most about. You can also extend your endpoint with the steps b + +https:///webhookhttps://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862-endpoint

Set your secret key. Remember to switch to your live secret key in production.

See your keys here: https://dashboard.stripe.com/apikeys

stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'

endpoint = stripe.WebhookEndpoint.create( url='https://example.com/my/webhook/endpoint', enabled_events=[ 'payment_intent.payment_failed', 'payment_intent.succeeded', ], )

Set your secret key. Remember to switch to your live secret key in production.

See your keys here: https://dashboard.stripe.com/apikeys

stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'

from django.http import HttpResponse

If you are testing your webhook locally with the Stripe CLI you

can find the endpoint's secret by running stripe listen

Otherwise, find your endpoint's secret in your webhook settings in the Developer Dashboard

endpoint_secret = 'whsec_...'

Using Django

@csrf_exempt def my_webhook_view(request): payload = request.body sig_header = request.META['t=1492774577, v1=5257a869e7ecebeda32affa62cdca3fa51cad7e77a0e56ff536d0ce8e108d8bd, v0=6ffbb59b2300aae63f272406069a9788598b792a944a07aba816edb039989a39'] event = None

try: event = stripe.Webhook.construct_event( payload, sig_header, endpoint_secret ) except ValueError as e: # Invalid payload print('Error parsing payload: {}'.format(str(e))) return HttpResponse(status=400) except stripe.error.SignatureVerificationError as e: # Invalid signature print('Error verifying webhook signature: {}'.format(str(e))) return HttpResponse(status=400)

Handle the event

if event.type == 'payment_intent.succeeded': payment_intent = event.data.object # contains a stripe.PaymentIntent print('PaymentIntent was successful!') elif event.type == 'payment_method.attached': payment_method = event.data.object # contains a stripe.PaymentMethod print('PaymentMethod was attached to a Customer!')

... handle other event types

else: print('Unhandled event type {}'.format(event.type)) import json

Webhooks are always sent as HTTP POST requests, so ensure

that only POST requests reach your webhook view by

decorating webhook() with require_POST.

To ensure that the webhook view can receive webhooks,

also decorate webhook() with csrf_exempt.

@require_POST @csrf_exempt def webhook(request): import json from django.http import HttpResponse

Using Django

@csrf_exempt def my_webhook_view(request): payload = request.body event = None

try: event = stripe.Event.construct_from( json.loads(payload), stripe.api_key ) except ValueError as e: # Invalid payload return HttpResponse(status=400)

Handle the event

if event.type == 'payment_intent.succeeded': payment_intent = event.data.object # contains a stripe.PaymentIntent # Then define and call a method to handle the successful payment intent. # handle_payment_intent_succeeded(payment_intent) elif event.type == 'payment_method.attached': payment_method = event.data.object # contains a stripe.PaymentMethod # Then define and call a method to handle the successful attachment of a PaymentMethod. # handle_payment_method_attached(payment_method)

... handle other event types

else: print('Unhandled event type {}'.format(event.type))

return HttpResponse(status=200) stripe listen --forward-to localhost:4242/stripe_webhooks stripe listen --events payment_intent.created,customer.created,payment_intent.succeeded,checkout.session.completed,payment_intent.payment_failed
--forward-to localhost:4242/webhook stripe listen --load-from-webhooks-api --forward-to localhost:5000 Ready! Your webhook signing secret is '{{whsec_ 5V2GHGaht2mGJGNOmesTtTaxuJWFRssS}}' (^C to quit)

stripe trigger payment_intent.succeeded Running fixture for: payment_intent Trigger succeeded! Check dashboard for event details. https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862>/<whsec_ 5V2GHGaht2mGJGNOmesTtTaxuJWFRssS>)

Process webhook data in request.body return HttpResponse(status=200)

Set your secret key. Remember to switch to your live secret key in production.

See your keys here: https://dashboard.stripe.com/apikeys

stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'

from django.http import HttpResponse

If you are testing your webhook locally with the Stripe CLI you

can find the endpoint's secret by running stripe listen

Otherwise, find your endpoint's secret in your webhook settings in the Developer Dashboard

endpoint_secret = 'whsec_...'

Using Django

@csrf_exempt def my_webhook_view(request): payload = request.body sig_header = request.META['t=1492774577, v1=5257a869e7ecebeda32affa62cdca3fa51cad7e77a0e56ff536d0ce8e108d8bd, v0=6ffbb59b2300aae63f272406069a9788598b792a944a07aba816edb039989a39'] event = None

try: event = stripe.Webhook.construct_event( payload, sig_header, endpoint_secret ) except ValueError as e: # Invalid payload print('Error parsing payload: {}'.format(str(e))) return HttpResponse(status=400) except stripe.error.SignatureVerificationError as e: # Invalid signature print('Error verifying webhook signature: {}'.format(str(e))) return HttpResponse(status=400)

Handle the event

if event.type == 'payment_intent.succeeded': payment_intent = event.data.object # contains a stripe.PaymentIntent print('PaymentIntent was successful!') elif event.type == 'payment_method.attached': payment_method = event.data.object # contains a stripe.PaymentMethod print('PaymentMethod was attached to a Customer!')

... handle other event types

else: print('Unhandled event type {}'.format(event.type))

return HttpResponse(status=200) import json

Webhooks are always sent as HTTP POST requests, so ensure

that only POST requests reach your webhook view by

decorating webhook() with require_POST.

To ensure that the webhook view can receive webhooks,

also decorate webhook() with csrf_exempt.

@require_POST @csrf_exempt def webhook(request): THE EVENT OBJECT { "id": "evt_1NG8Du2eZvKYlo2CUI79vXWy", "object": "event", "api_version": "2019-02-19", "created": 1686089970, "data": { "object": { "id": "seti_1NG8Du2eZvKYlo2C9XMqbR0x", "object": "setup_intent", "application": null, "automatic_payment_methods": null, "cancellation_reason": null, "client_secret": "seti_1NG8Du2eZvKYlo2C9XMqbR0x_secret_O2CdhLwGFh2Aej7bCY7qp8jlIuyR8DJ", "created": 1686089970, "customer": null, "description": null, "flow_directions": null, "last_setup_error": null, "latest_attempt": null, "livemode": false, "mandate": null, "metadata": {}, "next_action": null, "on_behalf_of": null, "payment_method": "pm_1NG8Du2eZvKYlo2CYzzldNr7", "payment_method_options": { "acss_debit": { "currency": "cad", "mandate_options": { "interval_description": "First day of every month", "payment_schedule": "interval", "transaction_type": "personal" }, "verification_method": "automatic" } }, "payment_method_types": [ "acss_debit" ], "single_use_mandate": null, "status": "requires_confirmation", "usage": "off_session" } }, "livemode": false, "pending_webhooks": 0, "request": { "id": null, "idempotency_key": null }, "type": "setup_intent.created"

Process webhook data in request.body



gh pr checkout 15

rew install gh

gh auth setup-git

gh auth setup-git [flags]
This command configures git to use GitHub CLI as a credential helper. For more information on git credential helpers please reference: https://git-scm.com/docs/gitcredentials.

By default, GitHub CLI will be set as the credential helper for all authenticated hosts. If there is no authenticated hosts the command fails with an error.

Alternatively, use the --hostname flag to specify a single host to be configured. If the host is not authenticated with, the command fails with an error.

Options

-f,  --force <--hostname> 
Force setup even if the host is not known. Must be used in conjunction with --hostname
-h,  --hostname <string> 
The hostname to configure git for
Examples

# Configure git to use GitHub CLI as the credential helper for all authenticated hosts
$ gh auth setup-git

# Configure git to use GitHub CLI as the credential helper for enterprise.internal host
$ gh auth setup-git --hostname enterprise.internal
See also

[gh auth](https://cli.github.com/manual/gh_auth)

sudo ./svc.sh install
Alternatively, the command takes an optional user argument to install the service as a different user.
./svc.sh install USERNAME
[Starting the service](https://docs.github.com/en/actions/creating-actions/metadata-syntax-for-github-actions#starting-the-service)

Start the service with the following command:

sudo ./svc.sh start
[Checking the status of the service](https://docs.github.com/en/actions/creating-actions/metadata-syntax-for-github-actions#checking-the-status-of-the-service)

Check the status of the service with the following command:

sudo ./svc.sh status
For more information on viewing the status of your self-hosted runner, see "[Monitoring and troubleshooting self-hosted runners](https://docs.github.com/en/actions/hosting-your-own-runners/managing-self-hosted-runners/monitoring-and-troubleshooting-self-hosted-runners)."

[Stopping the service](https://docs.github.com/en/actions/creating-actions/metadata-syntax-for-github-actions#stopping-the-service)

Stop the service with the following command:

sudo ./svc.sh stop
[Uninstalling the service](https://docs.github.com/en/actions/creating-actions/metadata-syntax-for-github-actions#uninstalling-the-service)

Stop the service if it is currently running.
Uninstall the service with the following command:
sudo ./svc.sh uninstall
FROM mcr.microsoft.com/dotnet/runtime-deps:6.0 as build

# Replace value with the latest runner release version
# source: https://github.com/actions/runner/releases
# ex: 2.303.0
ARG RUNNER_VERSION=""
ARG RUNNER_ARCH="x64"
# Replace value with the latest runner-container-hooks release version
# source: https://github.com/actions/runner-container-hooks/releases
# ex: 0.3.1
ARG RUNNER_CONTAINER_HOOKS_VERSION=""

ENV DEBIAN_FRONTEND=noninteractive
ENV RUNNER_MANUALLY_TRAP_SIG=1
ENV ACTIONS_RUNNER_PRINT_LOG_TO_STDOUT=1

RUN apt update -y && apt install curl unzip -y

RUN adduser --disabled-password --gecos "" --uid 1001 runner \
    && groupadd docker --gid 123 \
    && usermod -aG sudo runner \
    && usermod -aG docker runner \
    && echo "%sudo   ALL=(ALL:ALL) NOPASSWD:ALL" > /etc/sudoers \
    && echo "Defaults env_keep += \"DEBIAN_FRONTEND\"" >> /etc/sudoers

WORKDIR /home/runner

RUN curl -f -L -o runner.tar.gz https://github.com/actions/runner/releases/download/v${RUNNER_VERSION}/actions-runner-linux-${RUNNER_ARCH}-${RUNNER_VERSION}.tar.gz \
    && tar xzf ./runner.tar.gz \
    && rm runner.tar.gz

RUN curl -f -L -o runner-container-hooks.zip https://github.com/actions/runner-container-hooks/releases/download/v${RUNNER_CONTAINER_HOOKS_VERSION}/actions-runner-hooks-k8s-${RUNNER_CONTAINER_HOOKS_VERSION}.zip \
    && unzip ./runner-container-hooks.zip -d ./k8s \
    && rm runner-container-hooks.zip

USER runner
Copyright 2019 Moto Ishizawa

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
Press alt+up to activate
NAMESPACE="arc-systems"
helm install arc \
    --namespace "${AGENCY WEBHOOK}" \
    --create-namespace \
    oci://ghcr.io/actions/actions-runner-controller-charts/gha-runner-scale-set-controller

INSTALLATION_NAME="arc-runner-set"
NAMESPACE="arc-runners"
GITHUB_CONFIG_URL="https://github.com/<your_enterprise/org/repo>"
GITHUB_PAT="<PAT>"
helm install "${BHAHZGCJZK3BEVS7IRGZMKDF6USLO /  GitHub Runner tokens / BHAHZGDHHICG3LFF53OICRLF6UR24}" \
    --namespace "${AGENCY WEBHOOK}
    --create-namespace \
    --set githubConfigUrl="${GITHUB_CONFIG_URL}" \
    --set githubConfigSecret.github_token="${BHAHZGCJZK3BEVS7IRGZMKDF6USLO /  GitHub Runner tokens / BHAHZGDHHICG3LFF53OICRLF6UR24}" \
    oci://ghcr.io/actions/actions-runner-controller-charts/gha-runner-scale-set
helm list -A
kubectl get pods -n arc-systems
name: Actions Runner Controller Demo
on:
  workflow_dispatch:

jobs:
  Explore-GitHub-Actions:
    # You need to use the INSTALLATION_NAME from the previous step
    runs-on: arc-runner-set
    steps:
    - run: echo "🎉 This job uses runner scale set runners!"

kubectl get pods -n arc-runners
name: Run commands on different operating systems
on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  Run-npm-on-Ubuntu:
    name: Run npm on Ubuntu
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: '14'
      - run: npm help

  Run-PSScriptAnalyzer-on-Windows:
    name: Run PSScriptAnalyzer on Windows
    runs-on: windows-latest
    steps:
      - uses: actions/checkout@v4
      - name: Install PSScriptAnalyzer module
        shell: pwsh
        run: |
          Set-PSRepository PSGallery -InstallationPolicy Trusted
          Install-Module PSScriptAnalyzer -ErrorAction Stop
      - name: Get list of rules
        shell: pwsh
        run: |
          Get-ScriptAnalyzerRule
The following example demonstrates how to install Brew packages and casks as part of a job.

name: Build on macOS
on: push

jobs:
  build:
    runs-on: macos-latest
    steps:
      - name: Check out repository code
        uses: actions/checkout@v4
      - name: Install GitHub CLI
        run: |
          brew update
          brew install gh
      - name: Install Microsoft Edge
        run: |
          brew update
          brew install --cask microsoft-edge
Installing software on Windows runners

The following example demonstrates how to use Chocolatey to install the GitHub CLI as part of a job.

name: Build on Windows
on: push
jobs:
  build:
    runs-on: windows-latest
    steps:
      - run: choco install gh
      - run: gh version

      github.com
api.github.com
*.actions.githubusercontent.com

codeload.github.com
results-receiver.actions.githubusercontent.com
*.blob.core.windows.net
objects.githubusercontent.com
objects-origin.githubusercontent.com
github-releases.githubusercontent.com
github-registry-files.githubusercontent.com
*.actions.githubusercontent.com
Needed for downloading or publishing packages or containers to GitHub Packages:

Shell
*.pkg.github.com
ghcr.io
Needed for Git Large File Storage

Shell
github-cloud.githubusercontent.com
github-cloud.s3.amazonaws.com


# AGENCY-WEBHOOK
API ID  KEY SECRET KEY : 	pst_test_YWNjdF8xTTJKVGtMa2RJd0h1N2l4LE81ZEdIalZ6NlVuMUdjM3c3WkRnN0ZYRHZxRURwTXo_00gNK2DWAV
cr_2coazssVIEva7q1Fw2nwytLIq2N BOT USER bot_2coayXt1oJzWKxgTYyanAjQ3KPV 

2dvYx8b2Jxcr6rQ7rMK4g0f5lxd_6MRbqiQJdYkspcWN1vb65 Keith Bieszczat AUTH TOKEN 

cr_2dvYx8b2Jxcr6rQ7rMK4g0f5lxd bot_2dvYwRDLFZfzm3QuX1Yfq0xCPZh



2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd API KEY
AGENCY-WEBHOOK
git config --global --unset gpg.format
Use the gpg --list-secret-keys --keyid-format=long command to list the long form of the GPG keys for which you have both a public and private key. A private key is required for signing commits or tags.
Shell
gpg --list-secret-keys --keyid-format=long
Note: Some GPG installations on Linux may require you to use gpg2 --list-keys --keyid-format LONG to view a list of your existing keys instead. In this case you will also need to configure Git to use gpg2 by running git config --global gpg.program gpg2.
From the list of GPG keys, copy the long form of the GPG key ID you'd like to use. In this example, the GPG key ID is 3AA5C34371567BD2:
Shell

$ gpg --list-secret-keys --keyid-format=long
/Users/hubot/.gnupg/secring.gpg
------------------------------------
sec   4096R/3AA5C34371567BD2 2016-03-10 [expires: 2017-03-10]
uid                          Hubot <hubot@example.com>
ssb   4096R/4BB6D45482678BE3 2016-03-10
To set your primary GPG signing key in Git, paste the text below, substituting in the GPG primary key ID you'd like to use. In this example, the GPG key ID is 3AA5C34371567BD2:
git config --global user.signingkey 3AA5C34371567BD2
Alternatively, when setting a subkey include the ! suffix. In this example, the GPG subkey ID is 4BB6D45482678BE3:
git config --global user.signingkey 4BB6D45482678BE3!
Optionally, to configure Git to sign all commits by default, enter the following command:
git config --global commit.gpgsign true
For more information, see "Signing commits."
To add your GPG key to your .bashrc startup file, run the following command:
[ -f ~/.bashrc ] && echo -e '\nexport GPG_TTY=$(tty)' >> ~/.bashrc
Telling Git about your SSH key

You can use an existing SSH key to sign commits and tags, or generate a new one specifically for signing. For more information, see "Generating a new SSH key and adding it to the ssh-agent."

Note: SSH signature verification is available in Git 2.34 or later. To update your version of Git, see the Git website.
Open Terminal.
Configure Git to use SSH to sign commits and tags:
git config --global gpg.format ssh
To set your SSH signing key in Git, paste the text below, substituting /PATH/TO/.SSH/KEY.PUB with the path to the public key you'd like to use.
git config --global user.signingkey /PATH/TO/.SSH/KEY.PUB
Telling Git about your X.509 key

You can use smimesign to sign commits and tags using S/MIME.

Note: S/MIME signature verification is available in Git 2.19 or later. To update your version of Git, see the Git website.
Install smimesign.
Open Terminal.
Configure Git to use S/MIME to sign commits and tags. In Git 2.19 or later, use the git config gpg.x509.program and git config gpg.format commands:
To use S/MIME to sign for all repositories:
git config --global gpg.x509.program smimesign
git config --global gpg.format x509
To use S/MIME to sign for a single repository:
cd PATH-TO-REPOSITORY
git config --local gpg.x509.program smimesign
git config --local gpg.format x509
In Git 2.18 or earlier, use the git config gpg.program command:
To use S/MIME to sign for all repositories:
git config --global gpg.program smimesign
To use S/MIME to sign for a single repository:
cd  PATH-TO-REPOSITORY
git config --local gpg.program smimesign
If you're using an X.509 key that matches your committer identity, you can begin signing commits and tags.
If you're not using an X.509 key that matches your committer identity, list X.509 keys for which you have both a certificate and private key using the smimesign --list-keys command.
smimesign --list-keys
From the list of X.509 keys, copy the certificate ID of the X.509 key you'd like to use. In this example, the certificate ID is 0ff455a2708394633e4bb2f88002e3cd80cbd76f:
$ smimesign --list-keys
             ID: 0ff455a2708394633e4bb2f88002e3cd80cbd76f
            S/N: a2dfa7e8c9c4d1616f1009c988bb70f
      Algorithm: SHA256-RSA
       Validity: 2017-11-22 00:00:00 +0000 UTC - 2020-11-22 12:00:00 +0000 UTC
         Issuer: CN=DigiCert SHA2 Assured ID CA,OU=www.digicert.com,O=DigiCert Inc,C=US
        Subject: CN=Octocat,O=GitHub\, Inc.,L=San Francisco,ST=California,C=US
         Emails: octocat@github.com
To set your X.509 signing key in Git, paste the text below, substituting in the certificate ID you copied earlier.
To use your X.509 key to sign for all repositories:
git config --global user.signingkey 0ff455a2708394633e4bb2f88002e3cd80cbd76f
To use your X.509 key to sign for a single repository:
cd  PATH-TO-REPOSITORY
git config --local user.signingkey 0ff455a2708394633e4bb2f88002e3cd80cbd76fAPI ID KEY SECRET KEY : pst_test_YWNjdF8xTTJKVGtMa2RJd0h1N2l4LE81ZEdIalZ6NlVuMUdjM3c3WkRnN0ZYRHZxRURwTXo_00gNK2DWAV

HystrixCommand command = new HystrixCommand(arg1, arg2);

HystrixObservableCommand command = new HystrixObservableCommand(arg1, arg2);

K value = command.execute(); Future fValue = command.queue(); Observable ohValue = command.observe(); //hot observable Observable ocValue = command.toObservable(); //cold observable Account account = new UserGetAccount(accountId).execute();

//or

Observable accountObservable = new UserGetAccount(accountId).observe();

K value = command.execute(); Future fValue = command.queue(); Observable ohValue = command.observe(); //hot observable Observable ocValue = command.toObservable(); //cold observable


From 160bf0313c2cb0c55b440678a3b91e8b640ac131 Mon Sep 17 00:00:00 2001
From: keith T bieszczat sr <163609752+grateful345@users.noreply.github.com>
Date: Tue, 19 Mar 2024 19:41:11 -0500
Subject: [PATCH] Update README.md

cr_2coazssVIEva7q1Fw2nwytLIq2N BOT USER bot_2coayXt1oJzWKxgTYyanAjQ3KPV

2dvYx8b2Jxcr6rQ7rMK4g0f5lxd_6MRbqiQJdYkspcWN1vb65 Keith Bieszczat AUTH TOKEN

cr_2dvYx8b2Jxcr6rQ7rMK4g0f5lxd bot_2dvYwRDLFZfzm3QuX1Yfq0xCPZh

2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd API KEY
---
 README.md | 405 ++++++++++++++++++++++++++++++++++++++++++++++++++++++
 1 file changed, 405 insertions(+)

diff --git a/README.md b/README.md
index 7ab556e..71b805e 100644
--- a/README.md
+++ b/README.md
@@ -1,4 +1,409 @@
 # AGENCY-WEBHOOK
+
+
+Repository files navigation
+
+README
+AGENCY-WEBHOOK
+
+API ID KEY SECRET KEY : pst_test_YWNjdF8xTTJKVGtMa2RJd0h1N2l4LE81ZEdIalZ6NlVuMUdjM3c3WkRnN0ZYRHZxRURwTXo_00gNK2DWAV
+
+HystrixCommand command = new HystrixCommand(arg1, arg2);
+
+HystrixObservableCommand command = new HystrixObservableCommand(arg1, arg2);
+
+K value = command.execute(); Future fValue = command.queue(); Observable ohValue = command.observe(); //hot observable Observable ocValue = command.toObservable(); //cold observable Account account = new UserGetAccount(accountId).execute();
+
+//or
+
+Observable accountObservable = new UserGetAccount(accountId).observe();
+
+K value = command.execute(); Future fValue = command.queue(); Observable ohValue = command.observe(); //hot observable Observable ocValue = command.toObservable(); //cold observable
+
+apiVersion: networking.k8s.io/v1 kind: Ingress metadata: name: example-ingress annotations: k8s.ngrok.com/modules: ngrok-module-set spec: ingressClassName: ngrok rules: - host: app.example.com http: paths: - path: / pathType: Prefix backend: service: name: example-service port: number: 80
+
+kind: NgrokModuleSet apiVersion: ingress.k8s.ngrok.com/v1alpha1 metadata: name: ngrok-module-set modules: oauth: google: optionsPassthrough: false inactivityTimeout: 4h maximumDuration: 24h authCheckInterval: 1h apiVersion: networking.k8s.io/v1 kind: Ingress metadata: name: example-ingress annotations: k8s.ngrok.com/modules: ngrok-module-set spec: ingressClassName: ngrok rules: - host: your-domain.ngrok.app http: paths: - path: / pathType: Prefix backend: service: name: example-service port: number: 80
+
+apiVersion: v1 kind: Service metadata: name: example-service annotations: k8s.ngrok.com/app-protocols: '{"example-https-port":"HTTPS"}' spec: ports: - name: example-https-port port: 443 protocol: TCP targetPort: 8443 selector: app-name: some-example-app-label
+
+apiVersion: networking.k8s.io/v1 kind: Ingress metadata: name: example-ingress annotations: k8s.ngrok.com/modules: ngrok-module-set spec: ingressClassName: ngrok rules: - host: app.example.com http: paths: - path: / pathType: Prefix backend: service: name: example-service port: number: 443
+
+kind: NgrokModuleSet apiVersion: ingress.k8s.ngrok.com/v1alpha1 metadata: name: ngrok-module-set modules: headers: request: add: host: "localhost"
+
+apiVersion: networking.k8s.io/v1 kind: Ingress metadata: name: example-ingress annotations: k8s.ngrok.com/modules: ngrok-module-set spec: ingressClassName: ngrok rules: - host: your-domain.ngrok.app http: paths: - path: / pathType: Prefix backend: service: name: example-service port: number: 80
+
+ngrok http 80 --request-header-remove "foo" --request-header-add "foo: new-value" ssh -R 443:localhost:80 v2@connect.ngrok-agent.com http ssh -R example.ngrok.app:443:localhost:80 v2@connect.ngrok-agent.com http ssh -R 443:localhost:80 v2@connect.ngrok-agent.com http
+--basic-auth "username1:password1"
+--basic-auth "username2:password2" ssh -R 443:localhost:80 v2@connect.ngrok-agent.com http --oauth=google ssh -R 0:192.168.1.2:80 v2@connect.ngrok-agent.com http
+
+ssh -R 0:localhost:22 v2@connect.ngrok-agent.com tcp ssh -R 1.tcp.eu.ngrok.io:12345:localhost:3389 connect.eu.ngrok-agent.com tcp ssh -R app.example.com:443:localhost:443 v2@connect.ngrok-agent.com tls ssh -R 443:localhost:80 v2@connect.eu.ngrok-agent.com http
+
+This will cause the HTTP request in this case to become:
+
+GET / HTTP/1.1 host: example.ngrok.app foo: new-value
+
+ngrok http https://httpbin.org --domain your-domain.ngrok.app
+
+In another terminal, curl that endpoint:
+
+curl https://your-domain.ngrok.app/headers
+
+{ "headers": { "Accept": "/", "Accept-Encoding": "gzip", "Host": "your-domain.ngrok.app", "User-Agent": "curl/7.85.0", "X-Amzn-Trace-Id": "Root=1-64d939d7-638343a031ac3f895e36af65" } }
+
+Now, let's try manipulating the headers. We'll remove the user-agent header and add a header of our own with geo data. Stop your previous instance of ngrok with Ctrl+C and then restart ngrok with a new command.
+
+ngrok http https://httpbin.org
+--domain your-domain.ngrok.app
+--request-header-remove='user-agent'
+--request-header-add='country: ${.ngrok.geo.country_code}'
+
+curl https://your-domain.ngrok.app/headers
+
+{ "headers": { "Accept": "/", "Accept-Encoding": "gzip", "Country": "US", "Host": "your-domain.ngrok.app", "X-Amzn-Trace-Id": "Root=1-64d93b73-689c799b056568ff13546ef4" } }
+2coSXkUPJHKNejdfgFKZaF0CjKd_6NvztF58L172P1MHzwAHF NGOK AUTH TOKEN $ ngrok config add-authtoken 2coSXkUPJHKNejdfgFKZaF0CjKd_6NvztF58L172P1MHzwAHF Configuration File Alternatively, you can directly add the Authtoken to your ngrok.yml configuration file. Use ngrok config edit to open the file.
+
+in ngrok.yml
+
+authtoken: 2coSXkUPJHKNejdfgFKZaF0CjKd_6NvztF58L172P1MHzwAHF ep_2dMwdMHSNkmhguqcUSYjAQPryIn ID edge=edghts_2d7h0YrdnMObWZ8UvuA5kKFYMIh rd_2coZL6TjXyPJWuIBdmXP4BVP4Me rd_2coZL6TjXyPJWuIBdmXP4BVP4Me brew install ngrok/ngrok/ngrok
+
+Run the following command to add your authtoken to the default ngrok.yml configuration file.
+
+ngrok config add-authtoken 2coSXkUPJHKNejdfgFKZaF0CjKd_6NvztF58L172P1MHzwAHF
+
+Deploy your app online
+
+Put your app online at ephemeral domain Forwarding to your upstream service. For example, if it is listening on port http://localhost:8080, run:
+
+ngrok http http://localhost:8080 ngrok http --domain=bursting-turkey-really.ngrok-free.app 80 cr_2coSXkUPJHKNejdfgFKZaF0CjKd GOD964v@gmail.com usr_2coSXng7X2Ax9cfBzu5E26b6SDR
+
+cr_2coazssVIEva7q1Fw2nwytLIq2N BOT USER bot_2coayXt1oJzWKxgTYyanAjQ3KPV 
+
+2dvYx8b2Jxcr6rQ7rMK4g0f5lxd_6MRbqiQJdYkspcWN1vb65 Keith Bieszczat AUTH TOKEN 
+
+cr_2dvYx8b2Jxcr6rQ7rMK4g0f5lxd bot_2dvYwRDLFZfzm3QuX1Yfq0xCPZh
+
+2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd API KEY
+
+ngrok config check curl
+-X POST
+-H "Authorization: Bearer {2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd}"
+-H "Content-Type: application/json"
+-H "Ngrok-Version: 2"
+-d '{"acl":["bind:1.tcp.ngrok.io:20002","bind:132.devices.company.com"],"description":"for device #132","public_key":"ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDmGS49FkSODAcKhn3+/47DW2zEn19BZvzRQ8RZjL3v6hCIX2qXfsFK35EGxNI0wV23H4xXC2gVRPHKU71YnCb50tad3yMBTM6+2yfGsEDasEH/anmBLclChKvuGiT547RskZlpbAbdq3GvbzmY+R/2EBRMOiObpc8XmSzKAd05j28kqN0+rZO65SWId0MXdvJdSCSAnuRqBNd/aXKlu8hBPDcgwbT2lMkuR+ApoBS2FLRBOiQyt2Ol0T7Uuf7lTLlazpGB3uTw5zFYUNXkuuI6cAP8QYuY1Bne/hNrG8t3Aw9a1yc2C4Fz1hJ/4OMRxTQ8SUQf+Rmxs8DryMlMFJ8r device132@example.com"}'
+https://api.ngrok.com/ssh_credentials { "acl": ["bind:1.tcp.ngrok.io:20002", "bind:132.devices.company.com"], "created_at": "2024-02-16T19:35:31Z", "description": "for device #132", "id": "sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "public_key": "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDmGS49FkSODAcKhn3+/47DW2zEn19BZvzRQ8RZjL3v6hCIX2qXfsFK35EGxNI0wV23H4xXC2gVRPHKU71YnCb50tad3yMBTM6+2yfGsEDasEH/anmBLclChKvuGiT547RskZlpbAbdq3GvbzmY+R/2EBRMOiObpc8XmSzKAd05j28kqN0+rZO65SWId0MXdvJdSCSAnuRqBNd/aXKlu8hBPDcgwbT2lMkuR+ApoBS2FLRBOiQyt2Ol0T7Uuf7lTLlazpGB3uTw5zFYUNXkuuI6cAP8QYuY1Bne/hNrG8t3Aw9a1yc2C4Fz1hJ/4OMRxTQ8SUQf+Rmxs8DryMlMFJ8r device132@example.com", "uri": "https://api.ngrok.com/ssh_credentials/sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh" }
+
+curl
+-X GET
+-H "Authorization: Bearer {2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd}"
+-H "Ngrok-Version: 2"
+https://api.ngrok.com/ssh_credentials/sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh
+
+{ "acl": ["bind:1.tcp.ngrok.io:20002", "bind:132.devices.company.com"], "created_at": "2024-02-16T19:35:31Z", "description": "my dev machine", "id": "sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh", "metadata": "{"hostname": "macbook.local"}", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "public_key": "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDmGS49FkSODAcKhn3+/47DW2zEn19BZvzRQ8RZjL3v6hCIX2qXfsFK35EGxNI0wV23H4xXC2gVRPHKU71YnCb50tad3yMBTM6+2yfGsEDasEH/anmBLclChKvuGiT547RskZlpbAbdq3GvbzmY+R/2EBRMOiObpc8XmSzKAd05j28kqN0+rZO65SWId0MXdvJdSCSAnuRqBNd/aXKlu8hBPDcgwbT2lMkuR+ApoBS2FLRBOiQyt2Ol0T7Uuf7lTLlazpGB3uTw5zFYUNXkuuI6cAP8QYuY1Bne/hNrG8t3Aw9a1yc2C4Fz1hJ/4OMRxTQ8SUQf+Rmxs8DryMlMFJ8r device132@example.com", "uri": "https://api.ngrok.com/ssh_credentials/sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh" }
+
+curl
+-X GET
+-H "Authorization: Bearer {2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd}"
+-H "Ngrok-Version: 2"
+https://api.ngrok.com/ssh_credentials
+
+{ "next_page_uri": null, "ssh_credentials": [ { "acl": ["bind:1.tcp.ngrok.io:20002", "bind:132.devices.company.com"], "created_at": "2024-02-16T19:35:31Z", "description": "for device #132", "id": "sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "public_key": "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDmGS49FkSODAcKhn3+/47DW2zEn19BZvzRQ8RZjL3v6hCIX2qXfsFK35EGxNI0wV23H4xXC2gVRPHKU71YnCb50tad3yMBTM6+2yfGsEDasEH/anmBLclChKvuGiT547RskZlpbAbdq3GvbzmY+R/2EBRMOiObpc8XmSzKAd05j28kqN0+rZO65SWId0MXdvJdSCSAnuRqBNd/aXKlu8hBPDcgwbT2lMkuR+ApoBS2FLRBOiQyt2Ol0T7Uuf7lTLlazpGB3uTw5zFYUNXkuuI6cAP8QYuY1Bne/hNrG8t3Aw9a1yc2C4Fz1hJ/4OMRxTQ8SUQf+Rmxs8DryMlMFJ8r device132@example.com", "uri": "https://api.ngrok.com/ssh_credentials/sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh" } ], "uri": "https://api.ngrok.com/ssh_credentials" } curl
+-X PATCH
+-H "Authorization: Bearer {2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd}"
+-H "Content-Type: application/json"
+-H "Ngrok-Version: 2"
+-d '{"description":"my dev machine","metadata":"{"hostname": "macbook.local"}"}'
+https://api.ngrok.com/ssh_credentials/sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh { "acl": ["bind:1.tcp.ngrok.io:20002", "bind:132.devices.company.com"], "created_at": "2024-02-16T19:35:31Z", "description": "my dev machine", "id": "sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh", "metadata": "{"hostname": "macbook.local"}", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "public_key": "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDmGS49FkSODAcKhn3+/47DW2zEn19BZvzRQ8RZjL3v6hCIX2qXfsFK35EGxNI0wV23H4xXC2gVRPHKU71YnCb50tad3yMBTM6+2yfGsEDasEH/anmBLclChKvuGiT547RskZlpbAbdq3GvbzmY+R/2EBRMOiObpc8XmSzKAd05j28kqN0+rZO65SWId0MXdvJdSCSAnuRqBNd/aXKlu8hBPDcgwbT2lMkuR+ApoBS2FLRBOiQyt2Ol0T7Uuf7lTLlazpGB3uTw5zFYUNXkuuI6cAP8QYuY1Bne/hNrG8t3Aw9a1yc2C4Fz1hJ/4OMRxTQ8SUQf+Rmxs8DryMlMFJ8r device132@example.com", "uri": "https://api.ngrok.com/ssh_credentials/sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh" } curl
+-X POST
+-H "Authorization: Bearer {2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd}"
+-H "Content-Type: application/json"
+-H "Ngrok-Version: 2"
+-d '{"description":"development cred for alan@example.com"}'
+https://api.ngrok.com/credentials { "acl": [], "created_at": "2024-02-16T19:35:10Z", "description": "development cred for alan@example.com", "id": "cr_2cSjwF80LQJdOIaFZDbLWO9pMxd", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "token": "2cSjwF80LQJdOIaFZDbLWO9pMxd_3qYXgk4mMNpksRrJdRt6Z", "uri": "https://api.ngrok.com/credentials/cr_2cSjwF80LQJdOIaFZDbLWO9pMxd" } curl
+-X GET
+-H "Authorization: Bearer {2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd}"
+-H "Ngrok-Version: 2"
+https://api.ngrok.com/credentials/cr_2cSjwF80LQJdOIaFZDbLWO9pMxd
+
+{ "acl": [], "created_at": "2024-02-16T19:35:10Z", "description": "device alpha-2", "id": "cr_2cSjwF80LQJdOIaFZDbLWO9pMxd", "metadata": "{"device_id": "d5111ba7-0cc5-4ba3-8398-e6c79e4e89c2"}", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "token": null, "uri": "https://api.ngrok.com/credentials/cr_2cSjwF80LQJdOIaFZDbLWO9pMxd" } curl
+-X GET
+-H "Authorization: Bearer {2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd}"
+-H "Ngrok-Version: 2"
+https://api.ngrok.com/credentials
+
+{ "credentials": [ { "acl": [], "created_at": "2024-02-16T19:35:09Z", "description": "credential for "api-examples-c954256d6ada8b72@example.com"", "id": "cr_2cSjwL9yhXwTeYnIOSxZlvZ8S8y", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "token": null, "uri": "https://api.ngrok.com/credentials/cr_2cSjwL9yhXwTeYnIOSxZlvZ8S8y" }, { "acl": ["bind:1.tcp.ngrok.io:20002", "bind:132.devices.company.com"], "created_at": "2024-02-16T19:35:10Z", "description": "for device #132", "id": "cr_2cSjwHg6uyMl2h31jEgXZOHI77u", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "token": null, "uri": "https://api.ngrok.com/credentials/cr_2cSjwHg6uyMl2h31jEgXZOHI77u" }, { "acl": [], "created_at": "2024-02-16T19:35:10Z", "description": "development cred for alan@example.com", "id": "cr_2cSjwF80LQJdOIaFZDbLWO9pMxd", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "token": null, "uri": "https://api.ngrok.com/credentials/cr_2cSjwF80LQJdOIaFZDbLWO9pMxd" } ], "next_page_uri": null, "uri": "https://api.ngrok.com/credentials" }
+
+curl
+-X PATCH
+-H "Authorization: Bearer {2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd}"
+-H "Content-Type: application/json"
+-H "Ngrok-Version: 2"
+-d '{"description":"device alpha-2","metadata":"{"device_id": "d5111ba7-0cc5-4ba3-8398-e6c79e4e89c2"}"}'
+https://api.ngrok.com/credentials/cr_2cSjwF80LQJdOIaFZDbLWO9pMxd { "acl": [], "created_at": "2024-02-16T19:35:10Z", "description": "device alpha-2", "id": "cr_2cSjwF80LQJdOIaFZDbLWO9pMxd", "metadata": "{"device_id": "d5111ba7-0cc5-4ba3-8398-e6c79e4e89c2"}", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "token": null, "uri": "https://api.ngrok.com/credentials/cr_2cSjwF80LQJdOIaFZDbLWO9pMxd" } import ngrok
+
+listener = ngrok.forward("localhost:8080", authtoken_from_env=True, circuit_breaker=0.5)
+
+print(f"Ingress established at: {listener.url()}");
+
+package main
+
+import ( "context" "fmt" "log" "net" "net/http" "net/url" "os"
+
+"golang.ngrok.com/ngrok"
+"golang.ngrok.com/ngrok/config"
+)
+
+func main() { l, err := ngrok.Listen(context.Background(), config.HTTPEndpoint( config.WithCircuitBreaker(0.1), ), ngrok.WithAuthtokenFromEnv(), ) if err != nil { log.Fatal(err) } fmt.Println("Running at", l.URL()) go makeRequests(l.URL()) http.Serve(l, http.HandlerFunc(func(w http.ResponseWriter, r *http.Request) { if r.URL.Path == "/500" { w.WriteHeader(500) fmt.Fprintln(w, "Hello error!") } else { w.WriteHeader(200) fmt.Fprintln(w, "Hello world!") } })) }
+
+func makeRequests(appURL string) { // make sure we always dial the same IP addresss for testing purposes because // circuit breaker state is applied on each ngrok edge server individually u, _ := url.Parse(appURL) addrs, err := net.LookupHost(u.Host) if err != nil { log.Fatal(err) } httpClient := http.Client{Transport: &http.Transport{ Dial: func(network, _ string) (net.Conn, error) { return net.Dial(network, addrs[0]+":443") }, }}
+
+// make requests that return a 500 until the circuit opens
+for {
+	resp, err := httpClient.Get(appURL + "/500")
+	if err != nil {
+		log.Fatal(err)
+	}
+	fmt.Printf("Status Code %d\n", resp.StatusCode)
+	if resp.StatusCode == 503 {
+		fmt.Println("Circuit opened")
+		break
+	}
+}
+
+// make requests that will eventually return a 200 which will close the circuit
+for {
+	resp, err := httpClient.Get(appURL)
+	if err != nil {
+		log.Fatal(err)
+	}
+	fmt.Printf("Status Code %d\n", resp.StatusCode)
+	if resp.StatusCode != 503 {
+		fmt.Println("Circuit closed")
+		os.Exit(0)
+	}
+}
+}
+
+package main
+
+import ( "context" "fmt" "log" "net" "net/http" "net/url" "os"
+
+"golang.ngrok.com/ngrok"
+"golang.ngrok.com/ngrok/config"
+)
+
+func main() { l, err := ngrok.Listen(context.Background(), config.HTTPEndpoint( config.WithCircuitBreaker(0.1), ), ngrok.WithAuthtokenFromEnv(), ) if err != nil { log.Fatal(err) } fmt.Println("Running at", l.URL()) go makeRequests(l.URL()) http.Serve(l, http.HandlerFunc(func(w http.ResponseWriter, r *http.Request) { if r.URL.Path == "/500" { w.WriteHeader(500) fmt.Fprintln(w, "Hello error!") } else { w.WriteHeader(200) fmt.Fprintln(w, "Hello world!") } })) }
+
+func makeRequests(appURL string) { // make sure we always dial the same IP addresss for testing purposes because // circuit breaker state is applied on each ngrok edge server individually u, _ := url.Parse(appURL) addrs, err := net.LookupHost(u.Host) if err != nil { log.Fatal(err) } httpClient := http.Client{Transport: &http.Transport{ Dial: func(network, _ string) (net.Conn, error) { return net.Dial(network, addrs[0]+":443") }, }}
+
+// make requests that return a 500 until the circuit opens
+for {
+	resp, err := httpClient.Get(appURL + "/500")
+	if err != nil {
+		log.Fatal(err)
+	}
+	fmt.Printf("Status Code %d\n", resp.StatusCode)
+	if resp.StatusCode == 503 {
+		fmt.Println("Circuit opened")
+		break
+	}
+}
+
+// make requests that will eventually return a 200 which will close the circuit
+for {
+	resp, err := httpClient.Get(appURL)
+	if err != nil {
+		log.Fatal(err)
+	}
+	fmt.Printf("Status Code %d\n", resp.StatusCode)
+	if resp.StatusCode != 503 {
+		fmt.Println("Circuit closed")
+		os.Exit(0)
+	}
+}
+export NGROK_AUTHTOKEN="<2dvYx8b2Jxcr6rQ7rMK4g0f5lxd_6MRbqiQJdYkspcWN1vb65>" go mod init example.com/ngrok-circuit-breaker go get golang.ngrok.com/ngrok go run example.go import ngrok
+
+listener = ngrok.forward("localhost:8080", authtoken_from_env=True, verify_webhook_provider="twilio", verify_webhook_secret="{twilio signing secret}")
+
+print(f"Ingress established at: {listener.url()}");
+
+git clone https://github.com/ngrok/ngrok-webhook-nodejs-sample.git cd ngrok-webhook-nodejs-sample npm install npm start ngrok http 3000
+
+ngrok http 3000 --verify-webhook stripe --verify-webhook-secret {whsec_ 5V2GHGaht2mGJGNOmesTtTaxuJWFRssS}
+
+authtoken: 4nq9771bPxe8ctg7LKr_2ClH7Y15Zqe4bWLWF9p api_key: 24yRd5U3DestCQapJrrVHLOqiAC_7RviwRqpd3wc9dKLujQZN connect_timeout: 30s console_ui: true console_ui_color: transparent dns_resolver_ips:
+
+1.1.1.1
+8.8.8.8 heartbeat_interval: 1m heartbeat_tolerance: 5s inspect_db_size: 104857600 # 100mb inspect_db_size: 50000000 log_level: info log_format: json log: /var/log/ngrok.log metadata: '{"serial": "00012xa-33rUtz9", "comment": "For customer alan@example.com"}' proxy_url: socks5://localhost:9150 region: us remote_management: false root_cas: trusted update_channel: stable update_check: false version: 2 web_addr: localhost:4040 tunnels: website: addr: 8888 basic_auth:
+"bob:bobpassword" schemes:
+https host_header: "myapp.ngrok.dev" inspect: false proto: http domain: myapp.ngrok.dev
+e2etls: addr: 9000 proto: tls domain: myapp.example.com crt: example.crt key: example.key
+
+policyenforced: policy: inbound: - name: LimitIPs expressions: - "conn.ClientIP != '1.1.1.1'" actions: - type: deny addr: 8000 proto: tcp
+
+ssh-access: addr: 22 proto: tcp remote_addr: 1.tcp.ngrok.io:12345
+
+my-load-balanced-website: labels: - env=prod - team=infra addr: 8000
+
+tunnels:
+httpbin: proto: http addr: 8000 domain: alan-httpbin.ngrok.dev demo: proto: http addr: 9090 domain: demo.inconshreveable.com inspect: false ngrok start httpbin
+
+tunnels: my-cool-website: labels: - env=prod - team=infra addr: 8000 inspect: false ssh-tunnel: labels: - hostname=my-hostname - service=ssh - team=development addr: 22 api_key: 24yRd5U3DestCQapJrrVHLOqiAC_7RviwRqpd3wc9dKLujQZN authtoken: 4nq9771bPxe8ctg7LKr_2ClH7Y15Zqe4bWLWF9p
+
+log: /var/log/ngrok.log
+
+metadata
+
+This is a user-supplied custom string that will be returned as part of the ngrok API response to the list online sessions resource for all tunnels started by this agent. This is a useful mechanism to identify tunnels by your own device or customer identifier. Maximum 4096 characters.
+
+metadata: bad8c1c0-8fce-11e4-b4a9-0800200c9a66
+
+web_allow_hosts:
+
+8.8.8.8
+example.com curl http://localhost:4040/api/
+{ "tunnels": [ { "name": "command_line", "uri": "/api/tunnels/command_line", "public_url": "https://d95211d2.ngrok.io", "proto": "https", "config": { "addr": "localhost:80", "inspect": true, }, "metrics": { "conns": { "count": 0, "gauge": 0, "rate1": 0, "rate5": 0, "rate15": 0, "p50": 0, "p90": 0, "p95": 0, "p99": 0 }, "http": { "count": 0, "rate1": 0, "rate5": 0, "rate15": 0, "p50": 0, "p90": 0, "p95": 0, "p99": 0 } } }, ... ], "uri": "/api/tunnels" } { "addr": "22", "proto": "tcp", "name": "ssh" }
+
+{ "name": "", "uri": "/api/tunnels/", "public_url": "tcp://0.tcp.ngrok.io:53476", "proto": "tcp", "config": { "addr": "localhost:22", "inspect": false, }, "metrics": { "conns": { "count": 0, "gauge": 0, "rate1": 0, "rate5": 0, "rate15": 0, "p50": 0, "p90": 0, "p95": 0, "p99": 0 }, "http": { "count": 0, "rate1": 0, "rate5": 0, "rate15": 0, "p50": 0, "p90": 0, "p95": 0, "p99": 0 } } }
+
+{ "name": "command_line", "uri": "/api/tunnels/command_line", "public_url": "https://ac294125.ngrok.io", "proto": "https", "config": { "addr": "localhost:80", "inspect": true, }, "metrics": { "conns": { "count": 0, "gauge": 0, "rate1": 0, "rate5": 0, "rate15": 0, "p50": 0, "p90": 0, "p95": 0, "p99": 0 }, "http": { "count": 0, "rate1": 0, "rate5": 0, "rate15": 0, "p50": 0, "p90": 0, "p95": 0, "p99": 0 } } } BHAHZGCJZK3BEVS7IRGZMKDF6USLO runner token apply to all commands
+
+stripe login --api-key sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq
+
+stripe login
+
+stripe trigger payment_intent.succeeded
+
+Secret key
+
+pst_test_YWNjdF8xTTJKVGtMa2RJd0h1N2l4LE81ZEdIalZ6NlVuMUdjM3c3WkRnN0ZYRHZxRURwTXo_00gNK2DWAV run payment id
+
+po_1OZNhvGF83d3fsgWC9jdBgcQ
+
+run bank data DJqIeyHlhjb55r0K Routing number 031101279 ID ba_1OR7BGGF83d3fsgWxwDM4lDf
+
+$ Stripe endpoint we_1Ova66GF83d3fsgW2nbowkDw Webhook signing secret: whsec_ 5V2GHGaht2mGJGNOmesTtTaxuJWFRssS
+
+why?
+
+req_3SnomkF11VBTwG
+
+The payment failed. { "consent": { "terms_of_service": "accepted" }, "eid": "**", "expected_amount": "100000", "expected_payment_method_type": "link", "guid": "14b84001-905a-42f3-9e2b-18a9ebf0e15c540853", "init_checksum": "MXofbfTYAaKG1no6FZxkzMndcSrERGp3", "js_checksum": "qtod^n0=QU>azbu]Vn<D\^vUO[_esYxY=dwUca$<P<m^o?U^w", "key": "pk_live_*********************************************************************************************k76MVR", "last_displayed_line_item_group_details": { "shipping_rate_amount": "0", "subtotal": "100000", "total_discount_amount": "0", "total_exclusive_tax": "0", "total_inclusive_tax": "0" }, "muid": "eb78b5f0-bdd7-45f9-a924-dcf3e95a1a647d0ae4", "passive_captcha_ekey": "", "passive_captcha_token": "P1_eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJwYXNza2V5IjoibGxxQlR1SURGNkd1WWhCWTh4N1RXY2dLbWJHYUhpdk5DeTZBMDdPTnZ4NUNqdy9XcDkrR0hJTHo0bDdUbHFGSmVjSkNpSFR3N1AyVnZwVHh5RlUyVlgyL0lyZHVCZkc2eTd3RE9tTFRHcUsvUEwxK2V2SWpQcEhwNFRCaVJMaVV2eURPRG4wWnFPa1pONS9NNXVka0dsNER2R3E4djNaMHEvRXRESWZ0ZllNZTBCRVFZTklIU1dROXY3QVRZWHMxWUwvRXhQK3pubmlDUHkvOTQ3Z0kxdjd1Zzk1cG8ycnJGS0ErK2FKeHJsR3lnb3JzRTUwaVNtYm1mNlJuUURPYWcvbWh2OE9GNXg0bE1KMXVNdUw0Rm1UQzNpS2lMell3eDUyNDc2QWlvdEw4aEEzWWVYbEJySkdlT3lxSVRtaytraWY1M05Xd2VjdDY0KytnM3NGL0UrMjg4a04vSUFIQ0FEdEYxbU1vZEFSTjZjL3pvMlBTYUFtdGUzTVV5TTJXT09ZTENWM01VOHRhOHk0emc0d0txSXg0U3lKemxwcCtXVTRvRy9DU0ZRNXYwa29iNVBPMnJtc3QxTkVQT3ozMlNUQ1BFUkZReFdXeWtBaVErc01QbFVmZmhsYnBEcldrMnF6VEQxR0dxQ254MksxeExvYUlhVW5yWWxyNXFZZTVLVHJ4bnNQNUlDVTNrNjBlWVdwbzZBVVJCaGFiOE4rK1g3TEpuRzlLRmJTM2YxM2R5dDM5MlA1WTJZcEFGYUxnT0laSnppSjJOZHkvMXRxbURucFZXaVZrRG1xSjZJRU5UNTh4Y0NvS1oyRjRqVWtGSk5DVWRaejZYdVpLMHY5bGhtRmxoZGRSNGdjVWZQWWFtUjAwUG5wL3c5dXAySkF4UDRRc2RjN2RHUWhCOFJrL0NSVVdFTll5NEFLbXBLeldsMlNscy9SOEpUQUdraGRFdTZvbjNBb2Z5NmZJbC9kK0NCYzlwYjBHeDhaaU9qUmZFbjVMSWNBTUN0Ymp0TFkwaURWWFdQZUM1UUtaMUF1c051TVk2L1lVdFhNZk03eUNyeUVBMG45ajNlYy9hbk9zT01WUWxlWkFDT3RjRmx1KzIvVmlpUDVORG14VGRZc2R4MWU4VFR0MWFpL05IRmxVNXh4cGVmMEFldkx2NXRmWW41WTkxeU1vdGlZaXhvMnhFWkp6NmgycHZRVnpIVnN4aDNNeFRWMWlOZ1kySHVXbVNPbTZjOWdBRWtGZkZCSVM3V2VwY2g2Tng0TzlFVWh0VnpXaW5KRDFvNXZlYkdGMnBJakVYR0lSWVZNSCtWbnJaM2t1V2djOUpiRWtyYStiRjBkd0pxY2F2VityRkdqOW9ENFFSZkMwNmpSMzlvdU5CTmVzSU8xNWRFVE9TdDRHOGxMaUJ4QkhyL283VnR6bHZ2djdhbFI3K3VidlNXdlQ2QlI4cjdOQmxXR3BOM0lCRllnby96a0VJUmRnN0Fzb3RKWndPZENGdnBSbWhDYWJKVklzZTlwSXlrTWl3WGYvUnpTU2wzdkJiMSs4UDBtbFVkNEVCZS9CTnNTcmF4Nm9NWEVmR1c0N29YNFBmMTlqcm9qWnhyaDBOOWJ1b04yWlF0QWQwU255ZndQNUZYYTh2dWp0OGtrUXNlRHZaWVpCRi9TSW1BM2ZRdmM3VnZ5YVNSQktabHBzdFlzMElzYVhpU1pGbFg3NUdrbFVpZWNSREdleFROQVpObWtlN0lTbm4xbVpJaFpUOVlhN1RIdU0yM2dReEs3RnlFcUlzcjNadjYwVDBOSHptdk5lN0w0NkFudDFSbEIxZWQxWW1VN3pvVzdXbGZpOUc0MTZXZ28wQloyUDR6K1hmTXFQc2cwTFdKTytZVFI4Ym0wVzFpQ0ZEdWpUM3l5RGJJN0JWUTlwWDlEMnRjVXE0ajlpSTZjZktrb0d3Z2tCa1dtRmFuQ0QvV3BjTmVnSkJCMEJ0WHR2Z2NSeGQwbmpxR3F2aXIrZGF1TTlNZ0lrZDNLeHNCVXJkd2tySVJhOElvaDlCQmlkUDJMY0pkU1RWUittdFBMRW1iaWZoZVh5clRybUtEcEEvVnNCSmc2MEpBNXp3Q1E5NTlWWWQ5TFh5VnFhdnlrMzRwTC9NaTBPL1dnWmllbUhUNGFVSDdZVG5TekxMYmFQdW1aYVdpMkt4RFFkWmY0cW96akVya21iVnFOSk1XbXYzd2E3QkZhNzdyY0E2RjdXQmRUVkt0V0pqeXp0WWpyTHllNEpST0tsQlh1WmtxbVpnOGNsQlFoNGJobTI4c1FtQzI3UlBkM0dEMGwwTTFyMGpsZitpWDVLc3JGTitHNFJPMzFLT2ZNM2o1ajVzQzBaYytDa2JaNklwK1VKVmk2RmRESUFoMU5LOTl6eWhZR2QwMzlVU2FqdU02TmQxeG4zMTYxVUJQZGpkTFZpb3pFUFZqdXpEZUN6QXNmcDJWUTZyS1JmWUFjNEtVeVdmaEExTThUVHVXL1pJUW5ja2gzUm9UVm5JVE81bkh1YXNGYitYVEJZL0FaOEJzVjRkanFMdUVHc01YQThoV0FYMGxrejJXN1VWZVVINFpHald0T0d0SHZBZURJOTJiT0V4OXk0YWhrWU93czYyWURHL1F5c1FNc2pFWFMzb3d4ekcvNVBZaVJ6RlAwaDFYS09McXhNdmYrM2NlYlN3UkNOdkhMV2tYT2k1bk82TzROait5OGR2UGhVSWVBS0tWTTBGTmw5UW1XNzBFTEdPZjVOZzdWZGRBY3RWd3VsOUo0elAyUGhsOFF5bi8xK1l2bFpXMmpHUmQ3eXd2cUZVVVlPU2htNkk2VFB2eG4vVCtKWHJ4WUlaMmVnbVoyVy91UEhXbVFucGtZUUYzaEhIYnlkbnhDOEpGa2E3NGJNQjZRR3J0VHBvaGhUOFo1U0lXU1Iwbkt3UHhBOGdZaThDRlhKRXErcFpkT1RNYUhiay9RcDJmMFFCQXA4aEpKMU5IUWdrRCtZdEFBTnV5bWR5YW90RmJQeS9STnJyS1AyOTZiUlF5SVV4aU10dlo2Z1piMFRqK252WTRUVFU4UzNNWW14Nysrd242N1Rxcm11Zytjc3FMNEJVdnhmdGlCWnI3b0M1cnNmRFQ5d21XSS8iLCJleHAiOjE3MTA3NDI1OTksInNoYXJkX2lkIjo4MzM0NDA4OTcsInBkIjowLCJjZGF0YSI6IjRKOGNUeDBPRjd6byszdzB1WHNtZ0dzSEpubE5Geml0VUZON0dhYWNzQWpFdWZsbmlta3lydXpwT2FGVnl5S2hXSk9tVmdwcEdtOFZtMWNWOWJnL3BacDhHcDVmN1N0ZEpvTlU5M0JhaHRKbmE4V2pNZkVEWnp0QUUwTXRMQ0Qxb1Z2dzc4SDlJREdqK0FmTXVaZFp0OFpiT0JmZ1dmZUluRVVLNUx0dHhnOGtaUU93dW91S0ExTmxRamxiQk9vM1NGT1ZFdERPdTlESjdsN2JZL0x0OU9KME9NNTBZTjQ9VkpFeHI4ZHFFQWpuenI1UiJ9.pPcNQ2Y328R8U7Sar4Z5U0GO9y1caCAAPmbIy3aCnYo", "payment_method": "pm_1OvZUOGF83d3fsgWiXYpUHQh", "rv_timestamp": "qto>n<Q=U&CyY&>X^r<YNr<YN<Y_C<Y_C<Y^zY_<Y^n{U>o&U&CyY=P=eODdbL%e&areOMrY=n=YxnDd_Mv[bL>[OTCdOaveu%euUyX%n{U>e&U&Cyd&auY_n=d&;;X_d%d&UxdRP#[bd#exQxX=L&X&n%eu\\$ex]sY&ovXOUu[_$reunDd&osd=MueOP;d&<yY_<sX^o?U^w", "sid": "f931f0fd-f83a-4921-903f-45f5b359d9925f3b2a", "version": "2d3a08de7b" }
+
+pip3 install stripe python3 -m flask run --port=4242 python3 -m flask run --port=4242 $ stripe listen --forward-to localhost:4242/webhook $ stripe trigger payment_intent.succeeded #! /usr/bin/env python3.6
+
+Python 3.6 or newer required.
+
+import json import os import stripe
+
+This is your test secret API key.
+
+stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'
+
+#! /usr/bin/env python3.6
+
+Python 3.6 or newer required.
+
+import json import os import stripe
+
+This is your test secret API key.
+
+stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'
+
+Replace this endpoint secret with your endpoint's unique secret
+
+If you are testing with the CLI, find the secret by running 'stripe listen'
+
+If you are using an endpoint defined with the API or dashboard, look in your webhook settings
+
+at https://dashboard.stripe.com/webhooks
+
+endpoint_secret = 'whsec_...' from flask import Flask, jsonify, request
+
+app = Flask(name)
+
+@app.route('/webhook', methods=['POST']) def webhook(): event = None payload = request.data
+
+try:
+    event = json.loads(payload)
+except json.decoder.JSONDecodeError as e:
+    print('⚠️  Webhook error while parsing basic request.' + str(e))
+    return jsonify(success=False)
+if endpoint_secret:
+    # Only verify the event if there is an endpoint secret defined
+    # Otherwise use the basic event deserialized with json
+    sig_header = request.headers.get('stripe-signature')
+    try:
+        event = stripe.Webhook.construct_event(
+            payload, sig_header, endpoint_secret
+        )
+    except stripe.error.SignatureVerificationError as e:
+        print('⚠️  Webhook signature verification failed.' + str(e))
+        return jsonify(success=False)
+
+# Handle the event
+if event and event['type'] == 'payment_intent.succeeded':
+    payment_intent = event['data']['object']  # contains a stripe.PaymentIntent
+    print('Payment for {} succeeded'.format(payment_intent['amount']))
+    # Then define and call a method to handle the successful payment intent.
+    # handle_payment_intent_succeeded(payment_intent)
+elif event['type'] == 'payment_method.attached':
+    payment_method = event['data']['object']  # contains a stripe.PaymentMethod
+    # Then define and call a method to handle the successful attachment of a PaymentMethod.
+    # handle_payment_method_attached(payment_method)
+else:
+    # Unexpected event type
+    print('Unhandled event type {}'.format(event['type']))
+
+return jsonify(success=True)
+Run
+
+https://dashboard.stripe.com/test/payouts/po_1OZNhvGF83d3fsgWC9jdBgcQ#wb-N4Igdghgbglg5hALjA9mEAuUEDGyoCmAKhAEaYgAmBAzspMmjSADQiJkASMdKATgE9MAbQC6bPigCuiAt16CRogL5saMAF4wwcTGCkAbA2wAWBeCcQUA7AAYoJ1iFjrSMAzEQCAsimoUXGFIDAidqOm0kVDBmLBAaAhC8AkoASUoKAHcCAH0ARgB5KAgANhKAcQAxAA4AZkpagDMaOAB1ACYwUhRMgGsAEUynDnIMEAJCMERmNgmCKdjQRvdZPkX4ggg+HEcxpzokKVixCVppbdC9thRSACsCPHSKJzmpogEAB0uQF75JPneXyUbEoSEuwGUqg2SVkaQyGH0RjUiQesIAgohZABbD6IJ4IwwGSHKIA
+
+Download Stripe client secret
+
+const {client_secret: seti_1NG8Du2eZvKYlo2C9XMqbR0x_secret_O2CdhLwGFh2Aej7bCY7qp8jlIuyR8DJ/ } = await res.json();
+
+const {error} = await stripe.confirmPayment({ //Elements instance that was used to create the Payment Element elements, clientSecret, confirmParams: { return_url: 'https://example.com/order/123/complete', }, });
+
+if (error) { // This point will only be reached if there is an immediate error when // confirming the payment. Show error to your customer (for example, payment // details incomplete) setErrorMessage(error.message); } else { // Your customer will be redirected to your return_url. For some payment // methods like iDEAL, your customer will be redirected to an intermediate // site first to authorize the payment, then redirected to the return_url. } import stripe stripe.api_key = "sk_test_51OR5eP...OF00CdDfT6Xqsk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq" stripe.Event.list(limit=3) RESPONSE { "object": "list", "url": "/v1/events", "has_more": false, "data": [ { "id": "evt_1NG8Du2eZvKYlo2CUI79vXWy", "object": "event", "api_version": "2019-02-19", "created": 1686089970, "data": { "object": { "id": "seti_1NG8Du2eZvKYlo2C9XMqbR0x", "object": "setup_intent", "application": null, "automatic_payment_methods": null, "cancellation_reason": null, "client_secret": "seti_1NG8Du2eZvKYlo2C9XMqbR0x_secret_O2CdhLwGFh2Aej7bCY7qp8jlIuyR8DJ", "created": 1686089970, "customer": null, "description": null, "flow_directions": null, "last_setup_error": null, "latest_attempt": null, "livemode": false, "mandate": null, "metadata": {}, "next_action": null, "on_behalf_of": null, "payment_method": "pm_1NG8Du2eZvKYlo2CYzzldNr7", "payment_method_options": { "acss_debit": { "currency": "cad", "mandate_options": { "interval_description": "First day of every month", "payment_schedule": "interval", "transaction_type": "personal" }, "verification_method": "automatic" } }, "payment_method_types": [ "acss_debit" ], "single_use_mandate": null, "status": "requires_confirmation", "usage": "off_session" } }, "livemode": false, "pending_webhooks": 0, "request": { "id": null, "idempotency_key": null }, "type": "setup_intent.created" } {...} {...} ], }
+
+OK ID req_ZIIVfKfNp6QrOh
+
+const {client_secret: seti_1NG8Du2eZvKYlo2C9XMqbR0x_secret_O2CdhLwGFh2Aej7bCY7qp8jlIuyR8DJ} = await res.json();
+
+const {error} = await stripe.confirmPayment({ //Elements instance that was used to create the Payment Element elements, clientSecret, confirmParams: { return_url: 'https://example.com/order/123/complete', }, });
+
+if (error) { // This point will only be reached if there is an immediate error when // confirming the payment. Show error to your customer (for example, payment // details incomplete) setErrorMessage(error.message); } else { // Your customer will be redirected to your return_url. For some payment // methods like iDEAL, your customer will be redirected to an intermediate // site first to authorize the payment, then redirected to the return_url. } import stripe stripe.api_key = "sk_test_51OR5eP...OF00CdDfT6Xqsk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq" stripe.Event.list(limit=3) RESPONSE { "object": "list", "url": "/v1/events", "has_more": false, "data": [ { "id": "evt_1NG8Du2eZvKYlo2CUI79vXWy", "object": "event", "api_version": "2019-02-19", "created": 1686089970, "data": { "object": { "id": "seti_1NG8Du2eZvKYlo2C9XMqbR0x", "object": "setup_intent", "application": null, "automatic_payment_methods": null, "cancellation_reason": null, "client_secret": "seti_1NG8Du2eZvKYlo2C9XMqbR0x_secret_O2CdhLwGFh2Aej7bCY7qp8jlIuyR8DJ", "created": 1686089970, "customer": null, "description": null, "flow_directions": null, "last_setup_error": null, "latest_attempt": null, "livemode": false, "mandate": null, "metadata": {}, "next_action": null, "on_behalf_of": null, "payment_method": "pm_1NG8Du2eZvKYlo2CYzzldNr7", "payment_method_options": { "acss_debit": { "currency": "cad", "mandate_options": { "interval_description": "First day of every month", "payment_schedule": "interval", "transaction_type": "personal" }, "verification_method": "automatic" } }, "payment_method_types": [ "acss_debit" ], "single_use_mandate": null, "status": "requires_confirmation", "usage": "off_session" } }, "livemode": false, "pending_webhooks": 0, "request": { "id": null, "idempotency_key": 6f5410cb-1ecc-4302-8130-baf8dd8c0a50 }, "type": "setup_intent.created" } {...} {...} ], }
+
+stripe .retrieveSetupIntent( '{fcsess_client_secret_KRJTKvCY3IKoYTrW18EazcO3 /seti_1NG8Du2eZvKYlo2C9XMqbR0x_secret_O2CdhLwGFh2Aej7bCY7qp8jlIuyR8DJ }', ) .then(function(result) { // Handle result.error or result.paymentIntent }); stripe.collectFinancialConnectionsAccounts({ clientSecret: '{fcsess_client_secret_KRJTKvCY3IKoYTrW18EazcO3}' }) .then(function(result) { if (result.error) { // Inform the customer that there was an error. console.log(result.error.message);
+
+// Handle next step based on length of accounts array
+} else if (result.financialConnectionsSession.accounts.length === 0) {
+  console.log('No accounts were linked');
+} else {
+  console.log(result.financialConnectionsSession.accounts)
+}
+});
+
+{ "object": "customer_session", "client_secret": "_POpxYpmkXdtttYtZQYhrsOJZ2RCQ9kCqqXRU6qrP5c4Jgje", "components": { "buy_button": { "enabled": false }, "pricing_table": { "enabled": true } }, "customer": "cus_PO34b57IOUb83c", "expires_at": 1684790027, "livemode": false } { "object": "customer_session", "client_secret": "_POpxYpmkXdtttYtZQYhrsOJZ2RCQ9kCqqXRU6qrP5c4Jgje", "components": { "buy_button": { "enabled": false }, "pricing_table": { "enabled": true } }, "customer": "cus_PO34b57IOUb83c", "expires_at": 1684790027, "livemode": false }
+
+Create a folder $ mkdir actions-runner && cd actions-runner
+
+Download the latest runner package $ curl -o actions-runner-osx-x64-2.314.1.tar.gz -L https://github.com/actions/runner/releases/download/v2.314.1/actions-runner-osx-x64-2.314.1.tar.gz
+
+Optional: Validate the hash $ echo "3faff4667d6d12c41da962580168415d628e3ffba9924b9ac995752087efc921 actions-runner-osx-x64-2.314.1.tar.gz" | shasum -a 256 -c
+
+Extract the installer $ tar xzf ./actions-runner-osx-x64-2.314.1.tar.gz Configure
+
+Create the runner and start the configuration experience $ ./config.sh --url https://github.com/grateful345/Wiz-Go-call-sign --token BHAHZGDHHICG3LFF53OICRLF6UR24
+
+Last step, run it! $ ./run.sh Using your self-hosted runner
+
+Use this YAML in your workflow file for each job runs-on: self-hosted
+
+Orginization ID: e3ff35d1-cea4-4508-acb5-99d9cbd91e80
+
+
 pk_live_51OR5ePGF83d3fsgW22PwNtYiShCVYIsrzZq2WxlxN2UAaB2qEIu0aUFJzjJxPtNT3rAs0Rvdo9XIVPb7rRMaeo3W00ALk76MVR PUBLISHABLE KEY LIVE
 
 sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq secret test key STRIPERepository files navigation

README
AGENCY-WEBHOOK

API ID KEY SECRET KEY : pst_test_YWNjdF8xTTJKVGtMa2RJd0h1N2l4LE81ZEdIalZ6NlVuMUdjM3c3WkRnN0ZYRHZxRURwTXo_00gNK2DWAV

HystrixCommand command = new HystrixCommand(arg1, arg2);

HystrixObservableCommand command = new HystrixObservableCommand(arg1, arg2);

K value = command.execute(); Future fValue = command.queue(); Observable ohValue = command.observe(); //hot observable Observable ocValue = command.toObservable(); //cold observable Account account = new UserGetAccount(accountId).execute();

//or

Observable accountObservable = new UserGetAccount(accountId).observe();

K value = command.execute(); Future fValue = command.queue(); Observable ohValue = command.observe(); //hot observable Observable ocValue = command.toObservable(); //cold observable

apiVersion: networking.k8s.io/v1 kind: Ingress metadata: name: example-ingress annotations: k8s.ngrok.com/modules: ngrok-module-set spec: ingressClassName: ngrok rules: - host: app.example.com http: paths: - path: / pathType: Prefix backend: service: name: example-service port: number: 80

kind: NgrokModuleSet apiVersion: ingress.k8s.ngrok.com/v1alpha1 metadata: name: ngrok-module-set modules: oauth: google: optionsPassthrough: false inactivityTimeout: 4h maximumDuration: 24h authCheckInterval: 1h apiVersion: networking.k8s.io/v1 kind: Ingress metadata: name: example-ingress annotations: k8s.ngrok.com/modules: ngrok-module-set spec: ingressClassName: ngrok rules: - host: your-domain.ngrok.app http: paths: - path: / pathType: Prefix backend: service: name: example-service port: number: 80

apiVersion: v1 kind: Service metadata: name: example-service annotations: k8s.ngrok.com/app-protocols: '{"example-https-port":"HTTPS"}' spec: ports: - name: example-https-port port: 443 protocol: TCP targetPort: 8443 selector: app-name: some-example-app-label

apiVersion: networking.k8s.io/v1 kind: Ingress metadata: name: example-ingress annotations: k8s.ngrok.com/modules: ngrok-module-set spec: ingressClassName: ngrok rules: - host: app.example.com http: paths: - path: / pathType: Prefix backend: service: name: example-service port: number: 443

kind: NgrokModuleSet apiVersion: ingress.k8s.ngrok.com/v1alpha1 metadata: name: ngrok-module-set modules: headers: request: add: host: "localhost"

apiVersion: networking.k8s.io/v1 kind: Ingress metadata: name: example-ingress annotations: k8s.ngrok.com/modules: ngrok-module-set spec: ingressClassName: ngrok rules: - host: your-domain.ngrok.app http: paths: - path: / pathType: Prefix backend: service: name: example-service port: number: 80

ngrok http 80 --request-header-remove "foo" --request-header-add "foo: new-value" ssh -R 443:localhost:80 v2@connect.ngrok-agent.com http ssh -R example.ngrok.app:443:localhost:80 v2@connect.ngrok-agent.com http ssh -R 443:localhost:80 v2@connect.ngrok-agent.com http
--basic-auth "username1:password1"
--basic-auth "username2:password2" ssh -R 443:localhost:80 v2@connect.ngrok-agent.com http --oauth=google ssh -R 0:192.168.1.2:80 v2@connect.ngrok-agent.com http

ssh -R 0:localhost:22 v2@connect.ngrok-agent.com tcp ssh -R 1.tcp.eu.ngrok.io:12345:localhost:3389 connect.eu.ngrok-agent.com tcp ssh -R app.example.com:443:localhost:443 v2@connect.ngrok-agent.com tls ssh -R 443:localhost:80 v2@connect.eu.ngrok-agent.com http

This will cause the HTTP request in this case to become:

GET / HTTP/1.1 host: example.ngrok.app foo: new-value

ngrok http https://httpbin.org --domain your-domain.ngrok.app

In another terminal, curl that endpoint:

curl https://your-domain.ngrok.app/headers

{ "headers": { "Accept": "/", "Accept-Encoding": "gzip", "Host": "your-domain.ngrok.app", "User-Agent": "curl/7.85.0", "X-Amzn-Trace-Id": "Root=1-64d939d7-638343a031ac3f895e36af65" } }

Now, let's try manipulating the headers. We'll remove the user-agent header and add a header of our own with geo data. Stop your previous instance of ngrok with Ctrl+C and then restart ngrok with a new command.

ngrok http https://httpbin.org
--domain your-domain.ngrok.app
--request-header-remove='user-agent'
--request-header-add='country: ${.ngrok.geo.country_code}'

curl https://your-domain.ngrok.app/headers

{ "headers": { "Accept": "/", "Accept-Encoding": "gzip", "Country": "US", "Host": "your-domain.ngrok.app", "X-Amzn-Trace-Id": "Root=1-64d93b73-689c799b056568ff13546ef4" } }
2coSXkUPJHKNejdfgFKZaF0CjKd_6NvztF58L172P1MHzwAHF NGOK AUTH TOKEN $ ngrok config add-authtoken 2coSXkUPJHKNejdfgFKZaF0CjKd_6NvztF58L172P1MHzwAHF Configuration File Alternatively, you can directly add the Authtoken to your ngrok.yml configuration file. Use ngrok config edit to open the file.

in ngrok.yml

authtoken: 2coSXkUPJHKNejdfgFKZaF0CjKd_6NvztF58L172P1MHzwAHF ep_2dMwdMHSNkmhguqcUSYjAQPryIn ID edge=edghts_2d7h0YrdnMObWZ8UvuA5kKFYMIh rd_2coZL6TjXyPJWuIBdmXP4BVP4Me rd_2coZL6TjXyPJWuIBdmXP4BVP4Me brew install ngrok/ngrok/ngrok

Run the following command to add your authtoken to the default ngrok.yml configuration file.

ngrok config add-authtoken 2coSXkUPJHKNejdfgFKZaF0CjKd_6NvztF58L172P1MHzwAHF

Deploy your app online

Put your app online at ephemeral domain Forwarding to your upstream service. For example, if it is listening on port http://localhost:8080, run:

ngrok http http://localhost:8080 ngrok http --domain=bursting-turkey-really.ngrok-free.app 80 cr_2coSXkUPJHKNejdfgFKZaF0CjKd GOD964v@gmail.com usr_2coSXng7X2Ax9cfBzu5E26b6SDR

cr_2coazssVIEva7q1Fw2nwytLIq2N BOT USER bot_2coayXt1oJzWKxgTYyanAjQ3KPV 

2dvYx8b2Jxcr6rQ7rMK4g0f5lxd_6MRbqiQJdYkspcWN1vb65 Keith Bieszczat AUTH TOKEN 

cr_2dvYx8b2Jxcr6rQ7rMK4g0f5lxd bot_2dvYwRDLFZfzm3QuX1Yfq0xCPZh

2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd API KEY

ngrok config check curl
-X POST
-H "Authorization: Bearer {2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd}"
-H "Content-Type: application/json"
-H "Ngrok-Version: 2"
-d '{"acl":["bind:1.tcp.ngrok.io:20002","bind:132.devices.company.com"],"description":"for device #132","public_key":"ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDmGS49FkSODAcKhn3+/47DW2zEn19BZvzRQ8RZjL3v6hCIX2qXfsFK35EGxNI0wV23H4xXC2gVRPHKU71YnCb50tad3yMBTM6+2yfGsEDasEH/anmBLclChKvuGiT547RskZlpbAbdq3GvbzmY+R/2EBRMOiObpc8XmSzKAd05j28kqN0+rZO65SWId0MXdvJdSCSAnuRqBNd/aXKlu8hBPDcgwbT2lMkuR+ApoBS2FLRBOiQyt2Ol0T7Uuf7lTLlazpGB3uTw5zFYUNXkuuI6cAP8QYuY1Bne/hNrG8t3Aw9a1yc2C4Fz1hJ/4OMRxTQ8SUQf+Rmxs8DryMlMFJ8r device132@example.com"}'
https://api.ngrok.com/ssh_credentials { "acl": ["bind:1.tcp.ngrok.io:20002", "bind:132.devices.company.com"], "created_at": "2024-02-16T19:35:31Z", "description": "for device #132", "id": "sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "public_key": "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDmGS49FkSODAcKhn3+/47DW2zEn19BZvzRQ8RZjL3v6hCIX2qXfsFK35EGxNI0wV23H4xXC2gVRPHKU71YnCb50tad3yMBTM6+2yfGsEDasEH/anmBLclChKvuGiT547RskZlpbAbdq3GvbzmY+R/2EBRMOiObpc8XmSzKAd05j28kqN0+rZO65SWId0MXdvJdSCSAnuRqBNd/aXKlu8hBPDcgwbT2lMkuR+ApoBS2FLRBOiQyt2Ol0T7Uuf7lTLlazpGB3uTw5zFYUNXkuuI6cAP8QYuY1Bne/hNrG8t3Aw9a1yc2C4Fz1hJ/4OMRxTQ8SUQf+Rmxs8DryMlMFJ8r device132@example.com", "uri": "https://api.ngrok.com/ssh_credentials/sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh" }

curl
-X GET
-H "Authorization: Bearer {2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd}"
-H "Ngrok-Version: 2"
https://api.ngrok.com/ssh_credentials/sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh

{ "acl": ["bind:1.tcp.ngrok.io:20002", "bind:132.devices.company.com"], "created_at": "2024-02-16T19:35:31Z", "description": "my dev machine", "id": "sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh", "metadata": "{"hostname": "macbook.local"}", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "public_key": "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDmGS49FkSODAcKhn3+/47DW2zEn19BZvzRQ8RZjL3v6hCIX2qXfsFK35EGxNI0wV23H4xXC2gVRPHKU71YnCb50tad3yMBTM6+2yfGsEDasEH/anmBLclChKvuGiT547RskZlpbAbdq3GvbzmY+R/2EBRMOiObpc8XmSzKAd05j28kqN0+rZO65SWId0MXdvJdSCSAnuRqBNd/aXKlu8hBPDcgwbT2lMkuR+ApoBS2FLRBOiQyt2Ol0T7Uuf7lTLlazpGB3uTw5zFYUNXkuuI6cAP8QYuY1Bne/hNrG8t3Aw9a1yc2C4Fz1hJ/4OMRxTQ8SUQf+Rmxs8DryMlMFJ8r device132@example.com", "uri": "https://api.ngrok.com/ssh_credentials/sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh" }

curl
-X GET
-H "Authorization: Bearer {2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd}"
-H "Ngrok-Version: 2"
https://api.ngrok.com/ssh_credentials

{ "next_page_uri": null, "ssh_credentials": [ { "acl": ["bind:1.tcp.ngrok.io:20002", "bind:132.devices.company.com"], "created_at": "2024-02-16T19:35:31Z", "description": "for device #132", "id": "sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "public_key": "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDmGS49FkSODAcKhn3+/47DW2zEn19BZvzRQ8RZjL3v6hCIX2qXfsFK35EGxNI0wV23H4xXC2gVRPHKU71YnCb50tad3yMBTM6+2yfGsEDasEH/anmBLclChKvuGiT547RskZlpbAbdq3GvbzmY+R/2EBRMOiObpc8XmSzKAd05j28kqN0+rZO65SWId0MXdvJdSCSAnuRqBNd/aXKlu8hBPDcgwbT2lMkuR+ApoBS2FLRBOiQyt2Ol0T7Uuf7lTLlazpGB3uTw5zFYUNXkuuI6cAP8QYuY1Bne/hNrG8t3Aw9a1yc2C4Fz1hJ/4OMRxTQ8SUQf+Rmxs8DryMlMFJ8r device132@example.com", "uri": "https://api.ngrok.com/ssh_credentials/sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh" } ], "uri": "https://api.ngrok.com/ssh_credentials" } curl
-X PATCH
-H "Authorization: Bearer {2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd}"
-H "Content-Type: application/json"
-H "Ngrok-Version: 2"
-d '{"description":"my dev machine","metadata":"{"hostname": "macbook.local"}"}'
https://api.ngrok.com/ssh_credentials/sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh { "acl": ["bind:1.tcp.ngrok.io:20002", "bind:132.devices.company.com"], "created_at": "2024-02-16T19:35:31Z", "description": "my dev machine", "id": "sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh", "metadata": "{"hostname": "macbook.local"}", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "public_key": "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDmGS49FkSODAcKhn3+/47DW2zEn19BZvzRQ8RZjL3v6hCIX2qXfsFK35EGxNI0wV23H4xXC2gVRPHKU71YnCb50tad3yMBTM6+2yfGsEDasEH/anmBLclChKvuGiT547RskZlpbAbdq3GvbzmY+R/2EBRMOiObpc8XmSzKAd05j28kqN0+rZO65SWId0MXdvJdSCSAnuRqBNd/aXKlu8hBPDcgwbT2lMkuR+ApoBS2FLRBOiQyt2Ol0T7Uuf7lTLlazpGB3uTw5zFYUNXkuuI6cAP8QYuY1Bne/hNrG8t3Aw9a1yc2C4Fz1hJ/4OMRxTQ8SUQf+Rmxs8DryMlMFJ8r device132@example.com", "uri": "https://api.ngrok.com/ssh_credentials/sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh" } curl
-X POST
-H "Authorization: Bearer {2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd}"
-H "Content-Type: application/json"
-H "Ngrok-Version: 2"
-d '{"description":"development cred for alan@example.com"}'
https://api.ngrok.com/credentials { "acl": [], "created_at": "2024-02-16T19:35:10Z", "description": "development cred for alan@example.com", "id": "cr_2cSjwF80LQJdOIaFZDbLWO9pMxd", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "token": "2cSjwF80LQJdOIaFZDbLWO9pMxd_3qYXgk4mMNpksRrJdRt6Z", "uri": "https://api.ngrok.com/credentials/cr_2cSjwF80LQJdOIaFZDbLWO9pMxd" } curl
-X GET
-H "Authorization: Bearer {2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd}"
-H "Ngrok-Version: 2"
https://api.ngrok.com/credentials/cr_2cSjwF80LQJdOIaFZDbLWO9pMxd

{ "acl": [], "created_at": "2024-02-16T19:35:10Z", "description": "device alpha-2", "id": "cr_2cSjwF80LQJdOIaFZDbLWO9pMxd", "metadata": "{"device_id": "d5111ba7-0cc5-4ba3-8398-e6c79e4e89c2"}", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "token": null, "uri": "https://api.ngrok.com/credentials/cr_2cSjwF80LQJdOIaFZDbLWO9pMxd" } curl
-X GET
-H "Authorization: Bearer {2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd}"
-H "Ngrok-Version: 2"
https://api.ngrok.com/credentials

{ "credentials": [ { "acl": [], "created_at": "2024-02-16T19:35:09Z", "description": "credential for "api-examples-c954256d6ada8b72@example.com"", "id": "cr_2cSjwL9yhXwTeYnIOSxZlvZ8S8y", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "token": null, "uri": "https://api.ngrok.com/credentials/cr_2cSjwL9yhXwTeYnIOSxZlvZ8S8y" }, { "acl": ["bind:1.tcp.ngrok.io:20002", "bind:132.devices.company.com"], "created_at": "2024-02-16T19:35:10Z", "description": "for device #132", "id": "cr_2cSjwHg6uyMl2h31jEgXZOHI77u", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "token": null, "uri": "https://api.ngrok.com/credentials/cr_2cSjwHg6uyMl2h31jEgXZOHI77u" }, { "acl": [], "created_at": "2024-02-16T19:35:10Z", "description": "development cred for alan@example.com", "id": "cr_2cSjwF80LQJdOIaFZDbLWO9pMxd", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "token": null, "uri": "https://api.ngrok.com/credentials/cr_2cSjwF80LQJdOIaFZDbLWO9pMxd" } ], "next_page_uri": null, "uri": "https://api.ngrok.com/credentials" }

curl
-X PATCH
-H "Authorization: Bearer {2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd}"
-H "Content-Type: application/json"
-H "Ngrok-Version: 2"
-d '{"description":"device alpha-2","metadata":"{"device_id": "d5111ba7-0cc5-4ba3-8398-e6c79e4e89c2"}"}'
https://api.ngrok.com/credentials/cr_2cSjwF80LQJdOIaFZDbLWO9pMxd { "acl": [], "created_at": "2024-02-16T19:35:10Z", "description": "device alpha-2", "id": "cr_2cSjwF80LQJdOIaFZDbLWO9pMxd", "metadata": "{"device_id": "d5111ba7-0cc5-4ba3-8398-e6c79e4e89c2"}", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "token": null, "uri": "https://api.ngrok.com/credentials/cr_2cSjwF80LQJdOIaFZDbLWO9pMxd" } import ngrok

listener = ngrok.forward("localhost:8080", authtoken_from_env=True, circuit_breaker=0.5)

print(f"Ingress established at: {listener.url()}");

package main

import ( "context" "fmt" "log" "net" "net/http" "net/url" "os"

"golang.ngrok.com/ngrok"
"golang.ngrok.com/ngrok/config"
)

func main() { l, err := ngrok.Listen(context.Background(), config.HTTPEndpoint( config.WithCircuitBreaker(0.1), ), ngrok.WithAuthtokenFromEnv(), ) if err != nil { log.Fatal(err) } fmt.Println("Running at", l.URL()) go makeRequests(l.URL()) http.Serve(l, http.HandlerFunc(func(w http.ResponseWriter, r *http.Request) { if r.URL.Path == "/500" { w.WriteHeader(500) fmt.Fprintln(w, "Hello error!") } else { w.WriteHeader(200) fmt.Fprintln(w, "Hello world!") } })) }

func makeRequests(appURL string) { // make sure we always dial the same IP addresss for testing purposes because // circuit breaker state is applied on each ngrok edge server individually u, _ := url.Parse(appURL) addrs, err := net.LookupHost(u.Host) if err != nil { log.Fatal(err) } httpClient := http.Client{Transport: &http.Transport{ Dial: func(network, _ string) (net.Conn, error) { return net.Dial(network, addrs[0]+":443") }, }}

// make requests that return a 500 until the circuit opens
for {
	resp, err := httpClient.Get(appURL + "/500")
	if err != nil {
		log.Fatal(err)
	}
	fmt.Printf("Status Code %d\n", resp.StatusCode)
	if resp.StatusCode == 503 {
		fmt.Println("Circuit opened")
		break
	}
}

// make requests that will eventually return a 200 which will close the circuit
for {
	resp, err := httpClient.Get(appURL)
	if err != nil {
		log.Fatal(err)
	}
	fmt.Printf("Status Code %d\n", resp.StatusCode)
	if resp.StatusCode != 503 {
		fmt.Println("Circuit closed")
		os.Exit(0)
	}
}
}

package main

import ( "context" "fmt" "log" "net" "net/http" "net/url" "os"

"golang.ngrok.com/ngrok"
"golang.ngrok.com/ngrok/config"
)

func main() { l, err := ngrok.Listen(context.Background(), config.HTTPEndpoint( config.WithCircuitBreaker(0.1), ), ngrok.WithAuthtokenFromEnv(), ) if err != nil { log.Fatal(err) } fmt.Println("Running at", l.URL()) go makeRequests(l.URL()) http.Serve(l, http.HandlerFunc(func(w http.ResponseWriter, r *http.Request) { if r.URL.Path == "/500" { w.WriteHeader(500) fmt.Fprintln(w, "Hello error!") } else { w.WriteHeader(200) fmt.Fprintln(w, "Hello world!") } })) }

func makeRequests(appURL string) { // make sure we always dial the same IP addresss for testing purposes because // circuit breaker state is applied on each ngrok edge server individually u, _ := url.Parse(appURL) addrs, err := net.LookupHost(u.Host) if err != nil { log.Fatal(err) } httpClient := http.Client{Transport: &http.Transport{ Dial: func(network, _ string) (net.Conn, error) { return net.Dial(network, addrs[0]+":443") }, }}

// make requests that return a 500 until the circuit opens
for {
	resp, err := httpClient.Get(appURL + "/500")
	if err != nil {
		log.Fatal(err)
	}
	fmt.Printf("Status Code %d\n", resp.StatusCode)
	if resp.StatusCode == 503 {
		fmt.Println("Circuit opened")
		break
	}
}

// make requests that will eventually return a 200 which will close the circuit
for {
	resp, err := httpClient.Get(appURL)
	if err != nil {
		log.Fatal(err)
	}
	fmt.Printf("Status Code %d\n", resp.StatusCode)
	if resp.StatusCode != 503 {
		fmt.Println("Circuit closed")
		os.Exit(0)
	}
}
export NGROK_AUTHTOKEN="<2dvYx8b2Jxcr6rQ7rMK4g0f5lxd_6MRbqiQJdYkspcWN1vb65>" go mod init example.com/ngrok-circuit-breaker go get golang.ngrok.com/ngrok go run example.go import ngrok

listener = ngrok.forward("localhost:8080", authtoken_from_env=True, verify_webhook_provider="twilio", verify_webhook_secret="{twilio signing secret}")

print(f"Ingress established at: {listener.url()}");

git clone https://github.com/ngrok/ngrok-webhook-nodejs-sample.git cd ngrok-webhook-nodejs-sample npm install npm start ngrok http 3000

ngrok http 3000 --verify-webhook stripe --verify-webhook-secret {whsec_ 5V2GHGaht2mGJGNOmesTtTaxuJWFRssS}

authtoken: 4nq9771bPxe8ctg7LKr_2ClH7Y15Zqe4bWLWF9p api_key: 24yRd5U3DestCQapJrrVHLOqiAC_7RviwRqpd3wc9dKLujQZN connect_timeout: 30s console_ui: true console_ui_color: transparent dns_resolver_ips:

1.1.1.1
8.8.8.8 heartbeat_interval: 1m heartbeat_tolerance: 5s inspect_db_size: 104857600 # 100mb inspect_db_size: 50000000 log_level: info log_format: json log: /var/log/ngrok.log metadata: '{"serial": "00012xa-33rUtz9", "comment": "For customer alan@example.com"}' proxy_url: socks5://localhost:9150 region: us remote_management: false root_cas: trusted update_channel: stable update_check: false version: 2 web_addr: localhost:4040 tunnels: website: addr: 8888 basic_auth:
"bob:bobpassword" schemes:
https host_header: "myapp.ngrok.dev" inspect: false proto: http domain: myapp.ngrok.dev
e2etls: addr: 9000 proto: tls domain: myapp.example.com crt: example.crt key: example.key

policyenforced: policy: inbound: - name: LimitIPs expressions: - "conn.ClientIP != '1.1.1.1'" actions: - type: deny addr: 8000 proto: tcp

ssh-access: addr: 22 proto: tcp remote_addr: 1.tcp.ngrok.io:12345

my-load-balanced-website: labels: - env=prod - team=infra addr: 8000

tunnels:
httpbin: proto: http addr: 8000 domain: alan-httpbin.ngrok.dev demo: proto: http addr: 9090 domain: demo.inconshreveable.com inspect: false ngrok start httpbin

tunnels: my-cool-website: labels: - env=prod - team=infra addr: 8000 inspect: false ssh-tunnel: labels: - hostname=my-hostname - service=ssh - team=development addr: 22 api_key: 24yRd5U3DestCQapJrrVHLOqiAC_7RviwRqpd3wc9dKLujQZN authtoken: 4nq9771bPxe8ctg7LKr_2ClH7Y15Zqe4bWLWF9p

log: /var/log/ngrok.log

metadata

This is a user-supplied custom string that will be returned as part of the ngrok API response to the list online sessions resource for all tunnels started by this agent. This is a useful mechanism to identify tunnels by your own device or customer identifier. Maximum 4096 characters.

metadata: bad8c1c0-8fce-11e4-b4a9-0800200c9a66

web_allow_hosts:

8.8.8.8
example.com curl http://localhost:4040/api/
{ "tunnels": [ { "name": "command_line", "uri": "/api/tunnels/command_line", "public_url": "https://d95211d2.ngrok.io", "proto": "https", "config": { "addr": "localhost:80", "inspect": true, }, "metrics": { "conns": { "count": 0, "gauge": 0, "rate1": 0, "rate5": 0, "rate15": 0, "p50": 0, "p90": 0, "p95": 0, "p99": 0 }, "http": { "count": 0, "rate1": 0, "rate5": 0, "rate15": 0, "p50": 0, "p90": 0, "p95": 0, "p99": 0 } } }, ... ], "uri": "/api/tunnels" } { "addr": "22", "proto": "tcp", "name": "ssh" }

{ "name": "", "uri": "/api/tunnels/", "public_url": "tcp://0.tcp.ngrok.io:53476", "proto": "tcp", "config": { "addr": "localhost:22", "inspect": false, }, "metrics": { "conns": { "count": 0, "gauge": 0, "rate1": 0, "rate5": 0, "rate15": 0, "p50": 0, "p90": 0, "p95": 0, "p99": 0 }, "http": { "count": 0, "rate1": 0, "rate5": 0, "rate15": 0, "p50": 0, "p90": 0, "p95": 0, "p99": 0 } } }

{ "name": "command_line", "uri": "/api/tunnels/command_line", "public_url": "https://ac294125.ngrok.io", "proto": "https", "config": { "addr": "localhost:80", "inspect": true, }, "metrics": { "conns": { "count": 0, "gauge": 0, "rate1": 0, "rate5": 0, "rate15": 0, "p50": 0, "p90": 0, "p95": 0, "p99": 0 }, "http": { "count": 0, "rate1": 0, "rate5": 0, "rate15": 0, "p50": 0, "p90": 0, "p95": 0, "p99": 0 } } } BHAHZGCJZK3BEVS7IRGZMKDF6USLO runner token apply to all commands

stripe login --api-key sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq

stripe login

stripe trigger payment_intent.succeeded

Secret key

pst_test_YWNjdF8xTTJKVGtMa2RJd0h1N2l4LE81ZEdIalZ6NlVuMUdjM3c3WkRnN0ZYRHZxRURwTXo_00gNK2DWAV run payment id

po_1OZNhvGF83d3fsgWC9jdBgcQ

run bank data DJqIeyHlhjb55r0K Routing number 031101279 ID ba_1OR7BGGF83d3fsgWxwDM4lDf

$ Stripe endpoint we_1Ova66GF83d3fsgW2nbowkDw Webhook signing secret: whsec_ 5V2GHGaht2mGJGNOmesTtTaxuJWFRssS

why?

req_3SnomkF11VBTwG

The payment failed. { "consent": { "terms_of_service": "accepted" }, "eid": "**", "expected_amount": "100000", "expected_payment_method_type": "link", "guid": "14b84001-905a-42f3-9e2b-18a9ebf0e15c540853", "init_checksum": "MXofbfTYAaKG1no6FZxkzMndcSrERGp3", "js_checksum": "qtod^n0=QU>azbu]Vn<D\^vUO[_esYxY=dwUca$<P<m^o?U^w", "key": "pk_live_*********************************************************************************************k76MVR", "last_displayed_line_item_group_details": { "shipping_rate_amount": "0", "subtotal": "100000", "total_discount_amount": "0", "total_exclusive_tax": "0", "total_inclusive_tax": "0" }, "muid": "eb78b5f0-bdd7-45f9-a924-dcf3e95a1a647d0ae4", "passive_captcha_ekey": "", "passive_captcha_token": "P1_eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJwYXNza2V5IjoibGxxQlR1SURGNkd1WWhCWTh4N1RXY2dLbWJHYUhpdk5DeTZBMDdPTnZ4NUNqdy9XcDkrR0hJTHo0bDdUbHFGSmVjSkNpSFR3N1AyVnZwVHh5RlUyVlgyL0lyZHVCZkc2eTd3RE9tTFRHcUsvUEwxK2V2SWpQcEhwNFRCaVJMaVV2eURPRG4wWnFPa1pONS9NNXVka0dsNER2R3E4djNaMHEvRXRESWZ0ZllNZTBCRVFZTklIU1dROXY3QVRZWHMxWUwvRXhQK3pubmlDUHkvOTQ3Z0kxdjd1Zzk1cG8ycnJGS0ErK2FKeHJsR3lnb3JzRTUwaVNtYm1mNlJuUURPYWcvbWh2OE9GNXg0bE1KMXVNdUw0Rm1UQzNpS2lMell3eDUyNDc2QWlvdEw4aEEzWWVYbEJySkdlT3lxSVRtaytraWY1M05Xd2VjdDY0KytnM3NGL0UrMjg4a04vSUFIQ0FEdEYxbU1vZEFSTjZjL3pvMlBTYUFtdGUzTVV5TTJXT09ZTENWM01VOHRhOHk0emc0d0txSXg0U3lKemxwcCtXVTRvRy9DU0ZRNXYwa29iNVBPMnJtc3QxTkVQT3ozMlNUQ1BFUkZReFdXeWtBaVErc01QbFVmZmhsYnBEcldrMnF6VEQxR0dxQ254MksxeExvYUlhVW5yWWxyNXFZZTVLVHJ4bnNQNUlDVTNrNjBlWVdwbzZBVVJCaGFiOE4rK1g3TEpuRzlLRmJTM2YxM2R5dDM5MlA1WTJZcEFGYUxnT0laSnppSjJOZHkvMXRxbURucFZXaVZrRG1xSjZJRU5UNTh4Y0NvS1oyRjRqVWtGSk5DVWRaejZYdVpLMHY5bGhtRmxoZGRSNGdjVWZQWWFtUjAwUG5wL3c5dXAySkF4UDRRc2RjN2RHUWhCOFJrL0NSVVdFTll5NEFLbXBLeldsMlNscy9SOEpUQUdraGRFdTZvbjNBb2Z5NmZJbC9kK0NCYzlwYjBHeDhaaU9qUmZFbjVMSWNBTUN0Ymp0TFkwaURWWFdQZUM1UUtaMUF1c051TVk2L1lVdFhNZk03eUNyeUVBMG45ajNlYy9hbk9zT01WUWxlWkFDT3RjRmx1KzIvVmlpUDVORG14VGRZc2R4MWU4VFR0MWFpL05IRmxVNXh4cGVmMEFldkx2NXRmWW41WTkxeU1vdGlZaXhvMnhFWkp6NmgycHZRVnpIVnN4aDNNeFRWMWlOZ1kySHVXbVNPbTZjOWdBRWtGZkZCSVM3V2VwY2g2Tng0TzlFVWh0VnpXaW5KRDFvNXZlYkdGMnBJakVYR0lSWVZNSCtWbnJaM2t1V2djOUpiRWtyYStiRjBkd0pxY2F2VityRkdqOW9ENFFSZkMwNmpSMzlvdU5CTmVzSU8xNWRFVE9TdDRHOGxMaUJ4QkhyL283VnR6bHZ2djdhbFI3K3VidlNXdlQ2QlI4cjdOQmxXR3BOM0lCRllnby96a0VJUmRnN0Fzb3RKWndPZENGdnBSbWhDYWJKVklzZTlwSXlrTWl3WGYvUnpTU2wzdkJiMSs4UDBtbFVkNEVCZS9CTnNTcmF4Nm9NWEVmR1c0N29YNFBmMTlqcm9qWnhyaDBOOWJ1b04yWlF0QWQwU255ZndQNUZYYTh2dWp0OGtrUXNlRHZaWVpCRi9TSW1BM2ZRdmM3VnZ5YVNSQktabHBzdFlzMElzYVhpU1pGbFg3NUdrbFVpZWNSREdleFROQVpObWtlN0lTbm4xbVpJaFpUOVlhN1RIdU0yM2dReEs3RnlFcUlzcjNadjYwVDBOSHptdk5lN0w0NkFudDFSbEIxZWQxWW1VN3pvVzdXbGZpOUc0MTZXZ28wQloyUDR6K1hmTXFQc2cwTFdKTytZVFI4Ym0wVzFpQ0ZEdWpUM3l5RGJJN0JWUTlwWDlEMnRjVXE0ajlpSTZjZktrb0d3Z2tCa1dtRmFuQ0QvV3BjTmVnSkJCMEJ0WHR2Z2NSeGQwbmpxR3F2aXIrZGF1TTlNZ0lrZDNLeHNCVXJkd2tySVJhOElvaDlCQmlkUDJMY0pkU1RWUittdFBMRW1iaWZoZVh5clRybUtEcEEvVnNCSmc2MEpBNXp3Q1E5NTlWWWQ5TFh5VnFhdnlrMzRwTC9NaTBPL1dnWmllbUhUNGFVSDdZVG5TekxMYmFQdW1aYVdpMkt4RFFkWmY0cW96akVya21iVnFOSk1XbXYzd2E3QkZhNzdyY0E2RjdXQmRUVkt0V0pqeXp0WWpyTHllNEpST0tsQlh1WmtxbVpnOGNsQlFoNGJobTI4c1FtQzI3UlBkM0dEMGwwTTFyMGpsZitpWDVLc3JGTitHNFJPMzFLT2ZNM2o1ajVzQzBaYytDa2JaNklwK1VKVmk2RmRESUFoMU5LOTl6eWhZR2QwMzlVU2FqdU02TmQxeG4zMTYxVUJQZGpkTFZpb3pFUFZqdXpEZUN6QXNmcDJWUTZyS1JmWUFjNEtVeVdmaEExTThUVHVXL1pJUW5ja2gzUm9UVm5JVE81bkh1YXNGYitYVEJZL0FaOEJzVjRkanFMdUVHc01YQThoV0FYMGxrejJXN1VWZVVINFpHald0T0d0SHZBZURJOTJiT0V4OXk0YWhrWU93czYyWURHL1F5c1FNc2pFWFMzb3d4ekcvNVBZaVJ6RlAwaDFYS09McXhNdmYrM2NlYlN3UkNOdkhMV2tYT2k1bk82TzROait5OGR2UGhVSWVBS0tWTTBGTmw5UW1XNzBFTEdPZjVOZzdWZGRBY3RWd3VsOUo0elAyUGhsOFF5bi8xK1l2bFpXMmpHUmQ3eXd2cUZVVVlPU2htNkk2VFB2eG4vVCtKWHJ4WUlaMmVnbVoyVy91UEhXbVFucGtZUUYzaEhIYnlkbnhDOEpGa2E3NGJNQjZRR3J0VHBvaGhUOFo1U0lXU1Iwbkt3UHhBOGdZaThDRlhKRXErcFpkT1RNYUhiay9RcDJmMFFCQXA4aEpKMU5IUWdrRCtZdEFBTnV5bWR5YW90RmJQeS9STnJyS1AyOTZiUlF5SVV4aU10dlo2Z1piMFRqK252WTRUVFU4UzNNWW14Nysrd242N1Rxcm11Zytjc3FMNEJVdnhmdGlCWnI3b0M1cnNmRFQ5d21XSS8iLCJleHAiOjE3MTA3NDI1OTksInNoYXJkX2lkIjo4MzM0NDA4OTcsInBkIjowLCJjZGF0YSI6IjRKOGNUeDBPRjd6byszdzB1WHNtZ0dzSEpubE5Geml0VUZON0dhYWNzQWpFdWZsbmlta3lydXpwT2FGVnl5S2hXSk9tVmdwcEdtOFZtMWNWOWJnL3BacDhHcDVmN1N0ZEpvTlU5M0JhaHRKbmE4V2pNZkVEWnp0QUUwTXRMQ0Qxb1Z2dzc4SDlJREdqK0FmTXVaZFp0OFpiT0JmZ1dmZUluRVVLNUx0dHhnOGtaUU93dW91S0ExTmxRamxiQk9vM1NGT1ZFdERPdTlESjdsN2JZL0x0OU9KME9NNTBZTjQ9VkpFeHI4ZHFFQWpuenI1UiJ9.pPcNQ2Y328R8U7Sar4Z5U0GO9y1caCAAPmbIy3aCnYo", "payment_method": "pm_1OvZUOGF83d3fsgWiXYpUHQh", "rv_timestamp": "qto>n<Q=U&CyY&>X^r<YNr<YN<Y_C<Y_C<Y^zY_<Y^n{U>o&U&CyY=P=eODdbL%e&areOMrY=n=YxnDd_Mv[bL>[OTCdOaveu%euUyX%n{U>e&U&Cyd&auY_n=d&;;X_d%d&UxdRP#[bd#exQxX=L&X&n%eu\\$ex]sY&ovXOUu[_$reunDd&osd=MueOP;d&<yY_<sX^o?U^w", "sid": "f931f0fd-f83a-4921-903f-45f5b359d9925f3b2a", "version": "2d3a08de7b" }

pip3 install stripe python3 -m flask run --port=4242 python3 -m flask run --port=4242 $ stripe listen --forward-to localhost:4242/webhook $ stripe trigger payment_intent.succeeded #! /usr/bin/env python3.6

Python 3.6 or newer required.

import json import os import stripe

This is your test secret API key.

stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'

#! /usr/bin/env python3.6

Python 3.6 or newer required.

import json import os import stripe

This is your test secret API key.

stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'

Replace this endpoint secret with your endpoint's unique secret

If you are testing with the CLI, find the secret by running 'stripe listen'

If you are using an endpoint defined with the API or dashboard, look in your webhook settings

at https://dashboard.stripe.com/webhooks

endpoint_secret = 'whsec_...' from flask import Flask, jsonify, request

app = Flask(name)

@app.route('/webhook', methods=['POST']) def webhook(): event = None payload = request.data

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
Run

https://dashboard.stripe.com/test/payouts/po_1OZNhvGF83d3fsgWC9jdBgcQ#wb-N4Igdghgbglg5hALjA9mEAuUEDGyoCmAKhAEaYgAmBAzspMmjSADQiJkASMdKATgE9MAbQC6bPigCuiAt16CRogL5saMAF4wwcTGCkAbA2wAWBeCcQUA7AAYoJ1iFjrSMAzEQCAsimoUXGFIDAidqOm0kVDBmLBAaAhC8AkoASUoKAHcCAH0ARgB5KAgANhKAcQAxAA4AZkpagDMaOAB1ACYwUhRMgGsAEUynDnIMEAJCMERmNgmCKdjQRvdZPkX4ggg+HEcxpzokKVixCVppbdC9thRSACsCPHSKJzmpogEAB0uQF75JPneXyUbEoSEuwGUqg2SVkaQyGH0RjUiQesIAgohZABbD6IJ4IwwGSHKIA

Download Stripe client secret

const {client_secret: seti_1NG8Du2eZvKYlo2C9XMqbR0x_secret_O2CdhLwGFh2Aej7bCY7qp8jlIuyR8DJ/ } = await res.json();

const {error} = await stripe.confirmPayment({ //Elements instance that was used to create the Payment Element elements, clientSecret, confirmParams: { return_url: 'https://example.com/order/123/complete', }, });

if (error) { // This point will only be reached if there is an immediate error when // confirming the payment. Show error to your customer (for example, payment // details incomplete) setErrorMessage(error.message); } else { // Your customer will be redirected to your return_url. For some payment // methods like iDEAL, your customer will be redirected to an intermediate // site first to authorize the payment, then redirected to the return_url. } import stripe stripe.api_key = "sk_test_51OR5eP...OF00CdDfT6Xqsk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq" stripe.Event.list(limit=3) RESPONSE { "object": "list", "url": "/v1/events", "has_more": false, "data": [ { "id": "evt_1NG8Du2eZvKYlo2CUI79vXWy", "object": "event", "api_version": "2019-02-19", "created": 1686089970, "data": { "object": { "id": "seti_1NG8Du2eZvKYlo2C9XMqbR0x", "object": "setup_intent", "application": null, "automatic_payment_methods": null, "cancellation_reason": null, "client_secret": "seti_1NG8Du2eZvKYlo2C9XMqbR0x_secret_O2CdhLwGFh2Aej7bCY7qp8jlIuyR8DJ", "created": 1686089970, "customer": null, "description": null, "flow_directions": null, "last_setup_error": null, "latest_attempt": null, "livemode": false, "mandate": null, "metadata": {}, "next_action": null, "on_behalf_of": null, "payment_method": "pm_1NG8Du2eZvKYlo2CYzzldNr7", "payment_method_options": { "acss_debit": { "currency": "cad", "mandate_options": { "interval_description": "First day of every month", "payment_schedule": "interval", "transaction_type": "personal" }, "verification_method": "automatic" } }, "payment_method_types": [ "acss_debit" ], "single_use_mandate": null, "status": "requires_confirmation", "usage": "off_session" } }, "livemode": false, "pending_webhooks": 0, "request": { "id": null, "idempotency_key": null }, "type": "setup_intent.created" } {...} {...} ], }

OK ID req_ZIIVfKfNp6QrOh

const {client_secret: seti_1NG8Du2eZvKYlo2C9XMqbR0x_secret_O2CdhLwGFh2Aej7bCY7qp8jlIuyR8DJ} = await res.json();

const {error} = await stripe.confirmPayment({ //Elements instance that was used to create the Payment Element elements, clientSecret, confirmParams: { return_url: 'https://example.com/order/123/complete', }, });

if (error) { // This point will only be reached if there is an immediate error when // confirming the payment. Show error to your customer (for example, payment // details incomplete) setErrorMessage(error.message); } else { // Your customer will be redirected to your return_url. For some payment // methods like iDEAL, your customer will be redirected to an intermediate // site first to authorize the payment, then redirected to the return_url. } import stripe stripe.api_key = "sk_test_51OR5eP...OF00CdDfT6Xqsk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq" stripe.Event.list(limit=3) RESPONSE { "object": "list", "url": "/v1/events", "has_more": false, "data": [ { "id": "evt_1NG8Du2eZvKYlo2CUI79vXWy", "object": "event", "api_version": "2019-02-19", "created": 1686089970, "data": { "object": { "id": "seti_1NG8Du2eZvKYlo2C9XMqbR0x", "object": "setup_intent", "application": null, "automatic_payment_methods": null, "cancellation_reason": null, "client_secret": "seti_1NG8Du2eZvKYlo2C9XMqbR0x_secret_O2CdhLwGFh2Aej7bCY7qp8jlIuyR8DJ", "created": 1686089970, "customer": null, "description": null, "flow_directions": null, "last_setup_error": null, "latest_attempt": null, "livemode": false, "mandate": null, "metadata": {}, "next_action": null, "on_behalf_of": null, "payment_method": "pm_1NG8Du2eZvKYlo2CYzzldNr7", "payment_method_options": { "acss_debit": { "currency": "cad", "mandate_options": { "interval_description": "First day of every month", "payment_schedule": "interval", "transaction_type": "personal" }, "verification_method": "automatic" } }, "payment_method_types": [ "acss_debit" ], "single_use_mandate": null, "status": "requires_confirmation", "usage": "off_session" } }, "livemode": false, "pending_webhooks": 0, "request": { "id": null, "idempotency_key": 6f5410cb-1ecc-4302-8130-baf8dd8c0a50 }, "type": "setup_intent.created" } {...} {...} ], }

stripe .retrieveSetupIntent( '{fcsess_client_secret_KRJTKvCY3IKoYTrW18EazcO3 /seti_1NG8Du2eZvKYlo2C9XMqbR0x_secret_O2CdhLwGFh2Aej7bCY7qp8jlIuyR8DJ }', ) .then(function(result) { // Handle result.error or result.paymentIntent }); stripe.collectFinancialConnectionsAccounts({ clientSecret: '{fcsess_client_secret_KRJTKvCY3IKoYTrW18EazcO3}' }) .then(function(result) { if (result.error) { // Inform the customer that there was an error. console.log(result.error.message);

// Handle next step based on length of accounts array
} else if (result.financialConnectionsSession.accounts.length === 0) {
  console.log('No accounts were linked');
} else {
  console.log(result.financialConnectionsSession.accounts)
}
});

{ "object": "customer_session", "client_secret": "_POpxYpmkXdtttYtZQYhrsOJZ2RCQ9kCqqXRU6qrP5c4Jgje", "components": { "buy_button": { "enabled": false }, "pricing_table": { "enabled": true } }, "customer": "cus_PO34b57IOUb83c", "expires_at": 1684790027, "livemode": false } { "object": "customer_session", "client_secret": "_POpxYpmkXdtttYtZQYhrsOJZ2RCQ9kCqqXRU6qrP5c4Jgje", "components": { "buy_button": { "enabled": false }, "pricing_table": { "enabled": true } }, "customer": "cus_PO34b57IOUb83c", "expires_at": 1684790027, "livemode": false }

Create a folder $ mkdir actions-runner && cd actions-runner

Download the latest runner package $ curl -o actions-runner-osx-x64-2.314.1.tar.gz -L https://github.com/actions/runner/releases/download/v2.314.1/actions-runner-osx-x64-2.314.1.tar.gz

Optional: Validate the hash $ echo "3faff4667d6d12c41da962580168415d628e3ffba9924b9ac995752087efc921 actions-runner-osx-x64-2.314.1.tar.gz" | shasum -a 256 -c

Extract the installer $ tar xzf ./actions-runner-osx-x64-2.314.1.tar.gz Configure

Create the runner and start the configuration experience $ ./config.sh --url https://github.com/grateful345/Wiz-Go-call-sign --token BHAHZGDHHICG3LFF53OICRLF6UR24

Last step, run it! $ ./run.sh Using your self-hosted runner

Use this YAML in your workflow file for each job runs-on: self-hosted

Orginization ID: e3ff35d1-cea4-4508-acb5-99d9cbd91e80


pk_live_51OR5ePGF83d3fsgW22PwNtYiShCVYIsrzZq2WxlxN2UAaB2qEIu0aUFJzjJxPtNT3rAs0Rvdo9XIVPb7rRMaeo3W00ALk76MVR PUBLISHABLE KEY LIVE

sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq secret test key STRIPE
[12:45 AM]
pk_test_51OR5ePGF83d3fsgWcl7ad29rrqOUNvjdYXN1JrElZlEyDloYQpFPuxSeRZH8KiCgvshlSaDYnuu1xxYiiWOCHj7W00Nrph1csX PUBLISHABLE KEY TEST


pk_live_51OR5ePGF83d3fsgW22PwNtYiShCVYIsrzZq2WxlxN2UAaB2qEIu0aUFJzjJxPtNT3rAs0Rvdo9XIVPb7rRMaeo3W00ALk76MVR

o5 council mainframe Ai — 03/17/2024 11:02 PM
print(f"Success! Here is your starter subscription product id: {starter_subscription.id}") print(f"Success! Here is your starter subscription price id: {starter_subscription_price.id}") python3 create_price.py Success! Here is your starter subscription product id: prod_0KxBDl589O8KAxCG1alJgiA6 Success! Here is your starter subscription price id: price_0KxBDm589O8KAxCGMgG7scjb stripe events resend evt_1OpkWDGF83d3fsgWRuQHTout { "id": "evt_1OpkWDGF83d3fsgWRuQHTout", "object": "event", "api_version": "2023-10-16", "created": 1709354993, "data": { "object": { "id": "clock_1OpkVpGF83d3fsgWXAn5JwxT", "object": "test_helpers.test_clock", "created": 1709354969, "deletes_after": 1711946969, "frozen_time": 1709354959, "livemode": false, "name": "10 day", "status": "ready" } }, "livemode": false, "pending_webhooks": 0, "request": { "id": "req_h41wlESGApv90k", "idempotency_key": null }, "type": "test_helpers.test_clock.deleted" } stripe charges --help

o5 council mainframe Ai — 03/17/2024 11:55 PM
"masked_api_key": "*9e2a1"
  }
March 18, 2024

o5 council mainframe Ai — Yesterday at 12:01 AM


o5 council mainframe Ai — Yesterday at 12:47 AM
"masked_api_key": "*9e2a1"
  }
[12:49 AM]
AF0F3FCCE9EE2011EF183E67AD67D6F299326E1E2F1B8DA8567F9FDA006F78F6 DUO SECRET KEY
[12:50 AM]
sH9wUncg7GsTTGIe7ydnISPHHbxZeUd7TspSmGk2  DUO SECRET KEY
[12:51 AM]
DIFRJUINL7UM749ZLTCJ INTEGRATION KEY
[12:51 AM]
api-8f5baae1.duosecurity.com
[12:53 AM]
73.44.108.236 IP ADDRESS

o5 council mainframe Ai — Yesterday at 1:03 AM

o5 council mainframe Ai — 02/25/2024 1:30 AM
stripe.Product.modify(
  "prod_NWjs8kKbJWmuuc",
  metadata={"order_id": "6735"}
[1:35 AM]... (1 KB left)
Expand
message.txt
51 KB

o5 council mainframe Ai — Yesterday at 1:10 AM
https://buy.stripe.com/3cscMY617bed7bWdRh
[1:13 AM]
https://buy.stripe.com/3cscMY617bed7bWdRh?client_reference_id=1000&prefilled_email=god964v%40gmail.com&prefilled_promo_code=1000
[1:16 AM]
Secret key
pst_test_YWNjdF8xTTJKVGtMa2RJd0h1N2l4LE81ZEdIalZ6NlVuMUdjM3c3WkRnN0ZYRHZxRURwTXo_00gNK2DWAV

o5 council mainframe Ai — Yesterday at 1:20 AM
$ ./config.sh --url https://github.com/grateful345/Wiz-Go-call-sign --token BHAHZGCJZK3BEVS7IRGZMKDF6USLO
GitHub
GitHub - grateful345/Wiz-Go-call-sign
Contribute to grateful345/Wiz-Go-call-sign development by creating an account on GitHub.

[1:23 AM]
BHAHZGCJZK3BEVS7IRGZMKDF6USLO.   Runner tokens BHAHZGDHHICG3LFF53OICRLF6UR24
[1:25 AM]

[1:27 AM]
<script async
  src="https://js.stripe.com/v3/buy-button.js">
</script>

<stripe-buy-button
  buy-button-id="buy_btn_1OvZeLGF83d3fsgWAamtMu9r"
  publishable-key="pk_live_51OR5ePGF83d3fsgW22PwNtYiShCVYIsrzZq2WxlxN2UAaB2qEIu0aUFJzjJxPtNT3rAs0Rvdo9XIVPb7rRMaeo3W00ALk76MVR"
>
</stripe-buy-button>

o5 council mainframe Ai — Yesterday at 1:34 AM
https://buy.stripe.com/3cscMY617bed7bWdRh

o5 council mainframe Ai — Yesterday at 1:45 AM
DJqIeyHlhjb55r0K
Routing number
031101279
ID
ba_1OR7BGGF83d3fsgWxwDM4lDf
[1:46 AM]
po_1OZNhvGF83d3fsgWC9jdBgcQ

o5 council mainframe Ai — Yesterday at 1:56 AM
we_1Ova66GF83d3fsgW2nbowkDw
 Stripe endpoint
[1:57 AM]
https://dashboard.stripe.com/test/payouts/po_1OZNhvGF83d3fsgWC9jdBgcQ#wb-N4Igdghgbglg5hALjA9mEAuUEDGyoCmAKhAEaYgAmBAzspMmjSADQiJkASMdKATgE9MAbQC6bPigCuiAt16CRogL5saMAF4wwcTGCkAbA2wAWBeCcQUA7AAYoJ1iFjrSMAzEQCAsimoUXGFIDAidqOm0kVDBmLBAaAhC8AkoASUoKAHcCAH0ARgB5KAgANhKAcQAxAA4AZkpagDMaOAB1ACYwUhRMgGsAEUynDnIMEAJCMERmNgmCKdjQRvdZPkX4ggg+HEcxpzokKVixCVppbdC9thRSACsCPHSKJzmpogEAB0uQF75JPneXyUbEoSEuwGUqg2SVkaQyGH0RjUiQesIAgohZABbD6IJ4IwwGSHKIA
Stripe Login | Sign in to the Stripe Dashboard
Sign in to the Stripe Dashboard to manage business payments and operations in your account. Manage payments and refunds, respond to disputes and more.
[2:00 AM]
stripe login --api-key sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq

o5 council mainframe Ai — Yesterday at 2:04 AM
pip3 install stripe

o5 council mainframe Ai — Yesterday at 2:27 AM
Event details
evt_3OvZUOGF83d3fsgW0CVGOJLf (run it)
[2:31 AM]
whsec_ 5V2GHGaht2mGJGNOmesTtTaxuJWFRssS
[2:32 AM]
Webhook signing secret whsec_ 5V2GHGaht2mGJGNOmesTtTaxuJWFRssS


FILE:
evt_1OvyoVGF83d3fsgWW9GjCrme



{
  "object": {
    "id": "file_1OvyoVGF83d3fsgWJ2y8LUzQ",
    "object": "file",
    "created": 1710839911,
    "expires_at": null,
    "filename": "Untitled_20240318.csv",
    "links": {
      "object": "list",
      "data": [],
      "has_more": false,
      "url": "/v1/file_links?file=file_1OvyoVGF83d3fsgWJ2y8LUzQ"
    },
    "purpose": "sigma_scheduled_query",
    "size": 64,
    "title": "Untitled for 2024-03-18",
    "type": "csv",
    "url": "https://files.stripe.com/v1/files/file_1OvyoVGF83d3fsgWJ2y8LUzQ/contents"
  },
  "previous_attributes": null
}
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

Stripe-Signature:
t=1492774577,
v1=5257a869e7ecebeda32affa62cdca3fa51cad7e77a0e56ff536d0ce8e108d8bd,
v0=6ffbb59b2300aae63f272406069a9788598b792a944a07aba816edb039989a39

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
# Set your secret key. Remember to switch to your live secret key in production.
# See your keys here: https://dashboard.stripe.com/apikeys
stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'

endpoint = stripe.WebhookEndpoint.create(
  url='https://example.com/my/webhook/endpoint',
  enabled_events=[
    'payment_intent.payment_failed',
    'payment_intent.succeeded',
  ],
)
# Set your secret key. Remember to switch to your live secret key in production.
# See your keys here: https://dashboard.stripe.com/apikeys
stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'

from django.http import HttpResponse

# If you are testing your webhook locally with the Stripe CLI you
# can find the endpoint's secret by running `stripe listen`
# Otherwise, find your endpoint's secret in your webhook settings in the Developer Dashboard
endpoint_secret = 'whsec_...'

# Using Django
@csrf_exempt
def my_webhook_view(request):
  payload = request.body
  sig_header = request.META['Stripe-Signature:
t=1492774577,
v1=5257a869e7ecebeda32affa62cdca3fa51cad7e77a0e56ff536d0ce8e108d8bd,
v0=6ffbb59b2300aae63f272406069a9788598b792a944a07aba816edb039989a39']
  event = None

  try:
    event = stripe.Webhook.construct_event(
      payload, sig_header, endpoint_secret
    )
  except ValueError as e:
    # Invalid payload
    print('Error parsing payload: {}'.format(str(e)))
    return HttpResponse(status=400)
  except stripe.error.SignatureVerificationError as e:
    # Invalid signature
    print('Error verifying webhook signature: {}'.format(str(e)))
    return HttpResponse(status=400)

  # Handle the event
  if event.type == 'payment_intent.succeeded':
    payment_intent = event.data.object # contains a stripe.PaymentIntent
    print('PaymentIntent was successful!')
  elif event.type == 'payment_method.attached':
    payment_method = event.data.object # contains a stripe.PaymentMethod
    print('PaymentMethod was attached to a Customer!')
  # ... handle other event types
  else:
    print('Unhandled event type {}'.format(event.type))
import json

# Webhooks are always sent as HTTP POST requests, so ensure
# that only POST requests reach your webhook view by
# decorating `webhook()` with `require_POST`.
#
# To ensure that the webhook view can receive webhooks,
# also decorate `webhook()` with `csrf_exempt`.
@require_POST
@csrf_exempt
def webhook(request):
import json
from django.http import HttpResponse

# Using Django
@csrf_exempt
def my_webhook_view(request):
  payload = request.body
  event = None

  try:
    event = stripe.Event.construct_from(
      json.loads(payload), stripe.api_key
    )
  except ValueError as e:
    # Invalid payload
    return HttpResponse(status=400)

  # Handle the event
  if event.type == 'payment_intent.succeeded':
    payment_intent = event.data.object # contains a stripe.PaymentIntent
    # Then define and call a method to handle the successful payment intent.
    # handle_payment_intent_succeeded(payment_intent)
  elif event.type == 'payment_method.attached':
    payment_method = event.data.object # contains a stripe.PaymentMethod
    # Then define and call a method to handle the successful attachment of a PaymentMethod.
    # handle_payment_method_attached(payment_method)
  # ... handle other event types
  else:
    print('Unhandled event type {}'.format(event.type))

  return HttpResponse(status=200)
stripe listen --forward-to localhost:4242/stripe_webhooks
stripe listen --events payment_intent.created,customer.created,payment_intent.succeeded,checkout.session.completed,payment_intent.payment_failed \
  --forward-to localhost:4242/webhook
stripe listen --load-from-webhooks-api --forward-to localhost:5000
Ready! Your webhook signing secret is '{{whsec_ 5V2GHGaht2mGJGNOmesTtTaxuJWFRssS}}' (^C to quit)


stripe trigger payment_intent.succeeded
Running fixture for: payment_intent
Trigger succeeded! Check dashboard for event details.
[
](https://<[your-website](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862>/<we_1Ova66GF83d3fsgW2nbowkDw>)
  # Process webhook data in `request.body`  return HttpResponse(status=200)
# Set your secret key. Remember to switch to your live secret key in production.
# See your keys here: https://dashboard.stripe.com/apikeys
stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'

from django.http import HttpResponse

# If you are testing your webhook locally with the Stripe CLI you
# can find the endpoint's secret by running `stripe listen`
# Otherwise, find your endpoint's secret in your webhook settings in the Developer Dashboard
endpoint_secret = 'whsec_...'

# Using Django
@csrf_exempt
def my_webhook_view(request):
  payload = request.body
  sig_header = request.META['Stripe-Signature:
t=1492774577,
v1=5257a869e7ecebeda32affa62cdca3fa51cad7e77a0e56ff536d0ce8e108d8bd,
v0=6ffbb59b2300aae63f272406069a9788598b792a944a07aba816edb039989a39']
  event = None

  try:
    event = stripe.Webhook.construct_event(
      payload, sig_header, endpoint_secret
    )
  except ValueError as e:
    # Invalid payload
    print('Error parsing payload: {}'.format(str(e)))
    return HttpResponse(status=400)
  except stripe.error.SignatureVerificationError as e:
    # Invalid signature
    print('Error verifying webhook signature: {}'.format(str(e)))
    return HttpResponse(status=400)

  # Handle the event
  if event.type == 'payment_intent.succeeded':
    payment_intent = event.data.object # contains a stripe.PaymentIntent
    print('PaymentIntent was successful!')
  elif event.type == 'payment_method.attached':
    payment_method = event.data.object # contains a stripe.PaymentMethod
    print('PaymentMethod was attached to a Customer!')
  # ... handle other event types
  else:
    print('Unhandled event type {}'.format(event.type))

  return HttpResponse(status=200)
  import json

# Webhooks are always sent as HTTP POST requests, so ensure
# that only POST requests reach your webhook view by
# decorating `webhook()` with `require_POST`.
#
# To ensure that the webhook view can receive webhooks,
# also decorate `webhook()` with `csrf_exempt`.
@require_POST
@csrf_exempt
def webhook(request):
THE EVENT OBJECT
{
  "id": "evt_1NG8Du2eZvKYlo2CUI79vXWy",
  "object": "event",
  "api_version": "2019-02-19",
  "created": 1686089970,
  "data": {
    "object": {
      "id": "seti_1NG8Du2eZvKYlo2C9XMqbR0x",
      "object": "setup_intent",
      "application": null,
      "automatic_payment_methods": null,
      "cancellation_reason": null,
      "client_secret": "seti_1NG8Du2eZvKYlo2C9XMqbR0x_secret_O2CdhLwGFh2Aej7bCY7qp8jlIuyR8DJ",
      "created": 1686089970,
      "customer": null,
      "description": null,
      "flow_directions": null,
      "last_setup_error": null,
      "latest_attempt": null,
      "livemode": false,
      "mandate": null,
      "metadata": {},
      "next_action": null,
      "on_behalf_of": null,
      "payment_method": "pm_1NG8Du2eZvKYlo2CYzzldNr7",
      "payment_method_options": {
        "acss_debit": {
          "currency": "cad",
          "mandate_options": {
            "interval_description": "First day of every month",
            "payment_schedule": "interval",
            "transaction_type": "personal"
          },
          "verification_method": "automatic"
        }
      },
      "payment_method_types": [
        "acss_debit"
      ],
      "single_use_mandate": null,
      "status": "requires_confirmation",
      "usage": "off_session"
    }
  },
  "livemode": false,
  "pending_webhooks": 0,
  "request": {
    "id": null,
    "idempotency_key": null
  },
  "type": "setup_intent.created"


  # Process webhook data in `request.body`

  PATCH

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
Stripe-Signature:
t=1492774577,
v1=5257a869e7ecebeda32affa62cdca3fa51cad7e77a0e56ff536d0ce8e108d8bd,
v0=6ffbb59b2300aae63f272406069a9788598b792a944a07aba816edb039989a39

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
# Set your secret key. Remember to switch to your live secret key in production.
# See your keys here: https://dashboard.stripe.com/apikeys
stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'

endpoint = stripe.WebhookEndpoint.create(
  url='https://example.com/my/webhook/endpoint',
  enabled_events=[
    'payment_intent.payment_failed',
    'payment_intent.succeeded',
  ],
)
# Set your secret key. Remember to switch to your live secret key in production.
# See your keys here: https://dashboard.stripe.com/apikeys
stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'

from django.http import HttpResponse

# If you are testing your webhook locally with the Stripe CLI you
# can find the endpoint's secret by running `stripe listen`
# Otherwise, find your endpoint's secret in your webhook settings in the Developer Dashboard
endpoint_secret = 'whsec_...'

# Using Django
@csrf_exempt
def my_webhook_view(request):
  payload = request.body
  sig_header = request.META['Stripe-Signature:
t=1492774577,
v1=5257a869e7ecebeda32affa62cdca3fa51cad7e77a0e56ff536d0ce8e108d8bd,
v0=6ffbb59b2300aae63f272406069a9788598b792a944a07aba816edb039989a39']
  event = None

  try:
    event = stripe.Webhook.construct_event(
      payload, sig_header, endpoint_secret
    )
  except ValueError as e:
    # Invalid payload
    print('Error parsing payload: {}'.format(str(e)))
    return HttpResponse(status=400)
  except stripe.error.SignatureVerificationError as e:
    # Invalid signature
    print('Error verifying webhook signature: {}'.format(str(e)))
    return HttpResponse(status=400)

  # Handle the event
  if event.type == 'payment_intent.succeeded':
    payment_intent = event.data.object # contains a stripe.PaymentIntent
    print('PaymentIntent was successful!')
  elif event.type == 'payment_method.attached':
    payment_method = event.data.object # contains a stripe.PaymentMethod
    print('PaymentMethod was attached to a Customer!')
  # ... handle other event types
  else:
    print('Unhandled event type {}'.format(event.type))
import json

# Webhooks are always sent as HTTP POST requests, so ensure
# that only POST requests reach your webhook view by
# decorating `webhook()` with `require_POST`.
#
# To ensure that the webhook view can receive webhooks,
# also decorate `webhook()` with `csrf_exempt`.
@require_POST
@csrf_exempt
def webhook(request):
import json
from django.http import HttpResponse

# Using Django
@csrf_exempt
def my_webhook_view(request):
  payload = request.body
  event = None

  try:
    event = stripe.Event.construct_from(
      json.loads(payload), stripe.api_key
    )
  except ValueError as e:
    # Invalid payload
    return HttpResponse(status=400)

  # Handle the event
  if event.type == 'payment_intent.succeeded':
    payment_intent = event.data.object # contains a stripe.PaymentIntent
    # Then define and call a method to handle the successful payment intent.
    # handle_payment_intent_succeeded(payment_intent)
  elif event.type == 'payment_method.attached':
    payment_method = event.data.object # contains a stripe.PaymentMethod
    # Then define and call a method to handle the successful attachment of a PaymentMethod.
    # handle_payment_method_attached(payment_method)
  # ... handle other event types
  else:
    print('Unhandled event type {}'.format(event.type))

  return HttpResponse(status=200)
stripe listen --forward-to localhost:4242/stripe_webhooks
stripe listen --events payment_intent.created,customer.created,payment_intent.succeeded,checkout.session.completed,payment_intent.payment_failed \
  --forward-to localhost:4242/webhook
stripe listen --load-from-webhooks-api --forward-to localhost:5000
Ready! Your webhook signing secret is '{{whsec_ 5V2GHGaht2mGJGNOmesTtTaxuJWFRssS}}' (^C to quit)


stripe trigger payment_intent.succeeded
Running fixture for: payment_intent
Trigger succeeded! Check dashboard for event details.
[
](https://<[your-website](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862>/<we_1Ova66GF83d3fsgW2nbowkDw>)
  # Process webhook data in `request.body`  return HttpResponse(status=200)
# Set your secret key. Remember to switch to your live secret key in production.
# See your keys here: https://dashboard.stripe.com/apikeys
stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'

from django.http import HttpResponse

# If you are testing your webhook locally with the Stripe CLI you
# can find the endpoint's secret by running `stripe listen`
# Otherwise, find your endpoint's secret in your webhook settings in the Developer Dashboard
endpoint_secret = 'whsec_...'

# Using Django
@csrf_exempt
def my_webhook_view(request):
  payload = request.body
  sig_header = request.META['Stripe-Signature:
t=1492774577,
v1=5257a869e7ecebeda32affa62cdca3fa51cad7e77a0e56ff536d0ce8e108d8bd,
v0=6ffbb59b2300aae63f272406069a9788598b792a944a07aba816edb039989a39']
  event = None

  try:
    event = stripe.Webhook.construct_event(
      payload, sig_header, endpoint_secret
    )
  except ValueError as e:
    # Invalid payload
    print('Error parsing payload: {}'.format(str(e)))
    return HttpResponse(status=400)
  except stripe.error.SignatureVerificationError as e:
    # Invalid signature
    print('Error verifying webhook signature: {}'.format(str(e)))
    return HttpResponse(status=400)

  # Handle the event
  if event.type == 'payment_intent.succeeded':
    payment_intent = event.data.object # contains a stripe.PaymentIntent
    print('PaymentIntent was successful!')
  elif event.type == 'payment_method.attached':
    payment_method = event.data.object # contains a stripe.PaymentMethod
    print('PaymentMethod was attached to a Customer!')
  # ... handle other event types
  else:
    print('Unhandled event type {}'.format(event.type))

  return HttpResponse(status=200)
  import json

# Webhooks are always sent as HTTP POST requests, so ensure
# that only POST requests reach your webhook view by
# decorating `webhook()` with `require_POST`.
#
# To ensure that the webhook view can receive webhooks,
# also decorate `webhook()` with `csrf_exempt`.
@require_POST
@csrf_exempt
def webhook(request):
THE EVENT OBJECT
{
  "id": "evt_1NG8Du2eZvKYlo2CUI79vXWy",
  "object": "event",
  "api_version": "2019-02-19",
  "created": 1686089970,
  "data": {
    "object": {
      "id": "seti_1NG8Du2eZvKYlo2C9XMqbR0x",
      "object": "setup_intent",
      "application": null,
      "automatic_payment_methods": null,
      "cancellation_reason": null,
      "client_secret": "seti_1NG8Du2eZvKYlo2C9XMqbR0x_secret_O2CdhLwGFh2Aej7bCY7qp8jlIuyR8DJ",
      "created": 1686089970,
      "customer": null,
      "description": null,
      "flow_directions": null,
      "last_setup_error": null,
      "latest_attempt": null,
      "livemode": false,
      "mandate": null,
      "metadata": {},
      "next_action": null,
      "on_behalf_of": null,
      "payment_method": "pm_1NG8Du2eZvKYlo2CYzzldNr7",
      "payment_method_options": {
        "acss_debit": {
          "currency": "cad",
          "mandate_options": {
            "interval_description": "First day of every month",
            "payment_schedule": "interval",
            "transaction_type": "personal"
          },
          "verification_method": "automatic"
        }
      },
      "payment_method_types": [
        "acss_debit"
      ],
      "single_use_mandate": null,
      "status": "requires_confirmation",
      "usage": "off_session"
    }
  },
  "livemode": false,
  "pending_webhooks": 0,
  "request": {
    "id": null,
    "idempotency_key": null
  },
  "type": "setup_intent.created"


  # Process webhook data in `request.body`
---
 README.md | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)

diff --git a/README.md b/README.md
index 1f3d7ba..1efe598 100644
--- a/README.md
+++ b/README.md
@@ -248,7 +248,7 @@ stripe trigger payment_intent.succeeded
 Running fixture for: payment_intent
 Trigger succeeded! Check dashboard for event details.
 [
-](https://<[your-website](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862>/<whsec_ 5V2GHGaht2mGJGNOmesTtTaxuJWFRssS>)
+](https://<[your-website](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862>/<we_1Ova66GF83d3fsgW2nbowkDw>)
   # Process webhook data in `request.body`  return HttpResponse(status=200)
 # Set your secret key. Remember to switch to your live secret key in production.
 # See your keys here: https://dashboard.stripe.com/apikeys

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
Stripe-Signature:
t=1492774577,
v1=5257a869e7ecebeda32affa62cdca3fa51cad7e77a0e56ff536d0ce8e108d8bd,
v0=6ffbb59b2300aae63f272406069a9788598b792a944a07aba816edb039989a39

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
# Set your secret key. Remember to switch to your live secret key in production.
# See your keys here: https://dashboard.stripe.com/apikeys
stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'

endpoint = stripe.WebhookEndpoint.create(
  url='https://example.com/my/webhook/endpoint',
  enabled_events=[
    'payment_intent.payment_failed',
    'payment_intent.succeeded',
  ],
)
# Set your secret key. Remember to switch to your live secret key in production.
# See your keys here: https://dashboard.stripe.com/apikeys
stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'

from django.http import HttpResponse

# If you are testing your webhook locally with the Stripe CLI you
# can find the endpoint's secret by running `stripe listen`
# Otherwise, find your endpoint's secret in your webhook settings in the Developer Dashboard
endpoint_secret = 'whsec_...'

# Using Django
@csrf_exempt
def my_webhook_view(request):
  payload = request.body
  sig_header = request.META['Stripe-Signature:
t=1492774577,
v1=5257a869e7ecebeda32affa62cdca3fa51cad7e77a0e56ff536d0ce8e108d8bd,
v0=6ffbb59b2300aae63f272406069a9788598b792a944a07aba816edb039989a39']
  event = None

  try:
    event = stripe.Webhook.construct_event(
      payload, sig_header, endpoint_secret
    )
  except ValueError as e:
    # Invalid payload
    print('Error parsing payload: {}'.format(str(e)))
    return HttpResponse(status=400)
  except stripe.error.SignatureVerificationError as e:
    # Invalid signature
    print('Error verifying webhook signature: {}'.format(str(e)))
    return HttpResponse(status=400)

  # Handle the event
  if event.type == 'payment_intent.succeeded':
    payment_intent = event.data.object # contains a stripe.PaymentIntent
    print('PaymentIntent was successful!')
  elif event.type == 'payment_method.attached':
    payment_method = event.data.object # contains a stripe.PaymentMethod
    print('PaymentMethod was attached to a Customer!')
  # ... handle other event types
  else:
    print('Unhandled event type {}'.format(event.type))
import json

# Webhooks are always sent as HTTP POST requests, so ensure
# that only POST requests reach your webhook view by
# decorating `webhook()` with `require_POST`.
#
# To ensure that the webhook view can receive webhooks,
# also decorate `webhook()` with `csrf_exempt`.
@require_POST
@csrf_exempt
def webhook(request):
import json
from django.http import HttpResponse

# Using Django
@csrf_exempt
def my_webhook_view(request):
  payload = request.body
  event = None

  try:
    event = stripe.Event.construct_from(
      json.loads(payload), stripe.api_key
    )
  except ValueError as e:
    # Invalid payload
    return HttpResponse(status=400)

  # Handle the event
  if event.type == 'payment_intent.succeeded':
    payment_intent = event.data.object # contains a stripe.PaymentIntent
    # Then define and call a method to handle the successful payment intent.
    # handle_payment_intent_succeeded(payment_intent)
  elif event.type == 'payment_method.attached':
    payment_method = event.data.object # contains a stripe.PaymentMethod
    # Then define and call a method to handle the successful attachment of a PaymentMethod.
    # handle_payment_method_attached(payment_method)
  # ... handle other event types
  else:
    print('Unhandled event type {}'.format(event.type))

  return HttpResponse(status=200)
stripe listen --forward-to localhost:4242/stripe_webhooks
stripe listen --events payment_intent.created,customer.created,payment_intent.succeeded,checkout.session.completed,payment_intent.payment_failed \
  --forward-to localhost:4242/webhook
stripe listen --load-from-webhooks-api --forward-to localhost:5000
Ready! Your webhook signing secret is '{{whsec_ 5V2GHGaht2mGJGNOmesTtTaxuJWFRssS}}' (^C to quit)


stripe trigger payment_intent.succeeded
Running fixture for: payment_intent
Trigger succeeded! Check dashboard for event details.
[
](https://<[your-website](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862>/<we_1Ova66GF83d3fsgW2nbowkDw>)
  # Process webhook data in `request.body`  return HttpResponse(status=200)
# Set your secret key. Remember to switch to your live secret key in production.
# See your keys here: https://dashboard.stripe.com/apikeys
stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'

from django.http import HttpResponse

# If you are testing your webhook locally with the Stripe CLI you
# can find the endpoint's secret by running `stripe listen`
# Otherwise, find your endpoint's secret in your webhook settings in the Developer Dashboard
endpoint_secret = 'whsec_...'

# Using Django
@csrf_exempt
def my_webhook_view(request):
  payload = request.body
  sig_header = request.META['Stripe-Signature:
t=1492774577,
v1=5257a869e7ecebeda32affa62cdca3fa51cad7e77a0e56ff536d0ce8e108d8bd,
v0=6ffbb59b2300aae63f272406069a9788598b792a944a07aba816edb039989a39']
  event = None

  try:
    event = stripe.Webhook.construct_event(
      payload, sig_header, endpoint_secret
    )
  except ValueError as e:
    # Invalid payload
    print('Error parsing payload: {}'.format(str(e)))
    return HttpResponse(status=400)
  except stripe.error.SignatureVerificationError as e:
    # Invalid signature
    print('Error verifying webhook signature: {}'.format(str(e)))
    return HttpResponse(status=400)

  # Handle the event
  if event.type == 'payment_intent.succeeded':
    payment_intent = event.data.object # contains a stripe.PaymentIntent
    print('PaymentIntent was successful!')
  elif event.type == 'payment_method.attached':
    payment_method = event.data.object # contains a stripe.PaymentMethod
    print('PaymentMethod was attached to a Customer!')
  # ... handle other event types
  else:
    print('Unhandled event type {}'.format(event.type))

  return HttpResponse(status=200)
  import json

# Webhooks are always sent as HTTP POST requests, so ensure
# that only POST requests reach your webhook view by
# decorating `webhook()` with `require_POST`.
#
# To ensure that the webhook view can receive webhooks,
# also decorate `webhook()` with `csrf_exempt`.
@require_POST
@csrf_exempt
def webhook(request):
THE EVENT OBJECT
{
  "id": "evt_1NG8Du2eZvKYlo2CUI79vXWy",
  "object": "event",
  "api_version": "2019-02-19",
  "created": 1686089970,
  "data": {
    "object": {
      "id": "seti_1NG8Du2eZvKYlo2C9XMqbR0x",
      "object": "setup_intent",
      "application": null,
      "automatic_payment_methods": null,
      "cancellation_reason": null,
      "client_secret": "seti_1NG8Du2eZvKYlo2C9XMqbR0x_secret_O2CdhLwGFh2Aej7bCY7qp8jlIuyR8DJ",
      "created": 1686089970,
      "customer": null,
      "description": null,
      "flow_directions": null,
      "last_setup_error": null,
      "latest_attempt": null,
      "livemode": false,
      "mandate": null,
      "metadata": {},
      "next_action": null,
      "on_behalf_of": null,
      "payment_method": "pm_1NG8Du2eZvKYlo2CYzzldNr7",
      "payment_method_options": {
        "acss_debit": {
          "currency": "cad",
          "mandate_options": {
            "interval_description": "First day of every month",
            "payment_schedule": "interval",
            "transaction_type": "personal"
          },
          "verification_method": "automatic"
        }
      },
      "payment_method_types": [
        "acss_debit"
      ],
      "single_use_mandate": null,
      "status": "requires_confirmation",
      "usage": "off_session"
    }
  },
  "livemode": false,
  "pending_webhooks": 0,
  "request": {
    "id": null,
    "idempotency_key": null
  },
  "type": "setup_intent.created"


  # Process webhook data in `request.body`
---
 README.md | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)

diff --git a/README.md b/README.md
index 1f3d7ba..1efe598 100644
--- a/README.md
+++ b/README.md
@@ -248,7 +248,7 @@ stripe trigger payment_intent.succeeded
 Running fixture for: payment_intent
 Trigger succeeded! Check dashboard for event details.
 [
-](https://<[your-website](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862>/<whsec_ 5V2GHGaht2mGJGNOmesTtTaxuJWFRssS>)
+](https://<[your-website](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862>/<we_1Ova66GF83d3fsgW2nbowkDw>)
   # Process webhook data in `request.body`  return HttpResponse(status=200)
 # Set your secret key. Remember to switch to your live secret key in production.
 # See your keys here: https://dashboard.stripe.com/apikeys
---
 README.md | 383 ++++++++++++++++++++++++++++++++++++++++++++++++++++++
 1 file changed, 383 insertions(+)

diff --git a/README.md b/README.md
index 1efe598..1e08c57 100644
--- a/README.md
+++ b/README.md
@@ -361,3 +361,386 @@ THE EVENT OBJECT
 
 
   # Process webhook data in `request.body`
+
+  PATCH
+
+# AGENCY-WEBHOOK
+
+Download
+#! /usr/bin/env python3.6
+# Python 3.6 or newer required.
+
+import json
+import os
+import stripe
+# This is your test secret API key.
+stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'
+
+# Replace this endpoint secret with your endpoint's unique secret
+# If you are testing with the CLI, find the secret by running 'stripe listen'
+# If you are using an endpoint defined with the API or dashboard, look in your webhook settings
+# at https://dashboard.stripe.com/webhooks
+endpoint_secret = 'whsec_...'
+from flask import Flask, jsonify, request
+
+app = Flask(__name__)
+
+@app.route('/webhook', methods=['POST'])
+def webhook():
+    event = None
+    payload = request.data
+
+    try:
+        event = json.loads(payload)
+    except json.decoder.JSONDecodeError as e:
+        print('⚠️  Webhook error while parsing basic request.' + str(e))
+        return jsonify(success=False)
+    if endpoint_secret:
+        # Only verify the event if there is an endpoint secret defined
+        # Otherwise use the basic event deserialized with json
+        sig_header = request.headers.get('stripe-signature')
+        try:
+            event = stripe.Webhook.construct_event(
+                payload, sig_header, endpoint_secret
+            )
+        except stripe.error.SignatureVerificationError as e:
+            print('⚠️  Webhook signature verification failed.' + str(e))
+            return jsonify(success=False)
+
+    # Handle the event
+    if event and event['type'] == 'payment_intent.succeeded':
+        payment_intent = event['data']['object']  # contains a stripe.PaymentIntent
+        print('Payment for {} succeeded'.format(payment_intent['amount']))
+        # Then define and call a method to handle the successful payment intent.
+        # handle_payment_intent_succeeded(payment_intent)
+    elif event['type'] == 'payment_method.attached':
+        payment_method = event['data']['object']  # contains a stripe.PaymentMethod
+        # Then define and call a method to handle the successful attachment of a PaymentMethod.
+        # handle_payment_method_attached(payment_method)
+    else:
+        # Unexpected event type
+        print('Unhandled event type {}'.format(event['type']))
+
+    return jsonify(success=True)
+[
+](https://github.com/grateful345/AGENCY-WEBHOOK.git)https://github.com/grateful345/AGENCY-WEBHOOK.git
+echo "# AGENCY-WEBHOOK" >> README.md
+git init
+git add README.md
+git commit -m "first commit"
+git branch -M main
+git remote add origin https://github.com/grateful345/AGENCY-WEBHOOK.git
+git push -u origin main
+…or push an existing repository from the command line
+git remote add origin https://github.com/grateful345/AGENCY-WEBHOOK.git
+git branch -M main
+git push -u origin main
+Install the Stripe Python package
+Install the Stripe package and import it in your code. Alternatively, if you’re starting from scratch and need a requirements.txt file, download the project files using the link in the code editor.
+
+pip
+
+GitHub
+Install the package via pip:
+pip3 install stripe
+
+Server
+Create a new endpoint
+
+settings
+A webhook is an endpoint on your server that receives requests from Stripe, notifying you about events that happen on your account such as a customer disputing a charge or a successful recurring payment. Add a new endpoint to your server and make sure it’s publicly accessible so we can send unauthenticated POST requests.
+Server
+2
+Handle requests from Stripe
+Read the event data
+Stripe sends the event data in the request body. Each event is structured as an Event object with a type, id, and related Stripe resource nested under data.
+Server
+Handle the event
+As soon as you have the event object, check the type to know what kind of event happened. You can use one webhook to handle several different event types at once, or set up individual endpoints for specific events.
+Server
+Return a 200 response
+Build and run your server to test the endpoint at http://localhost:4242/webhook.
+python3 -m flask run --port=4242
+
+Server
+Download the CLI
+Use the Stripe CLI to test your webhook locally. Download the CLI and log in with your Stripe account. Alternatively, use a service like ngrok to make your local endpoint publicly accessible.
+stripe login
+
+Run in the Stripe Shell
+Server
+Forward events to your webhook
+
+settings
+Set up event forwarding with the CLI to send all Stripe events in testmode to your local webhook endpoint.
+stripe listen --forward-to localhost:4242/webhook
+
+Run in the Stripe Shell
+Server
+Simulate events
+
+settings
+Use the CLI to simulate specific events that test your webhook application logic by sending a POST request to your webhook endpoint with a mocked Stripe event object.
+stripe trigger payment_intent.succeeded
+
+Run in the Stripe Shell
+Server
+Congratulations!
+Stripe-Signature:
+t=1492774577,
+v1=5257a869e7ecebeda32affa62cdca3fa51cad7e77a0e56ff536d0ce8e108d8bd,
+v0=6ffbb59b2300aae63f272406069a9788598b792a944a07aba816edb039989a39
+
+You have a basic webhook endpoint ready to accept events from Stripe. Now add the application logic that your business needs to handle the events you care the most about. You can also extend your endpoint with the steps b
+[
+](https://<your-website>/<your-webhook-endpoint>)https://<your-website>/<[webhook](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862-endpoint>
+README.md | 3 +++
+1 file changed, 3 insertions(+)
+
+diff --git a/README.md b/README.md
+index 806cda8..9b1de77 100644
+--- a/README.md
++++ b/README.md
+@@ -121,3 +121,6 @@ Run in the Stripe Shell
+Server
+Congratulations!
+You have a basic webhook endpoint ready to accept events from Stripe. Now add the application logic that your business needs to handle the events you care the most about. You can also extend your endpoint with the steps b
++
++https:///<webhookhttps://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862-endpoint>
+# Set your secret key. Remember to switch to your live secret key in production.
+# See your keys here: https://dashboard.stripe.com/apikeys
+stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'
+
+endpoint = stripe.WebhookEndpoint.create(
+  url='https://example.com/my/webhook/endpoint',
+  enabled_events=[
+    'payment_intent.payment_failed',
+    'payment_intent.succeeded',
+  ],
+)
+# Set your secret key. Remember to switch to your live secret key in production.
+# See your keys here: https://dashboard.stripe.com/apikeys
+stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'
+
+from django.http import HttpResponse
+
+# If you are testing your webhook locally with the Stripe CLI you
+# can find the endpoint's secret by running `stripe listen`
+# Otherwise, find your endpoint's secret in your webhook settings in the Developer Dashboard
+endpoint_secret = 'whsec_...'
+
+# Using Django
+@csrf_exempt
+def my_webhook_view(request):
+  payload = request.body
+  sig_header = request.META['t=1492774577,
+v1=5257a869e7ecebeda32affa62cdca3fa51cad7e77a0e56ff536d0ce8e108d8bd,
+v0=6ffbb59b2300aae63f272406069a9788598b792a944a07aba816edb039989a39']
+  event = None
+
+  try:
+    event = stripe.Webhook.construct_event(
+      payload, sig_header, endpoint_secret
+    )
+  except ValueError as e:
+    # Invalid payload
+    print('Error parsing payload: {}'.format(str(e)))
+    return HttpResponse(status=400)
+  except stripe.error.SignatureVerificationError as e:
+    # Invalid signature
+    print('Error verifying webhook signature: {}'.format(str(e)))
+    return HttpResponse(status=400)
+
+  # Handle the event
+  if event.type == 'payment_intent.succeeded':
+    payment_intent = event.data.object # contains a stripe.PaymentIntent
+    print('PaymentIntent was successful!')
+  elif event.type == 'payment_method.attached':
+    payment_method = event.data.object # contains a stripe.PaymentMethod
+    print('PaymentMethod was attached to a Customer!')
+  # ... handle other event types
+  else:
+    print('Unhandled event type {}'.format(event.type))
+import json
+
+# Webhooks are always sent as HTTP POST requests, so ensure
+# that only POST requests reach your webhook view by
+# decorating `webhook()` with `require_POST`.
+#
+# To ensure that the webhook view can receive webhooks,
+# also decorate `webhook()` with `csrf_exempt`.
+@require_POST
+@csrf_exempt
+def webhook(request):
+import json
+from django.http import HttpResponse
+
+# Using Django
+@csrf_exempt
+def my_webhook_view(request):
+  payload = request.body
+  event = None
+
+  try:
+    event = stripe.Event.construct_from(
+      json.loads(payload), stripe.api_key
+    )
+  except ValueError as e:
+    # Invalid payload
+    return HttpResponse(status=400)
+
+  # Handle the event
+  if event.type == 'payment_intent.succeeded':
+    payment_intent = event.data.object # contains a stripe.PaymentIntent
+    # Then define and call a method to handle the successful payment intent.
+    # handle_payment_intent_succeeded(payment_intent)
+  elif event.type == 'payment_method.attached':
+    payment_method = event.data.object # contains a stripe.PaymentMethod
+    # Then define and call a method to handle the successful attachment of a PaymentMethod.
+    # handle_payment_method_attached(payment_method)
+  # ... handle other event types
+  else:
+    print('Unhandled event type {}'.format(event.type))
+
+  return HttpResponse(status=200)
+stripe listen --forward-to localhost:4242/stripe_webhooks
+stripe listen --events payment_intent.created,customer.created,payment_intent.succeeded,checkout.session.completed,payment_intent.payment_failed \
+  --forward-to localhost:4242/webhook
+stripe listen --load-from-webhooks-api --forward-to localhost:5000
+Ready! Your webhook signing secret is '{{whsec_ 5V2GHGaht2mGJGNOmesTtTaxuJWFRssS}}' (^C to quit)
+
+
+stripe trigger payment_intent.succeeded
+Running fixture for: payment_intent
+Trigger succeeded! Check dashboard for event details.
+[
+](https://<[your-website](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862>/<we_1Ova66GF83d3fsgW2nbowkDw>)
+  # Process webhook data in `request.body`  return HttpResponse(status=200)
+# Set your secret key. Remember to switch to your live secret key in production.
+# See your keys here: https://dashboard.stripe.com/apikeys
+stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'
+
+from django.http import HttpResponse
+
+# If you are testing your webhook locally with the Stripe CLI you
+# can find the endpoint's secret by running `stripe listen`

$ stripe listen

> Ready! Your webhook signing secret is whsec_abcdefg1234567
2022-01-28 09:47:46   --> customer.created [evt_abc123]
2022-01-28 09:48:22   --> charge.succeeded [evt_def456]
2022-01-28 09:48:58   --> charge.succeeded [evt_ghi789]

stripe listen --forward-to http://localhost:4242

stripe listen --events=payment_intent.succeeded
+# Otherwise, find your endpoint's secret in your webhook settings in the Developer Dashboard
+endpoint_secret = 'whsec_...'
+
+# Using Django
+@csrf_exempt
+def my_webhook_view(request):
+  payload = request.body
+  sig_header = request.META['t=1492774577,
+v1=5257a869e7ecebeda32affa62cdca3fa51cad7e77a0e56ff536d0ce8e108d8bd,
+v0=6ffbb59b2300aae63f272406069a9788598b792a944a07aba816edb039989a39']
+  event = None
+
+  try:
+    event = stripe.Webhook.construct_event(
+      payload, sig_header, endpoint_secret
+    )
+  except ValueError as e:
+    # Invalid payload
+    print('Error parsing payload: {}'.format(str(e)))
+    return HttpResponse(status=400)
+  except stripe.error.SignatureVerificationError as e:
+    # Invalid signature
+    print('Error verifying webhook signature: {}'.format(str(e)))
+    return HttpResponse(status=400)
+
+  # Handle the event
+  if event.type == 'payment_intent.succeeded':
+    payment_intent = event.data.object # contains a stripe.PaymentIntent
+    print('PaymentIntent was successful!')
+  elif event.type == 'payment_method.attached':
+    payment_method = event.data.object # contains a stripe.PaymentMethod
+    print('PaymentMethod was attached to a Customer!')
+  # ... handle other event types
+  else:
+    print('Unhandled event type {}'.format(event.type))
+
+  return HttpResponse(status=200)
+  import json
+
+# Webhooks are always sent as HTTP POST requests, so ensure
+# that only POST requests reach your webhook view by
+# decorating `webhook()` with `require_POST`.
+#
+# To ensure that the webhook view can receive webhooks,
+# also decorate `webhook()` with `csrf_exempt`.
+@require_POST
+@csrf_exempt
+def webhook(request):
+THE EVENT OBJECT
+{
+  "id": "evt_1NG8Du2eZvKYlo2CUI79vXWy",
+  "object": "event",
+  "api_version": "2019-02-19",
+  "created": 1686089970,
+  "data": {
+    "object": {
+      "id": "seti_1NG8Du2eZvKYlo2C9XMqbR0x",
+      "object": "setup_intent",
+      "application": null,
+      "automatic_payment_methods": null,
+      "cancellation_reason": null,
+      "client_secret": "seti_1NG8Du2eZvKYlo2C9XMqbR0x_secret_O2CdhLwGFh2Aej7bCY7qp8jlIuyR8DJ",
+      "created": 1686089970,
+      "customer": null,
+      "description": null,
+      "flow_directions": null,
+      "last_setup_error": null,
+      "latest_attempt": null,
+      "livemode": false,
+      "mandate": null,
+      "metadata": {},
+      "next_action": null,
+      "on_behalf_of": null,
+      "payment_method": "pm_1NG8Du2eZvKYlo2CYzzldNr7",
+      "payment_method_options": {
+        "acss_debit": {
+          "currency": "cad",
+          "mandate_options": {
+            "interval_description": "First day of every month",
+            "payment_schedule": "interval",
+            "transaction_type": "personal"
+          },
+          "verification_method": "automatic"
+        }
+      },
+      "payment_method_types": [
+        "acss_debit"
+      ],
+      "single_use_mandate": null,
+      "status": "requires_confirmation",
+      "usage": "off_session"
+    }
+  },
+  "livemode": false,
+  "pending_webhooks": 0,
+  "request": {
+    "id": null,
+    "idempotency_key": null
+  },
+  "type": "setup_intent.created"
+
+
+  # Process webhook data in `request.body`
+---
+ README.md | 2 +-
+ 1 file changed, 1 insertion(+), 1 deletion(-)
+
+diff --git a/README.md b/README.md
+index 1f3d7ba..1efe598 100644
+--- a/README.md
++++ b/README.md
+@@ -248,7 +248,7 @@ stripe trigger payment_intent.succeeded
+ Running fixture for: payment_intent
+ Trigger succeeded! Check dashboard for event details.
+ [
+-](https://<[your-website](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862>/<whsec_ 5V2GHGaht2mGJGNOmesTtTaxuJWFRssS>)
++](https://<[your-website](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862>/<we_1Ova66GF83d3fsgW2nbowkDw>)
+   # Process webhook data in `request.body`  return HttpResponse(status=200)
+ # Set your secret key. Remember to switch to your live secret key in production.
+ # See your keys here: https://dashboard.stripe.com/apikeys
stripe trigger invoice.payment_succeeded

Setting up fixture for: customer
Setting up fixture for: invoiceitem
Setting up fixture for: invoice
Setting up fixture for: invoice_pay
Trigger succeeded! Check dashboard for event details.

stripe trigger --help

Supported events:
  balance.available
  charge.captured
  charge.dispute.created
  charge.failed
  charge.refunded
  charge.succeeded
...
{
  "object": {
    "id": "file_1OvyoVGF83d3fsgWJ2y8LUzQ",
    "object": "file",
    "created": 1710839911,
    "expires_at": null,
    "filename": "Untitled_20240318.csv",
    "links": {
      "object": "list",
      "data": [],
      "has_more": false,
      "url": "/v1/file_links?file=file_1OvyoVGF83d3fsgWJ2y8LUzQ"
    },
    "purpose": "sigma_scheduled_query",
    "size": 64,
    "title": "Untitled for 2024-03-18",
    "type": "csv",
    "url": "https://files.stripe.com/v1/files/file_1OvyoVGF83d3fsgWJ2y8LUzQ/contents"
  },
  "previous_attributes": null
}



