### Install and run sshd

```
sudo apt-get install openssh-server
sudo systemctl enable ssh --now
```

To change the port for the SSH daemon (`sshd`), you need to edit the configuration file `/etc/ssh/sshd_config`. Here's a step-by-step guide to doing this:

1. **Open the SSH configuration file in a text editor:**

   You can use `nano`, `vim`, or any other text editor of your choice. Here’s how you can do it with `nano`:

   ```sh
   sudo nano /etc/ssh/sshd_config
   ```

2. **Locate the Port directive:**

   Look for the line that specifies the port number. It usually looks like this:

   ```sh
   #Port 22
   ```

   The `#` at the beginning of the line indicates that it is commented out and the default port (22) is being used.

3. **Uncomment and change the port number:**

   Remove the `#` at the beginning of the line and change the port number to your desired port. For example, to change the port to 2222, you would modify the line to:

   ```sh
   Port 2222
   ```

4. **Save and close the file:**

   If you are using `nano`, you can save and exit by pressing `Ctrl + X`, then `Y`, and then `Enter`.

5. **Adjust your firewall settings:**

   If you have a firewall enabled (such as `ufw`, `firewalld`, or `iptables`), you will need to allow traffic on the new port. For `ufw`, the command would be:

   ```sh
   sudo ufw allow 2222/tcp
   ```

   Replace `2222` with your chosen port number.

6. **Restart the SSH service:**

   After making these changes, you need to restart the SSH service for the changes to take effect. You can do this with the following command:

   ```sh
   sudo systemctl restart sshd
   ```

   On some systems, the service might be named `ssh` instead of `sshd`:

   ```sh
   sudo systemctl restart ssh
   ```

7. **Verify the change:**

   To ensure that `sshd` is now listening on the new port, you can use the following command:

   ```sh
   sudo netstat -tuln | grep 2222
   ```

   Or with `ss`:

   ```sh
   sudo ss -tuln | grep 2222
   ```

   Replace `2222` with your chosen port number. This command should show that `sshd` is listening on the new port.

**Note:** After changing the SSH port, you will need to specify the new port number when connecting via SSH. For example:

```sh
ssh -p 2222 user@your_server_ip
```

Replace `2222` with your chosen port number and `your_server_ip` with the actual IP address or hostname of your server.
