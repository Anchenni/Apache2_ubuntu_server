# Apache2_ubuntu_server

Here is a process of setting up a basic Apache web server on Ubuntu Server VM running on a linux machine. We'll go through the steps of installing Apache, configuring it to serve a simple HTML page, and then accessing that page from a web browser.

**Step 1: Install Apache on Ubuntu Server**

1. Connect to your Ubuntu Server VM.
2. Open a terminal window.

Run the following commands to install Apache:

```bash
sudo apt update
sudo apt install apache2
```

This will update the package list and install the Apache web server.

**Step 2: Start and Enable Apache**

After installing Apache, you need to start the service and enable it to start automatically on boot. Run these commands:

```bash
sudo systemctl start apache2
sudo systemctl enable apache2
```

**Step 3: Create a Simple HTML Page**

Now, let's create a simple HTML file to serve as your web page. You can use any text editor to create the file. For example, we'll use the `nano` text editor:

```bash
sudo nano /var/www/html/index.html
```

In the text editor, add the following simple HTML code:

```html
<!DOCTYPE html>
<html>
<head>
    <title>My Simple Website</title>
</head>
<body>
    <h1>Welcome to My Simple Website</h1>
    <p>This is a basic HTML page served by Apache on Ubuntu Server.</p>
</body>
</html>
```

Save the file by pressing `Ctrl + O`, then press `Enter`, and exit by pressing `Ctrl + X`.

**Step 4: Configure Firewall**

If you have a firewall enabled on your Ubuntu Server, you'll need to allow HTTP traffic. Run the following command to allow HTTP traffic through the firewall:

```bash
sudo ufw allow 80/tcp
```

**Step 5: Access Your Web Page**

Now, you should be able to access your simple web page from your Mac's web browser. Open a web browser and enter the IP address of your Ubuntu Server VM in the address bar. To find the IP address, you can use the following command:

```bash
ip a
```

Look for an IP address associated with your server's network interface (usually "eth0" or "ens33").

Enter the IP address in your browser, for example, `http://your_server_ip`. You should see your simple web page displayed.

**Step 6: Modify the HTML Page**

If you want to modify the HTML page in the future, simply edit the `/var/www/html/index.html` file using a text editor like `nano`, save the changes, and then refresh the web page in your browser.

That's it! You've successfully set up an Apache web server on your Ubuntu Server VM and served a simple HTML page. You can now build and customize your website further as needed.
