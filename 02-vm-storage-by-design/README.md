Scenario 1:

A small logistics company has a Linux VM in Azure that processes files uploaded by clients to a Storage Account. The VM runs a daily job that reads new files, processes them, and writes the results back as blobs. The company's security policy explicitly forbids hardcoded credentials or long-lived secrets stored in code or VM environment variables. The team is small and has no time to manage manual secret rotation.

Question:

What authentication mechanism do you choose for the VM to access the Storage Account?

Answers and decisions on: 

