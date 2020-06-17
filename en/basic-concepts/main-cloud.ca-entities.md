---
title: "Main CloudMC entities"
slug: main-cloudmc-entities
---


An **organization** is the entity to which we bill the services consumed on the CloudMC infrastructure. It hold various attributes that are common to all its users (e.g.: login page, logo, authentication type, policies, etc).

A **user** is a person that accesses the CloudMC console to manage his virtual resources.

A **department** is a hierarchical grouping of users within an organization. Grouping users by department is entirely optional, but may help in quickly selecting multiple users who work closely together.

A **role** is a named collection of permissions within an organization. A user may be assigned multiple roles (which are additive) to determine what he his able to do in the CloudMC console. See [Using system roles to enforce access control](system-roles.md) to learn more about this concept.

A **service** is an abstraction through which a user provision and interacts with his virtual resources.

An **environment** is a sandbox within a service where user can share resources. See [Using Environments to organize users & workloads](environments-to-organize-workloads-and-users.md) to learn more about this concept.

**Permissions** provide access or visibility to specific aspects of CloudMC. There are two types of permissions: System permissions control access to various intrinsic features of the CloudMC console, while environment permissions control access to a service's virtual resources and their operations.
