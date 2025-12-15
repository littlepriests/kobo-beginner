---
title: Install Koreader
weight: 4
---

These instructions are based off [the video](https://www.youtube.com/watch?v=OJ9AIJW-qGI) created by [@Techy-Notes](https://www.youtube.com/@jadehawk) on YouTube. I wanted to transcribe these procedures to preserve them, and give users more options for setting up Koreader. The doc won't cover how to jailbreak your Kindle, nor should you assume that it'll help you use Koreader on non-Kobo devices. 

## Set up Koreader as your default launcher

There is a lot of ejecting, checking, then plugging in your ereader in all of these procedures. This is intentional. It helps you keep clear idea of when things stopped working. 

If you did all these steps without ejecting your ereader once, got to the end, and things were broken, you wouldn't really know the phase that things went south. It's much more helpful to say "I added the file during step X and it worked. But when I completed step Y, I got this error." 

Anyway, be kind to yourself and safely eject, check, and replug it in.  

### Phase 1: Edit Kobo `.conf` file 

0. Plug in your ereader.
1. Go to **`.kobo` > Kobo > Kobo ereader.conf**. 
2. Open the `.conf` file in some kind of text editor (like VS Code, TextEdit, or Notepad) and add this snippet to the top of the file (Kobo will put it in the correct place when it updates):
   
    ```
    [FeatureSettings]
    ExcludeSyncFolders=(\\.(?!kobo|adobe).+|([^.][^/]*/)+\\..+)
    ```

    ![](./images/conf-edit.png)
3. Save, then safely eject your ereader.

{{< callout type="note" >}}
I'm not sure what this step does but I've reached out to Techy-Notes to confirm why we do this. What I can confirm right now is that my Kobo has worked just fine with this edit. {{< /callout >}}

### Phase 2: Install NickelMenu

0. Plug in your ereader.
1. Go to the [release page of the NickelMenu repository](https://github.com/pgaskin/NickelMenu/releases) and download the latest release of `KoboRoot.tgz`. 
    * The file you need is in the **Assets** section. 
    * I strongly recommend that you keep a copy of the most recent release handy. NickelMenu sometimes disappears as we tinker with our ereader, and the best way to get it back is to follow the NickelMenu install step.
2. Find where `KoboRoot.tgz` downloaded on your PC, then copy `KoboRoot.tgz` and paste it into the `.kobo` directory.

    ![An image that shows where KoboRoot appears inside the .kobo directory](./images/nm-koboroot.png)

3. Eject your ereader and let it update. 
4. Let Kobo boot up, and confirm that **NickelMenu** appears as a new menu item. Should be on the far right after **More**. 
5. Reconnect your Kobo again (lol), then look at the root directory. Notice the new folder that has appeared in your directory called `.adds`: that's good.
6. Open `.adds` to see a new folder named `nm`. Inside the `nm` directory, create a new file called `menu` (without a file extension) and paste in the following code snippet:

    ```
    experimental :menu_main_15505_icon :/mnt/onboard/.adds/nm/.icon.png
    experimental: menu_main_15505_label : +NM+

    menu_item    : main                  : Koreader+            : cmd_spawn        :quiet       :exec /mnt/onboard/.adds/Koreader/Koreader.sh
    menu_item    : main                  : Dark Mode            : nickel_setting   : toggle     : dark_mode
    menu_item    : main                  : Screenshots          : nickel_setting   : toggle     : screenshots
    menu_item    : main                  : Import books         : nickel_misc      : rescan_books_full
    menu_item    : main                  : Reboot               : power            : reboot
    menu_item    : main                  : Shutdown             : power            : shutdown
    menu_item    : main                  : WiFi On/Off          : nickel_setting   : toggle     : force_wifi
                                        chain_success        : nickel_wifi      : toggle
    menu_item    : main                  : USB Connect          : nickel_misc      : force_usb_connection
    # ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- #
    menu_item    : reader                : Dark Mode            : nickel_setting   : toggle     : dark_mode
    menu_item    : reader                : Screenshots          : nickel_setting   : toggle     : screenshots
    menu_item    : reader                : Goodreads            : nickel_browser   : https://www.goodreads.com/book
    menu_item    : reader                : USB Connect          : nickel_misc      : force_usb_connection
    # ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- #
    menu_item    : library               : Dark Mode            : nickel_setting   : toggle     : dark_mode
    menu_item    : library               : Screenshots          : nickel_setting   : toggle     : screenshots
    menu_item    : library               : Import books         : nickel_misc      : rescan_books_full
    menu_item    : library               : Reboot               : power            : reboot
    menu_item    : library               : Shutdown             : power            : shutdown
    menu_item    : library               : WiFi On/Off          : nickel_setting   : toggle     : force_wifi
                                        chain_success        : nickel_wifi      : toggle
    menu_item    : library               : USB Connect          : nickel_misc      : force_usb_connection
    ```

7. Eject safely, let your ereader update, and confirm that menu options appear by clicking the NickelMenu item on your default Kobo page. 

### Phase 3: Install Koreader

0. Plug in your ereader (lol).
1. Go to the [release page of the Koreader repository](https://github.com/Koreader/Koreader/releases) and download the file that corresponds with your ereader device. The files you need are located in the **Assets** subsection.

    ![From the releases page, there's a section called Assets. It contains the install file](./images/Koreader-assets.png)

2. It's a `.zip` file, so we need to extract its contents. Right click the `.zip` folder you just downloaded, and extract. A duplicate folder without the `.zip` file extension should appear in your working directory.
3. Inside that newly extracted folder, find the `Koreader` subdirectory, then right click copy that folder.
4. Paste the folder into `.adds`. The directory should now look like this:

   ![An image that shows the `.adds` folder with the two newly installed folders](./images/kr-nm-directory.png)

5. Eject your ereader and let it update, then view the fruits of your labor!

