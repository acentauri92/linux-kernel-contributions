# linux-kernel-contributions
This repository documents and organizes all of my contributions to the linux kernel with details about each patch submitted to the kernel.

## ![Contributions](https://img.shields.io/badge/Contributions-8-brightgreen)

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
- **Status**: ![Merged](https://img.shields.io/badge/Status-Merged-green)

### Contribution 4
- **Commit ID**: `df0b78a8`
- **Patch Link**: [lkml.org link to the patch](https://lkml.org/lkml/2024/11/18/494)
- **Description**: This commit fixes an unused value issue detected by Coverity
(CID 1357987). The value of utime is updated but has no use as it is
updated later on without using the stored value.
- **Files Changed**: `kernel/sched/cputime.c`
- **Status**: ![Under Review](https://img.shields.io/badge/Under_Review-1-yellow)

### Contribution 5
- **Commit ID**: `d53555e3`
- **Patch Link**: [lkml.org link to the patch](https://lkml.org/lkml/2024/12/12/497)
- **Description**: Remove the logically dead code in the last return statement of
amdgpu_ras_eeprom_init. The condition res < 0 is redundant since
res is already checked for a negative value earlier. Replace
return res < 0 ? res : 0; with return 0 to improve clarity
- **Files Changed**: `drivers/gpu/drm/amd/amdgpu/amdgpu_ras_eeprom.c`
- **Status**:![Merged](https://img.shields.io/badge/Status-Merged-green)

### Contribution 6
- **Commit ID**: `NA` - Reported a bug
- **Patch Link**: [lkml.org link to the patch](https://lore.kernel.org/all/20241219155719.84276-1-rf@opensource.cirrus.com/)
- **Description**: Delete two redundant assignments in cs_dsp_test_bin.c
- **Files Changed**: `drivers/firmware/cirrus/test/cs_dsp_test_bin.c`
- **Status**:![Merged](https://img.shields.io/badge/Status-Merged-green)

### Contribution 7
- **Commit ID**: `8ccc5947`
- **Patch Link**: [lkml.org link to the patch](https://lore.kernel.org/all/20250108050916.52721-1-dheeraj.linuxdev@gmail.com/)
- **Description**: The oxid variable in fdls_process_abts_req() was only being initialized
inside the if (tport) block, but was being used in a debug print statement
after that block. If tport was NULL, oxid would remain uninitialized.  Move
the oxid initialization to happen at declaration using
FNIC_STD_GET_OX_ID(fchdr).
- **Files Changed**: `drivers/scsi/fnic/fdls_disc.c b/drivers/scsi/fnic/fdls_disc.c`
- **Status**:![Awaiting Upstream](https://img.shields.io/badge/Status-Awaiting%20Upstream-blue)

  ### Contribution 8
- **Commit ID**: `61dc1fd9`
- **Patch Link**: [lkml.org link to the patch](https://git.kernel.org/pub/scm/linux/kernel/git/netdev/net.git/commit/?id=61dc1fd9205b)
- **Description**: Implement cleanup of descriptors in the TSO error path of
fec_enet_txq_submit_tso(). The cleanup
1. Unmaps DMA buffers for data descriptors skipping TSO header
2. Clears all buffer descriptors
3. Handles extended descriptors by clearing cbd_esc when enabled
- **Files Changed**: `drivers/net/ethernet/freescale/fec_main.c`
- **Status**:![Merged](https://img.shields.io/badge/Status-Merged-green)
