# andorid_device_samsung_m307fn
LineageOS Device Tree for Samsung Galaxy M30s|M307FN Model

# How to Build
# Sync the latest sources
repo init -u git://github.com/LineageOS/android.git -b lineage-18.1

repo sync

# Fetch Dependencies
clone android_device_samsung_m30s-common to device/samsung/m30s-common

clone android_device_samsung_m307fn to device/samsung/m307fn

clone android_kernel_samsung_m30s-common to kernel/samsung/m30s-common

fetch all the repositories mentioned in lineage.dependencies to appropriate directories

# setup ccache
export USE_CCACHE=1

export CCACHE_EXEC=/usr/bin/ccache

ccache -M 50G

*#ccache compression - if used lower ccache size to 20G(optional)*

ccache -o compression=true

# Build
source build/envsetup.sh

lunch lineage_m307fn-userdebug

mka bacon
