---
title: "GCP: Instance groups"
slug: gcp-instance-groups
---


**Instance groups** are used for providing backend services such as load balancing.  Instance groups exist in a single zone within a region, and may contain instances in that zone only.

To create, modify, or delete an instance group, an account with the *User* role must be a member of the environment which contains the instance, and also have the *Editor* or *Owner* environment role assigned.  An account with the *Administrator* role or higher may create, modify, or delete instance groups in an environment.

To manage instance groups, navigate to the desired GCP environment, click on the **Compute** tab, and then click on *Instance groups*.

### Adding an instance group

1. From the *Instance groups* page, click on *Add instance group*.  The *Add instance group* page will appear.
1. Provide a name for the instance group, and an optional description.
1. Select the region and zone where the instances to group are located.
1. If the selected zone has instances, a pop-up list labeled **Instances** will appear beneath the zone.  Select the instances to become members of this instance group.  Note that changing a zone will clear the list of instances already selected.
1. Click *Submit* to create the group.
1. You will be returned to the *Instance groups* page, the instance group will be created, and the instances will be added to the group.

**Note:** Once an instance group is created, its region and zone cannot be changed.

### Managing an instance group

1. From the *Instance groups* page, click on the **Action** menu, and select *Manage instance members*.  The *Manage instance members* dialogue box will appear.
1. The pop-up list labeled **Instances** will contain a list of the instances that are members of this group.
   - To remove an instance from the group, click the X mark to the right of an instance's name.
   - To add an instance to the group, click on the pop-up list, then click on the name of the instance you wish to add.
1. Click *Submit* when you have finished making changes.

### Deleting an instance group

An instance group that is used by a backend service cannot be deleted.  Deleting an instance group does not delete its member instances.

1. From the *Instance groups* page, click on the **Action** menu, and select *Delete*.
1. You will be asked to confirm the operation.  Click *Submit* to confirm.
