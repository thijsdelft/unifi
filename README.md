This is a collection of scripts and programs I have written for Ubiquiti Unifi products.

- startup.sh is for Debian 9
- startup2.sh is for Debian 11

Feel free to explore!

For instructions on how to set up an UniFi controller on Google Cloud Platform see
https://metis.fi/en/2018/02/unifi-on-gcp/


For the Firewall rule automation to be working:
1. During the **firewall** setup:
- do not add port 80 to the standard rule.
- Add a new rule with the name `allow-letsencrypt` to allow inbound traffic for 0.0.0.0/0 for port TCP 80.

2. During **Identity and API access**
-  In addition to the storage API on Read/Write, you also need to set the **Compute Engin** to *Read/Write*. Potentially tou alos need to set **Service Control** to *Enabled*, and **Service Management** to *Read Only*.

4. Under **Metadata** you need to add a new key/value pair:
  - key: `rulename` value: `allow-letsencrypt`
