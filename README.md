Parallel Delete Azure RM Virtual Machine-NIC-Disks (Updated Sept 2019)
======================================================================

            

Parallel Delete Virtual Machines in Azure:


This script will delete an Azure Resource manager Virtual Machine.


- It will also delete the associated Network Interface Card (NIC).


- optionally delete the public ip address.


- It will also remove both STANDARD and MANAGED Disks.


   - Including both the OSDisk and the DATADisks.


------------------


This function assumes a few things in relation to the storage of the STANDARD disks, which is that they all use the SAME storage account. 


If your DATA Disks use different storage accounts than your OSDisks, then you need to update the function accordingly.


------------------


You also need to make sure you  first log in and then SAVE YOUR CONTEXT


 


OR you can even use:


enable-azcontextautosave


then login


login-azaccount


plus ensure you have the correct subscription selected


get-azsubscription


select-azsubscription -id {guid}


Then you don't need to save your context plus you can update 
this line





Try {
                $ctx = Import-AzureRmContext -path $home\ctx.json -ErrorAction Stop





To




Try {
                $ctx = get-azcontext




 


-----------------------------------------------------------------------


- Added a delay in the loop to stop locks on TokenCache.dat


- fixed issue with Disk names


 



        
    
TechNet gallery is retiring! This script was migrated from TechNet script center to GitHub by Microsoft Azure Automation product group. All the Script Center fields like Rating, RatingCount and DownloadCount have been carried over to Github as-is for the migrated scripts only. Note : The Script Center fields will not be applicable for the new repositories created in Github & hence those fields will not show up for new Github repositories.
