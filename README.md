# Ansible Playbook for reducing AWS EBS volume size
EC2 instances use EBS volumes as storage. While AWS supports increasing volume size, size decrease is not supported.

# Tasks

create a new volume of smaller size, tag it 

attach the new volume to the instance

create a filesystem and mount it

rsync -avzh /data to new disk

stop the instance

detach an old volume

detach a new volume 

attach new volume and mount into the correct drive 

start instance

# Few things to consider

If your instance have a lof of new data coming in and you want min donwtime, you can rsync
all your data first, then stop your application and rsync data again.

The second start instance attempt can be removed if you're sure that the first will succeed.

You might want to check that your app is up after starting the instance.