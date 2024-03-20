# AGENCY-WEBHOOK
Stripe python gpg key :

gpg --encrypt --recipient 05D02D3D57ABFF46 FILENAME

Key ID: 05D02D3D57ABFF46
Key type: RSA
Key size: 2048 bits
Fingerprint: C330 33E4 B583 FE61 2EDE 877C 05D0 2D3D 57AB FF46
User ID: Stripe <security@stripe.com>


Stripe Python Library

pypi Build Status Coverage Status

The Stripe Python library provides convenient access to the Stripe API from applications written in the Python language. It includes a pre-defined set of classes for API resources that initialize themselves dynamically from API responses which makes it compatible with a wide range of versions of the Stripe API.

Documentation

See the Python API docs.

See video demonstrations covering how to use the library.

Installation

You don't need this source code unless you want to modify the package. If you just want to use the package, just run:

pip install --upgrade stripe
Install from source with:

python setup.py install
Requirements

Python 3.6+ (PyPy supported)
Python 2.7 deprecation

The Python Software Foundation (PSF) community announced the end of support of Python 2 on 01 January 2020. Starting with version 6.0.0 Stripe SDK Python packages will no longer support Python 2.7. To continue to get new features and security updates, please make sure to update your Python runtime to Python 3.6+.

The last version of the Stripe SDK that supports Python 2.7 is 5.5.0.

Usage

The library needs to be configured with your account's secret key which is available in your Stripe Dashboard. Set stripe.api_key to its value:

from stripe import StripeClient

client = StripeClient("sk_test_...")

# list customers
customers = client.customers.list()

# print the first customer's email
print(customers.data[0].email)

# retrieve specific Customer
customer = client.customers.retrieve("cus_123456789")

# print that customer's email
print(customer.email)
Handling exceptions

Unsuccessful requests raise exceptions. The class of the exception will reflect the sort of error that occurred. Please see the Api Reference for a description of the error classes you should handle, and for information on how to inspect these errors.

Per-request Configuration

Configure individual requests with the options argument. For example, you can make requests with a specific Stripe Version or as a connected account:

from stripe import StripeClient

client = StripeClient("sk_test_...")

# list customers
client.customers.list(
    options={
        "api_key": "sk_test_...",
        "stripe_account": "acct_...",
        "stripe_version": "2019-02-19",
    }
)

# retrieve single customer
client.customers.retrieve(
    "cus_123456789",
    options={
        "api_key": "sk_test_...",
        "stripe_account": "acct_...",
        "stripe_version": "2019-02-19",
    }
)
Configuring an HTTP Client

You can configure your StripeClient to use urlfetch, requests, pycurl, or urllib2 with the http_client option:

client = StripeClient("sk_test_...", http_client=stripe.UrlFetchClient())
client = StripeClient("sk_test_...", http_client=stripe.RequestsClient())
client = StripeClient("sk_test_...", http_client=stripe.PycurlClient())
client = StripeClient("sk_test_...", http_client=stripe.Urllib2Client())
Without a configured client, by default the library will attempt to load libraries in the order above (i.e. urlfetch is preferred with urllib2 used as a last resort). We usually recommend that people use requests.

Configuring a Proxy

A proxy can be configured with the proxy client option:

client = StripeClient("sk_test_...", proxy="https://user:pass@example.com:1234")
Configuring Automatic Retries

You can enable automatic retries on requests that fail due to a transient problem by configuring the maximum number of retries:

client = StripeClient("sk_test_...", max_network_retries=2)
Various errors can trigger a retry, like a connection error or a timeout, and also certain API responses like HTTP status 409 Conflict.

Idempotency keys are automatically generated and added to requests, when not given, to guarantee that retries are safe.

Logging

The library can be configured to emit logging that will give you better insight into what it's doing. The info logging level is usually most appropriate for production use, but debug is also available for more verbosity.

There are a few options for enabling it:

Set the environment variable STRIPE_LOG to the value debug or info

$ export STRIPE_LOG=debug
Set stripe.log:

import stripe
stripe.log = 'debug'
Enable it through Python's logging module:

import logging
logging.basicConfig()
logging.getLogger('stripe').setLevel(logging.DEBUG)
Accessing response code and headers

You can access the HTTP response code and headers using the last_response property of the returned resource.

customer = client.customers.retrieve(
    "cus_123456789"
)

print(customer.last_response.code)
print(customer.last_response.headers)
Writing a Plugin

If you're writing a plugin that uses the library, we'd appreciate it if you identified using stripe.set_app_info():

stripe.set_app_info("MyAwesomePlugin", version="1.2.34", url="https://myawesomeplugin.info")
This information is passed along when the library makes calls to the Stripe API.

Telemetry

By default, the library sends telemetry to Stripe regarding request latency and feature usage. These numbers help Stripe improve the overall latency of its API for all users, and improve popular features.

You can disable this behavior if you prefer:

stripe.enable_telemetry = False
Types

In v7.1.0 and newer, the library includes type annotations. See the wiki for a detailed guide.

Please note that some annotations use features that were only fairly recently accepted, such as Unpack[TypedDict] that was accepted in January 2023. We have tested that these types are recognized properly by Pyright. Support for Unpack in MyPy is still experimental, but appears to degrade gracefully. Please report an issue if there is anything we can do to improve the types for your type checker of choice.

Types and the Versioning Policy

We release type changes in minor releases. While stripe-python follows semantic versioning, our semantic versions describe the runtime behavior of the library alone. Our type annotations are not reflected in the semantic version. That is, upgrading to a new minor version of stripe-python might result in your type checker producing a type error that it didn't before. You can use a ~=x.x or x.x.* version specifier in your requirements.txt to constrain pip to a certain minor range of stripe-python.

Types and API Versions

The types describe the Stripe API version that was the latest at the time of release. This is the version that your library sends by default. If you are overriding stripe.api_version / stripe_version on the StripeClient, or using a webhook endpoint tied to an older version, be aware that the data you see at runtime may not match the types.

Beta SDKs

Stripe has features in the beta phase that can be accessed via the beta version of this package. We would love for you to try these and share feedback with us before these features reach the stable phase. To install a beta version use pip install with the exact version you'd like to use:

pip install stripe==v8.6.0b1
Note There can be breaking changes between beta versions. Therefore we recommend pinning the package version to a specific beta version in your requirements file or setup.py. This way you can install the same version each time without breaking changes unless you are intentionally looking for the latest beta version.
We highly recommend keeping an eye on when the beta feature you are interested in goes from beta to stable so that you can move from using a beta version of the SDK to the stable version.

If your beta feature requires a Stripe-Version header to be sent, set the stripe.api_version field using the stripe.add_beta_version function:

stripe.add_beta_version("feature_beta", "v3")
Support

New features and bug fixes are released on the latest major version of the Stripe Python library. If you are on an older major version, we recommend that you upgrade to the latest in order to use the new features and bug fixes including those for security vulnerabilities. Older major versions of the package will continue to be available for use, but will not be receiving any updates.

Development

The test suite depends on stripe-mock, so make sure to fetch and run it from a background terminal (stripe-mock's README also contains instructions for installing via Homebrew and other methods):

go install github.com/stripe/stripe-mock@latest
stripe-mock
Run the following command to set up the development virtualenv:

make
Run all tests on all supported Python versions:

make test
Run all tests for a specific Python version (modify -e according to your Python target):

TOX_ARGS="-e py37" make test
Run all tests in a single file:

TOX_ARGS="-e py37 -- tests/api_resources/abstract/test_updateable_api_resource.py" make test
Run a single test suite:

TOX_ARGS="-e py37 -- tests/api_resources/abstract/test_updateable_api_resource.py::TestUpdateableAPIResource" make test
Run a single test:

TOX_ARGS="-e py37 -- tests/api_resources/abstract/test_updateable_api_resource.py::TestUpdateableAPIResource::test_save" make test
Run the linter with:

make lint
The library uses Black for code formatting. Code must be formatted with Black before PRs are submitted, otherwise CI will fail. Run the formatter with:

make fmt
Generating a new keypair

The command-line option --gen-key is used to create a new primary keypair.

alice% gpg --gen-key
gpg (GnuPG) 0.9.4; Copyright (C) 1999 Free Software Foundation, Inc.
This program comes with ABSOLUTELY NO WARRANTY.
This is free software, and you are welcome to redistribute it
under certain conditions. See the file COPYING for details.

Please select what kind of key you want:
   (1) DSA and ElGamal (default)
   (2) DSA (sign only)
   (4) ElGamal (sign and encrypt)
Your selection?
GnuPG is able to create several different types of keypairs, but a primary key must be capable of making signatures. There are therefore only three options. Option 1 actually creates two keypairs. A DSA keypair is the primary keypair usable only for making signatures. An ElGamal subordinate keypair is also created for encryption. Option 2 is similar but creates only a DSA keypair. Option 4[1] creates a single ElGamal keypair usable for both making signatures and performing encryption. In all cases it is possible to later add additional subkeys for encryption and signing. For most users the default option is fine.
You must also choose a key size. The size of a DSA key must be between 512 and 1024 bits, and an ElGamal key may be of any size. GnuPG, however, requires that keys be no smaller than 768 bits. Therefore, if Option 1 was chosen and you choose a keysize larger than 1024 bits, the ElGamal key will have the requested size, but the DSA key will be 1024 bits.

About to generate a new ELG-E keypair.
              minimum keysize is  768 bits
              default keysize is 1024 bits
    highest suggested keysize is 2048 bits
What keysize do you want? (1024)
The longer the key the more secure it is against brute-force attacks, but for almost all purposes the default keysize is adequate since it would be cheaper to circumvent the encryption than try to break it. Also, encryption and decryption will be slower as the key size is increased, and a larger keysize may affect signature length. Once selected, the keysize can never be changed.
Finally, you must choose an expiration date. If Option 1 was chosen, the expiration date will be used for both the ElGamal and DSA keypairs.

Please specify how long the key should be valid.
         0 = key does not expire
      <n>  = key expires in n days
      <n>w = key expires in n weeks
      <n>m = key expires in n months
      <n>y = key expires in n years
Key is valid for? (0) 
For most users a key that does not expire is adequate. The expiration time should be chosen with care, however, since although it is possible to change the expiration date after the key is created, it may be difficult to communicate a change to users who have your public key.
You must provide a user ID in addition to the key parameters. The user ID is used to associate the key being created with a real person.

You need a User-ID to identify your key; the software constructs the user id
from Real Name, Comment and Email Address in this form:
    "Heinrich Heine (Der Dichter) <heinrichh@duesseldorf.de>"

Real name: 
Only one user ID is created when a key is created, but it is possible to create additional user IDs if you want to use the key in two or more contexts, e.g., as an employee at work and a political activist on the side. A user ID should be created carefully since it cannot be edited after it is created.
GnuPG needs a passphrase to protect the primary and subordinate private keys that you keep in your possession.

You need a Passphrase to protect your private key.    

Enter passphrase: 
There is no limit on the length of a passphrase, and it should be carefully chosen. From the perspective of security, the passphrase to unlock the private key is one of the weakest points in GnuPG (and other public-key encryption systems as well) since it is the only protection you have if another individual gets your private key. Ideally, the passphrase should not use words from a dictionary and should mix the case of alphabetic characters as well as use non-alphabetic characters. A good passphrase is crucial to the secure use of GnuPG.
Generating a revocation certificate

After your keypair is created you should immediately generate a revocation certificate for the primary public key using the option --gen-revoke. If you forget your passphrase or if your private key is compromised or lost, this revocation certificate may be published to notify others that the public key should no longer be used. A revoked public key can still be used to verify signatures made by you in the past, but it cannot be used to encrypt future messages to you. It also does not affect your ability to decrypt messages sent to you in the past if you still do have access to the private key.

alice% gpg --output revoke.asc --gen-revoke mykey
[...]
The argument mykey must be a key specifier, either the key ID of your primary keypair or any part of a user ID that identifies your keypair. The generated certificate will be left in the file revoke.asc. If the --output option is omitted, the result will be placed on standard output. Since the certificate is short, you may wish to print a hardcopy of the certificate to store somewhere safe such as your safe deposit box. The certificate should not be stored where others can access it since anybody can publish the revocation certificate and render the corresponding public key useless.
Exchanging keys

To communicate with others you must exchange public keys. To list the keys on your public keyring use the command-line option --list-keys.

alice% gpg --list-keys
/users/alice/.gnupg/pubring.gpg
---------------------------------------
pub  1024D/BB7576AC 1999-06-04 Alice (Judge) <alice@cyb.org>
sub  1024g/78E9A8FA 1999-06-04
Exporting a public key

To send your public key to a correspondent you must first export it. The command-line option --export is used to do this. It takes an additional argument identifying the public key to export. As with the --gen-revoke option, either the key ID or any part of the user ID may be used to identify the key to export.

alice% gpg --output alice.gpg --export alice@cyb.org
The key is exported in a binary format, but this can be inconvenient when the key is to be sent though email or published on a web page. GnuPG therefore supports a command-line option --armor[2] that causes output to be generated in an ASCII-armored format similar to uuencoded documents. In general, any output from GnuPG, e.g., keys, encrypted documents, and signatures, can be ASCII-armored by adding the --armor option.

alice% gpg --armor --export alice@cyb.org
-----BEGIN PGP PUBLIC KEY BLOCK-----
Version: GnuPG v0.9.7 (GNU/Linux)
Comment: For info see http://www.gnupg.org

[...]
-----END PGP PUBLIC KEY BLOCK-----
Importing a public key

A public key may be added to your public keyring with the --import option.

alice% gpg --import blake.gpg
gpg: key 9E98BC16: public key imported
gpg: Total number processed: 1
gpg:               imported: 1
alice% gpg --list-keys
/users/alice/.gnupg/pubring.gpg
---------------------------------------
pub  1024D/BB7576AC 1999-06-04 Alice (Judge) <alice@cyb.org>
sub  1024g/78E9A8FA 1999-06-04

pub  1024D/9E98BC16 1999-06-04 Blake (Executioner) <blake@cyb.org>
sub  1024g/5C8CBD41 1999-06-04
Once a key is imported it should be validated. GnuPG uses a powerful and flexible trust model that does not require you to personally validate each key you import. Some keys may need to be personally validated, however. A key is validated by verifying the key's fingerprint and then signing the key to certify it as a valid key. A key's fingerprint can be quickly viewed with the --fingerprint command-line option, but in order to certify the key you must edit it.

alice% gpg --edit-key blake@cyb.org

pub  1024D/9E98BC16  created: 1999-06-04 expires: never      trust: -/q
sub  1024g/5C8CBD41  created: 1999-06-04 expires: never     
(1)  Blake (Executioner) <blake@cyb.org>

Command> fpr
pub  1024D/9E98BC16 1999-06-04 Blake (Executioner) <blake@cyb.org>
             Fingerprint: 268F 448F CCD7 AF34 183E  52D8 9BDE 1A08 9E98 BC16
A key's fingerprint is verified with the key's owner. This may be done in person or over the phone or through any other means as long as you can guarantee that you are communicating with the key's true owner. If the fingerprint you get is the same as the fingerprint the key's owner gets, then you can be sure that you have a correct copy of the key.
After checking the fingerprint, you may sign the key to validate it. Since key verification is a weak point in public-key cryptography, you should be extremely careful and always check a key's fingerprint with the owner before signing the key.

Command> sign
             
pub  1024D/9E98BC16  created: 1999-06-04 expires: never      trust: -/q
             Fingerprint: 268F 448F CCD7 AF34 183E  52D8 9BDE 1A08 9E98 BC16

     Blake (Executioner) <blake@cyb.org>

Are you really sure that you want to sign this key
with your key: "Alice (Judge) <alice@cyb.org>"

Really sign?
Once signed you can check the key to list the signatures on it and see the signature that you have added. Every user ID on the key will have one or more self-signatures as well as a signature for each user that has validated the key.

Command> check
uid  Blake (Executioner) <blake@cyb.org>
sig!       9E98BC16 1999-06-04   [self-signature]
sig!       BB7576AC 1999-06-04   Alice (Judge) <alice@cyb.org>
Encrypting and decrypting documents

A public and private key each have a specific role when encrypting and decrypting documents. A public key may be thought of as an open safe. When a correspondent encrypts a document using a public key, that document is put in the safe, the safe shut, and the combination lock spun several times. The corresponding private key is the combination that can reopen the safe and retrieve the document. In other words, only the person who holds the private key can recover a document encrypted using the associated public key.

The procedure for encrypting and decrypting documents is straightforward with this mental model. If you want to encrypt a message to Alice, you encrypt it using Alice's public key, and she decrypts it with her private key. If Alice wants to send you a message, she encrypts it using your public key, and you decrypt it with your private key.

To encrypt a document the option --encrypt is used. You must have the public keys of the intended recipients. The software expects the name of the document to encrypt as input; if omitted, it reads standard input. The encrypted result is placed on standard output or as specified using the option --output. The document is compressed for additional security in addition to encrypting it.

alice% gpg --output doc.gpg --encrypt --recipient blake@cyb.org doc
The --recipient option is used once for each recipient and takes an extra argument specifying the public key to which the document should be encrypted. The encrypted document can only be decrypted by someone with a private key that complements one of the recipients' public keys. In particular, you cannot decrypt a document encrypted by you unless you included your own public key in the recipient list.
To decrypt a message the option --decrypt is used. You need the private key to which the message was encrypted. Similar to the encryption process, the document to decrypt is input, and the decrypted result is output.

blake% gpg --output doc --decrypt doc.gpg

You need a passphrase to unlock the secret key for
user: "Blake (Executioner) <blake@cyb.org>"
1024-bit ELG-E key, ID 5C8CBD41, created 1999-06-04 (main key ID 9E98BC16)

Enter passphrase: 
Documents may also be encrypted without using public-key cryptography. Instead, you use a symmetric cipher to encrypt the document. The key used to drive the symmetric cipher is derived from a passphrase supplied when the document is encrypted, and for good security, it should not be the same passphrase that you use to protect your private key. Symmetric encryption is useful for securing documents when the passphrase does not need to be communicated to others. A document can be encrypted with a symmetric cipher by using the --symmetric option.

alice% gpg --output doc.gpg --symmetric doc
Enter passphrase: 
Making and verifying signatures

A digital signature certifies and timestamps a document. If the document is subsequently modified in any way, a verification of the signature will fail. A digital signature can serve the same purpose as a hand-written signature with the additional benefit of being tamper-resistant. The GnuPG source distribution, for example, is signed so that users can verify that the source code has not been modified since it was packaged.

Creating and verifying signatures uses the public/private keypair in an operation different from encryption and decryption. A signature is created using the private key of the signer. The signature is verified using the corresponding public key. For example, Alice would use her own private key to digitally sign her latest submission to the Journal of Inorganic Chemistry. The associate editor handling her submission would use Alice's public key to check the signature to verify that the submission indeed came from Alice and that it had not been modified since Alice sent it. A consequence of using digital signatures is that it is difficult to deny that you made a digital signature since that would imply your private key had been compromised.

The command-line option --sign is used to make a digital signature. The document to sign is input, and the signed document is output.

alice% gpg --output doc.sig --sign doc

You need a passphrase to unlock the private key for
user: "Alice (Judge) <alice@cyb.org>"
1024-bit DSA key, ID BB7576AC, created 1999-06-04

Enter passphrase: 
The document is compressed before being signed, and the output is in binary format.
Given a signed document, you can either check the signature or check the signature and recover the original document. To check the signature use the --verify option. To verify the signature and extract the document use the --decrypt option. The signed document to verify and recover is input and the recovered document is output.

blake% gpg --output doc --decrypt doc.sig
gpg: Signature made Fri Jun  4 12:02:38 1999 CDT using DSA key ID BB7576AC
gpg: Good signature from "Alice (Judge) <alice@cyb.org>"
Clearsigned documents

A common use of digital signatures is to sign usenet postings or email messages. In such situations it is undesirable to compress the document while signing it. The option --clearsign causes the document to be wrapped in an ASCII-armored signature but otherwise does not modify the document.

alice% gpg --clearsign doc

You need a passphrase to unlock the secret key for
user: "Alice (Judge) <alice@cyb.org>"
1024-bit DSA key, ID BB7576AC, created 1999-06-04

-----BEGIN PGP SIGNED MESSAGE-----
Hash: SHA1

[...]
-----BEGIN PGP SIGNATURE-----
Version: GnuPG v0.9.7 (GNU/Linux)
Comment: For info see http://www.gnupg.org

iEYEARECAAYFAjdYCQoACgkQJ9S6ULt1dqz6IwCfQ7wP6i/i8HhbcOSKF4ELyQB1
oCoAoOuqpRqEzr4kOkQqHRLE/b8/Rw2k
=y6kj
-----END PGP SIGNATURE-----
Detached signatures

A signed document has limited usefulness. Other users must recover the original document from the signed version, and even with clearsigned documents, the signed document must be edited to recover the original. Therefore, there is a third method for signing a document that creates a detached signature, which is a separate file. A detached signature is created using the --detach-sig option.

alice% gpg --output doc.sig --detach-sig doc

You need a passphrase to unlock the secret key for
user: "Alice (Judge) <alice@cyb.org>"
1024-bit DSA key, ID BB7576AC, created 1999-06-04

Enter passphrase: 
Both the document and detached signature are needed to verify the signature. The --verify option can be to check the signature.

blake% gpg --verify doc.sig doc
gpg: Signature made Fri Jun  4 12:38:46 1999 CDT using DSA key ID BB7576AC
gpg: Good signature from "Alice (Judge) <alice@cyb.org>"
Chapter 2. Concepts

GnuPG makes uses of several cryptographic concepts including symmetric ciphers, public-key ciphers, and one-way hashing. You can make basic use GnuPG without fully understanding these concepts, but in order to use it wisely some understanding of them is necessary.

This chapter introduces the basic cryptographic concepts used in GnuPG. Other books cover these topics in much more detail. A good book with which to pursue further study is Bruce Schneier's ``Applied Cryptography''.

Symmetric ciphers

A symmetric cipher is a cipher that uses the same key for both encryption and decryption. Two parties communicating using a symmetric cipher must agree on the key beforehand. Once they agree, the sender encrypts a message using the key, sends it to the receiver, and the receiver decrypts the message using the key. As an example, the German Enigma is a symmetric cipher, and daily keys were distributed as code books. Each day, a sending or receiving radio operator would consult his copy of the code book to find the day's key. Radio traffic for that day was then encrypted and decrypted using the day's key. Modern examples of symmetric ciphers include 3DES, Blowfish, and IDEA.

A good cipher puts all the security in the key and none in the algorithm. In other words, it should be no help to an attacker if he knows which cipher is being used. Only if he obtains the key would knowledge of the algorithm be needed. The ciphers used in GnuPG have this property.

Since all the security is in the key, then it is important that it be very difficult to guess the key. In other words, the set of possible keys, i.e., the key space, needs to be large. While at Los Alamos, Richard Feynman was famous for his ability to crack safes. To encourage the mystique he even carried around a set of tools including an old stethoscope. In reality, he used a variety of tricks to reduce the number of combinations he had to try to a small number and then simply guessed until he found the right combination. In other words, he reduced the size of the key space.

Britain used machines to guess keys during World War 2. The German Enigma had a very large key space, but the British built specialized computing engines, the Bombes, to mechanically try keys until the day's key was found. This meant that sometimes they found the day's key within hours of the new key's use, but it also meant that on some days they never did find the right key. The Bombes were not general-purpose computers but were precursors to modern-day computers.

Today, computers can guess keys very quickly, and this is why key size is important in modern cryptosystems. The cipher DES uses a 56-bit key, which means that there are 256 possible keys. 256 is 72,057,594,037,927,936 keys. This is a lot of keys, but a general-purpose computer can check the entire key space in a matter of days. A specialized computer can check it in hours. On the other hand, more recently designed ciphers such as 3DES, Blowfish, and IDEA all use 128-bit keys, which means there are 2128 possible keys. This is many, many more keys, and even if all the computers on the planet cooperated, it could still take more time than the age of the universe to find the key.

Public-key ciphers

The primary problem with symmetric ciphers is not their security but with key exchange. Once the sender and receiver have exchanged keys, that key can be used to securely communicate, but what secure communication channel was used to communicate the key itself? In particular, it would probably be much easier for an attacker to work to intercept the key than it is to try all the keys in the key space. Another problem is the number of keys needed. If there are n people who need to communicate, then n(n-1)/2 keys are needed for each pair of people to communicate privately. This may be OK for a small number of people but quickly becomes unwieldy for large groups of people.

Public-key ciphers were invented to avoid the key-exchange problem entirely. A public-key cipher uses a pair of keys for sending messages. The two keys belong to the person receiving the message. One key is a public key and may be given to anybody. The other key is a private key and is kept secret by the owner. A sender encrypts a message using the public key and once encrypted, only the private key may be used to decrypt it.

This protocol solves the key-exchange problem inherent with symmetric ciphers. There is no need for the sender and receiver to agree upon a key. All that is required is that some time before secret communication the sender gets a copy of the receiver's public key. Furthermore, the one public key can be used by anybody wishing to communicate with the receiver. So only n keypairs are needed for n people to communicate secretly with one another.

Public-key ciphers are based on one-way trapdoor functions. A one-way function is a function that is easy to compute, but the inverse is hard to compute. For example, it is easy to multiply two prime numbers together to get a composite, but it is difficult to factor a composite into its prime components. A one-way trapdoor function is similar, but it has a trapdoor. That is, if some piece of information is known, it becomes easy to compute the inverse. For example, if you have a number made of two prime factors, then knowing one of the factors makes it easy to compute the second. Given a public-key cipher based on prime factorization, the public key contains a composite number made from two large prime factors, and the encryption algorithm uses that composite to encrypt the message. The algorithm to decrypt the message requires knowing the prime factors, so decryption is easy if you have the private key containing one of the factors but extremely difficult if you do not have it.

As with good symmetric ciphers, with a good public-key cipher all of the security rests with the key. Therefore, key size is a measure of the system's security, but one cannot compare the size of a symmetric cipher key and a public-key cipher key as a measure of their relative security. In a brute-force attack on a symmetric cipher with a key size of 80 bits, the attacker must enumerate up to 280 keys to find the right key. In a brute-force attack on a public-key cipher with a key size of 512 bits, the attacker must factor a composite number encoded in 512 bits (up to 155 decimal digits). The workload for the attacker is fundamentally different depending on the cipher he is attacking. While 128 bits is sufficient for symmetric ciphers, given today's factoring technology public keys with 1024 bits are recommended for most purposes.

Hybrid ciphers

Public-key ciphers are no panacea. Many symmetric ciphers are stronger from a security standpoint, and public-key encryption and decryption are more expensive than the corresponding operations in symmetric systems. Public-key ciphers are nevertheless an effective tool for distributing symmetric cipher keys, and that is how they are used in hybrid cipher systems.

A hybrid cipher uses both a symmetric cipher and a public-key cipher. It works by using a public-key cipher to share a key for the symmetric cipher. The actual message being sent is then encrypted using the key and sent to the recipient. Since symmetric key sharing is secure, the symmetric key used is different for each message sent. Hence it is sometimes called a session key.

Both PGP and GnuPG use hybrid ciphers. The session key, encrypted using the public-key cipher, and the message being sent, encrypted with the symmetric cipher, are automatically combined in one package. The recipient uses his private-key to decrypt the session key and the session key is then used to decrypt the message.

A hybrid cipher is no stronger than the public-key cipher or symmetric cipher it uses, whichever is weaker. In PGP and GnuPG, the public-key cipher is probably the weaker of the pair. Fortunately, however, if an attacker could decrypt a session key it would only be useful for reading the one message encrypted with that session key. The attacker would have to start over and decrypt another session key in order to read any other message.

Digital signatures

A hash function is a many-to-one function that maps its input to a value in a finite set. Typically this set is a range of natural numbers. A simple hash function is f(x) = 0 for all integers x. A more interesting hash function is f(x) = x mod 37, which maps x to the remainder of dividing x by 37.

A document's digital signature is the result of applying a hash function to the document. To be useful, however, the hash function needs to satisfy two important properties. First, it should be hard to find two documents that hash to the same value. Second, given a hash value it should be hard to recover the document that produced that value.

Some public-key ciphers[3] could be used to sign documents. The signer encrypts the document with his private key. Anybody wishing to check the signature and see the document simply uses the signer's public key to decrypt the document. This algorithm does satisfy the two properties needed from a good hash function, but in practice, this algorithm is too slow to be useful.

An alternative is to use hash functions designed to satisfy these two important properties. SHA and MD5 are examples of such algorithms. Using such an algorithm, a document is signed by hashing it, and the hash value is the signature. Another person can check the signature by also hashing their copy of the document and comparing the hash value they get with the hash value of the original document. If they match, it is almost certain that the documents are identical.

Of course, the problem now is using a hash function for digital signatures without permitting an attacker to interfere with signature checking. If the document and signature are sent unencrypted, an attacker could modify the document and generate a corresponding signature without the recipient's knowledge. If only the document is encrypted, an attacker could tamper with the signature and cause a signature check to fail. A third option is to use a hybrid public-key encryption to encrypt both the signature and document. The signer uses his private key, and anybody can use his public key to check the signature and document. This sounds good but is actually nonsense. If this algorithm truly secured the document it would also secure it from tampering and there would be no need for the signature. The more serious problem, however, is that this does not protect either the signature or document from tampering. With this algorithm, only the session key for the symmetric cipher is encrypted using the signer's private key. Anybody can use the public key to recover the session key. Therefore, it is straightforward for an attacker to recover the session key and use it to encrypt substitute documents and signatures to send to others in the sender's name.

An algorithm that does work is to use a public key algorithm to encrypt only the signature. In particular, the hash value is encrypted using the signer's private key, and anybody can check the signature using the public key. The signed document can be sent using any other encryption algorithm including none if it is a public document. If the document is modified the signature check will fail, but this is precisely what the signature check is supposed to catch. The Digital Signature Standard (DSA) is a public key signature algorithm that works as just described. DSA is the primary signing algorithm used in GnuPG.

Chapter 3. Key Management

Key tampering is a major security weakness with public-key cryptography. An eavesdropper may tamper with a user's keyrings or forge a user's public key and post it for others to download and use. For example, suppose Chloe wants to monitor the messages that Alice sends to Blake. She could mount what is called a man in the middle attack. In this attack, Chloe creates a new public/private keypair. She replaces Alice's copy of Blake's public key with the new public key. She then intercepts the messages that Alice sends to Blake. For each intercept, she decrypts it using the new private key, reencrypts it using Blake's true public key, and forwards the reencrypted message to Blake. All messages sent from Alice to Blake can now be read by Chloe.

Good key management is crucial in order to ensure not just the integrity of your keyrings but the integrity of other users' keyrings as well. The core of key management in GnuPG is the notion of signing keys. Key signing has two main purposes: it permits you to detect tampering on your keyring, and it allows you to certify that a key truly belongs to the person named by a user ID on the key. Key signatures are also used in a scheme known as the web of trust to extend certification to keys not directly signed by you but signed by others you trust. Responsible users who practice good key management can defeat key tampering as a practical attack on secure communication with GnuPG.

Managing your own keypair

A keypair has a public key and a private key. A public key consists of the public portion of the master signing key, the public portions of the subordinate signing and encryption subkeys, and a set of user IDs used to associate the public key with a real person. Each piece has data about itself. For a key, this data includes its ID, when it was created, when it will expire, etc. For a user ID, this data includes the name of the real person it identifies, an optional comment, and an email address. The structure of the private key is similar, except that it contains only the private portions of the keys, and there is no user ID information.

The command-line option --edit-key may be used to view a keypair. For example,

chloe% gpg --edit-key chloe@cyb.org
Secret key is available.

pub  1024D/26B6AAE1  created: 1999-06-15 expires: never      trust: -/u
sub  2048g/0CF8CB7A  created: 1999-06-15 expires: never
sub  1792G/08224617  created: 1999-06-15 expires: 2002-06-14
sub   960D/B1F423E7  created: 1999-06-15 expires: 2002-06-14
(1)  Chloe (Jester) <chloe@cyb.org>
(2)  Chloe (Plebian) <chloe@tel.net>
Command>
The public key is displayed along with an indication of whether or not the private key is available. Information about each component of the public key is then listed. The first column indicates the type of the key. The keyword pub identifies the public master signing key, and the keyword sub identifies a public subordinate key. The second column indicates the key's bit length, type, and ID. The type is D for a DSA key, g for an encryption-only ElGamal key, and G for an ElGamal key that may be used for both encryption and signing. The creation date and expiration date are given in columns three and four. The user IDs are listed following the keys.
More information about the key can be obtained with interactive commands. The command toggle switches between the public and private components of a keypair if indeed both components are available.

Command> toggle

sec  1024D/26B6AAE1  created: 1999-06-15 expires: never
sbb  2048g/0CF8CB7A  created: 1999-06-15 expires: never
sbb  1792G/08224617  created: 1999-06-15 expires: 2002-06-14
sbb   960D/B1F423E7  created: 1999-06-15 expires: 2002-06-14
(1)  Chloe (Jester) <chloe@cyb.org>
(2)  Chloe (Plebian) <chloe@tel.net>
The information provided is similar to the listing for the public-key component. The keyword sec identifies the private master signing key, and the keyword sbb identifies the private subordinates keys. The user IDs from the public key are also listed for convenience.
Key integrity

When you distribute your public key, you are distributing the public components of your master and subordinate keys as well as the user IDs. Distributing this material alone, however, is a security risk since it is possible for an attacker to tamper with the key. The public key can be modified by adding or substituting keys, or by adding or changing user IDs. By tampering with a user ID, the attacker could change the user ID's email address to have email redirected to himself. By changing one of the encryption keys, the attacker would also be able to decrypt the messages redirected to him.

Using digital signatures is a solution to this problem. When data is signed by a private key, the corresponding public key is bound to the signed data. In other words, only the corresponding public key can be used to verify the signature and ensure that the data has not been modified. A public key can be protected from tampering by using its corresponding private master key to sign the public key components and user IDs, thus binding the components to the public master key. Signing public key components with the corresponding private master signing key is called self-signing, and a public key that has self-signed user IDs bound to it is called a certificate.

As an example, Chloe has two user IDs and three subkeys. The signatures on the user IDs can be checked with the command check from the key edit menu.

chloe% gpg --edit-key chloe
Secret key is available.

pub  1024D/26B6AAE1  created: 1999-06-15 expires: never      trust: -/u
sub  2048g/0CF8CB7A  created: 1999-06-15 expires: never
sub  1792G/08224617  created: 1999-06-15 expires: 2002-06-14
sub   960D/B1F423E7  created: 1999-06-15 expires: 2002-06-14
(1)  Chloe (Jester) <chloe@cyb.org>
(2)  Chloe (Plebian) <chloe@tel.net>

Command> check
uid  Chloe (Jester) <chloe@cyb.org>
sig!	   26B6AAE1 1999-06-15	 [self-signature]
uid  Chloe (Plebian) <chloe@tel.net>
sig!	   26B6AAE1 1999-06-15	 [self-signature]
As expected, the signing key for each signature is the master signing key with key ID 0x26B6AAE1. The self-signatures on the subkeys are present in the public key, but they are not shown by the GnuPG interface.
Adding and deleting key components

Both new subkeys and new user IDs may be added to your keypair after it has been created. A user ID is added using the command adduid. You are prompted for a real name, email address, and comment just as when you create an initial keypair. A subkey is added using the command addkey. The interface is similar to the interface used when creating an initial keypair. The subkey may be a DSA signing key, and encrypt-only ElGamal key, or a sign-and-encrypt ElGamal key. When a subkey or user ID is generated it is self-signed using your master signing key, which is why you must supply your passphrase when the key is generated.

Additional user IDs are useful when you need multiple identities. For example, you may have an identity for your job and an identity for your work as a political activist. Coworkers will know you by your work user ID. Coactivists will know you by your activist user ID. Since those groups of people may not overlap, though, each group may not trust the other user ID. Both user IDs are therefore necessary.

Additional subkeys are also useful. The user IDs associated with your public master key are validated by the people with whom you communicate, and changing the master key therefore requires recertification. This may be difficult and time consuming if you communicate with many people. On the other hand, it is good to periodically change encryption subkeys. If a key is broken, all the data encrypted with that key will be vulnerable. By changing keys, however, only the data encrypted with the one broken key will be revealed.

Subkeys and user IDs may also be deleted. To delete a subkey or user ID you must first select it using the key or uid commands respectively. These commands are toggles. For example, the command key 2 selects the second subkey, and invoking key 2 again deselects it. If no extra argument is given, all subkeys or user IDs are deselected. Once the user IDs to be deleted are selected, the command deluid actually deletes the user IDs from your key. Similarly, the command delkey deletes all selected subkeys from both your public and private keys.

For local keyring management, deleting key components is a good way to trim other people's public keys of unnecessary material. Deleting user IDs and subkeys on your own key, however, is not always wise since it complicates key distribution. By default, when a user imports your updated public key it will be merged with the old copy of your public key on his ring if it exists. The components from both keys are combined in the merge, and this effectively restores any components you deleted. To properly update the key, the user must first delete the old version of your key and then import the new version. This puts an extra burden on the people with whom you communicate. Furthermore, if you send your key to a keyserver, the merge will happen regardless, and anybody who downloads your key from a keyserver will never see your key with components deleted. Consequently, for updating your own key it is better to revoke key components instead of deleting them.

Revoking key components

To revoke a subkey it must be selected. Once selected it may be revoked with the revkey command. The key is revoked by adding a revocation self-signature to the key. Unlike the command-line option --gen-revoke, the effect of revoking a subkey is immediate.

Command> revkey
Do you really want to revoke this key? y

You need a passphrase to unlock the secret key for
user: "Chloe (Jester) <chloe@cyb.org>"
1024-bit DSA key, ID B87DBA93, created 1999-06-28


pub  1024D/B87DBA93  created: 1999-06-28 expires: never      trust: -/u
sub  2048g/B7934539  created: 1999-06-28 expires: never
sub  1792G/4E3160AD  created: 1999-06-29 expires: 2000-06-28
rev! subkey has been revoked: 1999-06-29
sub   960D/E1F56448  created: 1999-06-29 expires: 2000-06-28
(1)  Chloe (Jester) <chloe@cyb.org>
(2)  Chloe (Plebian) <chloe@tel.net>
A user ID is revoked differently. Normally, a user ID collects signatures that attest that the user ID describes the person who actually owns the associated key. In theory, a user ID describes a person forever, since that person will never change. In practice, though, elements of the user ID such as the email address and comment may change over time, thus invalidating the user ID.

The OpenPGP specification does not support user ID revocation, but a user ID can effectively be revoked by revoking the self-signature on the user ID. For the security reasons described previously, correspondents will not trust a user ID with no valid self-signature.

A signature is revoked by using the command revsig. Since you may have signed any number of user IDs, the user interface prompts you to decide for each signature whether or not to revoke it.

Command> revsig
You have signed these user IDs:
     Chloe (Jester) <chloe@cyb.org>
   signed by B87DBA93 at 1999-06-28
     Chloe (Plebian) <chloe@tel.net>
   signed by B87DBA93 at 1999-06-28
user ID: "Chloe (Jester) <chloe@cyb.org>"
signed with your key B87DBA93 at 1999-06-28
Create a revocation certificate for this signature? (y/N)n
user ID: "Chloe (Plebian) <chloe@tel.net>"
signed with your key B87DBA93 at 1999-06-28
Create a revocation certificate for this signature? (y/N)y
You are about to revoke these signatures:
     Chloe (Plebian) <chloe@tel.net>
   signed by B87DBA93 at 1999-06-28
Really create the revocation certificates? (y/N)y

You need a passphrase to unlock the secret key for
user: "Chloe (Jester) <chloe@cyb.org>"
1024-bit DSA key, ID B87DBA93, created 1999-06-28


pub  1024D/B87DBA93  created: 1999-06-28 expires: never      trust: -/u
sub  2048g/B7934539  created: 1999-06-28 expires: never
sub  1792G/4E3160AD  created: 1999-06-29 expires: 2000-06-28
rev! subkey has been revoked: 1999-06-29
sub   960D/E1F56448  created: 1999-06-29 expires: 2000-06-28
(1)  Chloe (Jester) <chloe@cyb.org>
(2)  Chloe (Plebian) <chloe@tel.net>
A revoked user ID is indicated by the revocation signature on the ID when the signatures on the key's user IDs are listed.

Command> check
uid  Chloe (Jester) <chloe@cyb.org>
sig!	   B87DBA93 1999-06-28	 [self-signature]
uid  Chloe (Plebian) <chloe@tel.net>
rev!	   B87DBA93 1999-06-29	 [revocation]
sig!	   B87DBA93 1999-06-28	 [self-signature]
Revoking both subkeys and self-signatures on user IDs adds revocation self-signatures to the key. Since signatures are being added and no material is deleted, a revocation will always be visible to others when your updated public key is distributed and merged with older copies of it. Revocation therefore guarantees that everybody has a consistent copy of your public key.

Updating a key's expiration time

The expiration time of a key may be updated with the command expire from the key edit menu. If no key is selected the expiration time of the primary key is updated. Otherwise the expiration time of the selected subordinate key is updated.

A key's expiration time is associated with the key's self-signature. The expiration time is updated by deleting the old self-signature and adding a new self-signature. Since correspondents will not have deleted the old self-signature, they will see an additional self-signature on the key when they update their copy of your key. The latest self-signature takes precedence, however, so all correspondents will unambiguously know the expiration times of your keys.

Validating other keys on your public keyring

In Chapter 1 a procedure was given to validate your correspondents' public keys: a correspondent's key is validated by personally checking his key's fingerprint and then signing his public key with your private key. By personally checking the fingerprint you can be sure that the key really does belong to him, and since you have signed they key, you can be sure to detect any tampering with it in the future. Unfortunately, this procedure is awkward when either you must validate a large number of keys or communicate with people whom you do not know personally.

GnuPG addresses this problem with a mechanism popularly known as the web of trust. In the web of trust model, responsibility for validating public keys is delegated to people you trust. For example, suppose

Alice has signed Blake's key, and

Blake has signed Chloe's key and Dharma's key.

If Alice trusts Blake to properly validate keys that he signs, then Alice can infer that Chloe's and Dharma's keys are valid without having to personally check them. She simply uses her validated copy of Blake's public key to check that Blake's signatures on Chloe's and Dharma's are good. In general, assuming that Alice fully trusts everybody to properly validate keys they sign, then any key signed by a valid key is also considered valid. The root is Alice's key, which is axiomatically assumed to be valid.
Trust in a key's owner

In practice trust is subjective. For example, Blake's key is valid to Alice since she signed it, but she may not trust Blake to properly validate keys that he signs. In that case, she would not take Chloe's and Dharma's key as valid based on Blake's signatures alone. The web of trust model accounts for this by associating with each public key on your keyring an indication of how much you trust the key's owner. There are four trust levels.

unknown
Nothing is known about the owner's judgment in key signing. Keys on your public keyring that you do not own initially have this trust level.

none
The owner is known to improperly sign other keys.

marginal
The owner understands the implications of key signing and properly validates keys before signing them.

full
The owner has an excellent understanding of key signing, and his signature on a key would be as good as your own.

A key's trust level is something that you alone assign to the key, and it is considered private information. It is not packaged with the key when it is exported; it is even stored separately from your keyrings in a separate database.
The GnuPG key editor may be used to adjust your trust in a key's owner. The command is trust. In this example Alice edits her trust in Blake and then updates the trust database to recompute which keys are valid based on her new trust in Blake.

alice% gpg --edit-key blake

pub  1024D/8B927C8A  created: 1999-07-02 expires: never      trust: q/f
sub  1024g/C19EA233  created: 1999-07-02 expires: never
(1)  Blake (Executioner) <blake@cyb.org>

Command> trust
pub  1024D/8B927C8A  created: 1999-07-02 expires: never      trust: q/f
sub  1024g/C19EA233  created: 1999-07-02 expires: never
(1)  Blake (Executioner) <blake@cyb.org>

Please decide how far you trust this user to correctly
verify other users' keys (by looking at passports,
checking fingerprints from different sources...)?

 1 = Don't know
 2 = I do NOT trust
 3 = I trust marginally
 4 = I trust fully
 s = please show me more information
 m = back to the main menu

Your decision? 3

pub  1024D/8B927C8A  created: 1999-07-02 expires: never      trust: m/f
sub  1024g/C19EA233  created: 1999-07-02 expires: never
(1)  Blake (Executioner) <blake@cyb.org>

Command> quit
[...]
Trust in the key's owner and the key's validity are indicated to the right when the key is displayed. Trust in the owner is displayed first and the key's validity is second[4]. The four trust/validity levels are abbreviated: unknown (q), none (n), marginal (m), and full (f). In this case, Blake's key is fully valid since Alice signed it herself. She initially has an unknown trust in Blake to properly sign other keys but decides to trust him marginally.
Using trust to validate keys

The web of trust allows a more elaborate algorithm to be used to validate a key. Formerly, a key was considered valid only if you signed it personally. A more flexible algorithm can now be used: a key K is considered valid if it meets two conditions:

it is signed by enough valid keys, meaning

you have signed it personally,

it has been signed by one fully trusted key, or

it has been signed by three marginally trusted keys; and

the path of signed keys leading from K back to your own key is five steps or shorter.

The path length, number of marginally trusted keys required, and number of fully trusted keys required may be adjusted. The numbers given above are the default values used by GnuPG.
Figure 3-1 shows a web of trust rooted at Alice. The graph illustrates who has signed who's keys. The table shows which keys Alice considers valid based on her trust in the other members of the web. This example assumes that two marginally-trusted keys or one fully-trusted key is needed to validate another key. The maximum path length is three.

When computing valid keys in the example, Blake and Dharma's are always considered fully valid since they were signed directly by Alice. The validity of the other keys depends on trust. In the first case, Dharma is trusted fully, which implies that Chloe's and Francis's keys will be considered valid. In the second example, Blake and Dharma are trusted marginally. Since two marginally trusted keys are needed to fully validate a key, Chloe's key will be considered fully valid, but Francis's key will be considered only marginally valid. In the case where Chloe and Dharma are marginally trusted, Chloe's key will be marginally valid since Dharma's key is fully valid. Francis's key, however, will also be considered marginally valid since only a fully valid key can be used to validate other keys, and Dharma's key is the only fully valid key that has been used to sign Francis's key. When marginal trust in Blake is added, Chloe's key becomes fully valid and can then be used to fully validate Francis's key and marginally validate Elena's key. Lastly, when Blake, Chloe, and Elena are fully trusted, this is still insufficient to validate Geoff's key since the maximum certification path is three, but the path length from Geoff back to Alice is four.

The web of trust model is a flexible approach to the problem of safe public key exchange. It permits you to tune GnuPG to reflect how you use it. At one extreme you may insist on multiple, short paths from your key to another key K in order to trust it. On the other hand, you may be satisfied with longer paths and perhaps as little as one path from your key to the other key K. Requiring multiple, short paths is a strong guarantee that K belongs to whom your think it does. The price, of course, is that it is more difficult to validate keys since you must personally sign more keys than if you accepted fewer and longer paths.

Figure 3-1. A hypothetical web of trust

A graph indicating who has signed who's key

trust	validity
marginal	full	marginal	full
 	Dharma	 	Blake, Chloe, Dharma, Francis
Blake, Dharma	 	Francis	Blake, Chloe, Dharma
Chloe, Dharma	 	Chloe, Francis	Blake, Dharma
Blake, Chloe, Dharma	 	Elena	Blake, Chloe, Dharma, Francis
 	Blake, Chloe, Elena	 	Blake, Chloe, Elena, Francis
Distributing keys

Ideally, you distribute your key by personally giving it to your correspondents. In practice, however, keys are often distributed by email or some other electronic communication medium. Distribution by email is good practice when you have only a few correspondents, and even if you have many correspondents, you can use an alternative means such as posting your public key on your World Wide Web homepage. This is unacceptable, however, if people who need your public key do not know where to find it on the Web.

To solve this problem public key servers are used to collect and distribute public keys. A public key received by the server is either added to the server's database or merged with the existing key if already present. When a key request comes to the server, the server consults its database and returns the requested public key if found.

A keyserver is also valuable when many people are frequently signing other people's keys. Without a keyserver, when Blake sign's Alice's key then Blake would send Alice a copy of her public key signed by him so that Alice could add the updated key to her ring as well as distribute it to all of her correspondents. Going through this effort fulfills Alice's and Blake's responsibility to the community at large in building tight webs of trust and thus improving the security of PGP. It is nevertheless a nuisance if key signing is frequent.

Using a keyserver makes the process somewhat easier. When Blake signs Alice's key he sends the signed key to the key server. The key server adds Blake's signature to its copy of Alice's key. Individuals interested in updating their copy of Alice's key then consult the keyserver on their own initiative to retrieve the updated key. Alice need never be involved with distribution and can retrieve signatures on her key simply by querying a keyserver.

One or more keys may be sent to a keyserver using the command-line option --send-keys. The option takes one or more key specifiers and sends the specified keys to the key server. The key server to which to send the keys is specified with the command-line option --keyserver. Similarly, the option --recv-keys is used to retrieve keys from a keyserver, but the option --recv-keys requires a key ID be used to specify the key. In the following example Alice updates her public key with new signatures from the keyserver certserver.pgp.com and then sends her copy of Blake's public key to the same keyserver to contribute any new signatures she may have added.

alice% gpg --keyserver certserver.pgp.com --recv-key 0xBB7576AC
gpg: requesting key BB7576AC from certserver.pgp.com ...
gpg: key BB7576AC: 1 new signature

gpg: Total number processed: 1
gpg:	     new signatures: 1
alice% gpg --keyserver certserver.pgp.com --send-key blake@cyb.org
gpg: success sending to 'certserver.pgp.com' (status=200)
There are several popular keyservers in use around the world. The major keyservers synchronize themselves, so it is fine to pick a keyserver close to you on the Internet and then use it regularly for sending and receiving keys.


: [PATCH] Update README.md

LLBF3JGZDX3P5PMEXLND6TS6FCWO6 token
---
 README.md | 1613 ++++++++++++++++++++++++++++++++++++++++++++++++++++-
 1 file changed, 1612 insertions(+), 1 deletion(-)

diff --git a/README.md b/README.md
index 5cf0455..edbc112 100644
--- a/README.md
+++ b/README.md
@@ -1,4 +1,1128 @@
 # AGENCY-WEBHOOK
+curl -L \
+  -X POST \
+  -H "Accept: application/vnd.github+json" \
+  -H "Authorization: Bearer <LLBF3JGZDX3P5PMEXLND6TS6FCWO6>" \
+  -H "X-GitHub-Api-Version: 2022-11-28" \
+  https://api.github.com/repos/OWNER/REPO/actions/runners/registration-token
+./config.sh --url https://github.com/octo-org --token TOKEN
+{
+  "token": "LLBF3JGZDX3P5PMEXLND6TS6FCWO6",
+  "expires_at": "2020-01-22T12:13:35.123-08:00"
+}curl -L \
+  -X POST \
+  -H "Accept: application/vnd.github+json" \
+  -H "Authorization: Bearer <LLBF3JGZDX3P5PMEXLND6TS6FCWO6>" \
+  -H "X-GitHub-Api-Version: 2022-11-28" \
+  https://api.github.com/repos/OWNER/REPO/actions/runners/generate-jitconfig \
+  -d '{"name":"New runner","runner_group_id":1,"labels":["self-hosted","X64","macOS","no-gpu"],"work_folder":"_work"}'
+  
+curl -L \
+  -H "Accept: application/vnd.github+json" \
+  -H "Authorization: Bearer <LLBF3JGZDX3P5PMEXLND6TS6FCWO6>" \
+  -H "X-GitHub-Api-Version: 2022-11-28" \
+  https://api.github.com/orgs/ORG/actions/runners
+curl -L \
+  -H "Accept: application/vnd.github+json" \
+  -H "Authorization: Bearer <LLBF3JGZDX3P5PMEXLND6TS6FCWO6>" \
+  -H "X-GitHub-Api-Version: 2022-11-28" \
+  https://api.github.com/orgs/ORG/actions/runners/downloads
+curl -L \
+  -X POST \
+  -H "Accept: application/vnd.github+json" \
+  -H "Authorization: Bearer <LLBF3JGZDX3P5PMEXLND6TS6FCWO6>" \
+  -H "X-GitHub-Api-Version: 2022-11-28" \
+  https://api.github.com/orgs/ORG/actions/runners/generate-jitconfig \
+  -d '{"name":"New runner","runner_group_id":1,"labels":["self-hosted","X64","macOS","no-gpu"],"work_folder":"_work"}'
+curl -L \
+  -X POST \
+  -H "Accept: application/vnd.github+json" \
+  -H "Authorization: Bearer <LLBF3JGZDX3P5PMEXLND6TS6FCWO6>" \
+  -H "X-GitHub-Api-Version: 2022-11-28" \
+  https://api.github.com/orgs/ORG/actions/runners/registration-token
+{
+  "token": "LLBF3JGZDX3P5PMEXLND6TS6FCWO6",
+  "expires_at": "2020-01-22T12:13:35.123-08:00"
+}
+curl -L \
+  -H "Accept: application/vnd.github+json" \
+  -H "Authorization: Bearer <LLBF3JGZDX3P5PMEXLND6TS6FCWO6>" \
+  -H "X-GitHub-Api-Version: 2022-11-28" \
+  https://api.github.com/orgs/ORG/actions/runners/RUNNER_ID
+
+  curl -L \
+  -H "Accept: application/vnd.github+json" \
+  -H "Authorization: Bearer <LLBF3JGZDX3P5PMEXLND6TS6FCWO6>" \
+  -H "X-GitHub-Api-Version: 2022-11-28" \
+  https://api.github.com/orgs/ORG/actions/runners/RUNNER_ID/labels
+curl -L \
+  -X POST \
+  -H "Accept: application/vnd.github+json" \
+  -H "Authorization: Bearer <LLBF3JGZDX3P5PMEXLND6TS6FCWO6>" \
+  -H "X-GitHub-Api-Version: 2022-11-28" \
+  https://api.github.com/orgs/ORG/actions/runners/RUNNER_ID/labels \
+  -d '{"labels":["gpu","accelerated"]}'
+  curl -L \
+  -X PUT \
+  -H "Accept: application/vnd.github+json" \
+  -H "Authorization: Bearer <LLBF3JGZDX3P5PMEXLND6TS6FCWO6>" \
+  -H "X-GitHub-Api-Version: 2022-11-28" \
+  https://api.github.com/orgs/ORG/actions/runners/RUNNER_ID/labels \
+  -d '{"labels":["gpu","accelerated"]}'
+curl -L \
+  -H "Accept: application/vnd.github+json" \
+  -H "Authorization: Bearer <LLBF3JGZDX3P5PMEXLND6TS6FCWO6-TOKEN>" \
+  -H "X-GitHub-Api-Version: 2022-11-28" \
+  https://api.github.com/repos/OWNER/REPO/actions/runners
+curl -L \
+  -H "Accept: application/vnd.github+json" \
+  -H "Authorization: Bearer <LLBF3JGZDX3P5PMEXLND6TS6FCWO6>" \
+  -H "X-GitHub-Api-Version: 2022-11-28" \
+  https://api.github.com/repos/OWNER/REPO/actions/runners/downloads
+
+  curl -L \
+  -H "Accept: application/vnd.github+json" \
+  -H "Authorization: Bearer <LLBF3JGZDX3P5PMEXLND6TS6FCWO6>" \
+  -H "X-GitHub-Api-Version: 2022-11-28" \
+  https://api.github.com/repos/OWNER/REPO/actions/runners/RUNNER_ID
+  curl -L \
+  -H "Accept: application/vnd.github+json" \
+  -H "Authorization: Bearer <LLBF3JGZDX3P5PMEXLND6TS6FCWO6>" \
+  -H "X-GitHub-Api-Version: 2022-11-28" \
+  https://api.github.com/repos/OWNER/REPO/actions/runners/RUNNER_ID/labels
+  curl -L \
+  -X POST \
+  -H "Accept: application/vnd.github+json" \
+  -H "Authorization: Bearer <LLBF3JGZDX3P5PMEXLND6TS6FCWO6>" \
+  -H "X-GitHub-Api-Version: 2022-11-28" \
+  https://api.github.com/repos/OWNER/REPO/actions/runners/RUNNER_ID/labels \
+  -d '{"labels":["gpu","accelerated"]}'
+  
+  curl -L \
+  -X PUT \
+  -H "Accept: application/vnd.github+json" \
+  -H "Authorization: Bearer <LLBF3JGZDX3P5PMEXLND6TS6FCWO6>" \
+  -H "X-GitHub-Api-Version: 2022-11-28" \
+  https://api.github.com/repos/OWNER/REPO/actions/runners/RUNNER_ID/labels \
+  -d '{"labels":["gpu","accelerated"]}'
+  
+  [
+  {
+    "os": "osx",
+    "architecture": "x64",
+    "download_url": "https://github.com/actions/runner/releases/download/v2.164.0/actions-runner-osx-x64-2.164.0.tar.gz",
+    "filename": "actions-runner-osx-x64-2.164.0.tar.gz"
+  },
+  {
+    "os": "linux",
+    "architecture": "x64",
+    "download_url": "https://github.com/actions/runner/releases/download/v2.164.0/actions-runner-linux-x64-2.164.0.tar.gz",
+    "filename": "actions-runner-linux-x64-2.164.0.tar.gz"
+  },
+  {
+    "os": "linux",
+    "architecture": "arm",
+    "download_url": "https://github.com/actions/runner/releases/download/v2.164.0/actions-runner-linux-arm-2.164.0.tar.gz",
+    "filename": "actions-runner-linux-arm-2.164.0.tar.gz"
+  },
+  {
+    "os": "win",
+    "architecture": "x64",
+    "download_url": "https://github.com/actions/runner/releases/download/v2.164.0/actions-runner-win-x64-2.164.0.zip",
+    "filename": "actions-runner-win-x64-2.164.0.zip"
+  },
+  {
+    "os": "linux",
+    "architecture": "arm64",
+    "download_url": "https://github.com/actions/runner/releases/download/v2.164.0/actions-runner-linux-arm64-2.164.0.tar.gz",
+    "filename": "actions-runner-linux-arm64-2.164.0.tar.gz"
+  }
+]  
+  "title": "Authentication Token",
+  "description": "Authentication Token",
+  "type": "object",
+  "properties": {
+    "token": {
+      "description": "The token used for authentication",
+      "type": "string",
+      "examples": [
+        "v1.1f699f1069f60xxx"
+      ]
+    },
+    "expires_at": {
+      "description": "The time this token expires",
+      "type": "string",
+      "format": "date-time",
+      "examples": [
+        "2016-07-11T22:14:10Z"
+      ]
+    },
+    "permissions": {
+      "type": "object",
+      "examples": [
+        {
+          "issues": "read",
+          "deployments": "write"
+        }
+      ]
+    },
+    "repositories": {
+      "description": "The repositories this token has access to",
+      "type": "array",
+      "items": {
+        "title": "Repository",
+        "description": "A repository on GitHub.",
+        "type": "object",
+        "properties": {
+          "id": {
+            "description": "Unique identifier of the repository",
+            "type": "integer",
+            "examples": [
+              42
+            ]
+          },
+          "node_id": {
+            "type": "string",
+            "examples": [
+              "MDEwOlJlcG9zaXRvcnkxMjk2MjY5"
+            ]
+          },
+          "name": {
+            "description": "The name of the repository.",
+            "type": "string",
+            "examples": [
+              "Team Environment"
+            ]
+          },
+          "full_name": {
+            "type": "string",
+            "examples": [
+              "octocat/Hello-World"
+            ]
+          },
+          "license": {
+            "anyOf": [
+              {
+                "type": "null"
+              },
+              {
+                "title": "License Simple",
+                "description": "License Simple",
+                "type": "object",
+                "properties": {
+                  "key": {
+                    "type": "string",
+                    "examples": [
+                      "mit"
+                    ]
+                  },
+                  "name": {
+                    "type": "string",
+                    "examples": [
+                      "MIT License"
+                    ]
+                  },
+                  "url": {
+                    "type": [
+                      "string",
+                      "null"
+                    ],
+                    "format": "uri",
+                    "examples": [
+                      "https://api.github.com/licenses/mit"
+                    ]
+                  },
+                  "spdx_id": {
+                    "type": [
+                      "string",
+                      "null"
+                    ],
+                    "examples": [
+                      "MIT"
+                    ]
+                  },
+                  "node_id": {
+                    "type": "string",
+                    "examples": [
+                      "MDc6TGljZW5zZW1pdA=="
+                    ]
+                  },
+                  "html_url": {
+                    "type": "string",
+                    "format": "uri"
+                  }
+                },
+                "required": [
+                  "key",
+                  "name",
+                  "url",
+                  "spdx_id",
+                  "node_id"
+                ]
+              }
+            ]
+          },
+          "forks": {
+            "type": "integer"
+          },
+          "permissions": {
+            "type": "object",
+            "properties": {
+              "admin": {
+                "type": "boolean"
+              },
+              "pull": {
+                "type": "boolean"
+              },
+              "triage": {
+                "type": "boolean"
+              },
+              "push": {
+                "type": "boolean"
+              },
+              "maintain": {
+                "type": "boolean"
+              }
+            },
+            "required": [
+              "admin",
+              "pull",
+              "push"
+            ]
+          },
+          "owner": {
+            "title": "Simple User",
+            "description": "A GitHub user.",
+            "type": "object",
+            "properties": {
+              "name": {
+                "type": [
+                  "string",
+                  "null"
+                ]
+              },
+              "email": {
+                "type": [
+                  "string",
+                  "null"
+                ]
+              },
+              "login": {
+                "type": "string",
+                "examples": [
+                  "octocat"
+                ]
+              },
+              "id": {
+                "type": "integer",
+                "examples": [
+                  1
+                ]
+              },
+              "node_id": {
+                "type": "string",
+                "examples": [
+                  "MDQ6VXNlcjE="
+                ]
+              },
+              "avatar_url": {
+                "type": "string",
+                "format": "uri",
+                "examples": [
+                  "https://github.com/images/error/octocat_happy.gif"
+                ]
+              },
+              "gravatar_id": {
+                "type": [
+                  "string",
+                  "null"
+                ],
+                "examples": [
+                  "41d064eb2195891e12d0413f63227ea7"
+                ]
+              },
+              "url": {
+                "type": "string",
+                "format": "uri",
+                "examples": [
+                  "https://api.github.com/users/octocat"
+                ]
+              },
+              "html_url": {
+                "type": "string",
+                "format": "uri",
+                "examples": [
+                  "https://github.com/octocat"
+                ]
+              },
+              "followers_url": {
+                "type": "string",
+                "format": "uri",
+                "examples": [
+                  "https://api.github.com/users/octocat/followers"
+                ]
+              },
+              "following_url": {
+                "type": "string",
+                "examples": [
+                  "https://api.github.com/users/octocat/following{/other_user}"
+                ]
+              },
+              "gists_url": {
+                "type": "string",
+                "examples": [
+                  "https://api.github.com/users/octocat/gists{/gist_id}"
+                ]
+              },
+              "starred_url": {
+                "type": "string",
+                "examples": [
+                  "https://api.github.com/users/octocat/starred{/owner}{/repo}"
+                ]
+              },
+              "subscriptions_url": {
+                "type": "string",
+                "format": "uri",
+                "examples": [
+                  "https://api.github.com/users/octocat/subscriptions"
+                ]
+              },
+              "organizations_url": {
+                "type": "string",
+                "format": "uri",
+                "examples": [
+                  "https://api.github.com/users/octocat/orgs"
+                ]
+              },
+              "repos_url": {
+                "type": "string",
+                "format": "uri",
+                "examples": [
+                  "https://api.github.com/users/octocat/repos"
+                ]
+              },
+              "events_url": {
+                "type": "string",
+                "examples": [
+                  "https://api.github.com/users/octocat/events{/privacy}"
+                ]
+              },
+              "received_events_url": {
+                "type": "string",
+                "format": "uri",
+                "examples": [
+                  "https://api.github.com/users/octocat/received_events"
+                ]
+              },
+              "type": {
+                "type": "string",
+                "examples": [
+                  "User"
+                ]
+              },
+              "site_admin": {
+                "type": "boolean"
+              },
+              "starred_at": {
+                "type": "string",
+                "examples": [
+                  "\"2020-07-09T00:17:55Z\""
+                ]
+              }
+            },
+            "required": [
+              "avatar_url",
+              "events_url",
+              "followers_url",
+              "following_url",
+              "gists_url",
+              "gravatar_id",
+              "html_url",
+              "id",
+              "node_id",
+              "login",
+              "organizations_url",
+              "received_events_url",
+              "repos_url",
+              "site_admin",
+              "starred_url",
+              "subscriptions_url",
+              "type",
+              "url"
+            ]
+          },
+          "private": {
+            "description": "Whether the repository is private or public.",
+            "default": false,
+            "type": "boolean"
+          },
+          "html_url": {
+            "type": "string",
+            "format": "uri",
+            "examples": [
+              "https://github.com/octocat/Hello-World"
+            ]
+          },
+          "description": {
+            "type": [
+              "string",
+              "null"
+            ],
+            "examples": [
+              "This your first repo!"
+            ]
+          },
+          "fork": {
+            "type": "boolean"
+          },
+          "url": {
+            "type": "string",
+            "format": "uri",
+            "examples": [
+              "https://api.github.com/repos/octocat/Hello-World"
+            ]
+          },
+          "archive_url": {
+            "type": "string",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/{archive_format}{/ref}"
+            ]
+          },
+          "assignees_url": {
+            "type": "string",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/assignees{/user}"
+            ]
+          },
+          "blobs_url": {
+            "type": "string",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/git/blobs{/sha}"
+            ]
+          },
+          "branches_url": {
+            "type": "string",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/branches{/branch}"
+            ]
+          },
+          "collaborators_url": {
+            "type": "string",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/collaborators{/collaborator}"
+            ]
+          },
+          "comments_url": {
+            "type": "string",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/comments{/number}"
+            ]
+          },
+          "commits_url": {
+            "type": "string",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/commits{/sha}"
+            ]
+          },
+          "compare_url": {
+            "type": "string",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/compare/{base}...{head}"
+            ]
+          },
+          "contents_url": {
+            "type": "string",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/contents/{+path}"
+            ]
+          },
+          "contributors_url": {
+            "type": "string",
+            "format": "uri",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/contributors"
+            ]
+          },
+          "deployments_url": {
+            "type": "string",
+            "format": "uri",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/deployments"
+            ]
+          },
+          "downloads_url": {
+            "type": "string",
+            "format": "uri",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/downloads"
+            ]
+          },
+          "events_url": {
+            "type": "string",
+            "format": "uri",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/events"
+            ]
+          },
+          "forks_url": {
+            "type": "string",
+            "format": "uri",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/forks"
+            ]
+          },
+          "git_commits_url": {
+            "type": "string",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/git/commits{/sha}"
+            ]
+          },
+          "git_refs_url": {
+            "type": "string",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/git/refs{/sha}"
+            ]
+          },
+          "git_tags_url": {
+            "type": "string",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/git/tags{/sha}"
+            ]
+          },
+          "git_url": {
+            "type": "string",
+            "examples": [
+              "git:github.com/octocat/Hello-World.git"
+            ]
+          },
+          "issue_comment_url": {
+            "type": "string",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/issues/comments{/number}"
+            ]
+          },
+          "issue_events_url": {
+            "type": "string",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/issues/events{/number}"
+            ]
+          },
+          "issues_url": {
+            "type": "string",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/issues{/number}"
+            ]
+          },
+          "keys_url": {
+            "type": "string",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/keys{/key_id}"
+            ]
+          },
+          "labels_url": {
+            "type": "string",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/labels{/name}"
+            ]
+          },
+          "languages_url": {
+            "type": "string",
+            "format": "uri",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/languages"
+            ]
+          },
+          "merges_url": {
+            "type": "string",
+            "format": "uri",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/merges"
+            ]
+          },
+          "milestones_url": {
+            "type": "string",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/milestones{/number}"
+            ]
+          },
+          "notifications_url": {
+            "type": "string",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/notifications{?since,all,participating}"
+            ]
+          },
+          "pulls_url": {
+            "type": "string",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/pulls{/number}"
+            ]
+          },
+          "releases_url": {
+            "type": "string",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/releases{/id}"
+            ]
+          },
+          "ssh_url": {
+            "type": "string",
+            "examples": [
+              "git@github.com:octocat/Hello-World.git"
+            ]
+          },
+          "stargazers_url": {
+            "type": "string",
+            "format": "uri",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/stargazers"
+            ]
+          },
+          "statuses_url": {
+            "type": "string",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/statuses/{sha}"
+            ]
+          },
+          "subscribers_url": {
+            "type": "string",
+            "format": "uri",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/subscribers"
+            ]
+          },
+          "subscription_url": {
+            "type": "string",
+            "format": "uri",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/subscription"
+            ]
+          },
+          "tags_url": {
+            "type": "string",
+            "format": "uri",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/tags"
+            ]
+          },
+          "teams_url": {
+            "type": "string",
+            "format": "uri",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/teams"
+            ]
+          },
+          "trees_url": {
+            "type": "string",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/git/trees{/sha}"
+            ]
+          },
+          "clone_url": {
+            "type": "string",
+            "examples": [
+              "https://github.com/octocat/Hello-World.git"
+            ]
+          },
+          "mirror_url": {
+            "type": [
+              "string",
+              "null"
+            ],
+            "format": "uri",
+            "examples": [
+              "git:git.example.com/octocat/Hello-World"
+            ]
+          },
+          "hooks_url": {
+            "type": "string",
+            "format": "uri",
+            "examples": [
+              "http://api.github.com/repos/octocat/Hello-World/hooks"
+            ]
+          },
+          "svn_url": {
+            "type": "string",
+            "format": "uri",
+            "examples": [
+              "https://svn.github.com/octocat/Hello-World"
+            ]
+          },
+          "homepage": {
+            "type": [
+              "string",
+              "null"
+            ],
+            "format": "uri",
+            "examples": [
+              "https://github.com"
+            ]
+          },
+          "language": {
+            "type": [
+              "string",
+              "null"
+            ]
+          },
+          "forks_count": {
+            "type": "integer",
+            "examples": [
+              9
+            ]
+          },
+          "stargazers_count": {
+            "type": "integer",
+            "examples": [
+              80
+            ]
+          },
+          "watchers_count": {
+            "type": "integer",
+            "examples": [
+              80
+            ]
+          },
+          "size": {
+            "description": "The size of the repository, in kilobytes. Size is calculated hourly. When a repository is initially created, the size is 0.",
+            "type": "integer",
+            "examples": [
+              108
+            ]
+          },
+          "default_branch": {
+            "description": "The default branch of the repository.",
+            "type": "string",
+            "examples": [
+              "master"
+            ]
+          },
+          "open_issues_count": {
+            "type": "integer",
+            "examples": [
+              0
+            ]
+          },
+          "is_template": {
+            "description": "Whether this repository acts as a template that can be used to generate new repositories.",
+            "default": false,
+            "type": "boolean",
+            "examples": [
+              true
+            ]
+          },
+          "topics": {
+            "type": "array",
+            "items": {
+              "type": "string"
+            }
+          },
+          "has_issues": {
+            "description": "Whether issues are enabled.",
+            "default": true,
+            "type": "boolean",
+            "examples": [
+              true
+            ]
+          },
+          "has_projects": {
+            "description": "Whether projects are enabled.",
+            "default": true,
+            "type": "boolean",
+            "examples": [
+              true
+            ]
+          },
+          "has_wiki": {
+            "description": "Whether the wiki is enabled.",
+            "default": true,
+            "type": "boolean",
+            "examples": [
+              true
+            ]
+          },
+          "has_pages": {
+            "type": "boolean"
+          },
+          "has_downloads": {
+            "description": "Whether downloads are enabled.",
+            "default": true,
+            "type": "boolean",
+            "deprecated": true,
+            "examples": [
+              true
+            ]
+          },
+          "has_discussions": {
+            "description": "Whether discussions are enabled.",
+            "default": false,
+            "type": "boolean",
+            "examples": [
+              true
+            ]
+          },
+          "archived": {
+            "description": "Whether the repository is archived.",
+            "default": false,
+            "type": "boolean"
+          },
+          "disabled": {
+            "type": "boolean",
+            "description": "Returns whether or not this repository disabled."
+          },
+          "visibility": {
+            "description": "The repository visibility: public, private, or internal.",
+            "default": "public",
+            "type": "string"
+          },
+          "pushed_at": {
+            "type": [
+              "string",
+              "null"
+            ],
+            "format": "date-time",
+            "examples": [
+              "2011-01-26T19:06:43Z"
+            ]
+          },
+          "created_at": {
+            "type": [
+              "string",
+              "null"
+            ],
+            "format": "date-time",
+            "examples": [
+              "2011-01-26T19:01:12Z"
+            ]
+          },
+          "updated_at": {
+            "type": [
+              "string",
+              "null"
+            ],
+            "format": "date-time",
+            "examples": [
+              "2011-01-26T19:14:43Z"
+            ]
+          },
+          "allow_rebase_merge": {
+            "description": "Whether to allow rebase merges for pull requests.",
+            "default": true,
+            "type": "boolean",
+            "examples": [
+              true
+            ]
+          },
+          "temp_clone_token": {
+            "type": "string"
+          },
+          "allow_squash_merge": {
+            "description": "Whether to allow squash merges for pull requests.",
+            "default": true,
+            "type": "boolean",
+            "examples": [
+              true
+            ]
+          },
+          "allow_auto_merge": {
+            "description": "Whether to allow Auto-merge to be used on pull requests.",
+            "default": false,
+            "type": "boolean",
+            "examples": [
+              false
+            ]
+          },
+          "delete_branch_on_merge": {
+            "description": "Whether to delete head branches when pull requests are merged",
+            "default": false,
+            "type": "boolean",
+            "examples": [
+              false
+            ]
+          },
+          "allow_update_branch": {
+            "description": "Whether or not a pull request head branch that is behind its base branch can always be updated even if it is not required to be up to date before merging.",
+            "default": false,
+            "type": "boolean",
+            "examples": [
+              false
+            ]
+          },
+          "use_squash_pr_title_as_default": {
+            "type": "boolean",
+            "description": "Whether a squash merge commit can use the pull request title as default. **This property has been deprecated. Please use `squash_merge_commit_title` instead.",
+            "default": false,
+            "deprecated": true
+          },
+          "squash_merge_commit_title": {
+            "type": "string",
+            "enum": [
+              "PR_TITLE",
+              "COMMIT_OR_PR_TITLE"
+            ],
+            "description": "The default value for a squash merge commit title:\n\n- `PR_TITLE` - default to the pull request's title.\n- `COMMIT_OR_PR_TITLE` - default to the commit's title (if only one commit) or the pull request's title (when more than one commit)."
+          },
+          "squash_merge_commit_message": {
+            "type": "string",
+            "enum": [
+              "PR_BODY",
+              "COMMIT_MESSAGES",
+              "BLANK"
+            ],
+            "description": "The default value for a squash merge commit message:\n\n- `PR_BODY` - default to the pull request's body.\n- `COMMIT_MESSAGES` - default to the branch's commit messages.\n- `BLANK` - default to a blank commit message."
+          },
+          "merge_commit_title": {
+            "type": "string",
+            "enum": [
+              "PR_TITLE",
+              "MERGE_MESSAGE"
+            ],
+            "description": "The default value for a merge commit title.\n\n- `PR_TITLE` - default to the pull request's title.\n- `MERGE_MESSAGE` - default to the classic title for a merge message (e.g., Merge pull request #123 from branch-name)."
+          },
+          "merge_commit_message": {
+            "type": "string",
+            "enum": [
+              "PR_BODY",
+              "PR_TITLE",
+              "BLANK"
+            ],
+            "description": "The default value for a merge commit message.\n\n- `PR_TITLE` - default to the pull request's title.\n- `PR_BODY` - default to the pull request's body.\n- `BLANK` - default to a blank commit message."
+          },
+          "allow_merge_commit": {
+            "description": "Whether to allow merge commits for pull requests.",
+            "default": true,
+            "type": "boolean",
+            "examples": [
+              true
+            ]
+          },
+          "allow_forking": {
+            "description": "Whether to allow forking this repo",
+            "type": "boolean"
+          },
+          "web_commit_signoff_required": {
+            "description": "Whether to require contributors to sign off on web-based commits",
+            "default": false,
+            "type": "boolean"
+          },
+          "open_issues": {
+            "type": "integer"
+          },
+          "watchers": {
+            "type": "integer"
+          },
+          "master_branch": {
+            "type": "string"
+          },
+          "starred_at": {
+            "type": "string",
+            "examples": [
+              "\"2020-07-09T00:17:42Z\""
+            ]
+          },
+          "anonymous_access_enabled": {
+            "type": "boolean",
+            "description": "Whether anonymous git access is enabled for this repository"
+          }
+        },
+        "required": [
+          "archive_url",
+          "assignees_url",
+          "blobs_url",
+          "branches_url",
+          "collaborators_url",
+          "comments_url",
+          "commits_url",
+          "compare_url",
+          "contents_url",
+          "contributors_url",
+          "deployments_url",
+          "description",
+          "downloads_url",
+          "events_url",
+          "fork",
+          "forks_url",
+          "full_name",
+          "git_commits_url",
+          "git_refs_url",
+          "git_tags_url",
+          "hooks_url",
+          "html_url",
+          "id",
+          "node_id",
+          "issue_comment_url",
+          "issue_events_url",
+          "issues_url",
+          "keys_url",
+          "labels_url",
+          "languages_url",
+          "merges_url",
+          "milestones_url",
+          "name",
+          "notifications_url",
+          "owner",
+          "private",
+          "pulls_url",
+          "releases_url",
+          "stargazers_url",
+          "statuses_url",
+          "subscribers_url",
+          "subscription_url",
+          "tags_url",
+          "teams_url",
+          "trees_url",
+          "url",
+          "clone_url",
+          "default_branch",
+          "forks",
+          "forks_count",
+          "git_url",
+          "has_downloads",
+          "has_issues",
+          "has_projects",
+          "has_wiki",
+          "has_pages",
+          "homepage",
+          "language",
+          "archived",
+          "disabled",
+          "mirror_url",
+          "open_issues",
+          "open_issues_count",
+          "license",
+          "pushed_at",
+          "size",
+          "ssh_url",
+          "stargazers_count",
+          "svn_url",
+          "watchers",
+          "watchers_count",
+          "created_at",
+          "updated_at"
+        ]
+      }
+    },
+    "single_file": {
+      "type": [
+        "string",
+        "null"
+      ],
+      "examples": [
+        "config.yaml"
+      ]
+    },
+    "repository_selection": {
+      "description": "Describe whether all repositories have been selected or there's a selection involved",
+      "type": "string",
+      "enum": [
+        "all",
+        "selected"
+      ]
+    }
+  },
+  "required": [
+    "token",
+    "expires_at"
+  ]
+}
+
 # REPLACE "v0.25.2" with the version you wish to deploy
 kubectl create -f https://github.com/actions/actions-runner-controller/releases/download/v0.25.2/actions-runner-controller.yaml
 
@@ -818,7 +1942,494 @@ spec:
         # like firecracker and kata. Basically they run containers within dedicated micro vms and so
         # it's more like you can use `privileged: true` safer with those runtimes.
         #
-        # privileged: true      
+        # privileged: true
+
+kind: RunnerDeployment
+spec:
+  template:
+    spec:
+      dockerVolumeMounts:
+        - mountPath: /var/lib/docker
+          name: docker
+      volumeMounts:
+        - mountPath: /tmp
+          name: tmp
+      volumes:
+        - name: docker
+          emptyDir:
+            medium: Memory
+        - name: work # this volume gets automatically used up for the workdir
+          emptyDir:
+            medium: Memory
+        - name: tmp
+          emptyDir:
+            medium: Memory
+      ephemeral: true # recommended to not leak data between builds.
+NVME SSD
+
+In this example we provide NVME backed storage for the workdir, docker sidecar and /tmp within the runner. Here we use a working example on GKE, which will provide the NVME disk at /mnt/disks/ssd0. We will be placing the respective volumes in subdirs here and in order to be able to run multiple runners we will use the pod name as a prefix for subdirectories. Also the disk will fill up over time and disk space will not be freed until the node is removed.
+
+Beware that running these persistent backend volumes leave data behind between 2 different jobs on the workdir and /tmp with ephemeral: false.
+
+kind: RunnerDeployment
+spec:
+  template:
+    spec:
+      env:
+      - name: POD_NAME
+        valueFrom:
+          fieldRef:
+            fieldPath: metadata.name
+      dockerVolumeMounts:
+      - mountPath: /var/lib/docker
+        name: docker
+        subPathExpr: $(POD_NAME)-docker
+      - mountPath: /runner/_work
+        name: work
+        subPathExpr: $(POD_NAME)-work
+      volumeMounts:
+      - mountPath: /runner/_work
+        name: work
+        subPathExpr: $(POD_NAME)-work
+      - mountPath: /tmp
+        name: tmp
+        subPathExpr: $(POD_NAME)-tmp
+      dockerEnv:
+      - name: POD_NAME
+        valueFrom:
+          fieldRef:
+            fieldPath: metadata.name
+      volumes:
+      - hostPath:
+          path: /mnt/disks/ssd0
+        name: docker
+      - hostPath:
+          path: /mnt/disks/ssd0
+        name: work
+      - hostPath:
+          path: /mnt/disks/ssd0
+        name: tmp
+      ephemeral: true # VERY important. otherwise data inside the workdir and /tmp is not cleared between builds
+Docker image layers caching
+
+Note: Ensure that the volume mount is added to the container that is running the Docker daemon.
+docker stores pulled and built image layers in the daemon's (not client) local storage area which is usually at /var/lib/docker.
+
+By leveraging RunnerSet's dynamic PV provisioning feature and your CSI driver, you can let ARC maintain a pool of PVs that are reused across runner pods to retain /var/lib/docker.
+
+Be sure to add the volume mount to the container that is supposed to run the docker daemon.
+
+Be sure to trigger several workflow runs before checking if the cache is effective. ARC requires an Available PV to be reused for the new runner pod, and a PV becomes Available only after some time after the previous runner pod that was using the PV terminated. See the related discussion.
+
+By default, ARC creates a sidecar container named docker within the runner pod for running the docker daemon. In that case, it's where you need the volume mount so that the manifest looks like:
+
+kind: RunnerSet
+metadata:
+  name: example
+spec:
+  template:
+    spec:
+      containers:
+      - name: docker
+        volumeMounts:
+        - name: var-lib-docker
+          mountPath: /var/lib/docker
+  volumeClaimTemplates:
+  - metadata:
+      name: var-lib-docker
+    spec:
+      accessModes:
+      - ReadWriteOnce
+      resources:
+        requests:
+          storage: 10Mi
+      storageClassName: var-lib-docker
+With dockerdWithinRunnerContainer: true, you need to add the volume mount to the runner container.
+
+Go module and build caching
+
+Go is known to cache builds under $HOME/.cache/go-build and downloaded modules under $HOME/pkg/mod. The module cache dir can be customized by setting GOMOD_CACHE so by setting it to somewhere under $HOME/.cache, we can have a single PV to host both build and module cache, which might improve Go module downloading and building time.
+
+Be sure to trigger several workflow runs before checking if the cache is effective. ARC requires an Available PV to be reused for the new runner pod, and a PV becomes Available only after some time after the previous runner pod that was using the PV terminated. See the related discussion.
+
+kind: RunnerSet
+metadata:
+  name: example
+spec:
+  template:
+    spec:
+      containers:
+      - name: runner
+        env:
+        - name: GOMODCACHE
+          value: "/home/runner/.cache/go-mod"
+        volumeMounts:
+        - name: cache
+          mountPath: "/home/runner/.cache"
+  volumeClaimTemplates:
+  - metadata:
+      name: cache
+    spec:
+      accessModes:
+      - ReadWriteOnce
+      resources:
+        requests:
+          storage: 10Mi
+      storageClassName: cache
+PV-backed runner work directory
+
+ARC works by automatically creating runner pods for running actions/runner and running config.sh which you had to ran manually without ARC.
+
+config.sh is the script provided by actions/runner to pre-configure the runner process before being started. One of the options provided by config.sh is --work, which specifies the working directory where the runner runs your workflow jobs in.
+
+The volume and the partition that hosts the work directory should have several or dozens of GBs free space that might be used by your workflow jobs.
+
+By default, ARC uses /runner/_work as work directory, which is powered by Kubernetes's emptyDir. emptyDir is usually backed by a directory created within a host's volume, somewhere under /var/lib/kuberntes/pods. Therefore your host's volume that is backing /var/lib/kubernetes/pods must have enough free space to serve all the concurrent runner pods that might be deployed onto your host at the same time.
+
+So, in case you see a job failure seemingly due to "disk full", it's very likely you need to reconfigure your host to have more free space.
+
+In case you can't rely on host's volume, consider using RunnerSet and backing the work directory with a ephemeral PV.
+
+Kubernetes 1.23 or greater provides the support for generic ephemeral volumes, which is designed to support this exact use-case. It's defined in the Pod spec API so it isn't currently available for RunnerDeployment. RunnerSet is based on Kubernetes' StatefulSet which mostly embeds the Pod spec under spec.template.spec, so there you go.
+
+kind: RunnerSet
+metadata:
+  name: example
+spec:
+  template:
+    spec:
+      containers:
+      - name: runner
+        volumeMounts:
+        - mountPath: /runner/_work
+          name: work
+      - name: docker
+        volumeMounts:
+        - mountPath: /runner/_work
+          name: work
+      volumes:
+      - name: work
+        ephemeral:
+          volumeClaimTemplate:
+            spec:
+              accessModes: [ "ReadWriteOnce" ]
+              storageClassName: "runner-work-dir"
+              resources:
+                requests:
+                  storage: 10Gi
+jobs:
+  release:
+    runs-on: self-hosted
+When you have multiple kinds of self-hosted runners, you can distinguish between them using labels. In order to do so, you can specify one or more labels in your Runner or RunnerDeployment spec.
+
+apiVersion: actions.summerwind.dev/v1alpha1
+kind: RunnerDeployment
+metadata:
+  name: custom-runner
+spec:
+  replicas: 1
+  template:
+    spec:
+      repository: actions/actions-runner-controller
+      labels:
+        - custom-runner
+Once this spec is applied, you can observe the labels for your runner from the repository or organization in the GitHub settings page for the repository or organization. You can now select a specific runner from your workflow by using the label in runs-on:
+
+jobs:
+  release:
+    runs-on: custom-runner
+
+apiVersion: actions.summerwind.dev/v1alpha1
+kind: RunnerDeployment
+metadata:
+  name: custom-runner
+spec:
+  replicas: 1
+  template:
+    spec:
+      group: NewGroup
+GitHub supports custom visibility in a Runner Group to make it available to a specific set of repositories only. By default if no GitHub authentication is included in the webhook server ARC will be assumed that all runner groups to be usable in all repositories. Currently, GitHub does not include the repository runner group membership information in the workflow_job event (or any webhook). To make the ARC "runner group aware" additional GitHub API calls are needed to find out what runner groups are visible to the webhook's repository. This behaviour will impact your rate-limit budget and so the option needs to be explicitly configured by the end user.
+
+This option will be enabled when proper GitHub authentication options (token, app or basic auth) are provided in the webhook server and useRunnerGroupsVisibility is set to true, e.g.
+
+githubWebhookServer:
+  enabled: false
+  replicaCount: 1
+  useRunnerGroupsVisibility: true
+apiVersion: actions.summerwind.dev/v1alpha1
+kind: RunnerDeployment
+metadata:
+  name: custom-runner
+spec:
+  replicas: 1
+  template:
+    spec:
+      group: NewGroup
+GitHub supports custom visibility in a Runner Group to make it available to a specific set of repositories only. By default if no GitHub authentication is included in the webhook server ARC will be assumed that all runner groups to be usable in all repositories. Currently, GitHub does not include the repository runner group membership information in the workflow_job event (or any webhook). To make the ARC "runner group aware" additional GitHub API calls are needed to find out what runner groups are visible to the webhook's repository. This behaviour will impact your rate-limit budget and so the option needs to be explicitly configured by the end user.
+
+This option will be enabled when proper GitHub authentication options (token, app or basic auth) are provided in the webhook server and useRunnerGroupsVisibility is set to true, e.g.
+
+githubWebhookServer:
+  enabled: false
+  replicaCount: 1
+  useRunnerGroupsVisibility: true
+nodeSelector:
+  kubernetes.io/os: linux
+cert-manager has 4 different application within it the main application, the webhook, the cainjector and the startupapicheck. In the parameters or values file you use for the deployment you need to add the nodeSelector property four times, one for each application.
+
+For the actions-runner-controller you only have to use the nodeSelector only for the main deployment, so it only has to be set once.
+
+Once this is set up, you will need to deploy two different RunnerDeployment's, one for Windows and one for Linux. The Linux deployment can use either the default image or a custom one, however, there isn't a default Windows image so for Windows deployments you will have to build your own image.
+
+Below we share an example of the YAML used to create the deployment for each Operating System and a Dockerfile for the Windows deployment.
+
+Windows
+RunnerDeployment
+
+---
+apiVersion: actions.summerwind.dev/v1alpha1
+kind: RunnerDeployment
+metadata:
+  name: k8s-runners-windows
+  namespace: actions-runner-system
+spec:
+  template:
+    spec:
+      image: <repo>/<image>:<windows-tag>
+      dockerdWithinRunnerContainer: true
+      nodeSelector:
+        kubernetes.io/os: windows
+        kubernetes.io/arch: amd64
+      repository: <owner>/<repo>
+      labels:
+        - windows
+        - X64
+Dockerfile
+
+Note that you'd need to patch the below Dockerfile if you need a graceful termination. See https://github.com/actions/actions-runner-controller/pull/1608/files#r917319574 for more information.
+FROM mcr.microsoft.com/windows/servercore:ltsc2019
+
+WORKDIR /actions-runner
+
+SHELL ["powershell", "-Command", "$ErrorActionPreference = 'Stop';$ProgressPreference='silentlyContinue';"]
+
+RUN Invoke-WebRequest -Uri https://github.com/actions/runner/releases/download/v2.292.0/actions-runner-win-x64-2.292.0.zip -OutFile actions-runner-win-x64-2.292.0.zip
+
+RUN if((Get-FileHash -Path actions-runner-win-x64-2.292.0.zip -Algorithm SHA256).Hash.ToUpper() -ne 'f27dae1413263e43f7416d719e0baf338c8d80a366fed849ecf5fffcec1e941f'.ToUpper()){ throw 'Computed checksum did not match' }
+
+RUN Add-Type -AssemblyName System.IO.Compression.FileSystem ; [System.IO.Compression.ZipFile]::ExtractToDirectory('actions-runner-win-x64-2.292.0.zip', $PWD)
+
+RUN Invoke-WebRequest -Uri 'https://aka.ms/install-powershell.ps1' -OutFile install-powershell.ps1; ./install-powershell.ps1 -AddToPath
+
+RUN powershell Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
+
+RUN powershell choco install git.install --params "'/GitAndUnixToolsOnPath'" -y
+
+RUN powershell choco feature enable -n allowGlobalConfirmation
+
+CMD [ "pwsh", "-c", "./config.cmd --name $env:RUNNER_NAME --url https://github.com/$env:RUNNER_REPO --token $env:RUNNER_TOKEN --labels $env:RUNNER_LABELS --unattended --replace --ephemeral; ./run.cmd"]
+Linux
+RunnerDeployment
+
+---
+apiVersion: actions.summerwind.dev/v1alpha1
+kind: RunnerDeployment
+metadata:
+  name: k8s-runners-linux
+  namespace: actions-runner-system
+spec:
+  template:
+    spec:
+      image: <repo>/<image>:<linux-tag>
+      nodeSelector:
+        kubernetes.io/os: linux
+        kubernetes.io/arch: amd64
+      repository: <owner>:<repo>
+      labels:
+        - linux
+        - X64
+
+kind: Secret
+data:
+  github_app_id: ...
+  github_app_installation_id: ...
+  github_app_private_key: ...
+---
+kind: RunnerDeployment
+metadata:
+  namespace: org1-runners
+spec:
+  template:
+    spec:
+      githubAPICredentialsFrom:
+        secretRef:
+          name: org1-github-app
+---
+kind: HorizontalRunnerAutoscaler
+metadata:
+  namespace: org1-runners
+spec:
+  githubAPICredentialsFrom:
+    secretRef:
+      name: org1-github-app
+apiVersion: actions.summerwind.dev/v1alpha1
+kind: RunnerDeployment
+metadata:
+  name: example-runnerdeployment
+spec:
+  template:
+    spec:
+      env:
+        # Disable various runner entrypoint log levels 
+        - name: LOG_DEBUG_DISABLED
+          value: "true"
+        - name: LOG_NOTICE_DISABLED
+          value: "true"
+        - name: LOG_WARNING_DISABLED
+          value: "true"
+        - name: LOG_ERROR_DISABLED
+          value: "true"
+        - name: LOG_SUCCESS_DISABLED
+          value: "true"
+        # Issues a sleep command at the start of the entrypoint
+        - name: STARTUP_DELAY_IN_SECONDS
+          value: "2"
+        # Specify the duration to wait for the docker daemon to be available
+        # The default duration of 120 seconds is sometimes too short
+        # to reliably wait for the docker daemon to start
+        # See https://github.com/actions/actions-runner-controller/issues/1804
+        - name: WAIT_FOR_DOCKER_SECONDS
+          value: 120
+        # Disables the wait for the docker daemon to be available check
+        - name: DISABLE_WAIT_FOR_DOCKER
+          value: "true"
+        # Disables automatic runner updates
+        # WARNING : Upon a new version of the actions/runner software being released 
+        # GitHub stops allocating jobs to runners on the previous version of the
+        # actions/runner software after 30 days.
+        - name: DISABLE_RUNNER_UPDATE
+          value: "true"
+There are a few advanced envvars also that are available only for dind runners:
+
+apiVersion: actions.summerwind.dev/v1alpha1
+kind: RunnerDeployment
+metadata:
+  name: example-runnerdeployment
+spec:
+  template:
+    spec:
+      dockerdWithinRunnerContainer: true
+      image: summerwind/actions-runner-dind
+      env:
+        # Sets the respective default-address-pools fields within dockerd daemon.json
+        # See https://github.com/actions/actions-runner-controller/pull/1971 for more information.
+        # Also see https://github.com/docker/docs/issues/8663 for the default base/size values in dockerd.
+        - name: DOCKER_DEFAULT_ADDRESS_POOL_BASE
+          value: "172.17.0.0/12"
+        - name: DOCKER_DEFAULT_ADDRESS_POOL_SIZE
+          value: "24"
+More options can be configured by mounting a configmap to the daemon.json location:
+
+rootless: /home/runner/.config/docker/daemon.json
+rootful: /etc/docker/daemon.json
+apiVersion: actions.summerwind.dev/v1alpha1
+kind: RunnerDeployment
+metadata:
+  name: example-runnerdeployment
+spec:
+  template:
+    spec:
+      dockerdWithinRunnerContainer: true
+      image: summerwind/actions-runner-dind(-rootless)
+      volumeMounts:
+        - mountPath: /home/runner/.config/docker/daemon.json
+          name: daemon-config-volume
+          subPath: daemon.json
+      volumes:
+        - name: daemon-config-volume
+          configMap:
+            name: daemon-cm
+            items:
+              - key: daemon.json
+                path: daemon.json
+      securityContext:
+        fsGroup: 1001 # runner user id
+apiVersion: v1
+kind: ConfigMap
+metadata:
+  name: daemon-cm
+data:
+  daemon.json: |
+    {
+      "log-level": "warn",
+      "dns": ["x.x.x.x"]
+    }
+# dindrunnerdeployment.yaml
+apiVersion: actions.summerwind.dev/v1alpha1
+kind: RunnerDeployment
+metadata:
+  name: example-dindrunnerdeploy
+spec:
+  replicas: 1
+  template:
+    spec:
+      image: summerwind/actions-runner-dind
+      dockerdWithinRunnerContainer: true
+      repository: mumoshu/actions-runner-controller-ci
+      env: []
+Runner with rootless DinD
+
+When using the DinD runner, it assumes that the main runner is rootful, which can be problematic in a regulated or more security-conscious environment, such as co-tenanting across enterprise projects. The actions-runner-dind-rootless image runs rootless Docker inside the container as runner user. Note that this user does not have sudo access, so anything requiring admin privileges must be built into the runner's base image (like running apt to install additional software).
+
+Runner with K8s Jobs
+
+When using the default runner, jobs that use a container will run in docker. This necessitates privileged mode, either on the runner pod or the sidecar container
+
+By setting the container mode, you can instead invoke these jobs using a kubernetes implementation while not executing in privileged mode.
+
+The runner will dynamically spin up pods and k8s jobs in the runner's namespace to run the workflow, so a workVolumeClaimTemplate is required for the runner's working directory, and a service account with the appropriate permissions.
+
+There are some limitations to this approach, mainly job containers are required on all workflows.
+
+# runner.yaml
+apiVersion: actions.summerwind.dev/v1alpha1
+kind: Runner
+metadata:
+  name: example-runner
+spec:
+  repository: example/myrepo
+  containerMode: kubernetes
+  serviceAccountName: my-service-account
+  workVolumeClaimTemplate:
+    storageClassName: "my-dynamic-storage-class"
+    accessModes:
+    - ReadWriteOnce
+    resources:
+      requests:
+        storage: 10Gi
+  env: []
+
+metrics:
+  serviceAnnotations: {}
+  serviceMonitor: false
+  serviceMonitorLabels: {}
++ port: 8080
+  proxy:
++   enabled: false
+If Prometheus is available inside the cluster, then add some podAnnotations to begin scraping the metrics:
+
+podAnnotations:
++ prometheus.io/scrape: "true"
++ prometheus.io/path: /metrics
++ prometheus.io/port: "8080"
+
+
+
+
+
+
+
+     
       
     import ngrok


curl -L \
  -X POST \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <LLBF3JGZDX3P5PMEXLND6TS6FCWO6>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/repos/OWNER/REPO/actions/runners/registration-token
./config.sh --url https://github.com/octo-org --token TOKEN
{
  "token": "LLBF3JGZDX3P5PMEXLND6TS6FCWO6",
  "expires_at": "2020-01-22T12:13:35.123-08:00"
}curl -L \
  -X POST \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <LLBF3JGZDX3P5PMEXLND6TS6FCWO6>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/repos/OWNER/REPO/actions/runners/generate-jitconfig \
  -d '{"name":"New runner","runner_group_id":1,"labels":["self-hosted","X64","macOS","no-gpu"],"work_folder":"_work"}'
  
curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <LLBF3JGZDX3P5PMEXLND6TS6FCWO6>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/orgs/ORG/actions/runners
curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <LLBF3JGZDX3P5PMEXLND6TS6FCWO6>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/orgs/ORG/actions/runners/downloads
curl -L \
  -X POST \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <LLBF3JGZDX3P5PMEXLND6TS6FCWO6>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/orgs/ORG/actions/runners/generate-jitconfig \
  -d '{"name":"New runner","runner_group_id":1,"labels":["self-hosted","X64","macOS","no-gpu"],"work_folder":"_work"}'
curl -L \
  -X POST \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <LLBF3JGZDX3P5PMEXLND6TS6FCWO6>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/orgs/ORG/actions/runners/registration-token
{
  "token": "LLBF3JGZDX3P5PMEXLND6TS6FCWO6",
  "expires_at": "2020-01-22T12:13:35.123-08:00"
}
curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <LLBF3JGZDX3P5PMEXLND6TS6FCWO6>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/orgs/ORG/actions/runners/RUNNER_ID

  curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <LLBF3JGZDX3P5PMEXLND6TS6FCWO6>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/orgs/ORG/actions/runners/RUNNER_ID/labels
curl -L \
  -X POST \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <LLBF3JGZDX3P5PMEXLND6TS6FCWO6>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/orgs/ORG/actions/runners/RUNNER_ID/labels \
  -d '{"labels":["gpu","accelerated"]}'
  curl -L \
  -X PUT \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <LLBF3JGZDX3P5PMEXLND6TS6FCWO6>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/orgs/ORG/actions/runners/RUNNER_ID/labels \
  -d '{"labels":["gpu","accelerated"]}'
curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <LLBF3JGZDX3P5PMEXLND6TS6FCWO6-TOKEN>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/repos/OWNER/REPO/actions/runners
curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <LLBF3JGZDX3P5PMEXLND6TS6FCWO6>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/repos/OWNER/REPO/actions/runners/downloads

  curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <LLBF3JGZDX3P5PMEXLND6TS6FCWO6>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/repos/OWNER/REPO/actions/runners/RUNNER_ID
  curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <LLBF3JGZDX3P5PMEXLND6TS6FCWO6>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/repos/OWNER/REPO/actions/runners/RUNNER_ID/labels
  curl -L \
  -X POST \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <LLBF3JGZDX3P5PMEXLND6TS6FCWO6>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/repos/OWNER/REPO/actions/runners/RUNNER_ID/labels \
  -d '{"labels":["gpu","accelerated"]}'
  
  curl -L \
  -X PUT \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <LLBF3JGZDX3P5PMEXLND6TS6FCWO6>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/repos/OWNER/REPO/actions/runners/RUNNER_ID/labels \
  -d '{"labels":["gpu","accelerated"]}'
  
  [
  {
    "os": "osx",
    "architecture": "x64",
    "download_url": "https://github.com/actions/runner/releases/download/v2.164.0/actions-runner-osx-x64-2.164.0.tar.gz",
    "filename": "actions-runner-osx-x64-2.164.0.tar.gz"
  },
  {
    "os": "linux",
    "architecture": "x64",
    "download_url": "https://github.com/actions/runner/releases/download/v2.164.0/actions-runner-linux-x64-2.164.0.tar.gz",
    "filename": "actions-runner-linux-x64-2.164.0.tar.gz"
  },
  {
    "os": "linux",
    "architecture": "arm",
    "download_url": "https://github.com/actions/runner/releases/download/v2.164.0/actions-runner-linux-arm-2.164.0.tar.gz",
    "filename": "actions-runner-linux-arm-2.164.0.tar.gz"
  },
  {
    "os": "win",
    "architecture": "x64",
    "download_url": "https://github.com/actions/runner/releases/download/v2.164.0/actions-runner-win-x64-2.164.0.zip",
    "filename": "actions-runner-win-x64-2.164.0.zip"
  },
  {
    "os": "linux",
    "architecture": "arm64",
    "download_url": "https://github.com/actions/runner/releases/download/v2.164.0/actions-runner-linux-arm64-2.164.0.tar.gz",
    "filename": "actions-runner-linux-arm64-2.164.0.tar.gz"
  }
]  
  "title": "Authentication Token",
  "description": "Authentication Token",
  "type": "object",
  "properties": {
    "token": {
      "description": "The token used for authentication",
      "type": "string",
      "examples": [
        "v1.1f699f1069f60xxx"
      ]
    },
    "expires_at": {
      "description": "The time this token expires",
      "type": "string",
      "format": "date-time",
      "examples": [
        "2016-07-11T22:14:10Z"
      ]
    },
    "permissions": {
      "type": "object",
      "examples": [
        {
          "issues": "read",
          "deployments": "write"
        }
      ]
    },
    "repositories": {
      "description": "The repositories this token has access to",
      "type": "array",
      "items": {
        "title": "Repository",
        "description": "A repository on GitHub.",
        "type": "object",
        "properties": {
          "id": {
            "description": "Unique identifier of the repository",
            "type": "integer",
            "examples": [
              42
            ]
          },
          "node_id": {
            "type": "string",
            "examples": [
              "MDEwOlJlcG9zaXRvcnkxMjk2MjY5"
            ]
          },
          "name": {
            "description": "The name of the repository.",
            "type": "string",
            "examples": [
              "Team Environment"
            ]
          },
          "full_name": {
            "type": "string",
            "examples": [
              "octocat/Hello-World"
            ]
          },
          "license": {
            "anyOf": [
              {
                "type": "null"
              },
              {
                "title": "License Simple",
                "description": "License Simple",
                "type": "object",
                "properties": {
                  "key": {
                    "type": "string",
                    "examples": [
                      "mit"
                    ]
                  },
                  "name": {
                    "type": "string",
                    "examples": [
                      "MIT License"
                    ]
                  },
                  "url": {
                    "type": [
                      "string",
                      "null"
                    ],
                    "format": "uri",
                    "examples": [
                      "https://api.github.com/licenses/mit"
                    ]
                  },
                  "spdx_id": {
                    "type": [
                      "string",
                      "null"
                    ],
                    "examples": [
                      "MIT"
                    ]
                  },
                  "node_id": {
                    "type": "string",
                    "examples": [
                      "MDc6TGljZW5zZW1pdA=="
                    ]
                  },
                  "html_url": {
                    "type": "string",
                    "format": "uri"
                  }
                },
                "required": [
                  "key",
                  "name",
                  "url",
                  "spdx_id",
                  "node_id"
                ]
              }
            ]
          },
          "forks": {
            "type": "integer"
          },
          "permissions": {
            "type": "object",
            "properties": {
              "admin": {
                "type": "boolean"
              },
              "pull": {
                "type": "boolean"
              },
              "triage": {
                "type": "boolean"
              },
              "push": {
                "type": "boolean"
              },
              "maintain": {
                "type": "boolean"
              }
            },
            "required": [
              "admin",
              "pull",
              "push"
            ]
          },
          "owner": {
            "title": "Simple User",
            "description": "A GitHub user.",
            "type": "object",
            "properties": {
              "name": {
                "type": [
                  "string",
                  "null"
                ]
              },
              "email": {
                "type": [
                  "string",
                  "null"
                ]
              },
              "login": {
                "type": "string",
                "examples": [
                  "octocat"
                ]
              },
              "id": {
                "type": "integer",
                "examples": [
                  1
                ]
              },
              "node_id": {
                "type": "string",
                "examples": [
                  "MDQ6VXNlcjE="
                ]
              },
              "avatar_url": {
                "type": "string",
                "format": "uri",
                "examples": [
                  "https://github.com/images/error/octocat_happy.gif"
                ]
              },
              "gravatar_id": {
                "type": [
                  "string",
                  "null"
                ],
                "examples": [
                  "41d064eb2195891e12d0413f63227ea7"
                ]
              },
              "url": {
                "type": "string",
                "format": "uri",
                "examples": [
                  "https://api.github.com/users/octocat"
                ]
              },
              "html_url": {
                "type": "string",
                "format": "uri",
                "examples": [
                  "https://github.com/octocat"
                ]
              },
              "followers_url": {
                "type": "string",
                "format": "uri",
                "examples": [
                  "https://api.github.com/users/octocat/followers"
                ]
              },
              "following_url": {
                "type": "string",
                "examples": [
                  "https://api.github.com/users/octocat/following{/other_user}"
                ]
              },
              "gists_url": {
                "type": "string",
                "examples": [
                  "https://api.github.com/users/octocat/gists{/gist_id}"
                ]
              },
              "starred_url": {
                "type": "string",
                "examples": [
                  "https://api.github.com/users/octocat/starred{/owner}{/repo}"
                ]
              },
              "subscriptions_url": {
                "type": "string",
                "format": "uri",
                "examples": [
                  "https://api.github.com/users/octocat/subscriptions"
                ]
              },
              "organizations_url": {
                "type": "string",
                "format": "uri",
                "examples": [
                  "https://api.github.com/users/octocat/orgs"
                ]
              },
              "repos_url": {
                "type": "string",
                "format": "uri",
                "examples": [
                  "https://api.github.com/users/octocat/repos"
                ]
              },
              "events_url": {
                "type": "string",
                "examples": [
                  "https://api.github.com/users/octocat/events{/privacy}"
                ]
              },
              "received_events_url": {
                "type": "string",
                "format": "uri",
                "examples": [
                  "https://api.github.com/users/octocat/received_events"
                ]
              },
              "type": {
                "type": "string",
                "examples": [
                  "User"
                ]
              },
              "site_admin": {
                "type": "boolean"
              },
              "starred_at": {
                "type": "string",
                "examples": [
                  "\"2020-07-09T00:17:55Z\""
                ]
              }
            },
            "required": [
              "avatar_url",
              "events_url",
              "followers_url",
              "following_url",
              "gists_url",
              "gravatar_id",
              "html_url",
              "id",
              "node_id",
              "login",
              "organizations_url",
              "received_events_url",
              "repos_url",
              "site_admin",
              "starred_url",
              "subscriptions_url",
              "type",
              "url"
            ]
          },
          "private": {
            "description": "Whether the repository is private or public.",
            "default": false,
            "type": "boolean"
          },
          "html_url": {
            "type": "string",
            "format": "uri",
            "examples": [
              "https://github.com/octocat/Hello-World"
            ]
          },
          "description": {
            "type": [
              "string",
              "null"
            ],
            "examples": [
              "This your first repo!"
            ]
          },
          "fork": {
            "type": "boolean"
          },
          "url": {
            "type": "string",
            "format": "uri",
            "examples": [
              "https://api.github.com/repos/octocat/Hello-World"
            ]
          },
          "archive_url": {
            "type": "string",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/{archive_format}{/ref}"
            ]
          },
          "assignees_url": {
            "type": "string",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/assignees{/user}"
            ]
          },
          "blobs_url": {
            "type": "string",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/git/blobs{/sha}"
            ]
          },
          "branches_url": {
            "type": "string",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/branches{/branch}"
            ]
          },
          "collaborators_url": {
            "type": "string",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/collaborators{/collaborator}"
            ]
          },
          "comments_url": {
            "type": "string",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/comments{/number}"
            ]
          },
          "commits_url": {
            "type": "string",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/commits{/sha}"
            ]
          },
          "compare_url": {
            "type": "string",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/compare/{base}...{head}"
            ]
          },
          "contents_url": {
            "type": "string",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/contents/{+path}"
            ]
          },
          "contributors_url": {
            "type": "string",
            "format": "uri",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/contributors"
            ]
          },
          "deployments_url": {
            "type": "string",
            "format": "uri",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/deployments"
            ]
          },
          "downloads_url": {
            "type": "string",
            "format": "uri",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/downloads"
            ]
          },
          "events_url": {
            "type": "string",
            "format": "uri",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/events"
            ]
          },
          "forks_url": {
            "type": "string",
            "format": "uri",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/forks"
            ]
          },
          "git_commits_url": {
            "type": "string",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/git/commits{/sha}"
            ]
          },
          "git_refs_url": {
            "type": "string",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/git/refs{/sha}"
            ]
          },
          "git_tags_url": {
            "type": "string",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/git/tags{/sha}"
            ]
          },
          "git_url": {
            "type": "string",
            "examples": [
              "git:github.com/octocat/Hello-World.git"
            ]
          },
          "issue_comment_url": {
            "type": "string",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/issues/comments{/number}"
            ]
          },
          "issue_events_url": {
            "type": "string",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/issues/events{/number}"
            ]
          },
          "issues_url": {
            "type": "string",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/issues{/number}"
            ]
          },
          "keys_url": {
            "type": "string",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/keys{/key_id}"
            ]
          },
          "labels_url": {
            "type": "string",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/labels{/name}"
            ]
          },
          "languages_url": {
            "type": "string",
            "format": "uri",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/languages"
            ]
          },
          "merges_url": {
            "type": "string",
            "format": "uri",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/merges"
            ]
          },
          "milestones_url": {
            "type": "string",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/milestones{/number}"
            ]
          },
          "notifications_url": {
            "type": "string",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/notifications{?since,all,participating}"
            ]
          },
          "pulls_url": {
            "type": "string",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/pulls{/number}"
            ]
          },
          "releases_url": {
            "type": "string",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/releases{/id}"
            ]
          },
          "ssh_url": {
            "type": "string",
            "examples": [
              "git@github.com:octocat/Hello-World.git"
            ]
          },
          "stargazers_url": {
            "type": "string",
            "format": "uri",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/stargazers"
            ]
          },
          "statuses_url": {
            "type": "string",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/statuses/{sha}"
            ]
          },
          "subscribers_url": {
            "type": "string",
            "format": "uri",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/subscribers"
            ]
          },
          "subscription_url": {
            "type": "string",
            "format": "uri",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/subscription"
            ]
          },
          "tags_url": {
            "type": "string",
            "format": "uri",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/tags"
            ]
          },
          "teams_url": {
            "type": "string",
            "format": "uri",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/teams"
            ]
          },
          "trees_url": {
            "type": "string",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/git/trees{/sha}"
            ]
          },
          "clone_url": {
            "type": "string",
            "examples": [
              "https://github.com/octocat/Hello-World.git"
            ]
          },
          "mirror_url": {
            "type": [
              "string",
              "null"
            ],
            "format": "uri",
            "examples": [
              "git:git.example.com/octocat/Hello-World"
            ]
          },
          "hooks_url": {
            "type": "string",
            "format": "uri",
            "examples": [
              "http://api.github.com/repos/octocat/Hello-World/hooks"
            ]
          },
          "svn_url": {
            "type": "string",
            "format": "uri",
            "examples": [
              "https://svn.github.com/octocat/Hello-World"
            ]
          },
          "homepage": {
            "type": [
              "string",
              "null"
            ],
            "format": "uri",
            "examples": [
              "https://github.com"
            ]
          },
          "language": {
            "type": [
              "string",
              "null"
            ]
          },
          "forks_count": {
            "type": "integer",
            "examples": [
              9
            ]
          },
          "stargazers_count": {
            "type": "integer",
            "examples": [
              80
            ]
          },
          "watchers_count": {
            "type": "integer",
            "examples": [
              80
            ]
          },
          "size": {
            "description": "The size of the repository, in kilobytes. Size is calculated hourly. When a repository is initially created, the size is 0.",
            "type": "integer",
            "examples": [
              108
            ]
          },
          "default_branch": {
            "description": "The default branch of the repository.",
            "type": "string",
            "examples": [
              "master"
            ]
          },
          "open_issues_count": {
            "type": "integer",
            "examples": [
              0
            ]
          },
          "is_template": {
            "description": "Whether this repository acts as a template that can be used to generate new repositories.",
            "default": false,
            "type": "boolean",
            "examples": [
              true
            ]
          },
          "topics": {
            "type": "array",
            "items": {
              "type": "string"
            }
          },
          "has_issues": {
            "description": "Whether issues are enabled.",
            "default": true,
            "type": "boolean",
            "examples": [
              true
            ]
          },
          "has_projects": {
            "description": "Whether projects are enabled.",
            "default": true,
            "type": "boolean",
            "examples": [
              true
            ]
          },
          "has_wiki": {
            "description": "Whether the wiki is enabled.",
            "default": true,
            "type": "boolean",
            "examples": [
              true
            ]
          },
          "has_pages": {
            "type": "boolean"
          },
          "has_downloads": {
            "description": "Whether downloads are enabled.",
            "default": true,
            "type": "boolean",
            "deprecated": true,
            "examples": [
              true
            ]
          },
          "has_discussions": {
            "description": "Whether discussions are enabled.",
            "default": false,
            "type": "boolean",
            "examples": [
              true
            ]
          },
          "archived": {
            "description": "Whether the repository is archived.",
            "default": false,
            "type": "boolean"
          },
          "disabled": {
            "type": "boolean",
            "description": "Returns whether or not this repository disabled."
          },
          "visibility": {
            "description": "The repository visibility: public, private, or internal.",
            "default": "public",
            "type": "string"
          },
          "pushed_at": {
            "type": [
              "string",
              "null"
            ],
            "format": "date-time",
            "examples": [
              "2011-01-26T19:06:43Z"
            ]
          },
          "created_at": {
            "type": [
              "string",
              "null"
            ],
            "format": "date-time",
            "examples": [
              "2011-01-26T19:01:12Z"
            ]
          },
          "updated_at": {
            "type": [
              "string",
              "null"
            ],
            "format": "date-time",
            "examples": [
              "2011-01-26T19:14:43Z"
            ]
          },
          "allow_rebase_merge": {
            "description": "Whether to allow rebase merges for pull requests.",
            "default": true,
            "type": "boolean",
            "examples": [
              true
            ]
          },
          "temp_clone_token": {
            "type": "string"
          },
          "allow_squash_merge": {
            "description": "Whether to allow squash merges for pull requests.",
            "default": true,
            "type": "boolean",
            "examples": [
              true
            ]
          },
          "allow_auto_merge": {
            "description": "Whether to allow Auto-merge to be used on pull requests.",
            "default": false,
            "type": "boolean",
            "examples": [
              false
            ]
          },
          "delete_branch_on_merge": {
            "description": "Whether to delete head branches when pull requests are merged",
            "default": false,
            "type": "boolean",
            "examples": [
              false
            ]
          },
          "allow_update_branch": {
            "description": "Whether or not a pull request head branch that is behind its base branch can always be updated even if it is not required to be up to date before merging.",
            "default": false,
            "type": "boolean",
            "examples": [
              false
            ]
          },
          "use_squash_pr_title_as_default": {
            "type": "boolean",
            "description": "Whether a squash merge commit can use the pull request title as default. **This property has been deprecated. Please use `squash_merge_commit_title` instead.",
            "default": false,
            "deprecated": true
          },
          "squash_merge_commit_title": {
            "type": "string",
            "enum": [
              "PR_TITLE",
              "COMMIT_OR_PR_TITLE"
            ],
            "description": "The default value for a squash merge commit title:\n\n- `PR_TITLE` - default to the pull request's title.\n- `COMMIT_OR_PR_TITLE` - default to the commit's title (if only one commit) or the pull request's title (when more than one commit)."
          },
          "squash_merge_commit_message": {
            "type": "string",
            "enum": [
              "PR_BODY",
              "COMMIT_MESSAGES",
              "BLANK"
            ],
            "description": "The default value for a squash merge commit message:\n\n- `PR_BODY` - default to the pull request's body.\n- `COMMIT_MESSAGES` - default to the branch's commit messages.\n- `BLANK` - default to a blank commit message."
          },
          "merge_commit_title": {
            "type": "string",
            "enum": [
              "PR_TITLE",
              "MERGE_MESSAGE"
            ],
            "description": "The default value for a merge commit title.\n\n- `PR_TITLE` - default to the pull request's title.\n- `MERGE_MESSAGE` - default to the classic title for a merge message (e.g., Merge pull request #123 from branch-name)."
          },
          "merge_commit_message": {
            "type": "string",
            "enum": [
              "PR_BODY",
              "PR_TITLE",
              "BLANK"
            ],
            "description": "The default value for a merge commit message.\n\n- `PR_TITLE` - default to the pull request's title.\n- `PR_BODY` - default to the pull request's body.\n- `BLANK` - default to a blank commit message."
          },
          "allow_merge_commit": {
            "description": "Whether to allow merge commits for pull requests.",
            "default": true,
            "type": "boolean",
            "examples": [
              true
            ]
          },
          "allow_forking": {
            "description": "Whether to allow forking this repo",
            "type": "boolean"
          },
          "web_commit_signoff_required": {
            "description": "Whether to require contributors to sign off on web-based commits",
            "default": false,
            "type": "boolean"
          },
          "open_issues": {
            "type": "integer"
          },
          "watchers": {
            "type": "integer"
          },
          "master_branch": {
            "type": "string"
          },
          "starred_at": {
            "type": "string",
            "examples": [
              "\"2020-07-09T00:17:42Z\""
            ]
          },
          "anonymous_access_enabled": {
            "type": "boolean",
            "description": "Whether anonymous git access is enabled for this repository"
          }
        },
        "required": [
          "archive_url",
          "assignees_url",
          "blobs_url",
          "branches_url",
          "collaborators_url",
          "comments_url",
          "commits_url",
          "compare_url",
          "contents_url",
          "contributors_url",
          "deployments_url",
          "description",
          "downloads_url",
          "events_url",
          "fork",
          "forks_url",
          "full_name",
          "git_commits_url",
          "git_refs_url",
          "git_tags_url",
          "hooks_url",
          "html_url",
          "id",
          "node_id",
          "issue_comment_url",
          "issue_events_url",
          "issues_url",
          "keys_url",
          "labels_url",
          "languages_url",
          "merges_url",
          "milestones_url",
          "name",
          "notifications_url",
          "owner",
          "private",
          "pulls_url",
          "releases_url",
          "stargazers_url",
          "statuses_url",
          "subscribers_url",
          "subscription_url",
          "tags_url",
          "teams_url",
          "trees_url",
          "url",
          "clone_url",
          "default_branch",
          "forks",
          "forks_count",
          "git_url",
          "has_downloads",
          "has_issues",
          "has_projects",
          "has_wiki",
          "has_pages",
          "homepage",
          "language",
          "archived",
          "disabled",
          "mirror_url",
          "open_issues",
          "open_issues_count",
          "license",
          "pushed_at",
          "size",
          "ssh_url",
          "stargazers_count",
          "svn_url",
          "watchers",
          "watchers_count",
          "created_at",
          "updated_at"
        ]
      }
    },
    "single_file": {
      "type": [
        "string",
        "null"
      ],
      "examples": [
        "config.yaml"
      ]
    },
    "repository_selection": {
      "description": "Describe whether all repositories have been selected or there's a selection involved",
      "type": "string",
      "enum": [
        "all",
        "selected"
      ]
    }
  },
  "required": [
    "token",
    "expires_at"
  ]
}

# REPLACE "v0.25.2" with the version you wish to deploy
kubectl create -f https://github.com/actions/actions-runner-controller/releases/download/v0.25.2/actions-runner-controller.yaml

helm repo add actions-runner-controller https://actions-runner-controller.github.io/actions-runner-controller
helm upgrade --install --namespace actions-runner-system --create-namespace \
             --wait actions-runner-controller actions-runner-controller/actions-runner-controller
$ kubectl create secret generic controller-manager \
    -n actions-runner-system \
    --from-literal=github_app_id=${APP_ID} \
    --from-literal=github_app_installation_id=${INSTALLATION_ID} \
    --from-file=github_app_private_key=${PRIVATE_KEY_FILE_PATH}
      kubectl create secret generic controller-manager \
    -n actions-runner-system \
    --from-literal=github_token=${BHAHZGCJZK3BEVS7IRGZMKDF6USLO /  GitHub Runner tokens :
    / BHAHZGDHHICG3LFF53OICRLF6UR24}
    $ kubectl create secret tls actions-runner-controller-serving-cert \
  -n actions-runner-system \
  --cert=path/to/cert/file \
  --key=path/to/key/file

$ CA_BUNDLE=$(cat path/to/ca.pem | base64)
$ helm upgrade --install actions-runner-controller/actions-runner-controller \
  certManagerEnabled=false \
  admissionWebHooks.caBundle=${CA_BUNDLE}
$ helm upgrade --install actions-runner-controller/actions-runner-controller \
  certManagerEnabled=false

apiVersion: actions.summerwind.dev/v1alpha1
kind: RunnerDeployment
metadata:
  name: example-runnerdeploy
spec:
  template:
    spec:
      repository: USER/REO
      serviceAccountName: my-service-account
      securityContext:
        # For Ubuntu 20.04 runner
        fsGroup: 1000
        # Use 1001 for Ubuntu 22.04 runner
        #fsGroup: 1001
# runnerdeployment.yaml
apiVersion: actions.summerwind.dev/v1alpha1
kind: RunnerDeployment
metadata:
  name: example-runnerdeploy
spec:
  # This will deploy 2 runners now
  replicas: 2
  template:
    spec:
      repository: mumoshu/actions-runner-controller-ci
$ kubectl apply -f runnerdeployment.yaml
runnerdeployment.actions.summerwind.dev/example-runnerdeploy created
You can see that 2 runners have been created as specified by replicas: 2:

$ kubectl get runners
NAME                             REPOSITORY                             STATUS
example-runnerdeploy2475h595fr   mumoshu/actions-runner-controller-ci   Running
example-runnerdeploy2475ht2qbr   mumoshu/actions-runner-controller-ci   Running
Deploying runners with RunnerSets

This feature requires controller version => v0.20.0
We can also deploy sets of RunnerSets the same way, a basic RunnerSet would look like this:

apiVersion: actions.summerwind.dev/v1alpha1
kind: RunnerSet
metadata:
  name: example
spec:
  replicas: 1
  repository: mumoshu/actions-runner-controller-ci
  # Other mandatory fields from StatefulSet
  selector:
    matchLabels:
      app: example
  serviceName: example
  template:
    metadata:
      labels:
        app: example
As it is based on StatefulSet, selector and template.metadata.labels it needs to be defined and have the exact same set of labels. serviceName must be set to some non-empty string as it is also required by StatefulSet.

Runner-related fields like ephemeral, repository, organization, enterprise, and so on should be written directly under spec.

Fields like volumeClaimTemplates that originates from StatefulSet should also be written directly under spec.

Pod-related fields like security contexts and volumes are written under spec.template.spec like StatefulSet.

Similarly, container-related fields like resource requests and limits, container image names and tags, security context, and so on are written under spec.template.spec.containers. There are two reserved container name, runner and docker. The former is for the container that runs actions runner and the latter is for the container that runs a dockerd.

For a more complex example, see the below:

apiVersion: actions.summerwind.dev/v1alpha1
kind: RunnerSet
metadata:
  name: example
spec:
  replicas: 1
  repository: mumoshu/actions-runner-controller-ci
  dockerdWithinRunnerContainer: true
  template:
    spec:
      securityContext:
        # All level/role/type/user values will vary based on your SELinux policies.
        # See https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux_atomic_host/7/html/container_security_guide/docker_selinux_security_policy for information about SELinux with containers
        seLinuxOptions:
          level: "s0"
          role: "system_r"
          type: "super_t"
          user: "system_u"
      containers:
      - name: runner
        env: []
        resources:
          limits:
            cpu: "4.0"
            memory: "8Gi"
          requests:
            cpu: "2.0"
            memory: "4Gi"
        # This is an advanced configuration. Don't touch it unless you know what you're doing.
        securityContext:
          # Usually, the runner container's privileged field is derived from dockerdWithinRunnerContainer.
          # But in the case where you need to run privileged job steps even if you don't use docker/don't need dockerd within the runner container,
          # just specified `privileged: true` like this.
          # See https://github.com/actions/actions-runner-controller/issues/1282
          # Do note that specifying `privileged: false` while using dind is very likely to fail, even if you use some vm-based container runtimes
          # like firecracker and kata. Basically they run containers within dedicated micro vms and so
          # it's more like you can use `privileged: true` safer with those runtimes.
          #
          # privileged: true
      - name: docker
        resources:
          limits:
            cpu: "4.0"
            memory: "8Gi"
          requests:
            cpu: "2.0"
            memory: "4Gi"

# runnerdeployment.yaml
apiVersion: actions.summerwind.dev/v1alpha1
kind: RunnerDeployment
metadata:
  name: example-runnerdeploy
spec:
  replicas: 1
  template:
    spec:
      repository: mumoshu/actions-runner-controller-ci
Apply the created manifest file to your Kubernetes.

$ kubectl apply -f runnerdeployment.yaml
runnerdeployment.actions.summerwind.dev/example-runnerdeploy created
You can see that 1 runner and its underlying pod has been created as specified by replicas: 1 attribute:

$ kubectl get runners
NAME                             REPOSITORY                             STATUS
example-runnerdeploy2475h595fr   mumoshu/actions-runner-controller-ci   Running

$ kubectl get pods
NAME                           READY   STATUS    RESTARTS   AGE
example-runnerdeploy2475ht2qbr 2/2     Running   0          1m
The runner you created has been registered directly to the defined repository, you should be able to see it in the settings of the repository.

Now you can use your self-hosted runner. See the official documentation on how to run a job with it.

Adding runners to an organization

To add the runner to an organization, you only need to replace the repository field with organization, so the runner will register itself to the organization.

apiVersion: actions.summerwind.dev/v1alpha1
kind: RunnerDeployment
metadata:
  name: example-runnerdeploy
spec:
  replicas: 1
  template:
    spec:
      organization: your-organization-name
Now you can see the runner on the organization level (if you have organization owner permissions).

Adding runners to an enterprise

To add the runner to an enterprise, you only need to replace the repository field with enterprise, so the runner will register itself to the enterprise.

apiVersion: actions.summerwind.dev/v1alpha1
kind: RunnerDeployment
metadata:
  name: example-runnerdeploy
spec:
  replicas: 1
  template:
    spec:
      enterprise: your-enterprise-name
apiVersion: actions.summerwind.dev/v1alpha1
kind: RunnerDeployment
metadata:
  name: example-runner-deployment
spec:
  template:
    spec:
      repository: example/myrepo
---
apiVersion: actions.summerwind.dev/v1alpha1
kind: HorizontalRunnerAutoscaler
metadata:
  name: example-runner-deployment-autoscaler
spec:
  # Runners in the targeted RunnerDeployment won't be scaled down
  # for 5 minutes instead of the default 10 minutes now
  scaleDownDelaySecondsAfterScaleOut: 300
  scaleTargetRef:
    kind: RunnerDeployment
    # # In case the scale target is RunnerSet:
    # kind: RunnerSet
    name: example-runner-deployment
  minReplicas: 1
  maxReplicas: 5
  metrics:
  - type: PercentageRunnersBusy
    scaleUpThreshold: '0.75'
    scaleDownThreshold: '0.25'
    scaleUpFactor: '2'
    scaleDownFactor: '0.5'
Pull Driven Scaling

To configure webhook driven scaling see the Webhook Driven Scaling section
The pull based metrics are configured in the metrics attribute of a HRA (see snippet below). The period between polls is defined by the controller's --sync-period flag. If this flag isn't provided then the controller defaults to a sync period of 1m, this can be configured in seconds or minutes.

Be aware that the shorter the sync period the quicker you will consume your rate limit budget, depending on your environment this may or may not be a risk. Consider monitoring ARCs rate limit budget when configuring this feature to find the optimal performance sync period.

apiVersion: actions.summerwind.dev/v1alpha1
kind: HorizontalRunnerAutoscaler
metadata:
  name: example-runner-deployment-autoscaler
spec:
  scaleTargetRef:
    kind: RunnerDeployment
    # # In case the scale target is RunnerSet:
    # kind: RunnerSet
    name: example-runner-deployment
  minReplicas: 1
  maxReplicas: 5
  # Your chosen scaling metrics here
  metrics: []
Metric Options:

TotalNumberOfQueuedAndInProgressWorkflowRuns

The TotalNumberOfQueuedAndInProgressWorkflowRuns metric polls GitHub for all pending workflow runs against a given set of repositories. The metric will scale the runner count up to the total number of pending jobs at the sync time up to the maxReplicas configuration.

Benefits of this metric

Supports named repositories allowing you to restrict the runner to a specified set of repositories server-side.
Scales the runner count based on the depth of the job queue meaning a 1:1 scaling of runners to queued jobs.
Like all scaling metrics, you can manage workflow allocation to the RunnerDeployment through the use of GitHub labels.
Drawbacks of this metric

A list of repositories must be included within the scaling metric. Maintaining a list of repositories may not be viable in larger environments or self-serve environments.
May not scale quickly enough for some users' needs. This metric is pull based and so the queue depth is polled as configured by the sync period, as a result scaling performance is bound by this sync period meaning there is a lag to scaling activity.
Relatively large amounts of API requests are required to maintain this metric, you may run into API rate limit issues depending on the size of your environment and how aggressive your sync period configuration is.
Example RunnerDeployment backed by a HorizontalRunnerAutoscaler:

apiVersion: actions.summerwind.dev/v1alpha1
kind: RunnerDeployment
metadata:
  name: example-runner-deployment
spec:
  template:
    spec:
      repository: example/myrepo
---
apiVersion: actions.summerwind.dev/v1alpha1
kind: HorizontalRunnerAutoscaler
metadata:
  name: example-runner-deployment-autoscaler
spec:
  scaleTargetRef:
    kind: RunnerDeployment
    # # In case the scale target is RunnerSet:
    # kind: RunnerSet
    name: example-runner-deployment
  minReplicas: 1
  maxReplicas: 5
  metrics:
  - type: TotalNumberOfQueuedAndInProgressWorkflowRuns
    repositoryNames:
    # A repository name is the REPO part of `github.com/OWNER/REPO`
    - myrepo
PercentageRunnersBusy

The HorizontalRunnerAutoscaler will poll GitHub for the number of runners in the busy state which live in the RunnerDeployment's namespace, it will then scale depending on how you have configured the scale factors.

Benefits of this metric

Supports named repositories server-side the same as the TotalNumberOfQueuedAndInProgressWorkflowRuns metric #313
Supports GitHub organization wide scaling without maintaining an explicit list of repositories, this is especially useful for those that are working at a larger scale. #223
Like all scaling metrics, you can manage workflow allocation to the RunnerDeployment through the use of GitHub labels
Supports scaling desired runner count on both a percentage increase / decrease basis as well as on a fixed increase / decrease count basis #223 #315
Drawbacks of this metric

May not scale quickly enough for some users' needs. This metric is pull based and so the number of busy runners is polled as configured by the sync period, as a result scaling performance is bound by this sync period meaning there is a lag to scaling activity.
We are scaling up and down based on indicative information rather than a count of the actual number of queued jobs and so the desired runner count is likely to under provision new runners or overprovision them relative to actual job queue depth, this may or may not be a problem for you.
Examples of each scaling type implemented with a RunnerDeployment backed by a HorizontalRunnerAutoscaler:

---
apiVersion: actions.summerwind.dev/v1alpha1
kind: HorizontalRunnerAutoscaler
metadata:
  name: example-runner-deployment-autoscaler
spec:
  scaleTargetRef:
    kind: RunnerDeployment
    # # In case the scale target is RunnerSet:
    # kind: RunnerSet
    name: example-runner-deployment
  minReplicas: 1
  maxReplicas: 5
  metrics:
  - type: PercentageRunnersBusy
    scaleUpThreshold: '0.75'    # The percentage of busy runners at which the number of desired runners are re-evaluated to scale up
    scaleDownThreshold: '0.3'   # The percentage of busy runners at which the number of desired runners are re-evaluated to scale down
    scaleUpFactor: '1.4'        # The scale up multiplier factor applied to desired count
    scaleDownFactor: '0.7'      # The scale down multiplier factor applied to desired count
---
apiVersion: actions.summerwind.dev/v1alpha1
kind: HorizontalRunnerAutoscaler
metadata:
  name: example-runner-deployment-autoscaler
spec:
  scaleTargetRef:
    kind: RunnerDeployment
    # # In case the scale target is RunnerSet:
    # kind: RunnerSet
    name: example-runner-deployment
  minReplicas: 1
  maxReplicas: 5
  metrics:
  - type: PercentageRunnersBusy
    scaleUpThreshold: '0.75'    # The percentage of busy runners at which the number of desired runners are re-evaluated to scale up
    scaleDownThreshold: '0.3'   # The percentage of busy runners at which the number of desired runners are re-evaluated to scale down
    scaleUpAdjustment: 2        # The scale up runner count added to desired count
    scaleDownAdjustment: 1      # The scale down runner count subtracted from the desired count
Combining Pull Driven Scaling Metrics

If a HorizontalRunnerAutoscaler is configured with a secondary metric of TotalNumberOfQueuedAndInProgressWorkflowRuns, then be aware that the controller will check the primary metric of PercentageRunnersBusy first and will only use the secondary metric to calculate the desired replica count if the primary metric returns 0 desired replicas.

PercentageRunnersBusy metrics must appear before TotalNumberOfQueuedAndInProgressWorkflowRuns; otherwise, the controller will fail to process the HorizontalRunnerAutoscaler. A valid configuration follows.

---
apiVersion: actions.summerwind.dev/v1alpha1
kind: HorizontalRunnerAutoscaler
metadata:
  name: example-runner-deployment-autoscaler
spec:
  scaleTargetRef:
    kind: RunnerDeployment
    # # In case the scale target is RunnerSet:
    # kind: RunnerSet
    name: example-runner-deployment
  minReplicas: 1
  maxReplicas: 5
  metrics:
  - type: PercentageRunnersBusy
    scaleUpThreshold: '0.75'    # The percentage of busy runners at which the number of desired runners are re-evaluated to scale up
    scaleDownThreshold: '0.3'   # The percentage of busy runners at which the number of desired runners are re-evaluated to scale down
    scaleUpAdjustment: 2        # The scale up runner count added to desired count
    scaleDownAdjustment: 1      # The scale down runner count subtracted from the desired count
  - type: TotalNumberOfQueuedAndInProgressWorkflowRuns
    repositoryNames:
    # A repository name is the REPO part of `github.com/OWNER/REPO`
    - myrepo
Webhook Driven Scaling

This feature requires controller version => v0.20.0
To configure pull driven scaling see the Pull Driven Scaling section
Alternatively ARC can be configured to scale based on the workflow_job webhook event. The primary benefit of autoscaling on webhooks compared to the pull driven scaling is that ARC is immediately notified of the scaling need.

Webhooks are processed by a separate webhook server. The webhook server receives workflow_job webhook events and scales RunnerDeployments / RunnerSets by updating HRAs configured for the webhook trigger. Below is an example set-up where a HRA has been configured to scale a RunnerDeployment from a workflow_job event:

apiVersion: actions.summerwind.dev/v1alpha1
kind: RunnerDeployment
metadata:
  name: example-runners
spec:
  template:
    spec:
      repository: example/myrepo
---
apiVersion: actions.summerwind.dev/v1alpha1
kind: HorizontalRunnerAutoscaler
metadata:
  name: example-runners
spec:
  minReplicas: 1
  maxReplicas: 10
  scaleTargetRef:
    kind: RunnerDeployment
    # # In case the scale target is RunnerSet:
    # kind: RunnerSet
    name: example-runners
  scaleUpTriggers:
    - githubEvent:
        workflowJob: {}
      duration: "30m"
With the workflowJob trigger, each event adds or subtracts a single runner. the scaleUpTriggers.amount field is ignored.

The duration field is there because event delivery is not guaranteed. If a scale-up event is received, but the corresponding scale-down event is not, then the extra runner would be left running forever if there were not some clean-up mechanism. The duration field sets the maximum amount of time to wait for a scale-down event. Scale-down happens at the earlier of receiving the scale-down event or the expiration of duration after the scale-up event is processed and the scale-up itself is initiated.

The lifecycle of a runner provisioned from a webhook is different from that of a runner provisioned from the pull based scaling method:

GitHub sends a workflow_job event to ARC with status=queued
ARC finds the HRA with a workflow_job webhook scale trigger that backs a RunnerDeployment / RunnerSet with matching runner labels. (If it finds more than one match, the event is ignored.)
The matched HRA adds a capacityReservation to its list and sets it to expire at current time + HRA.spec.scaleUpTriggers[].duration
If there are fewer replicas running than maxReplicas, HRA adds a replica and sets the EffectiveTime of that replica to the current time
At this point there are a few things that can happen:

Due to idle runners already being available, the job is assigned to one of them and the new runner is left dangling due to it not being used
The job gets allocated to the runner just launched
If there are already maxReplicas replicas running, the job waits for its capacityReservation to be assigned to one of them
If the runner gets assigned the job that triggered the scale up, the lifecycle looks like this:

The new runner gets allocated the job and processes it
Upon the job ending GitHub sends another workflow_job event to ARC but with status=completed
The HRA removes the oldest capacity reservation from its capacityReservations and picks a runner to terminate ensuring it isn't busy via the GitHub API beforehand
If the job has to wait for a runner because there are already maxReplicas replicas running, the lifecycle looks like this:

A capacityReservation is added to the list, but no scale-up happens because that would exceed maxReplicas
When one of the existing runners finishes a job, GitHub sends another workflow_job event to ARC but with status=completed (or status=canceled if the job was cancelled)
The HRA removes the oldest capacity reservation from its capacityReservations, the oldest waiting capacityReservation becomes active, and its duration timer starts
GitHub assigns a waiting job to the newly available runner
If the job is cancelled before it is allocated to a runner then the lifecycle looks like this:

Upon the job cancellation GitHub sends another workflow_job event to ARC but with status=cancelled
The HRA removes the oldest capacity reservation from its capacityReservations and picks a runner to terminate ensuring it isn't busy via the GitHub API beforehand
If the status=completed or status=cancelled is never delivered to ARC (which happens occasionally) then the lifecycle looks like this:

The scale trigger duration specified via HRA.spec.scaleUpTriggers[].duration elapses
The HRA notices that the capacity reservation has expired, removes it from HRA's capacityReservation list and (unless there are maxReplicas running and jobs waiting) terminates the expired runner ensuring it isn't busy via the GitHub API beforehand
Your HRA.spec.scaleUpTriggers[].duration value should be set long enough to account for the following things:

The potential amount of time it could take for a pod to become Running e.g. you need to scale horizontally because there isn't a node available +
The amount of time it takes for GitHub to allocate a job to that runner +
The amount of time it takes for the runner to notice the allocated job and starts running it +
The length of time it takes for the runner to complete the job
Install with Helm

To enable this feature, you first need to install the GitHub webhook server. To install via our Helm chart, see the values documentation for all configuration options

$ helm upgrade --install --namespace actions-runner-system --create-namespace \
             --wait actions-runner-controller actions-runner-controller/actions-runner-controller \
             --set "githubWebhookServer.enabled=true,service.type=NodePort,githubWebhookServer.ports[0].nodePort=33080"
The above command will result in exposing the node port 33080 for Webhook events. Usually, you need to create an external load balancer targeted to the node port, and register the hostname or the IP address of the external load balancer to the GitHub Webhook.

With a custom Kubernetes ingress controller:

CAUTION: The Kubernetes ingress controllers described below is just a suggestion from the community and the ARC team will not provide any user support for ingress controllers as it's not a part of this project.

The following guide on creating an ingress has been contributed by the awesome ARC community and is provided here as-is. You may, however, still be able to ask for help on the community on GitHub Discussions if you have any problems.
Kubernetes provides Ingress resources to let you configure your ingress controller to expose a Kubernetes service. If you plan to expose ARC via Ingress, you might not be required to make it a NodePort service (although nothing would prevent an ingress controller to expose NodePort services too):

$ helm upgrade --install --namespace actions-runner-system --create-namespace \
             --wait actions-runner-controller actions-runner-controller/actions-runner-controller \
             --set "githubWebhookServer.enabled=true"
The command above will create a new deployment and a service for receiving Github Webhooks on the actions-runner-system namespace.

Now we need to expose this service so that GitHub can send these webhooks over the network with TLS protection.

You can do it in any way you prefer, here we'll suggest doing it with a k8s Ingress. For the sake of this example we'll expose this service on the following URL:

https://your.domain.com/actions-runner-controller-github-webhook-server
Where your.domain.com should be replaced by your own domain.

Note: This step assumes you already have a configured cert-manager and domain name for your cluster.
Let's start by creating an Ingress file called arc-webhook-server.yaml with the following contents:

apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: actions-runner-controller-github-webhook-server
  namespace: actions-runner-system
  annotations:
    kubernetes.io/ingress.class: nginx
    nginx.ingress.kubernetes.io/backend-protocol: "HTTP"
spec:
  tls:
  - hosts:
    - your.domain.com
    secretName: your-tls-secret-name
  rules:
    - http:
        paths:
          - path: /actions-runner-controller-github-webhook-server
            pathType: Prefix
            backend:
              service:
                name: actions-runner-controller-github-webhook-server
                port:
                  number: 80
Make sure to set the spec.tls.secretName to the name of your TLS secret and spec.tls.hosts[0] to your own domain.

Then create this resource on your cluster with the following command:

kubectl apply -n actions-runner-system -f arc-webhook-server.yaml
Configuring GitHub for sending webhooks for our newly created webhook server:

After this step your webhook server should be ready to start receiving webhooks from GitHub.

To configure GitHub to start sending you webhooks, go to the settings page of your repository or organization then click on Webhooks, then on Add webhook.

There set the "Payload URL" field with the webhook URL you just created, if you followed the example ingress above the URL would be something like this:

https://your.domain.com/actions-runner-controller-github-webhook-server
Remember to replace your.domain.com with your own domain.
Then click on "Content type" and choose application/json.

Then click on "let me select individual events" and choose Workflow Jobs.

Then click on Add Webhook.

GitHub will then send a ping event to your webhook server to check if it is working, if it is you'll see a green V mark alongside your webhook on the Settings -> Webhooks page.

Once you were able to confirm that the Webhook server is ready and running from GitHub create or update your HorizontalRunnerAutoscaler resources by learning the following configuration examples.

Install with Kustomize

To install this feature using Kustomize, add github-webhook-server resources to your kustomization.yaml file as in the example below:

apiVersion: kustomize.config.k8s.io/v1beta1
kind: Kustomization

resources:
# You should already have this
- github.com/actions/actions-runner-controller/config//default?ref=v0.22.2
# Add the below!
- github.com/actions/actions-runner-controller/config//github-webhook-server?ref=v0.22.2

Finally, you will have to configure an ingress so that you may configure the webhook in github. An example of such ingress can be find below:

```yaml
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: actions-runners-webhook-server
spec:
  rules:
  - http:
      paths:
      - path: /
        backend:
          service:
            name: github-webhook-server
            port:
              number: 80
        pathType: Exact
Autoscaling to/from 0

This feature requires controller version => v0.19.0
The regular RunnerDeployment / RunnerSet replicas: attribute as well as the HorizontalRunnerAutoscaler minReplicas: attribute supports being set to 0.

The main use case for scaling from 0 is with the HorizontalRunnerAutoscaler kind. To scale from 0 whilst still being able to provision runners as jobs are queued we must use the HorizontalRunnerAutoscaler with only certain scaling configurations, only the below configurations support scaling from 0 whilst also being able to provision runners as jobs are queued:

TotalNumberOfQueuedAndInProgressWorkflowRuns
PercentageRunnersBusy + TotalNumberOfQueuedAndInProgressWorkflowRuns
Webhook-based autoscaling
PercentageRunnersBusy can't be used alone for scale-from-zero as, by its definition, it needs one or more GitHub runners to become busy to be able to scale. If there isn't a runner to pick up a job and enter a busy state then the controller will never know to provision a runner to begin with as this metric has no knowledge of the job queue and is relying on using the number of busy runners as a means for calculating the desired replica count.

Webhook-based autoscaling is the best option as it is relatively easy to configure and also it can scale quickly.

Scheduled Overrides

This feature requires controller version => v0.19.0
Scheduled Overrides allows you to configure HorizontalRunnerAutoscaler so that its spec: gets updated only during a certain period of time. This feature is usually used for the following scenarios:

You want to reduce your infrastructure costs by scaling your Kubernetes nodes down outside a given period
You want to scale for scheduled spikes in workloads
The most basic usage of this feature is to set a non-repeating override:

apiVersion: actions.summerwind.dev/v1alpha1
kind: HorizontalRunnerAutoscaler
metadata:
  name: example-runner-deployment-autoscaler
spec:
  scaleTargetRef:
    kind: RunnerDeployment
    # # In case the scale target is RunnerSet:
    # kind: RunnerSet
    name: example-runner-deployment
  scheduledOverrides:
  # Override minReplicas to 100 only between 2021-06-01T00:00:00+09:00 and 2021-06-03T00:00:00+09:00
  - startTime: "2021-06-01T00:00:00+09:00"
    endTime: "2021-06-03T00:00:00+09:00"
    minReplicas: 100
  minReplicas: 1
A scheduled override without recurrenceRule is considered a one-off override, that is active between startTime and endTime. In the second scenario, it overrides minReplicas to 100 only between 2021-06-01T00:00:00+09:00 and 2021-06-03T00:00:00+09:00.

A more advanced configuration is to include a recurrenceRule in the override:

apiVersion: actions.summerwind.dev/v1alpha1
kind: HorizontalRunnerAutoscaler
metadata:
  name: example-runner-deployment-autoscaler
spec:
  scaleTargetRef:
    kind: RunnerDeployment
    # # In case the scale target is RunnerSet:
    # kind: RunnerSet
    name: example-runner-deployment
  scheduledOverrides:
  # Override minReplicas to 0 only between 0am sat to 0am mon
  - startTime: "2021-05-01T00:00:00+09:00"
    endTime: "2021-05-03T00:00:00+09:00"
    recurrenceRule:
      frequency: Weekly
      # Optional sunset datetime attribute
      # untilTime: "2022-05-01T00:00:00+09:00"
    minReplicas: 0
  minReplicas: 1
A recurring override is initially active between startTime and endTime, and then it repeatedly gets activated after a certain period of time denoted by frequency.

frequecy can take one of the following values:

Daily
Weekly
Monthly
Yearly
By default, a scheduled override repeats forever. If you want it to repeat until a specific point in time, define untilTime. The controller creates the last recurrence of the override until the recurrence's startTime is equal or earlier than untilTime.

Do ensure that you have enough slack for untilTime so that a delayed or offline actions-runner-controller is much less likely to miss the last recurrence. For example, you might want to set untilTime to M minutes after the last recurrence's startTime, so that actions-runner-controller being offline up to M minutes doesn't miss the last recurrence.

Combining Multiple Scheduled Overrides:

In case you have a more complex scenario, try writing two or more entries under scheduledOverrides.

The earlier entry is prioritized higher than later entries. So you usually define one-time overrides at the top of your list, then yearly, monthly, weekly, and lastly daily overrides.

A common use case for this may be to have 1 override to scale to 0 during non-working hours and another override to scale to 0 on weekends.

Configuring automatic termination

As of ARC 0.27.0 (unreleased as of 2022/09/30), runners can only wait for 15 seconds by default on pod termination.

This can be problematic in two scenarios:

Scenario 1 - RunnerSet-only: You're triggering updates other than replica changes to RunnerSet very often- With current implementation, every update except replicas change to RunnerSet may result in terminating the in-progress workflow jobs to fail.
Scenario 2 - RunnerDeployment and RunnerSet: You have another Kubernetes controller that evicts runner pods directly, not consulting ARC.
RunnerDeployment is not affected by the Scenario 1 as RunnerDeployment-managed runners are already tolerable to unlimitedly long in-progress running job while being replaced, as it's graceful termination process is handled outside of the entrypoint and the Kubernetes' pod termination process.
To make it more reliable, please set spec.template.spec.terminationGracePeriodSeconds field and the RUNNER_GRACEFUL_STOP_TIMEOUT environment variable appropriately. NOTE: if you are using the default configuration of running DinD as a sidecar, you'll need to set this environment variable in both spec.template.spec.env as well as spec.template.spec.dockerEnv for RunnerDeployment objects, otherwise the docker container will recieve the same termination signal and exit while the remainder of the build runs.

If you want the pod to terminate in approximately 110 seconds at the latest since the termination request, try terminationGracePeriodSeconds of 110 and RUNNER_GRACEFUL_STOP_TIMEOUT of like 90.

The difference between terminationGracePeriodSeconds and RUNNER_GRACEFUL_STOP_TIMEOUT can vary depending on your environment and cluster.

The idea is two fold:

RUNNER_GRACEFUL_STOP_TIMEOUT is for giving the runner the longest possible time to wait for the in-progress job to complete. You should keep this smaller than terminationGracePeriodSeconds so that you don't unnecessarily cancel running jobs.
terminationGracePeriodSeconds is for giving the runner the longest possible time to stop before disappear. If the pod forcefully terminated before a graceful stop, the job running within the runner pod can hang like 10 minutes in the GitHub Actions Workflow Run/Job UI. A correct value for this avoids the hang, even though it had to cancel the running job due to the approaching deadline.
We know the default 15 seconds timeout is too short to be useful at all. In near future, we might raise the default to, for example, 100 seconds, so that runners that are tend to run up to 100 seconds jobs can terminate gracefully without failing running jobs. It will also allow the job which were running on the node that was requsted for termination to correct report its status as "cancelled", rather than hanging approximately 10 minutes in the Actions Web UI until it finally fails(without any specific error message). 100 seconds is just an example. It might be a good default in case you're using AWS EC2 Spot Instances because they tend to send termination notice two minutes before the termination. If you have any other suggestions for the default value, please share your thoughts in Discussions.
Additional Settings

You can pass details through the spec selector. Here's an eg. of what you may like to do:

apiVersion: actions.summerwind.dev/v1alpha1
kind: RunnerDeployment
metadata:
  name: actions-runner
  namespace: default
spec:
  replicas: 2
  template:
    metadata:
      annotations:
        cluster-autoscaler.kubernetes.io/safe-to-evict: "true"
    spec:
      priorityClassName: "high"
      nodeSelector:
        node-role.kubernetes.io/test: ""

      securityContext:
        #All level/role/type/user values will vary based on your SELinux policies.
        #See https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux_atomic_host/7/html/container_security_guide/docker_selinux_security_policy for information about SELinux with containers
        seLinuxOptions:
          level: "s0"
          role: "system_r"
          type: "super_t"
          user: "system_u"

      tolerations:
      - effect: NoSchedule
        key: node-role.kubernetes.io/test
        operator: Exists

      topologySpreadConstraints:
        - maxSkew: 1
          topologyKey: kubernetes.io/hostname
          whenUnsatisfiable: ScheduleAnyway
          labelSelector:
            matchLabels:
              runner-deployment-name: actions-runner

      repository: mumoshu/actions-runner-controller-ci
      # The default "summerwind/actions-runner" images are available at DockerHub:
      # https://hub.docker.com/r/summerwind/actions-runner
      # You can also build your own and specify it like the below:
      image: custom-image/actions-runner:latest
      imagePullPolicy: Always
      resources:
        limits:
          cpu: "4.0"
          memory: "8Gi"
        requests:
          cpu: "2.0"
          memory: "4Gi"
      # Timeout after a node crashed or became unreachable to evict your pods somewhere else (default 5mins)
      tolerations:
        - key: "node.kubernetes.io/unreachable"
          operator: "Exists"
          effect: "NoExecute"
          tolerationSeconds: 10
      # true (default) = The runner restarts after running jobs, to ensure a clean and reproducible build environment
      # false = The runner is persistent across jobs and doesn't automatically restart
      # This directly controls the behaviour of `--once` flag provided to the github runner
      ephemeral: false
      # true (default) = A privileged docker sidecar container is included in the runner pod.
      # false = A docker sidecar container is not included in the runner pod and you can't use docker.
      # If set to false, there are no privileged container and you cannot use docker.
      dockerEnabled: false
      # Optional Docker containers network MTU
      # If your network card MTU is smaller than Docker's default 1500, you might encounter Docker networking issues.
      # To fix these issues, you should setup Docker MTU smaller than or equal to that on the outgoing network card.
      # More information:
      # - https://mlohr.com/docker-mtu/
      dockerMTU: 1500
      # Optional Docker registry mirror
      # Docker Hub has an aggressive rate-limit configuration for free plans.
      # To avoid disruptions in your CI/CD pipelines, you might want to setup an external or on-premises Docker registry mirror.
      # More information:
      # - https://docs.docker.com/docker-hub/download-rate-limit/
      # - https://cloud.google.com/container-registry/docs/pulling-cached-images
      dockerRegistryMirror: https://mirror.gcr.io/
      # false (default) = Docker support is provided by a sidecar container deployed in the runner pod.
      # true = No docker sidecar container is deployed in the runner pod but docker can be used within the runner container instead. The image summerwind/actions-runner-dind is used by default.
      dockerdWithinRunnerContainer: true
      #Optional environment variables for docker container
      # Valid only when dockerdWithinRunnerContainer=false
      dockerEnv:
        - name: HTTP_PROXY
          value: http://example.com
      # Docker sidecar container image tweaks examples below, only applicable if dockerdWithinRunnerContainer = false
      dockerdContainerResources:
        limits:
          cpu: "4.0"
          memory: "8Gi"
        requests:
          cpu: "2.0"
          memory: "4Gi"
      # Additional N number of sidecar containers
      sidecarContainers:
        - name: mysql
          image: mysql:5.7
          env:
            - name: MYSQL_ROOT_PASSWORD
              value: abcd1234
          securityContext:
            runAsUser: 0
      # workDir if not specified (default = /runner/_work)
      # You can customise this setting allowing you to change the default working directory location
      # for example, the below setting is the same as on the ubuntu-18.04 image
      workDir: /home/runner/work
      # You can mount some of the shared volumes to the dind container using dockerVolumeMounts, like any other volume mounting.
      # NOTE: in case you want to use an hostPath like the following example, make sure that Kubernetes doesn't schedule more than one runner
      # per physical host. You can achieve that by setting pod anti-affinity rules and/or resource requests/limits.
      volumes:
        - name: docker-extra
          hostPath:
            path: /mnt/docker-extra
            type: DirectoryOrCreate
        - name: repo
          hostPath:
            path: /mnt/repo
            type: DirectoryOrCreate
      dockerVolumeMounts:
        - mountPath: /var/lib/docker
          name: docker-extra
      # You can mount some of the shared volumes to the runner container using volumeMounts.
      # NOTE: Do not try to mount the volume onto the runner workdir itself as it will not work. You could mount it however on a subdirectory in the runner workdir
      # Please see https://github.com/actions/actions-runner-controller/issues/630#issuecomment-862087323 for more information.
      volumeMounts:
        - mountPath: /home/runner/work/repo
          name: repo
      # Optional storage medium type of runner volume mount.
      # More info: https://kubernetes.io/docs/concepts/storage/volumes/#emptydir
      # "" (default) = Node's default medium
      # Memory = RAM-backed filesystem (tmpfs)
      # NOTE: Using RAM-backed filesystem gives you fastest possible storage on your host nodes.
      volumeStorageMedium: ""
      # Total amount of local storage resources required for runner volume mount.
      # The default limit is undefined.
      # NOTE: You can make sure that nodes' resources are never exceeded by limiting used storage size per runner pod.
      # You can even disable the runner mount completely by setting limit to zero if dockerdWithinRunnerContainer = true.
      # Please see https://github.com/actions/actions-runner-controller/pull/674 for more information.
      volumeSizeLimit: 4Gi
      # Optional name of the container runtime configuration that should be used for pods.
      # This must match the name of a RuntimeClass resource available on the cluster.
      # More info: https://kubernetes.io/docs/concepts/containers/runtime-class
      runtimeClassName: "runc"
      # This is an advanced configuration. Don't touch it unless you know what you're doing.
      containers:
      - name: runner
        # Usually, the runner container's privileged field is derived from dockerdWithinRunnerContainer.
        # But in the case where you need to run privileged job steps even if you don't use docker/don't need dockerd within the runner container,
        # just specified `privileged: true` like this.
        # See https://github.com/actions/actions-runner-controller/issues/1282
        # Do note that specifying `privileged: false` while using dind is very likely to fail, even if you use some vm-based container runtimes
        # like firecracker and kata. Basically they run containers within dedicated micro vms and so
        # it's more like you can use `privileged: true` safer with those runtimes.
        #
        # privileged: true

kind: RunnerDeployment
spec:
  template:
    spec:
      dockerVolumeMounts:
        - mountPath: /var/lib/docker
          name: docker
      volumeMounts:
        - mountPath: /tmp
          name: tmp
      volumes:
        - name: docker
          emptyDir:
            medium: Memory
        - name: work # this volume gets automatically used up for the workdir
          emptyDir:
            medium: Memory
        - name: tmp
          emptyDir:
            medium: Memory
      ephemeral: true # recommended to not leak data between builds.
NVME SSD

In this example we provide NVME backed storage for the workdir, docker sidecar and /tmp within the runner. Here we use a working example on GKE, which will provide the NVME disk at /mnt/disks/ssd0. We will be placing the respective volumes in subdirs here and in order to be able to run multiple runners we will use the pod name as a prefix for subdirectories. Also the disk will fill up over time and disk space will not be freed until the node is removed.

Beware that running these persistent backend volumes leave data behind between 2 different jobs on the workdir and /tmp with ephemeral: false.

kind: RunnerDeployment
spec:
  template:
    spec:
      env:
      - name: POD_NAME
        valueFrom:
          fieldRef:
            fieldPath: metadata.name
      dockerVolumeMounts:
      - mountPath: /var/lib/docker
        name: docker
        subPathExpr: $(POD_NAME)-docker
      - mountPath: /runner/_work
        name: work
        subPathExpr: $(POD_NAME)-work
      volumeMounts:
      - mountPath: /runner/_work
        name: work
        subPathExpr: $(POD_NAME)-work
      - mountPath: /tmp
        name: tmp
        subPathExpr: $(POD_NAME)-tmp
      dockerEnv:
      - name: POD_NAME
        valueFrom:
          fieldRef:
            fieldPath: metadata.name
      volumes:
      - hostPath:
          path: /mnt/disks/ssd0
        name: docker
      - hostPath:
          path: /mnt/disks/ssd0
        name: work
      - hostPath:
          path: /mnt/disks/ssd0
        name: tmp
      ephemeral: true # VERY important. otherwise data inside the workdir and /tmp is not cleared between builds
Docker image layers caching

Note: Ensure that the volume mount is added to the container that is running the Docker daemon.
docker stores pulled and built image layers in the daemon's (not client) local storage area which is usually at /var/lib/docker.

By leveraging RunnerSet's dynamic PV provisioning feature and your CSI driver, you can let ARC maintain a pool of PVs that are reused across runner pods to retain /var/lib/docker.

Be sure to add the volume mount to the container that is supposed to run the docker daemon.

Be sure to trigger several workflow runs before checking if the cache is effective. ARC requires an Available PV to be reused for the new runner pod, and a PV becomes Available only after some time after the previous runner pod that was using the PV terminated. See the related discussion.

By default, ARC creates a sidecar container named docker within the runner pod for running the docker daemon. In that case, it's where you need the volume mount so that the manifest looks like:

kind: RunnerSet
metadata:
  name: example
spec:
  template:
    spec:
      containers:
      - name: docker
        volumeMounts:
        - name: var-lib-docker
          mountPath: /var/lib/docker
  volumeClaimTemplates:
  - metadata:
      name: var-lib-docker
    spec:
      accessModes:
      - ReadWriteOnce
      resources:
        requests:
          storage: 10Mi
      storageClassName: var-lib-docker
With dockerdWithinRunnerContainer: true, you need to add the volume mount to the runner container.

Go module and build caching

Go is known to cache builds under $HOME/.cache/go-build and downloaded modules under $HOME/pkg/mod. The module cache dir can be customized by setting GOMOD_CACHE so by setting it to somewhere under $HOME/.cache, we can have a single PV to host both build and module cache, which might improve Go module downloading and building time.

Be sure to trigger several workflow runs before checking if the cache is effective. ARC requires an Available PV to be reused for the new runner pod, and a PV becomes Available only after some time after the previous runner pod that was using the PV terminated. See the related discussion.

kind: RunnerSet
metadata:
  name: example
spec:
  template:
    spec:
      containers:
      - name: runner
        env:
        - name: GOMODCACHE
          value: "/home/runner/.cache/go-mod"
        volumeMounts:
        - name: cache
          mountPath: "/home/runner/.cache"
  volumeClaimTemplates:
  - metadata:
      name: cache
    spec:
      accessModes:
      - ReadWriteOnce
      resources:
        requests:
          storage: 10Mi
      storageClassName: cache
PV-backed runner work directory

ARC works by automatically creating runner pods for running actions/runner and running config.sh which you had to ran manually without ARC.

config.sh is the script provided by actions/runner to pre-configure the runner process before being started. One of the options provided by config.sh is --work, which specifies the working directory where the runner runs your workflow jobs in.

The volume and the partition that hosts the work directory should have several or dozens of GBs free space that might be used by your workflow jobs.

By default, ARC uses /runner/_work as work directory, which is powered by Kubernetes's emptyDir. emptyDir is usually backed by a directory created within a host's volume, somewhere under /var/lib/kuberntes/pods. Therefore your host's volume that is backing /var/lib/kubernetes/pods must have enough free space to serve all the concurrent runner pods that might be deployed onto your host at the same time.

So, in case you see a job failure seemingly due to "disk full", it's very likely you need to reconfigure your host to have more free space.

In case you can't rely on host's volume, consider using RunnerSet and backing the work directory with a ephemeral PV.

Kubernetes 1.23 or greater provides the support for generic ephemeral volumes, which is designed to support this exact use-case. It's defined in the Pod spec API so it isn't currently available for RunnerDeployment. RunnerSet is based on Kubernetes' StatefulSet which mostly embeds the Pod spec under spec.template.spec, so there you go.

kind: RunnerSet
metadata:
  name: example
spec:
  template:
    spec:
      containers:
      - name: runner
        volumeMounts:
        - mountPath: /runner/_work
          name: work
      - name: docker
        volumeMounts:
        - mountPath: /runner/_work
          name: work
      volumes:
      - name: work
        ephemeral:
          volumeClaimTemplate:
            spec:
              accessModes: [ "ReadWriteOnce" ]
              storageClassName: "runner-work-dir"
              resources:
                requests:
                  storage: 10Gi
jobs:
  release:
    runs-on: self-hosted
When you have multiple kinds of self-hosted runners, you can distinguish between them using labels. In order to do so, you can specify one or more labels in your Runner or RunnerDeployment spec.

apiVersion: actions.summerwind.dev/v1alpha1
kind: RunnerDeployment
metadata:
  name: custom-runner
spec:
  replicas: 1
  template:
    spec:
      repository: actions/actions-runner-controller
      labels:
        - custom-runner
Once this spec is applied, you can observe the labels for your runner from the repository or organization in the GitHub settings page for the repository or organization. You can now select a specific runner from your workflow by using the label in runs-on:

jobs:
  release:
    runs-on: custom-runner

apiVersion: actions.summerwind.dev/v1alpha1
kind: RunnerDeployment
metadata:
  name: custom-runner
spec:
  replicas: 1
  template:
    spec:
      group: NewGroup
GitHub supports custom visibility in a Runner Group to make it available to a specific set of repositories only. By default if no GitHub authentication is included in the webhook server ARC will be assumed that all runner groups to be usable in all repositories. Currently, GitHub does not include the repository runner group membership information in the workflow_job event (or any webhook). To make the ARC "runner group aware" additional GitHub API calls are needed to find out what runner groups are visible to the webhook's repository. This behaviour will impact your rate-limit budget and so the option needs to be explicitly configured by the end user.

This option will be enabled when proper GitHub authentication options (token, app or basic auth) are provided in the webhook server and useRunnerGroupsVisibility is set to true, e.g.

githubWebhookServer:
  enabled: false
  replicaCount: 1
  useRunnerGroupsVisibility: true
apiVersion: actions.summerwind.dev/v1alpha1
kind: RunnerDeployment
metadata:
  name: custom-runner
spec:
  replicas: 1
  template:
    spec:
      group: NewGroup
GitHub supports custom visibility in a Runner Group to make it available to a specific set of repositories only. By default if no GitHub authentication is included in the webhook server ARC will be assumed that all runner groups to be usable in all repositories. Currently, GitHub does not include the repository runner group membership information in the workflow_job event (or any webhook). To make the ARC "runner group aware" additional GitHub API calls are needed to find out what runner groups are visible to the webhook's repository. This behaviour will impact your rate-limit budget and so the option needs to be explicitly configured by the end user.

This option will be enabled when proper GitHub authentication options (token, app or basic auth) are provided in the webhook server and useRunnerGroupsVisibility is set to true, e.g.

githubWebhookServer:
  enabled: false
  replicaCount: 1
  useRunnerGroupsVisibility: true
nodeSelector:
  kubernetes.io/os: linux
cert-manager has 4 different application within it the main application, the webhook, the cainjector and the startupapicheck. In the parameters or values file you use for the deployment you need to add the nodeSelector property four times, one for each application.

For the actions-runner-controller you only have to use the nodeSelector only for the main deployment, so it only has to be set once.

Once this is set up, you will need to deploy two different RunnerDeployment's, one for Windows and one for Linux. The Linux deployment can use either the default image or a custom one, however, there isn't a default Windows image so for Windows deployments you will have to build your own image.

Below we share an example of the YAML used to create the deployment for each Operating System and a Dockerfile for the Windows deployment.

Windows
RunnerDeployment

---
apiVersion: actions.summerwind.dev/v1alpha1
kind: RunnerDeployment
metadata:
  name: k8s-runners-windows
  namespace: actions-runner-system
spec:
  template:
    spec:
      image: <repo>/<image>:<windows-tag>
      dockerdWithinRunnerContainer: true
      nodeSelector:
        kubernetes.io/os: windows
        kubernetes.io/arch: amd64
      repository: <owner>/<repo>
      labels:
        - windows
        - X64
Dockerfile

Note that you'd need to patch the below Dockerfile if you need a graceful termination. See https://github.com/actions/actions-runner-controller/pull/1608/files#r917319574 for more information.
FROM mcr.microsoft.com/windows/servercore:ltsc2019

WORKDIR /actions-runner

SHELL ["powershell", "-Command", "$ErrorActionPreference = 'Stop';$ProgressPreference='silentlyContinue';"]

RUN Invoke-WebRequest -Uri https://github.com/actions/runner/releases/download/v2.292.0/actions-runner-win-x64-2.292.0.zip -OutFile actions-runner-win-x64-2.292.0.zip

RUN if((Get-FileHash -Path actions-runner-win-x64-2.292.0.zip -Algorithm SHA256).Hash.ToUpper() -ne 'f27dae1413263e43f7416d719e0baf338c8d80a366fed849ecf5fffcec1e941f'.ToUpper()){ throw 'Computed checksum did not match' }

RUN Add-Type -AssemblyName System.IO.Compression.FileSystem ; [System.IO.Compression.ZipFile]::ExtractToDirectory('actions-runner-win-x64-2.292.0.zip', $PWD)

RUN Invoke-WebRequest -Uri 'https://aka.ms/install-powershell.ps1' -OutFile install-powershell.ps1; ./install-powershell.ps1 -AddToPath

RUN powershell Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))

RUN powershell choco install git.install --params "'/GitAndUnixToolsOnPath'" -y

RUN powershell choco feature enable -n allowGlobalConfirmation

CMD [ "pwsh", "-c", "./config.cmd --name $env:RUNNER_NAME --url https://github.com/$env:RUNNER_REPO --token $env:RUNNER_TOKEN --labels $env:RUNNER_LABELS --unattended --replace --ephemeral; ./run.cmd"]
Linux
RunnerDeployment

---
apiVersion: actions.summerwind.dev/v1alpha1
kind: RunnerDeployment
metadata:
  name: k8s-runners-linux
  namespace: actions-runner-system
spec:
  template:
    spec:
      image: <repo>/<image>:<linux-tag>
      nodeSelector:
        kubernetes.io/os: linux
        kubernetes.io/arch: amd64
      repository: <owner>:<repo>
      labels:
        - linux
        - X64

kind: Secret
data:
  github_app_id: ...
  github_app_installation_id: ...
  github_app_private_key: ...
---
kind: RunnerDeployment
metadata:
  namespace: org1-runners
spec:
  template:
    spec:
      githubAPICredentialsFrom:
        secretRef:
          name: org1-github-app
---
kind: HorizontalRunnerAutoscaler
metadata:
  namespace: org1-runners
spec:
  githubAPICredentialsFrom:
    secretRef:
      name: org1-github-app
apiVersion: actions.summerwind.dev/v1alpha1
kind: RunnerDeployment
metadata:
  name: example-runnerdeployment
spec:
  template:
    spec:
      env:
        # Disable various runner entrypoint log levels 
        - name: LOG_DEBUG_DISABLED
          value: "true"
        - name: LOG_NOTICE_DISABLED
          value: "true"
        - name: LOG_WARNING_DISABLED
          value: "true"
        - name: LOG_ERROR_DISABLED
          value: "true"
        - name: LOG_SUCCESS_DISABLED
          value: "true"
        # Issues a sleep command at the start of the entrypoint
        - name: STARTUP_DELAY_IN_SECONDS
          value: "2"
        # Specify the duration to wait for the docker daemon to be available
        # The default duration of 120 seconds is sometimes too short
        # to reliably wait for the docker daemon to start
        # See https://github.com/actions/actions-runner-controller/issues/1804
        - name: WAIT_FOR_DOCKER_SECONDS
          value: 120
        # Disables the wait for the docker daemon to be available check
        - name: DISABLE_WAIT_FOR_DOCKER
          value: "true"
        # Disables automatic runner updates
        # WARNING : Upon a new version of the actions/runner software being released 
        # GitHub stops allocating jobs to runners on the previous version of the
        # actions/runner software after 30 days.
        - name: DISABLE_RUNNER_UPDATE
          value: "true"
There are a few advanced envvars also that are available only for dind runners:

apiVersion: actions.summerwind.dev/v1alpha1
kind: RunnerDeployment
metadata:
  name: example-runnerdeployment
spec:
  template:
    spec:
      dockerdWithinRunnerContainer: true
      image: summerwind/actions-runner-dind
      env:
        # Sets the respective default-address-pools fields within dockerd daemon.json
        # See https://github.com/actions/actions-runner-controller/pull/1971 for more information.
        # Also see https://github.com/docker/docs/issues/8663 for the default base/size values in dockerd.
        - name: DOCKER_DEFAULT_ADDRESS_POOL_BASE
          value: "172.17.0.0/12"
        - name: DOCKER_DEFAULT_ADDRESS_POOL_SIZE
          value: "24"
More options can be configured by mounting a configmap to the daemon.json location:

rootless: /home/runner/.config/docker/daemon.json
rootful: /etc/docker/daemon.json
apiVersion: actions.summerwind.dev/v1alpha1
kind: RunnerDeployment
metadata:
  name: example-runnerdeployment
spec:
  template:
    spec:
      dockerdWithinRunnerContainer: true
      image: summerwind/actions-runner-dind(-rootless)
      volumeMounts:
        - mountPath: /home/runner/.config/docker/daemon.json
          name: daemon-config-volume
          subPath: daemon.json
      volumes:
        - name: daemon-config-volume
          configMap:
            name: daemon-cm
            items:
              - key: daemon.json
                path: daemon.json
      securityContext:
        fsGroup: 1001 # runner user id
apiVersion: v1
kind: ConfigMap
metadata:
  name: daemon-cm
data:
  daemon.json: |
    {
      "log-level": "warn",
      "dns": ["x.x.x.x"]
    }
# dindrunnerdeployment.yaml
apiVersion: actions.summerwind.dev/v1alpha1
kind: RunnerDeployment
metadata:
  name: example-dindrunnerdeploy
spec:
  replicas: 1
  template:
    spec:
      image: summerwind/actions-runner-dind
      dockerdWithinRunnerContainer: true
      repository: mumoshu/actions-runner-controller-ci
      env: []
Runner with rootless DinD

When using the DinD runner, it assumes that the main runner is rootful, which can be problematic in a regulated or more security-conscious environment, such as co-tenanting across enterprise projects. The actions-runner-dind-rootless image runs rootless Docker inside the container as runner user. Note that this user does not have sudo access, so anything requiring admin privileges must be built into the runner's base image (like running apt to install additional software).

Runner with K8s Jobs

When using the default runner, jobs that use a container will run in docker. This necessitates privileged mode, either on the runner pod or the sidecar container

By setting the container mode, you can instead invoke these jobs using a kubernetes implementation while not executing in privileged mode.

The runner will dynamically spin up pods and k8s jobs in the runner's namespace to run the workflow, so a workVolumeClaimTemplate is required for the runner's working directory, and a service account with the appropriate permissions.

There are some limitations to this approach, mainly job containers are required on all workflows.

# runner.yaml
apiVersion: actions.summerwind.dev/v1alpha1
kind: Runner
metadata:
  name: example-runner
spec:
  repository: example/myrepo
  containerMode: kubernetes
  serviceAccountName: my-service-account
  workVolumeClaimTemplate:
    storageClassName: "my-dynamic-storage-class"
    accessModes:
    - ReadWriteOnce
    resources:
      requests:
        storage: 10Gi
  env: []

metrics:
  serviceAnnotations: {}
  serviceMonitor: false
  serviceMonitorLabels: {}
+ port: 8080
  proxy:
+   enabled: false
If Prometheus is available inside the cluster, then add some podAnnotations to begin scraping the metrics:

podAnnotations:
+ prometheus.io/scrape: "true"
+ prometheus.io/path: /metrics
+ prometheus.io/port: "8080"







     
      
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



