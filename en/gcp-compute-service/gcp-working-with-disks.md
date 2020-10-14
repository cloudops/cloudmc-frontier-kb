---
title: "GCP: Working with disks and snapshots"
slug: gcp-working-with-disks-and-snapshots
---


A **disk** is storage that is presented to an instance as a block device, which can then be mounted and used.  All instances have a **boot disk**, which can be resized but which cannot detached from its instance.  Additional persistent disks can be created, resized, attached or detached, and deleted.

To create, modify, or delete a disk, an account with the *User* role must be a member of the environment which contains the instance, and also have the *Editor* or *Owner* environment role assigned.  An account with the *Administrator* role or higher may create, modify, or delete disks in an environment.

To access disks, navigate to your Google Cloud Platform environment and click on the **Compute** tab, then click on *Disks*.

### Create a disk

1. From the *Disks* page, click *Add disk*.  You will be taken to the *Add disk* page.
1. Enter a name for your disk.
1. Select the region and zone where you want the disk to be available.  The region and zone cannot be changed once the disk is created. A disk can only be attached to an instance in the same region and zone.
1. Enter the parameters for disk type, disk size, and block size.
1. Click *Submit*.  The disk will be created and will appear in the on the *Disks* page in the **ready** state.

### Attach a disk to an instance

A disk can not be attached to an instance when the disk is already in the **attached** state.

1. From the *Disks* page, click the **Action** menu to the right of the disk you wish to attach, and click *Attach*.
1. The *Attach* dialogue box will appear.  Select the desired instance from the **Instance** pop-up list.
1. Choose whether this disk should be presented to the instance as a writeable device, or as a read-only device.
1. Choose whether this disk should be preserved if the instance to which it is attached is deleted, or if this disk should be deleted along with the attached instance.
1. Click *Submit*.  The disk will be attached to the instance, and the disk will appear in the **attached** state.  The disk is now ready ready to be mounted or partitioned.

### Detach a disk from an instance

**Note:**  Detaching a disk from a running instance may result in disk corruption and data loss.  Always gracefully unmount the volume from within the instance's operating system prior to detaching a disk.

1. From the *Disks* page, click the **Action** menu to the right of the disk you wish to detach, and click *Detach*.
1. A dialogue box will appear, asking for confirmation to continue.  Click *Submit*.
1. The disk will be detached and will return to the **ready** state.

Alternatively, a disk may be detached from an instance via the *Instance details* page.

### Resize a disk

A disk can be resized to increase the amount of storage space allocated.  Disk space can can only be increased.  Decreasing the size of a disk in not supported.

1. From the *Disks* page, click the **Action** menu to the right of the disk you wish to resize, and click *Resize*.
1. A dialogue box will appear.  In the text box labeled **Disk size**, enter the number of gigabytes desired for the disk.
1. Click *Submit*.  The disk will be resized and a notification will appear when the operation has completed.
1. The filesystem can now be extended from within the instance's operating system.

Alternatively, a disk may be resized if it is attached via the instance's *Instance details* page.

### Delete a disk

A disk must be detached before it can be deleted.  Deleting a disk is permanent.  This action cannot be undone.

1. From the *Disks* page, click the **Action** menu to the right of the disk you wish to delete, and click *Delete*.
1. A dialogue box will appear, asking for confirmation to continue.  Click *Submit*.
1. This disk will be deleted and will be removed from the list of disks.

### Take a snapshot of a disk

A snapshot of a disk is an instantaneous copy of a disk at a given point in time.

1. From the *Disks* page, click the **Action** menu to the right of the disk you wish to snapshot, and click *Take snapshot*.
1. A dialogue box will appear, asking for the name to give to the snapshot.  Click *Submit*.
1. The snapshot will be taken, and will appear on the *Snapshots* page in the **Creating** state.
1. When the snapshot is created, it will change to the **Uploading** state.  When it is complete, it will appear in the **Ready** state.
