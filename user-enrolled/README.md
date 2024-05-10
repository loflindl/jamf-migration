To use this script you will need an Enrollment Invitation in the destination Jamf, configured to not require login.
The script will use this to download the enrollment profile, to install the new MDM Profile.

1. Add the script to the source Jamf
2. Add a policy to run the script
* Parameter 4: Invitation ID for the no-login Enrollment Invitation (last part of the invite URL, or listed in Enrollment Invitations)
* Parameter 5: Destination Jamf server - e.g newjamf.jamfcloud.com
* Parameter 6: Source Jamf server, for using the API to remove MDM
* Parameter 7: Source Jamf api auth - "user:password" (without quotes) which has been base64-encoded
   * The API account must have permissions to permissions to Create/Read/Update Computers, Flush MDM Commands, and send the Computer Unmanage command
3. Scope the policy to Macs you wish to migrate.  It's probably best to run it from Self Service rather than at check-in.
