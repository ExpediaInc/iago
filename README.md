EAN's fork of Twitter's Iago repo
=================================

The fork exists to make the Twitter iago distribution deployable using EAN's deployment process, see
https://confluence/display/EAN/EAN+Continuous+Delivery

Use the ean-iago Chef role to apply the ean-iago recipe to a node. See ean-iago-cookbook.

Twitter's Iago repo
-------------------

See https://github.com/twitter/iago/

Unfortunately it seems that Twitter does not publish the iago and iago distribution artifacts to a Maven repository. 

EAN's (forked) Iago repo
------------------------

See https://github.com/ExpediaInc/iago

`master` branch - a direct copy of the Twitter maintained repo that we forked.

`manifest` branch:

- `README-EAN.md` is the file you are reading now. 
- `manifest.json` is required for EAN deployments to work.
- `.gitignore`

Other branches are topic branches for developing new Iago features.

Maintenance of EAN's fork of Iago
---------------------------------

New commits from Twitter's repo should be periodically merged into the master branch of EAN's forked Iago repo.

Bamboo build
------------

See https://bamboo.ean/browse/PLATFORM-IAGO

Bamboo is used to build the manifest branch and either the master branch or any topic branch from EAN's Iago fork. 
The build creates the ean-iago distribution and uploads it to Amazon S3. Once uploaded to S3 it is then ready for 
deployment using Chef. 
