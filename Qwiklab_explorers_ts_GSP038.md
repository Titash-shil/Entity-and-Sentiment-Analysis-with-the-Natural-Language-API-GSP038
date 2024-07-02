# Entity and Sentiment Analysis with the Natural Language API || [GSP038](https://www.cloudskillsboost.google/course_templates/667/labs/461610) ||

# # Like, comment, share & Don't forget to subscribe [Qwiklab_Explorers_ts](https://youtube.com/@titashshil?si=RgamNu1dc9jVIbJN) 👍😄🤝


* ### CREATE AN API_KEY > APIs & Services > Credentials > Create Credentials > API key
## Run in cloudshell 
```cmd
gcloud beta compute ssh  linux-instance
```
### Press Y Enter > Enter > Enter > Press N Enter
```cmd
gcloud services enable apikeys.googleapis.com
gcloud alpha services api-keys create --display-name="Qwiklab_Explorers_TS" 
KEY_NAME=$(gcloud alpha services api-keys list --format="value(name)" --filter "displayName=Qwiklab_Explorers_TS")
API_KEY=$(gcloud alpha services api-keys get-key-string $KEY_NAME --format="value(keyString)")
echo $API_KEY
touch request.json
tee request.json <<EOF
{
  "document":{
    "type":"PLAIN_TEXT",
    "content":"Joanne Rowling, who writes under the pen names J. K. Rowling and Robert Galbraith, is a British novelist and screenwriter who wrote the Harry Potter fantasy series."
  },
  "encodingType":"UTF8"
}
EOF
cat request.json
curl "https://language.googleapis.com/v1/documents:analyzeEntities?key=${API_KEY}" -s -X POST -H "Content-Type: application/json" --data-binary @request.json > result.json
cat result.json
```

# Congratulations ..!!🎉  You completed the lab shortly..😃💯

# *Well done..!* 👏

# Thank you for visiting.... :) 🗯️

# [Qwiklab_Explorers_ts](https://youtube.com/@titashshil?si=RgamNu1dc9jVIbJN)
