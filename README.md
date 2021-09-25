Note: This set up has been done on an Ubuntu OS (20.04) 
# 1. GoPhish Instalation

1. Install Gophish
```
sudo wget https://github.com/gophish/gophish/releases/download/v0.11.0/gophish-v0.11.0-linux-64bit.zip
unzip gophish-v0.11.0-linux-64bit.zip
```

2. Modify `config.json` file
   1. Replace `"listen_url": "127.0.01:3333"` to `"listen_url": "0.0.0.0:3333"` so as to listen on all interfaces

3. Make the gophish file executable: `chmod +x gophish`

4. Run the executable: `./gophish`

5. Temporary admin credentials will be displayed when the above executable is ran: e.g `time="2021-09-25T12:13:24+02:00" level=info msg="Please login with the username admin and the password gophish"`

5. Go to `https://<ip address>:3333` to login to the GoPhish Admin Pae using the above credentials.

# 2. Create a Gmail Account / Use Existing One

1. Make sure 2FA is turned off for this account and 'Allow Less secure apps access' setting is turned on. 

# 3. Install Ngrok
```
sudo wget https://bin.equinox.io/c/4VmDzA7iaHb/ngrok-stable-linux-amd64.zip
unzip ngrok-stable-linux-amd64.zip
./ngrok authtoken <your_auth_token>
./ngrok http 80
```

NB: You can obtain the auth_token by creating an account on https://ngrok.com/