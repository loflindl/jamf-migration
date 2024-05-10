The script to migrate a Mac as prestage-enrolled requires that the Mac be reassigned to the destination Jamf first, ie in ASM/ABM.  The Mac must be assigned to a Prestage Enrollment in the destination Jamf.

1. Add the script to the source Jamf
2. Add a policy to run the script
* Parameter 4: Source Jamf server, for using the API to remove MDM
* Parameter 5: Source Jamf api auth - "user:password" (without quotes) which has been base64-encoded
  * The API account must have permissions to permissions to Create/Read/Update Computers, Flush MDM Commands, and send the Computer Unmanage command
* Parameter 6 (optional): Destination Jamf server, for using the API to check if the computer is assigned to a prestage
* Parameter 7 (optional): Destination Jamf api auth - "user:password" (without quotes) which has been base64-encoded
  * The API account needs read-only access to computers and prestages only 
3. Scope the policy to Macs you wish to migrate.  It's probably best to run it from Self Service rather than at check-in.
