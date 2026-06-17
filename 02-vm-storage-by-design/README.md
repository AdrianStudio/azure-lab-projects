Scenario 1:

A small logistics company has a Linux VM in Azure that processes files uploaded by clients to a Storage Account. The VM runs a daily job that reads new files, processes them, and writes the results back as blobs. The company's security policy explicitly forbids hardcoded credentials or long-lived secrets stored in code or VM environment variables. The team is small and has no time to manage manual secret rotation.

Question:

What authentication mechanism do you choose for the VM to access the Storage Account?

Options:

A) Store the Storage Account connection string in /etc/environment on the VM. The processing script reads it on startup.
B) Generate a SAS token with one-year expiration and read/write permissions on the blob container. Embed the SAS in the application configuration file.
C) Enable a system-assigned Managed Identity on the VM. Assign the Storage Blob Data Contributor RBAC role to that identity, scoped to the Storage Account. The script calls az login --identity before reading or writing blobs.
D) Create a Service Principal in Entra ID. Store its client secret in Azure Key Vault. The VM authenticates to Key Vault, retrieves the secret, and uses it to authenticate to the Storage Account.

Anwer:

A) I would not opt for option A, because client requested for 2 main things: The password to not be hardcoded anywhere, and for the process to be easy as its a small company with no time to manage secret rotations. Due to the password being sotred in /etc/environment this automatically discards option A.

B) I would not opt for option B either, same as before, even tho the token is managed via SAS, its still stored, and it also skips rule 2, no manual secret rotation, which is something you have to do every year, or if someone gets acces to that key and they shouldnt, so this option is discarded.

C) I would opt for this option. Why? It meets the clients request. Password is not hardcoded stored anywhere. The environment is configured via MI on the VM, meaning that the VM uses Managed Identity to communicate with the secret in order to allow for employees to acces. This meets both expectations, no hardcoded keys, no manual secret rotation. This is the best and correct option.

D) Many people would choose this option, I did too at one point, but its not the best option. This may seem correct since the password is not hardcoded anywhere, but it has an expiry date, 1 or 2 years, then someone has to rotate it manually, which completely defeats the expectations that the client had. And finally, if the secret gets leaked, anyone can use it from any VM. 
Veredict:

Option C is better, an SP secret can get leaked, causing anyone being able to access from anywhere, if the MI gets "leaked" (it can't actually), its only usable from one specific machine. It meets clients expectations, and thats always the offer you want to give.

