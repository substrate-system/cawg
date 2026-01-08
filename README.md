# Browser-Native Provenance

Prove the provenance (creator and creation time) of data on the web.

How do you know who originally wrote a blog post, or took a photograph?
The web has no native mechanism for verifying authorship, integrity, or
creation time. This is exacerbated by AI, because now there is no way to be
certain that something was created by a human.


## Solution

We can use _good old-fashioned_ asymmetric cryptography to sove this &mdash;
a _browser-native cryptography toolkit_ for identity, signing, and provenance.

Modern browsers support `WebCrypto`, which gives us a way to sign and
verify things, but _time_ is still an unknown. Verifying that
a given private key signed something is trivial, but how do we know _when_
it was signed? Anyone can write any timestamp they want.
We need another way to prove time in relation to signatures.

One solution is Bitcoin. A blockchain solves global timestamping and
ordering, without trusted parties. Bitcoin is the only widely deployed,
permissionless global timestamping system.

Another solution is [RFC 3161](https://www.ietf.org/rfc/rfc3161.txt), or
[trusted timestamping](https://en.wikipedia.org/wiki/Trusted_timestamping).
A trusted third party is introduced who will vouch that the timestamp
is legitimate.


## Formats

The [Creator Assertions Working Group (CAWG)](https://cawg.io/) is extending
the [C2PA specification](https://c2pa.org/) to make
[additional claims about content](https://cawg.io/faq/#_what_are_creator_assertions).
This project would use the CAWG specifications to create unforgable proof of
existence &mdash; proof that an artifact existed no later than a given time.

### rfc 3161

See [IETF page](https://www.ietf.org/rfc/rfc3161.txt).

### `OP_RETURN`

Store arbitrary data on Bitcoin blockchain.

See [bitcoin.it wiki](https://en.bitcoin.it/wiki/OP_RETURN).

## See Also

* [List of free rfc3161 servers](https://gist.github.com/Manouchehri/fd754e402d98430243455713efada710)
* [Trusted Timestamping - Wikipedia](https://en.wikipedia.org/wiki/Trusted_timestamping)
* [Creator Assertions Working Group](https://cawg.io/)
* [Coalition for Content Provenance and Authenticity (C2PA)](https://c2pa.org/)
