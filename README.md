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
`ean-iago-deploy` branch - our version of master with two extra files: manifest.json and README-EAN.md

`README-EAN.md` is the file you are reading now. `manifest.json` is required for EAN deployments to work.

Maintenance of EAN's fork of Iago
---------------------------------

New commits from Twitter's repo should be periodically merged into the master branch of EAN's forked Iago repo. The changes can then be merged from EAN's master branch into the ean-iago-deploy branch. When the ean-iago-deploy branch is pushed into the ExpediaInc github repo the Bamboo build will create a new version of the distribution, see below. 

Bamboo build
------------

See https://bamboo.ean/browse/PLATFORM-IAGO

Bamboo is used to build the ean-iago-deploy branch of EAN's Iago fork. The build creates the ean-iago distribution and
uploads it to Amazon S3. Once uploaded to S3 it is then ready for deployment using Chef. 
