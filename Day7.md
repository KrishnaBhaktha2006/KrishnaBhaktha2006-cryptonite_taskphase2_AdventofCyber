# Oh, no. I'M SPEAKING IN CLOUDTRAIL!

*Flag:* no flag

How you approached the challenge:

- step 1: Well i tried step by step what they told to try and i was getting stuff just had to go to the questions and see correctly what they wanted.We could use "jq '.[]' book_list.json" to beauitfy queries.

- step 2: For the first 2 questions i think this was enough
```
bash
jq -r '.Records[] | select(.eventSource == "s3.amazonaws.com" and .requestParameters.bucketName=="wareville-care4wares") | [.eventTime, .eventName, .userIdentity.userName // "N/A",.requestParameters.bucketName // "N/A", .requestParameters.key // "N/A", .sourceIPAddress // "N/A"]' cloudtrail_log.json
```
and then for other questions 
```
bash
jq -r '["Event_Time", "Event_Source", "Event_Name", "User_Name", "Source_IP"], (.Records[] | select(.sourceIPAddress=="53.94.201.69") | [.eventTime, .eventSource, .eventName, .userIdentity.userName // "N/A", .sourceIPAddress // "N/A"]) | @tsv' cloudtrail_log.json | column -t -s $'\t'
jq -r '["Event_Time","Event_Source","Event_Name", "User_Name","User_Agent","Source_IP"],(.Records[] | select(.userIdentity.userName=="PLACEHOLDER") | [.eventTime, .eventSource, .eventName, .userIdentity.userName // "N/A",.userAgent // "N/A",.sourceIPAddress // "N/A"]) | @tsv' cloudtrail_log.json | column -t -s $'\t'
grep INSERT rds.log
```

![image](https://github.com/user-attachments/assets/a8a0dc6d-ead3-492c-a107-1f317723e119)

![image](https://github.com/user-attachments/assets/22dd641c-38dc-4289-ba6a-ea1accd942b0)

I actually most of them myself except the mcskidys actual ip address i tried searching it in multiple times but i didnt get it.So i checked the yt soln for that question.

What you learned through solving this challenge:

1. Being able to filter out and read logs.

Other incorrect methods you tried:

- No incorrect methods tried other than trying every command to get the question i couldnt get and analysing each one of them.

References

- https://www.youtube.com/watch?v=134vRszJTus
