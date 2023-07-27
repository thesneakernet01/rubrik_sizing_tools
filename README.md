# rubrik_sizing_tools

How to Use:

RVTools
Download RVTools from here: https://github.com/thesneakernet01/rubrik_sizing_tools/blob/main/RVTools4.4.3.zip

Run and connect to your vCenter Server.  Save all data to a single excel spreadsheet.

M365 PowerShell Script

Launch Powershell (needs >= v5.1)
Run the following in powershell: Install-Module Microsoft.Graph.Reports, Microsoft.Graph.Groups, ExchangeOnlineManagement

Download Script from here: https://github.com/rubrikinc/microsoft-365-sizing/blob/main/Get-RubrikM365SizingInfo.ps1

Run the powershell script and authenticate microsoft azure.  The script with then leverage the Microsoft Graph API to generate an HTML report saved in the same folder as the script is run from.
./Get-RubrikM365SizingInfo.ps1

If you wish to run the script against only on group in Azure AD use the following:

./Get-RubrikM365SizingInfo.ps1 -AzureAdGroupName "RubrikEmployees"

The majority of the information collected is directly from the Microsoft 365 Usage reports that are found in the admin center. The benefit of this approach is that the information can be pulled in bulk and does not require a complete crawl of your Microsoft 365 subscription.

The only downside of this approach is that the Usage reports do not contain any In-Place archive information. To gather that information Rubrik will request a separate set of permissions to pull statistics for each In-Place archive in your environment. Depending on the size of you environment, this can take a significant amount of time.
