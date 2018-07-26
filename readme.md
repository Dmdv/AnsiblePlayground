https://linuxacademy.com/howtoguides/posts/show/topic/13750-managing-docker-containers-with-ansible




Deploying and Destroying Custom Docker Containers


Since we need to login to Docker registry, we need to be able to put our secrets in the code. To avoid exposing credentials in the clear, we will use ansible-vault to encrypt them. Create a file called secrets.yml with your login info:


---
docker_hub_username: yourusername
docker_hub_password: yourpassword
docker_hub_email: youremail@example.com

Run ansible-vault against the file. It will prompt for a password to encrypt it:


stardust:ansible_docker_demo rilindo$ ansible-vault encrypt secret.yml 
New Vault password: 
Confirm New Vault password: 
Encryption successful
The file will look something like this:


$ANSIBLE_VAULT;1.1;AES256
36626666333261633834313438336264383534353036633135333837633035303432366136353632
3839336362303934393462643665366438653432633232300a336264353063316136663433343435
39393231333864663230373836303865616163353034323262333035363336333537373265333932
3863343532636161660a653435623135336436656533346632626132656130633136356565303139
3338
