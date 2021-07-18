# GCP Setup For Serverless Function

```
$ gcloud auth login
```

> Create a new project and set this project as the current context
```
$ gcloud projects create sudswastik-function
$ gcloud config set project sudswastik-function
```

> Enable Cloud build API

>  Enable Billing 
```
$ gcloud services enable cloudbuild.googleapis.com
```

> Create the functions project and deploy
```
$ gcloud functions deploy mock-json --entry-point=mockjson  --region=us-central1  \
--memory=256MB  --runtime=nodejs14 --trigger-http \ --allow-unauthenticated
```

> Test the function

```
$ gcloud functions call mock-json
```