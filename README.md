****************
# Dixicoin Masternode Script
****************

**Compiled for Ubuntu 16.0.4** 

- Intended for New Install with Install Script or quick update to version 4.5.0
- Install Script will install basic dependencies and pre-compiled version of Dixicoin v4.5.0
- Older versions "should" be replaced in this process and also updated to current version.
- If your version does not upgrade please remove your old.

****************
**Instructions:** 

Step 1. wget url-to-dixicoin_install.sh (Located on the Dixicoin GitHub)

Step 2. chmod +x dixicoin_install.sh (changes permissions so the script may be executed)

Step 3. bash dixicoin_install.sh (runs the install script)


****************
The install process can take some time and is determined by the updated condition of your vps. Please wait if the process appears to have ceased or "hang". 

**Patience is the key at this point.**

When the Installation is near completion you will be asked to paste in a Masternode Private Key.

This can be obtained from your local wallet in the debug console with the command: masternode genkey

After pasting in your generated key you will be prompted with some basic information and control of the vps. 

Check that your vps is running and syncing: dixicoin-cli getinfo (Blocks should be increasing)

****************
**Other useful commands of operation:**

systemctl start dixicoin.service

systemctl stop dixicoin.service

systemctl status dixicoin.service

systemctl enable dixicoin.service

systemctl disable dixicoin.service


dixicoind (manual start daemon without service)

dixicoin-cli getinfo

dixicoin-cli mnsync status

dixicoin-cli masternode status

dixicoin-cli stop (manual daemon stop without the service)

****************
**Basic needs from the PC wallet**

1. Private key - Command: masternode genkey

2. Masternode addy - Command: getaccountaddress MN1 (Important not to have spaces in an alias name)

3. Transaction ID - Command: masternode outputs (Important to wait for the transaction to confirm first)

****************
After sending the 5000 coins collateral to the created MN address wait for the transaction to confirm.
Once confirmed you will record the details from masternode outputs including the output index number indicated at the end of the transaction. 

This will be a 0 or a 1 and is important to include in the masternode.conf file

Follow the example in the masternode.conf and enter your details. Restart your PC wallet and allow it to fully sync
and move to your debug console to start your masternode.

****************
Run the following command to start the masternode:

masternode start-alias MN1 (Replace MN1 with your MN alias)

****************
Check the VPS to see if the activation was a success:

dixicoin-cli masternode status

If the VPS fails to start please stop the daemon on the VPS for a minute and then restart the vps and ensure the initial sync checks are complete prior to activation. 

Reapply the activate command from your local wallet.

