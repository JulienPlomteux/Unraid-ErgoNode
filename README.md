# Unraid-ErgoNode
Allows you to run a ERGO node on your unRAID server using the OFFICIAL DOCKER.  </br> While syncing to the current height, your docker might crash  and it might take a wile (few hours to a day at most) depending  on your cpu and ram.  </br> Once the sync is done you can setup your wallet following the blog: https://ergoplatform.org/en/blog/2019_12_02_how_to_setup  </br> - UI for the wallet can be found at [IP]:[PORT:9053]/panel  </br> - For the swagger [IP]:[PORT:9053]/swagger </br> 
</br> If you have any questions send me a message at https://forums.unraid.net/profile/163009-mrlafontaine/ or on discord mrlafontaine#0504
</br>
<h4> Support me </h4>
If you liked this guide and want to say thanks feel free to buy me a coffee: 9hWidxom5qCRtu4Bq3EjibVRSAhwMhvEC3DTf61jyzGapwvmTBR

<h1> Installation Guide </h1>
  Before doing anything you will need to create a config file !
</br>
<h3> Creating the config file using windows file explorer: </h3> 
I have chosen to create the node in appdata/ergonode </br>
- Create a .txt file:
</br>

![image](https://user-images.githubusercontent.com/60188215/159179520-e91668bd-8ecd-4493-b3e8-d31f807b50f0.png)

</br>
- Open the .txt file you just created and paste the following: </br>

```
    ergo {
      node {
        mining = false
      }
    }

    scorex {
     restApi {
        ## Hex-encoded Blake2b256 hash of an API key. 
        ## Should be 64-chars long Base16 string.
        ## below is the hash of the string 'hello'
        ## replace with your actual hash 
        apiKeyHash = "324dcf027dd4a30a932c441f365a25e86b173defa4b8e58948253471b81b72cf"
      }
    }
```
- Save the file: crtl+s and close it.
- Now rename the txt file to 'ergo.conf' removing the .txt extention, click yes for the warning.

![image](https://user-images.githubusercontent.com/60188215/159177105-2b9e9588-cc38-4d4e-a3a1-5e293a88d5e4.png)

<h3> Creating the config file using the command line: </h3> 
- Navigate to your appdata folder:

```
cd /mnt/user/appdata
```

- Open unraid command line and create a folder in appdata named, in my case, ergonode: 

```
mkdir ergonode
```
- Create a file named ergo.conf and paste the default config:

```
nano ergo.conf
```
and paste this inside: 

```
    ergo {
      node {
        mining = false
      }
    }

    scorex {
     restApi {
        ## Hex-encoded Blake2b256 hash of an API key. 
        ## Should be 64-chars long Base16 string.
        ## below is the hash of the string 'hello'
        ## replace with your actual hash 
        apiKeyHash = "324dcf027dd4a30a932c441f365a25e86b173defa4b8e58948253471b81b72cf"
      }
    }
```
<h2>Now for the unraid template: </h2>

![image](https://user-images.githubusercontent.com/60188215/159179497-1b813fa1-6cec-48b9-b31c-390b1bda2cec.png)

