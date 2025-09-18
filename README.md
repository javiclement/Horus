# Manual AceStream Engine Update for Horus Addon

This guide provides instructions to fix the "You need to buy Proxy server option" error in the Horus addon by manually updating the AceStream engine. This issue occurs because version 1.1.9 of the Horus addon installs AceStream version 3.1.48, which has a known bug. The solution is to replace it with the corrected version 3.1.61.

-----

## 🚀 Installation Instructions

Follow these steps to replace the outdated AceStream engine with the new one.

1.  **Download the compatible engine:** Download the AceStream version 3.1.61 engine from the provided link:

    `https://github.com/javiclement/Horus/releases/download/v3.1.61/acestream_elec.tar.gz`

2.  **Locate the installation directory:** Use a file explorer or an SSH connection to navigate to your Horus addon's data path. You will find the `acestream.engine` folder inside. **Delete all its contents.**

    `.../storage/.kodi/userdata/addon_data/plugin.video.horus/acestream.engine/`

3.  **Copy the new files:** Unzip the `.tar.gz` file you downloaded in step 1 and copy all the extracted files into the now-empty `acestream.engine` folder.

4.  **Grant execution permissions (Crucial step):** Connect to your device via SSH. Navigate to the `acestream.engine` folder and run the command below to grant execution permissions to the start and stop scripts.

    ```bash
    # Navigate to the correct directory
    cd /storage/.kodi/userdata/addon_data/plugin.video.horus/acestream.engine/

    # Grant execution permissions
    chmod +x acestream.start acestream.stop
    ```

5.  **Restart and test:** Restart Kodi completely. The Horus addon will now use the new engine you've installed, and the "Proxy Server" issue should be resolved.
