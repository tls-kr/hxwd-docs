---
title: Users, groups and permissions
---
# Users, groups and permissions

All users of this application belong to one or more groups. This is used for determining which user has permission to read or edit a resource.  Currently, the following groups are defined:

| Name of group | Explanation                                                                           |
| ------------- | ------------------------------------------------------------------------------------- |
| guest         | Group for visitors that are not logged in                                             |
| tls-user      | All users are member of this group. Most resources can be read, but only few changed. |
| tls-editor    | This group has far more rights to change resources or create new ones.                |
| tls-admin     | Rights to perform administrative tasks that require access to all resources           |
|               |                                                                                       |
## Access rights to resources

Separate rights exist to `read`, `write` or `execute` a resource.  The latter is relevant for scripts but also folders, where the right to execute means the read to open it and list its contents. 

With slight simplification, it can be said that for every resource, each of these rights is defined for the `owner` of the resource, the group to which this resource has been assigned and for everybody else.  

## Different views of the database

What this all boils down to is that the way a resource is displayed differs considerably for different user groups.  The screenshots used to explain the workings of the database in this manual usually assume a user in the group `tls-user` and shows what would be available to such a user, except, of course where specific tasks for editors are explained. 