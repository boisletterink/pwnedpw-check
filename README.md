This is a script to check if a password has already been seen online by Troy
Hunt's /haveibeenpwned/ service. This service contains a huge amount of known
passwords and matching account names or email addresses associated with it.

Usage: run the script and enter the password to test twice.

This scripts attempts to keep your password secret by sending only the first
5 digits of the hash (ie. 20 bits) to the site's web API. The site API will
then return all known hashes in this group. Typically, it'll yield about 450
hashes of known passwords that have a hash starting with those 5 digits. The
site won't know if your actual password was found, nor will it know the
complete hash.

Keep in mind that if your password has not yet been found but it is easy to
find (eg. it is a dictionary word), a malicious person seeing your request
on the site may still find your password, but will not have certainty he
found your actual password. To minimize the risk of interception, we use
HTTPS for the API lookup.
