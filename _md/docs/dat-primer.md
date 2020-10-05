## A Quick Primer on DWebX

[DWebX](https://dwebx.foundation) is a peer-to-peer protocol for publishing files. It uses cryptography to sign and verify all information. Like BitTorrent, users can "seed" data to help keep it online and contribute bandwidth.

Each "dwebx" is given a public key address which looks like this:

> <a href="dwebx://43dfc9f23fdded8cc7c01c71c0702a0529130af0258e7fb30bf5a0a3f73d69b3/">dwebx://43dfc9f23fdded8cc7c01c71c0702a0529130af0258e7fb30bf5a0a3f73d69b3/</a>

The public key is a 64-character hex string, but DNS may be used to provide a human-readable shortname:

> <a href="dwebx://dwebx.foundation/">dwebx://dwebx.foundation/</a>

DWebX is a highly flexible protocol. It can sync many kinds of data, including event logs and key-value databases. However, the most common usecase is to share filesets which are called "hyperdrives."

Applications like the [DBrowserX Browser](https://dbrowser.com) use DWebX hyperdrives as websites. Users can browse to the hyperdrives and view the HTML/CSS/JS just like any HTTP website. Because anybody can create a ddrive by simply creating a new public key, users on the DWebX Web can freely create and publish their own websites.