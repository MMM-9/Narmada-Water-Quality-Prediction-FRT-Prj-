# Narmada-Water-Quality-Prediction-FRT-Prj


Step 1:
Login and Open your azure Education Default Directory and go to create resource.


![Screenshot (479)](https://user-images.githubusercontent.com/63444165/156872307-b8629a1a-8617-4b6a-bf8f-912a9278d12f.png)


This opens the login page.


![Screenshot (480)](https://user-images.githubusercontent.com/63444165/156872344-d703b2ed-45de-4726-ba77-76eff4cb163b.png)


After login, you land up on this page. You can also see your account details here.


![Screenshot (481)](https://user-images.githubusercontent.com/63444165/156872373-49025eae-9aae-427a-aac1-5a208b75dbc6.png)


![image](https://user-images.githubusercontent.com/63444165/155882999-16b8eaf6-e2bf-49c7-ac5b-566a931486f5.png)




Step 2:
Type Azure ML and click on create, fill in all the details and click on review+create.Finally, click on create.
You can see your workspace created.


![image](https://user-images.githubusercontent.com/63444165/155883102-1847dab3-b627-43cd-a620-933c7b8e22b9.png)




Step3:
Click on Launch studio.


![Screenshot (482)](https://user-images.githubusercontent.com/63444165/156872430-1d922615-0192-410c-8fb7-e826c48d7de1.png)


![Screenshot (476)](https://user-images.githubusercontent.com/63444165/156872456-fb9f40e0-2855-4f2e-bafd-106b3e9ae938.png)




Step 4: 
Go to compute and create new compute instance, fill in all the required details.


![image](https://user-images.githubusercontent.com/63444165/156882359-c5ff4216-4817-4e30-8434-3560c85fb792.png)


![image](https://user-images.githubusercontent.com/63444165/156882420-aedd8924-3d9e-49d8-8ccf-bc6e63ad013c.png)




 
Step 5: While it takes time to create the instance we go to the following Website:
https://data.gov.in/resources/water-quality-river-narmada-and-its-tributaries-2008
and download the data in xlsx format. Since Azure ML Studio does not support data in xlsx format we convert it to .csv format using the py script given in the repo.


![image](https://user-images.githubusercontent.com/63444165/155883335-057148d7-6e68-4d8e-b123-ad537f9ad8d5.png)


![image](https://user-images.githubusercontent.com/63444165/155883371-e7a3adf5-8afd-4f3f-869f-4f72c672834e.png)




Step 6: As we can see the compute instance is created.


![image](https://user-images.githubusercontent.com/63444165/155883455-efe6abb0-f7d3-467e-b8f8-a40d3dba30cc.png)


![image](https://user-images.githubusercontent.com/63444165/156882620-a0dcc0b3-72f3-4070-bf49-6c98189fc516.png)


And it is running.


![Screenshot (483)](https://user-images.githubusercontent.com/63444165/156872687-a73de097-71fa-4721-90e9-08bcf0f870b7.png)





Step 7:
We name the downloaded dataset as book.xlsx and convert it to csv format and upload that csv to the datasets.
For simplicity, as of now we are scrapping other information and only including the Min, Max and Mean data of the Temp and D.O. in out data alongwith the Station Code.
Go to datasets create new and fill in all the details


![image](https://user-images.githubusercontent.com/63444165/156883146-69dfb426-e44a-49d4-9b4f-c16f16e692a4.png)


![image](https://user-images.githubusercontent.com/63444165/155883566-ab1d9939-9db9-4ea7-9701-c181e8a2f6a7.png)


![image](https://user-images.githubusercontent.com/63444165/156883196-235ffdff-6311-4c70-b6df-e85bdee9be06.png)


![image](https://user-images.githubusercontent.com/63444165/155883585-739b8c9f-688c-426c-8499-eb600c3d2b00.png)


we can see the preview of the data set here. Also the schema can be shown here.


![image](https://user-images.githubusercontent.com/63444165/155883624-6ec4a78b-ac91-4bd2-9a79-8b79c70ca455.png)


![image](https://user-images.githubusercontent.com/63444165/155883683-b7106a37-c27b-4c60-8d41-b6e96c48eb7e.png)




Step 8:
Now we go to pipelines and fill in all details and create new pipeline.


![image](https://user-images.githubusercontent.com/63444165/156883099-502c4187-2540-4c6a-8e1f-51350c267440.png)




Step 9:
We choose our dataset by searching the name "Book".


![image](https://user-images.githubusercontent.com/63444165/155883807-addfa35b-cb4c-4335-ba0f-bc7a5a588d6e.png)


![image](https://user-images.githubusercontent.com/63444165/156883273-5c2636e9-6fa5-4612-a200-5d7b5e8a6090.png)




Step 10:
We need to normalize the dataset to remove null entries or duplicate entries.


![image](https://user-images.githubusercontent.com/63444165/156883483-ab1ea711-b423-4918-ab9a-46491ddb01b0.png)


![image](https://user-images.githubusercontent.com/63444165/156883549-dab42bf1-1431-45bf-83af-d95ef0ff07cf.png)


![image](https://user-images.githubusercontent.com/63444165/155883839-da2e90bd-e569-4a9c-9404-b1a1d8282e31.png)




Step 11: 
Now we start building our pipeline.


We connect book to normalize data module and then will edit its properties.


![image](https://user-images.githubusercontent.com/63444165/155883884-db8e4ca5-c5f5-4af0-b5d3-aa8012d5969b.png)


![image](https://user-images.githubusercontent.com/63444165/155883898-d738fd26-96a1-4e8f-9add-7039bbbaef50.png)


we connect the nomalized data to split data for training and testing purpose.


![image](https://user-images.githubusercontent.com/63444165/155883927-ed141d38-e72b-4677-8bbb-37c1e3bd8e51.png)


we connect the respective ML Algorithm Modules for one training datset we only connected it to Decision Forest, for another we will connect it to SVM as well as Decision
Forest


![image](https://user-images.githubusercontent.com/63444165/155884001-d2db0689-eb0b-4cd2-8a7c-fc3f1b73cf76.png)


Also we set the parameters as per our need


![image](https://user-images.githubusercontent.com/63444165/156883630-40801ae7-bfb5-4b19-8811-12be2d659b0e.png)


We connect the Score Model to split data as well as to Train Model.Then we connect it to respective evaluation Modules and then we add those rows to the set.


![image](https://user-images.githubusercontent.com/63444165/155884143-2b7fe373-4fae-4f74-9f2c-091a7be7ebb2.png)


The whole pipeline looks something like this:


![image](https://user-images.githubusercontent.com/63444165/155884176-9bd8db75-3cc6-485a-a261-056517af2711.png)


![image](https://user-images.githubusercontent.com/63444165/156883672-6585c0a1-850a-4f66-9e09-703fefc82f1a.png)




Step 12:
Now we click on submit to run the model.


![image](https://user-images.githubusercontent.com/63444165/155884228-18a01734-237a-45f1-8fe9-b4d85c63e453.png)




Step 13: 
Fill in all the details


![image](https://user-images.githubusercontent.com/63444165/155884262-17e9fe72-a74e-4030-a46e-9fcbb5b46b4a.png)


![image](https://user-images.githubusercontent.com/63444165/156883814-2ecd6219-e06b-4cd1-b0b6-5fc2f8d04bea.png)




Step 14:
Upon Submission, the pipelines would start running and we can see something like this:


![image](https://user-images.githubusercontent.com/63444165/156883842-3d19a240-a1f3-4da3-b301-5c6ae7342e41.png)


![image](https://user-images.githubusercontent.com/63444165/155884295-4001cd55-905d-4168-aa7c-0763643652c7.png)




Step 15:
The Pipeline Run is Completed. 


![image](https://user-images.githubusercontent.com/63444165/155884329-6bb59910-88d9-4dee-8d9a-17594811ffed.png)





Step 16:
Now we can publish the pipeline.


![image](https://user-images.githubusercontent.com/63444165/155884402-6afe93d5-a596-4676-9b03-6d01fe410bc4.png)


![image](https://user-images.githubusercontent.com/63444165/156884513-146a6967-8f36-4b56-a915-219f8e0a2b62.png)



The overall project looks something like this:


![Screenshot (478)](https://user-images.githubusercontent.com/63444165/156882223-8f2939e7-a380-49a6-814b-f8f9b3909c3a.png)





Step 17:
We can also preview the results dataset


![image](https://user-images.githubusercontent.com/63444165/155884367-1192c95d-5126-4600-8bb0-752968c16d58.png)




Step 18:
so that's it , we can share the URL to the FRT platform from Experiments.


![image](https://user-images.githubusercontent.com/63444165/155884408-9b4b80f2-be0d-4ba8-ab8f-4dca1730253c.png)


![image](https://user-images.githubusercontent.com/63444165/156884561-b03a9b49-721e-4f2f-82f5-9a4d990b0a0b.png)



Thank you so much for Reading. This was my first Azure ML studio Project so do let me know if I have made any mistakes. 
Also do let me know if there is a way of importing the ML pipelines to github or in python code.


# Project URL in azure:
https://ml.azure.com/experiments/id/ed245e9e-b96e-4e15-89b6-952fd1cceede?wsid=/subscriptions/a1d86d4a-3f8d-44bd-986f-aff9f795abcb/resourcegroups/AzureML/workspaces/FutureReadyTalent&tid=e8e002e4-11bb-4d6a-9b3a-59adcd55c79e



# Link for Video:
https://drive.google.com/file/d/1ZFV3P2Pj0WtR3X98p7e6cH0uLdUaDYGY/view?usp=sharing


Bibliography and References:
https://futurereadytalent.in/learning
https://www.google.com/search?q=how+to+migrate+a+Azure+ML+studio+project+to+github+repo&rlz=1C1CHZN_enIN932IN932&ei=2i4bYuXvPICXseMP67Oe4AE&ved=0ahUKEwjlxNS9tJ_2AhWAS2wGHeuZBxwQ4dUDCA4&uact=5&oq=how+to+migrate+a+Azure+ML+studio+project+to+github+repo&gs_lcp=Cgdnd3Mtd2l6EAM6BwgAEEcQsAM6BAghEApKBAhBGABKBAhGGABQ1wJY8yFgiCVoAXABeACAAaICiAHAF5IBBjAuNC4xMJgBAKABAcgBCMABAQ&sclient=gws-wiz
https://www.c-sharpcorner.com/UploadFile/f55fd9/prediction-of-water-quality-in-river/
https://docs.microsoft.com/en-us/azure/developer/
https://docs.microsoft.com/en-us/azure/machine-learning/how-to-deploy-pipelines
https://github.com/Azure/MachineLearningNotebooks/blob/master/how-to-use-azureml/machine-learning-pipelines/README.md
https://data.gov.in/resources/water-quality-river-narmada-and-its-tributaries-2008

