.. This Source Code Form is subject to the terms of the Mozilla Public
.. License, v. 2.0. If a copy of the MPL was not distributed with this
.. file, You can obtain one at http://mozilla.org/MPL/2.0/.

View Restore Scripts for Staging
================================

This directory contains SQL scripts for views which depend on matviews, and generally fail to load during backup/restore as part of the MiniDB database-shrinking process.  The new LoadMiniDB.py script will load these views, one at a time, at the end of restoring the database.

If loadMiniDB.py does not run these scripts because it cannot find the file location, then they can be run with the one-line shell script, loadviews.sh:

loadviews.sh {databasename}

Default databasename is "breakpad".  This script must be run as the database superuser.

