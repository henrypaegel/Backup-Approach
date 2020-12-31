# Current Backup Approach
## *How to do what, when and where*

1. * Daily Timeshift Backup to internal SSD; *last nine (three each) snapshots are being kept*
   * sync particular drive (above) to NAS-Share
   * Do a full Disk Clone to the NAS-Share every other week; *last four snapshots are being kept*
2. * Sync NAS-Share to OneDrive every Night
   * Backup NAS to USB-Drive once a Month; *rotate between two drives (one off-site)*

| Backup           | Program     | Target       | Frequency                | Automatic / manual | RTO       | RPO            | Procedure                               |
|------------------|-------------|--------------|--------------------------|--------------------|-----------|----------------|-----------------------------------------|
| Onsite Backup 1  | Timeshift   | internal SSD | Daily / Weekly / Monthly | Automatic          | 5 minutes  | Up to 1 day   | None. Runs when computer does.          |
|                  | Cloudberry  | Synology NAS | Daily                    | Automatic          | 20 minutes | Up to 1 day   | None. Runs when computer does.          |
| Onsite Backup 2  | Clonezilla  | Synology NAS | Every other week         | Manual             | 1 hour     | Up to 2 weeks | Write Clonezilla disk image to NAS      |
| Offsite Backup 1 | CloudSync   | OneDrive     | Daily                    | Automatic          | 6 hours    | Up to 2 weeks | None. Runs when server does.            |
| Offsite Backup 2 | HyperBackup | USB Drive    | Monthly                  | Manual             | 12 hours   | Up to 1 month | Backup whole NAS-Array to external HDD. |


