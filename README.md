# list-mobile-users

# This script is to extract list of Mobile User from the machine, you can use this in JAMF Pro, under extension attributes.

#!/bin/bash
localAccounts=$(dscl . list /Users UniqueID | awk '$2 > 1000 { print $1 }')

echo "<result>${localAccounts}</result>"
