cloud cost will go down only if you are doing this efficiently

let say there is a developer here ok you have granted this developer proper IAM access is that this developer can create an ec2 enstance so this developer has good knowledge of cloud so went ahead and he created his own ec2 instance on the cloud platform and what he has done is he has attached a volume to this ec2 instance or by default when you create an ec2 instance there is a volume attached to it right without volume you cannot store data inside the ec2.

let say you want to create some files you want to update some configurations and stuff like that so this developer has created the ec2 instance and he has started populating the volume and what he has done he or she basically the volume is filled with the information that is very sensitive for the organization or you know they just want to take the backup of the volume so what this person has done he has taken backup each and every day and taking backup volumes is nothing but you this person has started taking the snapshots

in this technology terms we call it a snapshots if you take a snapshot of a volume that means you have technically a backup of the volume so each and every day this person has started taking the snapshots

right now afterawhile what ha happened you know this person said that ok this
feature is deprecated no I don't want this so let me delete the ec2 instance it is of no more useful and this person went ahead and lets say say deleted the volume as well or for example he was using some external volume so like just say that this person created additional volume for the ec2 instance and deleted the ec2 instance but forgot to delete the volume now if the volume itself is forgotten to delete of afcourse the snapshots that this person has has taken each and every day will also be forgotten and will not be deleted and AWS will keep charging you for all these snapshots and all these volumes so

s3 buckets that are created by some developer and probably that developer is stopped using the s3 buckets but he has forgotten to delete the s3 buckets and the content in the s3 bucket right when you keep updayeing the content in the s3 bucket eventually aws charge will go significantly high right or


so there are 200 resources on aws and manually monitoring this 200 resources to verify if someone has created some stale resources lets
resources is something someone has created but forgotten to delete those
resources so that way cloud cost will go high than you expected if you are not doing the cost efficiently right if you not managing the cost of the cloud platform efficiently then what would happen the cloud cost will go high right now what is that means for an organization so organization has moved to cloud platform assuming their cost will go down but it is actually going high so this is one of the primary responsibilities of Devops engineer.

Devops engineer should make sure that the cloud cost should go down and how Devops engineer can ensure that by looking at if there are any stale resources on the cloud platform if there are any stale resources then Devops engineer can typically do two things
Devops engineer can send out the notifications 
delete option


fetch all the ebs snapshots
to filter out the snapshot that are stale
