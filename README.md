# andorid_device_samsung_m215f
LineageOS Device Tree for Samsung Galaxy M21|M215F Model

# How to Build
# Sync the latest sources
repo init -u git://github.com/LineageOS/android.git -b lineage-18.1

repo sync

# Fetch Dependencies
clone android_device_samsung_m21-common to device/samsung/m21-common

clone android_device_samsung_m307fn to device/samsung/m215f

clone android_kernel_samsung_m21-common to kernel/samsung/m21-common

fetch all the repositories mentioned in lineage.dependencies to appropriate directories

# setup ccache
export USE_CCACHE=1

export CCACHE_EXEC=/usr/bin/ccache

ccache -M 50G

*#ccache compression - if used lower ccache size to 20G(optional)*

ccache -o compression=true

# Build
source build/envsetup.sh

lunch lineage_m215f-userdebug

mka bacon
