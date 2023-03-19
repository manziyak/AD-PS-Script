# AD-PS-Script
# AD accounts set to no expiration date
# Set the base DN to search from
$base_dn = "DC=yourdomain,DC=com"

# Get all user accounts with no expiration date set
$users = Get-ADUser -Filter { accountExpires -eq 0 } -SearchBase $base_dn

# Print the list of users with no expiration date set
Write-Host "List of AD accounts set with no expiration date:"
foreach ($user in $users) {
    Write-Host $user.SamAccountName
}
