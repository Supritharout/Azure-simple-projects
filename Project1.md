#Host a Static Website using Azure Blob Storage

Requirement:

Azure Free Account
Azure Portal
Basic HTML and CSS files

Step 1: Create a Storage Account

1. Login to Azure Portal.
2. Search Storage Account.
3. Click Create. 

Subscription           :  Azure subscription 1
Resource group         :  Azure-RG
Location               :  Central India
Storage account name   :  suprithawebsite
Primary service        :  Azure Blob Storage or Azure Data Lake Storage
Performance            :  Standard
Replication            :  Locally redundant storage (LRS)

4. Review and create.

Step2: Enable static website hosting

1. select your storage account
2. go to data management on the left panel
3. select static website
4. click enable
5. give index.html as document name and error.html in error document path. 
6. save 

Step3: Upload the files

1. select your storage account
2. go to data storage and select containers
3. you will see the default container name as $web

Step4: create html and css file and store in your local (index.html and style.css) Take any html and css code of your choice from internet.

Step5: Uploadings of file in the container.

1. select $web container
2. click on upload.
3. select your html and css file and upload

Step6: Open the website

1. Return to static website page under data management 
2. You will see primary end point, copy the url and paste in your browser.
