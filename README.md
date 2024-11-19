# linux-kernel-contributions
This repository documents and organizes all of my contributions to the linux kernel with details about each patch submitted to the kernel.

## ![Contributions](https://img.shields.io/badge/Contributions-4-brightgreen)

### Contribution 1
- **Commit ID**: `13876109`  
- **Patch Link**: [lkml.org link to the patch](https://lkml.org/lkml/2024/11/15/446)
- **Description**: Fix a useless call issue detected by Coverity (CID 1508092). The call to horrible_allowedips_lookup_v4 is unnecessary as its return value is never checked.
- **Files Changed**: `drivers/net/wireguard/selftest/allowedips.c`
- **Status**: ![Awaiting Upstream](https://img.shields.io/badge/Status-Awaiting%20Upstream-blue)

### Contribution 2
- **Commit ID**: `13878083`
- **Patch Link**: [lkml.org link to the patch](https://lkml.org/lkml/2024/11/18/100)
- **Description**: This commit fixes a useless call issue detected by Coverity (CID 1507978). The call to rockchip_i2s_ch_to_io is unnecessary as its return value is never checked or used.
- **Files Changed**: `sound/soc/rockchip/rockchip_i2s_tdm.c`
- **Status**: ![Under Review](https://img.shields.io/badge/Under_Review-1-yellow)

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
- **Commit ID**: `def5678`
- **Patch Link**: [lkml.org link to the patch](https://lkml.org/lkml/2024/11/15/209)
- **Description**: fixes an "Arguments in wrong order" issue detected by Coverity (CID 1376875).
- **Files Changed**: `net/batman-adv/distributed-arp-table.c`
- **Status**: ![Rejected](https://img.shields.io/badge/Status-Rejected-red)
