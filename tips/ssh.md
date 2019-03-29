# SSH

#### Creating a new key

###### Linux/MacOS

```
$ ssh-keygen -t rsa -f ~/.ssh/[KEY_FILENAME] -C [USER_NAME]
$ ssh-keygen -t rsa -f ~/.ssh/google_cloud -C anshul

# Restrict Access only to yourself
$ chmod 400 ~/.ssh/[KEY_FILENAME]
```

#### Locating the key file

###### Linux/MacOS

```
Public key file: ~/.ssh/[KEY_FILENAME].pub
Private key file: ~/.ssh/[KEY_FILENAME]
```

#### Update the server \(GCP Compute\)

###### Linux/MacOS

```
1. Copy your public key and add it to the compute instance by editing it from GCP console
2. For the first time you'll need to ssh from your local machine using your private key, as shown below:

$ ssh -i ~/.ssh/google_cloud <user_name>@<ip_address>

This may ask you to provide a passphrase in case you did setup one.
```

#### SSH into servers with no public IP

```
https://cloud.google.com/compute/docs/instances/adding-removing-ssh-keys#locatesshkeys
https://cloud.google.com/compute/docs/instances/connecting-advanced#thirdpartytools
```



