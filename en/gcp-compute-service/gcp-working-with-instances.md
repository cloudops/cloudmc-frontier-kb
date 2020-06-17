---
title: "GCP: Working with instances"
slug: gcp-working-with-instances
---


To create, modify, or delete an instance, an account with the *User* role must be a member of the environment which contains the instance, and also have the *Editor* or *Owner* environment role assigned.  An account with the *Administrator* role or higher may create, modify, or delete instances in an environment.

To access instances, navigate to your GCP environment and click on the **Compute** tab.

### Add an instance

1. Click on *Add instance*.
1. On the *Add instance* page, enter the required parameters for the desired instance.  The estimated hourly and monthly costs will appear on the right hand side.
1. You may choose to allow HTTP (port 80) or HTTPS (port 443) traffic, or both.  This will create a firewall rule allowing the selected traffic to this VM.
1. You may choose to attach a public IP to the instance using the **Attach external IP** pop-up menu.
   - **None:**  Your instance will not have a public IP.
   - **New ephemeral IP:**  Your instance will be assigned a new public IP every time it boots.
   - **New static IP:**  A public IP will be reserved specifically for this instance, and will be the same every time it boots.
1. You may choose to specify a startup script to be executed every time the instance boots.  Enter the desired startup script in the text box labeled **Automation - Startup script**. For instances running Unix-based operating systems, this can be a shell script, and for Windows instances this can be a metadata key, where the value is the desired batch commands or PowerShell commands.
1. Click *Submit*.  The new instance will appear in the list, and will be in the **provisioning** state.  Once the instance has been provisioned, it will transition to the **running** state.

### Get instance details

1. From the **Compute** tab, click on the instance.  This will take you to the *Instance details* page.
   - On the **Compute** tab, clicking on an instance's name or IP address will copy that data to your clipboard, and will *not* take you to the *Instance details* page.
1. On the *Instance details* page, clicking on any string will copy it into your clipboard.
1. Clicking on *Disks* will take you to the *Instance disks* page, where you can add, resize, detach, or delete disks on this instance. See [GCP: Working with disks](gcp-working-with-disks.md) for more information.

### Stop a running instance

1. From the **Compute** tab, click on the **Action** menu to the right of the instance, and select *Stop instance*.
1. A dialogue box will appear, asking for confirmation to continue.  Click *Submit*.
1. The instance will enter the **stopping** state.  Once the instance has stopped running, it will enter the **terminated** state.

**Note:** If the instance does not stop within 90 seconds, the instance will be force-stopped.

### Starting a stopped instance

1. From the **Compute** tab, click on the **Action** menu to the right of the instance, and select *Start instance*.
1. The instance will enter the **provisioning** state.  Once the instance is booting, it will enter the **running** state.

### Delete an instance

An instance in any state may be deleted.

**Note:** Deleting an instance will delete the boot disk, and also any disks that were attached to the instance with the deletion rule *Delete disk* selected.

1. From the **Compute** tab, click on the **Action** menu to the right of the instance, and select *Delete*.
1. A dialogue box will appear, asking for confirmation to continue.  Click *Submit*.
1. If the instance is running, it will enter the **stopping** state, after which it will be deleted.  If the instance is already stopped, it will be deleted immediately.

### Connect via SSH

 Use this command to configure SSH access to the instance.  You will be asked to provide your SSH public key, or to select an existing key.

  1. From the **Compute** tab, click the **Action** menu to the right of the instance, and select **Get SSH command**.
  1. The **Get SSH command** dialogue box will appear.
     - If you have already configured one or more SSH public keys, those will appear in the pop-up menu labeled **SSH key**.
     - If you do not have an SSH key configured, or if you wish to configure a new one, select the option *New SSH key* from the **SSH key** pop-up menu, then enter the desired public key in the text box labeled **Public Key**.
  1. Click *Submit*.
  1. The dialogue box will disappear.  A firewall rule will be created allowing SSH traffic (port 22) to this instance.  A notification will appear, providing the SSH command that can be used to connect to the instance.

**Note:**  Your SSH client should already be configured with the private key for the public key you have selected.
