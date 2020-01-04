[Azure Training Material](../index.md) >> [Azure Backup and Site Recovery](.)

1. #### [Azure Backup](azure-backup.md)  
2. #### [Azure Site Recovery](azure-site-recovery.md)  


```
root@NDL01252:~# az backup --help

Group
    az backup : Manage Azure Backups.
        This command group is in preview. It may be changed/removed in a future release.
Subgroups:
    container        : Resource which houses items or applications to be protected.
    item             : An item which is already protected or backed up to an Azure Recovery services
                       vault with an associated policy.
    job              : Entity which contains details of the job.
    policy           : A backup policy defines when you want to take a backup and for how long you
                       would retain each backup copy.
    protectable-item : Manage the item which is yet to be protected or backed up to an Azure
                       Recovery services vault with an associated policy.
    protection       : Manage protection of your items, enable protection or disable it, or take on-
                       demand backups.
    recoveryconfig   : Manage recovery configuration of an Azure workload backed up item.
    recoverypoint    : A snapshot of data at that point-of-time, stored in Recovery Services Vault,
                       from which you can restore information.
    restore          : Restore backed up items from recovery points in a Recovery Services vault.
    vault            : Online storage entity in Azure used to hold data such as backup copies,
                       recovery points and backup policies.
```
