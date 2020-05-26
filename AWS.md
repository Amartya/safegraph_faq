layout: page
title: "AWS Setup"
permalink: /aws/

Once you have made it through the initial onboarding and decided what you want/need from the consortium, now you are trying to get into the data and do some real work! First off,  let’s talk about what AWS s3 is. 
Essentially, s3 is a system designed by Amazon web services to host your data and allow people all over the world to download it to their computers! How is this different than any other download button on the internet, you may ask? With AWS s3, once you have downloaded the files for the first time, you are able to ‘update’ your local download folder with new information without having to download the entire set over and over again (with the sync command)! So, while that first download may seem overwhelming, the following downloads will be much quicker!
In order to keep the system from being misused, SafeGraph has opted to add 3 credentials to the s3 bucket:
- Access Key
- Secret Access Key
- Default Region Name

When you run the first command `aws configure - -profile safegraph`, you are telling your computer to create a profile name with the aforementioned credentials added to them. Think of it like giving a roommate a key to your house – anyone with the key can get inside. Now, with that same analogy in mind, SafeGraph changes the ‘locks to the house’ once a week, which means you have to create a new key on a weekly basis. To do so, you simply run the `aws configure - -profile safegraph` command again to give yourself a new key!

Okay, so you are halfway there! The s3 bucket is set up like a minicomputer with files stored all over the place! To access those files, you need to tell s3 2 things 1) Where to get the information and 2) where to put it on your computer. In the documentation linked above, you will find a command that looks like this `aws s3 sync s3://sq-c19-response/monthly-patterns/ ./mylocaldirectory/ - -profilesafegraph`. So, lets break this down. You are telling your computer to find the folder in the s3 bucketcalled monthly-patterns and download it to a new folder on your computer called 'mylocaldirectory'(the '/'  at the end tells it to make a directory if one doesn’t exist). If you use the command line above, this will create a new folder under c://Users/{your_name}/mylocaldirectory. An easy way to find that spot is to just do a search for ‘mylocaldirectory’ in your search bar or do a search for 'monthly-patterns'. If you wish to change where the information is stored on your computer, you just need to add that path where './mylocaldirectory/' is located.

If you wish to change what data you are pulling, you can find a comprehensive list of endpoints [HERE](https://docs.google.com/spreadsheets/d/1UNWvPzkUTTlXBZ6M6iGhM_7sr8h-MxsZdE7iOszkAmk/edit#gid=0). On the far right column you will see a label 'AWS s3 path' – you can copy that and replace the information where you see "s3://sq-c19-response/monthly-patterns/" above. 

## AWS Troubleshooting ##
Please note, if your concerns are not addressed here, you can submit your issues with AWS
[HERE](https://safegraphcovid19.slack.com/archives/C0114D7SJCF) and get personalized help!

> I have downloaded AWS and followed the instructions, but after I install it, I can’t type
anything!

After installing AWS to your location computer, you will see a message that says "[process complete]". Once you see this  message, you can close the window by pressing the 'X' in the top right corner (alternatively, press CMD + Q on Mac). After closing that window, simply open a new window and start adding the commands above. You can open a new window by pressing the windows key followed by 'cmd' in your search bar (Windows), or on Mac by finding the launchpad icon in your navigation menu at the bottom and finding 'Terminal'.

> I have put in the commands I want to access the data in the directory I want, but I am getting the error “WinError 5, Access Denied”!

To fix this error, close the command window you are working in. Go back to where you launched the command panel in the first place, but this time right click the app and select “run as admin” from the menu.

> I am getting a standard “Access Denied” or “403” error when I try to access the data!

You should ensure that your credentials are correct! Navigate to the credential page located [HERE](https://safegraphcovid19.slack.com/archives/C0109NPA543/p1585177965017700). Remember, they change on a weekly basis! To change your credentials simply retype the “aws configure - -profile safegraph” command with the new keys in place.

> I am getting an error: “fatal error: An error occurred (SignatureDoesNotMatch)”!

You likely have a typo somewhere in your command. Try retyping the command from scratch to ensure you don’t have any missing/mistyped pieces!

> I used the sync command but only got some of the files I thought I was downloading!

This can be a few different things. First off, you should run an ‘ls’ command on the folder you are syncing to make sure the files exist in the s3 bucket. An example of an ls command is: `aws s3 ls s3://sg-c19-response/weekly-patterns/ -- profile safegraph`. This will tell you everything that is inside that folder. If you confirm that the files are in fact in the bucket/folder, and they are not on your computer, simply rerun the sync command. Sometimes partial downloads happen when too many people are hitting the folder at the same time! The good news is it will not have to redownload the other files again.



*all content from Jack Lindsay's excellent Starter Material Guide v2.*
