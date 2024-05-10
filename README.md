# Migrating a Mac from one Jamf server to another

To consolidate on one Jamf instance, or migrate from on-prem Jamf to cloud Jamf, you either have to re-enroll your Macs manually, or find a way to migrate them.

Macs can be migrated from one Jamf to another by setting up one of these two scripts to handle the migration and using a policy in the source Jamf to run the script.

* jamf-migrate-to-user-enrolled
* jamf-migrate-to-prestage-enrolled

Both scripts will remove the existing MDM profile, then enroll the Mac in the destination Jamf.  As the names indicate, the end result is a user-enrolled Mac or a prestage-enrolled Mac.  
It doesn't matter if the Mac was originally prestage-enrolled or user-enrolled - both scripts can use the Jamf API to remove the MDM Profile on prestage-enrolled Macs when the profile is marked non-removable.

Both will require the end-user to enter their password in order to install the new MDM Profile.  There's no way around that, Apple doesn't allow automating that part.
However the scripts will temporarily elevate the console user to Admin (if they are not already) - then demote them back to Standard when finished.

Since user interaction is required, the scripts will prompt the user with instructions - and, re-prompt in some cases (e.g to click "Install" on the profile).  There are "DIALOG_" variables at the top that can be used to customize the messages for your organization.

More details including screenshots of the user experience: https://wikis.utexas.edu/display/~loflindl/Migrating+a+Mac+from+one+Jamf+server+to+another
