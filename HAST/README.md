# illumos port of FreeBSD's HAST (High Available STorage)

This is regarding the port of FreeBSD's HAST (High Available STorage) to illumos and assoicated distributions, with the scope to extend functionality regarding:

- multi-homed storage with I/O fencing mechanisms using reservations (see https://github.com/jfqd/illumos-omnios/blob/master/usr/src/man/man7i/mhd.7i);
- cluster membership vote counts via a Quorum device/server, therefore eliminating a potential split-brain scenario;
- support for multi-homed stretched clusters up to at least 4-nodes (2-local and 2-remote).

However, RAID-1 over TCP/IP (how HAST has been originally conceived) could provide the basis for a stretched cluster for HA ZFS iSCSI JBOD solutions between sites without a high-bandwidth/low-latency interconnect to provide a multi-site multi-homed storage solution.

The original source code of concern can be found here:

- https://github.com/freebsd/freebsd/tree/master/sbin/hastd
- https://github.com/freebsd/freebsd/tree/master/sbin/hastctl


Further development should be done with the inclusion of iSCSI shared block-devices, and also support for more nodes than just the current limit of two, therefore adding the capability of a potential stretched cluster configuration.
