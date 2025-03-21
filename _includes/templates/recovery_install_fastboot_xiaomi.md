{%- assign device = site.data.devices[page.device] %}
{%- unless device.no_oem_unlock_switch %}
## Unlocking the bootloader

{% include alerts/note.html content="The steps below only need to be run once per device. They **require** a machine running Windows 7 or newer." %}
{% include alerts/warning.html content="Unlocking the bootloader will erase all data on your device! Before proceeding, ensure the data you would like to retain is backed up to your PC and/or your Google account, or equivalent. Please note that OEM backup solutions like Samsung and Motorola backup may not be accessible from LineageOS once installed." %}
{% include alerts/warning.html content="The official unlock tool provided by Xiaomi on their website may be out of date or non-functional, a newer version is provided below." %}

1. Create a Mi account on [Xiaomi's website](https://global.account.xiaomi.com/pass/register). Beware that one account can only unlock four unique devices every year (one HyperOS device, three MIUI devices), and even then only once every 30 days.
2. Add a phone number to your Mi account.
3. Insert a SIM into your phone.
4. Enable developer options in `Settings` > `About Phone` by repeatedly tapping `MIUI Version`.
5. Link the device to your Mi account in `Settings` > `Additional settings` > `Developer options` > `Mi Unlock status`.
6. Download the [Mi Unlock app](https://en.miui.com/unlock/download_en.html) (or [v7.6.727.43](https://miuirom.xiaomi.com/rom/u1106245679/7.6.727.43/miflash_unlock_en_7.6.727.43.zip)).
7. Ensure that your device has the appropriate drivers installed by running `driver_install.exe` (for 32-bit) or `driver_install_64.exe` (for 64-bit), which are included with Mi Unlock, otherwise, the Mi Unlock app may not detect your device.
8. Run the Mi Unlock app and follow the instructions provided by the app. The app may tell you that you have to wait up to 30 days. If it does so, please wait for the quoted amount of time before continuing to the next step! It is ideal to start this step at **midnight (GMT+8)**, as Xiaomi only allows a limited number of devices to be unlocked each day.
9. After the device and Mi account are successfully verified, the bootloader should be unlocked.
10. Since the device resets completely, you will need to re-enable USB debugging to continue.

{% endunless %}

{% include snippets/before_recovery_install.md %}

{% include templates/recovery_install_fastboot_generic.md %}
