---
title: "Microsoft Azure: Working with instances"
slug: azure-working-with-instances
---


To create, modify, or delete an instance, an account with the *User* role must be a member of the environment which contains the instance, and also have the *Editor* or *Owner* environment role assigned.  An account with the *Administrator* role or higher may create, modify, or delete instances in an environment.

To access instances, navigate to your Microsoft Azure environment and click on the **Instances** tab.

<!-- Creating an environment - Advanced - Select region -->

### Add an instance

Prior to adding an instance, you must have at least one network created in your Microsoft Azure environment.

   1. Click on *Add instance*.
   1. On the *Add instance* page, enter the required parameters for the desired instance.  The estimated hourly and monthly costs will appear on the right hand side.
   1. Select the region in which to create the instance.  The region cannot be changed once the instance is created.
   1. You may choose to attach a public IP when the instance is created.  There must be a public IP address already allocated and unattached in the network where the instance is to be created.
   1. Select the subnet to attach to this instance.
   1. Click *Submit*.  The **Instances** tab will appear.  When the new instance has been created, it will appear in the list, and will be in the **provisioning** state.  Once the instance has been provisioned, it will transition to the **running** state.

### Get instance details

1. From the **Instances** tab, click on the instance.  This will take you to the *Instance details* page.
   - On the **Instances** tab, clicking on an instance's name or IP address will copy that data to your clipboard, and will *not* take you to the *Instance details* page.
1. On the *Instance details* page, clicking on any string will copy it into your clipboard.
1. Clicking on *Disks* will take you to the *Instance disks* page, where you can add, resize, detach, or delete disks on this instance. See [Azure: Working with disks](azure-working-with-disks.md) for more information.

### Stop a running instance

1. From the **Instances** tab, click on the **Action** menu to the right of the instance, and select *Stop*.
1. A dialogue box will appear, asking for confirmation to continue.  Click *Submit*.
1. The instance will enter the **Stopping** state.  Once the instance has stopped running, it will enter the **Stopped** state.

### Starting a stopped instance

1. From the **Instances** tab, click on the **Action** menu to the right of the instance, and select *Start*.
1. The instance will enter the **Processing** state.  Once the instance is booting, it will enter the **Running** state.

### Delete an instance

An instance in any state may be deleted.  Any disks attached to the instance, including the boot disk, will remain in the **Detached** state and will not be deleted.

1. From the **Instances** tab, click on the **Action** menu to the right of the instance, and select *Delete*.
1. A dialogue box will appear, asking for confirmation to continue.  Click *Submit*.
1. The instance will enter the **Deleting** state.  When the deletion is complete, the instance will be removed from the **Instances** tab.
