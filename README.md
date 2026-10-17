# Local manifest: Galaxy Core Prime SM-G360T1 (cprimeltemtr)

LineageOS 14.1 (Android 7.1.2) for the MetroPCS Galaxy Core Prime.

```bash
repo init -u https://github.com/LineageOS/android.git -b cm-14.1 --depth=1
mkdir -p .repo/local_manifests
curl -L -o .repo/local_manifests/cprimeltemtr.xml \
  https://raw.githubusercontent.com/tadashiutau/local_manifests/lineage-14.1/cprimeltemtr.xml
repo sync -c --no-tags --no-clone-bundle
# The WebView prebuilts are stored in Git LFS:
for a in arm arm64 x86 x86_64; do (cd external/chromium-webview/prebuilt/$a && git lfs pull); done
```

Build (Ubuntu 18.04 with OpenJDK 8):

```bash
source build/envsetup.sh
brunch cprimeltemtr
```

| Path | Repo | Branch |
|---|---|---|
| device/samsung/cprimeltemtr | tadashiutau/android_device_samsung_cprimeltemtr | lineage-14.1 |
| device/samsung/coreprimelte-common | tadashiutau/android_device_samsung_coreprimelte-common | cprimeltemtr-14.1 |
| device/samsung/msm8916-common | tadashiutau/android_device_samsung_msm8916-common | cprimeltemtr-14.1 |
| kernel/samsung/msm8916 | tadashiutau/android_kernel_samsung_msm8916 | cprimeltemtr-14.1 |
| vendor/samsung | tadashiutau/proprietary_vendor_samsung | cprimeltemtr-14.1 |
