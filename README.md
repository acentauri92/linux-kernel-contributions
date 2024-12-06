# linux-kernel-contributions
This repository documents and organizes all of my contributions to the linux kernel with details about each patch submitted to the kernel.

## ![Contributions](https://img.shields.io/badge/Contributions-5-brightgreen)

### Contribution 1
- **Commit ID**: `13876109`  
- **Patch Link**: [lkml.org link to the patch](https://lkml.org/lkml/2024/11/15/446)
- **Description**: Fix a useless call issue detected by Coverity (CID 1508092). The call to horrible_allowedips_lookup_v4 is unnecessary as its return value is never checked.
- **Files Changed**: `drivers/net/wireguard/selftest/allowedips.c`
- **Status**: ![Merged](https://img.shields.io/badge/Status-Merged-green)

### Contribution 2
- **Commit ID**: `13878083`
- **Patch Link**: [lkml.org link to the patch](https://lkml.org/lkml/2024/11/18/100)
- **Description**: This commit fixes a useless call issue detected by Coverity (CID 1507978). The call to rockchip_i2s_ch_to_io is unnecessary as its return value is never checked or used.
- **Files Changed**: `sound/soc/rockchip/rockchip_i2s_tdm.c`
- **Status**: ![Merged](https://img.shields.io/badge/Status-Merged-green)

### Contribution 3
- **Commit ID**: `13879416`
- **Patch Link**: [lkml.org link to the patch](https://lkml.org/lkml/2024/11/19/164)
- **Description**: This commit fixes an unused value issue detected by Coverity (CID
1519008). The error condition for the invalid MIPI CSI-2 is not
properly handled as the break statement would only exit the switch block
and not the entire loop. Fixed this by returning the error immediately
after the switch block.
- **Files Changed**: `drivers/media/platform/rockchip/rkisp1/rkisp1-dev.c`
- **Status**: ![Awaiting Upstream](https://img.shields.io/badge/Status-Awaiting%20Upstream-blue)

### Contribution 4
- **Commit ID**: `df0b78a8`
- **Patch Link**: [lkml.org link to the patch](https://lkml.org/lkml/2024/11/18/494)
- **Description**: This commit fixes an unused value issue detected by Coverity
(CID 1357987). The value of utime is updated but has no use as it is
updated later on without using the stored value.
- **Files Changed**: `kernel/sched/cputime.c`
- **Status**: ![Under Review](https://img.shields.io/badge/Under_Review-1-yellow)

### Contribution 5
- **Commit ID**: `db9f0e67`
- **Patch Link**: [lkml.org link to the patch](https://lkml.org/lkml/2024/12/6/245)
- **Description**: This commit addresses a structurally dead code issue detected by
Coverity (CID 1602227). An integer is returned early in one of the
switch cases causing the later statements to never be called. The
return statement is removed following convention in the other switch
cases.
- **Files Changed**: `drivers/hwmon/pmbus/tps25990.c`
- **Status**: ![Under Review](https://img.shields.io/badge/Under_Review-1-yellow)

### Contribution 6
- **Commit ID**: `a8ab7a54`
- **Patch Link**: [lkml.org link to the patch](https://lkml.org/lkml/2024/12/6/308)
- **Description**: This patch addresses the Out-of-bounds read issue detected by
Coverity (CID 1602214). The function ath12k_mac_vdev_create() accesses
the vif->link_conf array using link_id, which is derived from
arvif->link_id. In cases where arvif->link_id equals 15, the index
exceeds the bounds of the array, which contains only 15 elements.This
results in an out-of-bounds read.
- **Files Changed**: `drivers/net/wireless/ath/ath12k/mac.c`
- **Status**: ![Under Review](https://img.shields.io/badge/Under_Review-1-yellow)

### Contribution 7
- **Commit ID**: `def5678`
- **Patch Link**: [lkml.org link to the patch](https://lkml.org/lkml/2024/11/15/209)
- **Description**: fixes an "Arguments in wrong order" issue detected by Coverity (CID 1376875).
- **Files Changed**: `net/batman-adv/distributed-arp-table.c`
- **Status**: ![Rejected](https://img.shields.io/badge/Status-Rejected-red)
