---
title: "Microsoft Azure: Working with disks"
slug: azure-working-with-disks
---


A **disk** is storage that is presented to an instance as a block device, which can then be mounted and used.  All instances have a boot disk, which can be resized but which cannot be detached from its instance.  Additional disks can be created, resized, attached or detached, and deleted.

To create, modify, or delete a disk, an account with the *User* role must be a member of the environment which contains the instance, and also have the *Editor* or *Owner* environment role assigned.  An account with the *Administrator* role or higher may create, modify, or delete disks in an environment.

To access disks, navigate to your Microsoft Azure environment and click on the **Disks** tab.

### Create a disk

1. From the *Disks* tab, click *Add disk*.  You will be taken to the *Add disk* page.
1. Enter a name for your disk.
1. Select the region where you want the disk to be available.  The region cannot be changed once the disk is created.  A disk can only be attached to an instance in the same region.
1. Enter the parameters for disk type and disk size.
1. Click *Submit*.  The **Disks** tab will appear.  The disk will be created and will appear in the **Detached** state.

### Attach a disk to an instance

A disk can only be attached to an instance when the disk is in the **Detached** state.

1. From the **Disks** tab, click the **Action** menu to the right of the disk you wish to attach, and click *Attach*.
1. The *Attach* dialogue box will appear.  Select the desired instance from the **Instance** pop-up list.
   - By default, a disk is attached to an instance with the lowest Logical Unit Number (LUN) available on the instance.  If a custom LUN is required for this disk, check the **Custom LUN** box and specify which LUN you wish to assign this disk.  The chosen LUN must be unique from all other disks attached to the instance.
1. Click *Submit*.  The disk will be attached to the instance, and the disk will appear in the **Attached** state.  The disk is now ready ready to be mounted or partitioned.

### Detach a disk from an instance

**Note:**  Detaching a disk from a running instance may result in disk corruption and data loss.  Always gracefully unmount the volume from within the instance's operating system prior to detaching a disk.

1. From the *Disks* tab, click the **Action** menu to the right of the disk you wish to detach, and click *Detach*.
1. A dialogue box will appear, asking for confirmation to continue.  Click *Submit*.
1. The disk will be detached and will return to the **Detached** state.

Alternatively, a disk may be detached from an instance via the *Instance details* page.

### Resize a disk or change disk type

A disk can be resized to increase the amount of storage space allocated.  Disk space can can only be increased.  Decreasing the size of a disk in not supported.  Additionally, the performance type of the disk can be changed.

**Note:** If the disk is attached to a running instance, modification of the disk will restart the instance.

1. From the *Disks* page, click the **Action** menu to the right of the disk you wish to modify, and click *Edit*.
1. The *Edit* page will appear.
1. To change the performance type of the disk,
1. To resize the disk, move the **Disk size** slider to the number of gigabytes desired for the disk.
1. Click *Submit*.  The disk will be modified accordingly, and a notification will appear when the operation has completed.
1. The filesystem can now be extended from within the instance's operating system.

Alternatively, a disk may be resized if it is attached via the instance's *Instance details* page.

### Delete a disk

A disk must be detached before it can be deleted.  Deleting a disk is permanent.  This action cannot be undone.

1. From the **Disks** tab, click the **Action** menu to the right of the disk you wish to delete, and click *Delete*.
1. A dialogue box will appear, asking for confirmation to continue.  Click *Submit*.
1. This disk will be deleted and will be removed from the list of disks.
