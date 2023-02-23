# Miscellaneous utilities

## sendmail-gpg-wrapper

This is a script that accepts:

- The from-address, to-address, and subject as arguments
- The message body from stdin

The script encrypts the message body with `gpg -ea -r to-address` and pipes the
result to sendmail, with the To:, From:, and Subject: headers preceding the
GPG-encrypted message. (Postfix's `sendmail` does not accept a subject line as
an argument.)

Usage: `sendmail-gpg-wrapper from@domain.com to@domain.com "Email subject"`
