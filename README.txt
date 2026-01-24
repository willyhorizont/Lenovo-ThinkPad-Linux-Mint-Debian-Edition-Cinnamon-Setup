Lenovo-ThinkPad-Linux-Mint-Debian-Edition-Cinnamon-Setup



Part 1 - Installation

    1. Download LMDE .ISO

    2. Prepare 2 USB stick, Download Ventoy2Disk make 1 USB stick GPT/UEFI and 1 USB stick MBR/Legacy

    3. Download Ventoy2Disk make 1 USB stick GPT/UEFI and 1 USB stick MBR/Legacy

    4. Install LMDE Cinnamon
        ```
        partition: efi
        size: 512MiB
        format: FAT32
        mount point: /boot/efi
        Flags: EFI System Partition, ESP, boot

        partition: root
        size: sisa disk
        format: ext4
        mount point: /
        Flags: none
        ```



Part 2 - Local setup

    1. Removable media
        * OFF <- Prompt or start programs on media insertion

    2. System Settings > Effects
        * OFF <- Desktop and window effects

    3. Privacy
        * OFF <- Remember recently accesed files

    4 Power Management
        * Power
            * On A/C power
                * Turn off the screen when inactive for = 30 minutes
                * Suspend when inactive for = Never
                * When the lid is closed = Suspend
            * On battery power
                * Turn off the screen when inactive for = 5 minutes
                * Suspend when inactive for = Never
                * When the lid is closed = Suspend
        * Brightness
            * ON <- On battery, dim screen when inactive
            * Brightness level when inactive = 30%
            * Dim screen after inactive for = 2 minutes

    5. Screensaver
        * Settings
            * Delay before starting the screensaver = Never
            * ON <- Lock the computer when put to sleep
            * ON <- Lock the computer after the screensaver starts
            * Delay before locking = Lock immediately
        * Customize
            * Date and Time
                * ON <- Always show the clock
                * ON <- Use a custom date and time format
                * Time format = %I:%M %p | %H:%M:%S
                * Date format = (%m/12 month) | %a, %d %b %Y
                * Time Font = Noto Sans Regular 40
                * Date Font = Noto Sans Regular 24
            * Away message
                * Show this message when the screen is locked = @willyhorizont
                * Font = Noto Sans Regular 24
                * OFF <- Ask for a custom message when locking the screen from the menu
            * General
                * OFF <- Allow keyboard shortcut
                * OFF <- Show media player controls
                * OFF <- Show album art
                * ON <- Show info panel
                * OFF <- Allow floating clock and album art widgets

    6. Display
        * Settings
            * ON <- Disable automatic screen rotation
            * ON <- Enable fractional scaling controls (experimental)
        * Layout
            * Monitor scale = 125%

    7. Windows
        * Behavior
            * Location of newly opened windows = Center
        * Alt-Tab
            * OFF <- Show windows from all workspaces

    8. Mouse and Touchpad
        * Mouse
            * Acceleration = Constant
        * Touchpad
            * ON <- Reverse scrolling direction

    9. Date & Time
        * ON <- Use 24h clock
        * ON <- Display the date
        * ON <- Display seconds

    10. System Settings > Font Selection
        * Default Font -> Noto Sans Regular 10
        * Desktop Font -> Noto Sans Regular 10
        * Document Font -> Sans Regular 10
        * Monospace Font -> DejaVu Sans Mono Book 10
        * Window title Font -> Noto Sans Regular 10

    11. Desktop
        * Desktop Layout = Show desktop icons on primary monitor only
        * Desktop Icons
            * OFF <- Computer
            * OFF <- Home
            * OFF <- Trash
            * OFF <- Mounted Drives
            * OFF <- Network
        * Options
            * ON <- Show icons from missing monitors

    12. Change File Explorer settings
        * View
            * ON <- Show Hidden Files
        * Edit
            * Preferences
                * Behavior
                    * Choose: Double click to open item
                    * Choose: Run executable text files when they are opened
                    * OFF <- Automatically mount removable media when inserted and on startup
                    * OFF <- Automatically open a folder for automounted media
                    * OFF <- Prompt or autoron/autostart programs when media are inserted
                    * ON <- Automatically close the devices's tab, pane, or window when a device is unmounted or ejected
                    * OFF <- Detect content of media and suggest application to open
                * List Columns
                    * Name
                    * Size
                    * Type
                    * Date Modified
                    * Detailed Type
                    * MIME Type

    13. Change default screenshot file type to JPG
        ```

        gsettings get org.gnome.gnome-screenshot default-file-type
        gsettings set org.gnome.gnome-screenshot default-file-type "jpg"
        gsettings get org.gnome.gnome-screenshot default-file-type
        ```

    14. Change default screenshot save directory to "~/Pictures/Screenshots"
        ```

        gsettings get org.gnome.gnome-screenshot auto-save-directory
        gsettings set org.gnome.gnome-screenshot auto-save-directory "~/Pictures/Screenshots"
        gsettings get org.gnome.gnome-screenshot auto-save-directory
        ```

    15. Change important-Applets settings
        * Power Manager
            * Display = Show percentage
            * ON <- Always show all batteries
        * Calendar (Taskbar clock)
            * OFF <- Show calendar events
            * OFF <- Show week numbers in calendar
            * ON <- Use custom date format
            * format = (%m/12 month) | %a, %d %b %Y | %H:%M:%S | %I:%M %p
            * tooltip = check phone calendar for more
        * Notifications
            * ON <- Show empty tray
        * Corner bar
            * ON <- Peek at the desktop on hover

    16. Night light
        * ON <- Enable night light
        * Schedule = Specify start and end times
            Start = 18:00
            End = 06:00

    17. Ibus Preferences
        * OFF <- Show icon on system tray

    18. Terminal
        * Cursor shape = I-Beam

    19. Text Editor
        * View
            * ON <- Side pane
        * Edit
            * Preferences
                * Editor
                    * Display
                        * ON <- Display line numbers
                    * Indentation
                        * ON <- Automatic indentation
                * Theme
                    * ON <- Use dark theme variant (if available)
                    * Theme = Oblivion




Part 3 - Network setup

    1. Change official repositories mirrors to the fastest mirrors in Software Sources

    2. Change preferences in Update Manager
        * OFF <- Hide the update manager after applying updates
        * OFF <- Only show a tray icon when updates are available or in case of errors
        * OFF <- Refresh the list of updates automatically
        * ON <- Cinnamon spice updates
        * ON <- Flatpak updates
        * OFF <- Apply updates automatically
        * OFF <- Update Cinnamon spices automatically
        * OFF <- Update Flatpaks automatically
        * OFF <- Remove obsolete kernels and dependencies

    3. Install multimedia codecs

    4. Instal language pack

    5. Turn ON firewall



Part 4 - Copy backups
    * install git and clone https://github.com/willyhorizont/Lenovo-ThinkPad-Linux-Mint-Debian-Edition-Cinnamon-Setup to "~/Documents"
    ```

    sudo apt install git -y
    cd ~/Documents && git clone https://github.com/willyhorizont/Lenovo-ThinkPad-Linux-Mint-Debian-Edition-Cinnamon-Setup
    ```

    * copy fastfetch config.jsonc to "~/.config/fastfetch/config.jsonc"
    ```

    fastfetch
    fastfetch --gen-config
    fastfetch
    cp -r ~/Documents/Lenovo-ThinkPad-Linux-Mint-Debian-Edition-Cinnamon-Setup/fastfetch-config/config.jsonc ~/.config/fastfetch/config.jsonc
    fastfetch
    ```

    * copy icon collection to "~/Icons"
    ```

    [ -e ~/Icons ] && echo "~/Icons exist" || "~/Icons not exist"
    cp -r ~/Documents/Lenovo-ThinkPad-Linux-Mint-Debian-Edition-Cinnamon-Setup/Icons ~/
    [ -e ~/Icons ] && echo "~/Icons exist" || "~/Icons not exist"

    ```

    * copy font collection to "~/.local/share/fonts"
    ```

    [ -e ~/.local/share/fonts ] && echo "~/.local/share/fonts exist" || "~/.local/share/fonts not exist"
    mkdir -p ~/.local/share/fonts && cp -r ~/Documents/Lenovo-ThinkPad-Linux-Mint-Debian-Edition-Cinnamon-Setup/.local-share-fonts/. ~/.local/share/fonts
    [ -e ~/.local/share/fonts ] && echo "~/.local/share/fonts exist" || "~/.local/share/fonts not exist"
    ```

    * create "~/Pictures/Screenshots"
    ```

    [ -e ~/Pictures/Screenshots ] && echo "~/Pictures/Screenshots exist" || "~/Pictures/Screenshots not exist"
    mkdir -p ~/Pictures/Screenshots
    [ -e ~/Pictures/Screenshots ] && echo "~/Pictures/Screenshots exist" || "~/Pictures/Screenshots not exist"
    ```

    * copy desktop wallpaper image collection to "~/Pictures/Wallpapers"
    ```

    [ -e ~/Pictures/Wallpapers ] && echo "~/Pictures/Wallpapers exist" || "~/Pictures/Wallpapers not exist"
    cp -r ~/Documents/Lenovo-ThinkPad-Linux-Mint-Debian-Edition-Cinnamon-Setup/Wallpapers ~/Pictures
    [ -e ~/Pictures/Wallpapers ] && echo "~/Pictures/Wallpapers exist" || "~/Pictures/Wallpapers not exist"
    ```


    * copy login image collection to "/usr/share/backgrounds/popular-iconic"
    ```

    [ -e /usr/share/backgrounds/popular-iconic ] && echo "/usr/share/backgrounds/popular-iconic exist" || "/usr/share/backgrounds/popular-iconic not exist"
    sudo mkdir -p /usr/share/backgrounds/popular-iconic
    [ -e /usr/share/backgrounds/popular-iconic ] && echo "/usr/share/backgrounds/popular-iconic exist" || "/usr/share/backgrounds/popular-iconic not exist"

    [ -e /usr/share/backgrounds/popular-iconic/Wildebeest-and-Penguin-in-Deep-Sea.jpg ] && echo "/usr/share/backgrounds/popular-iconic/Wildebeest-and-Penguin-in-Deep-Sea.jpg exist" || "/usr/share/backgrounds/popular-iconic/Wildebeest-and-Penguin-in-Deep-Sea.jpg not exist"
    sudo cp -r ~/Documents/Lenovo-ThinkPad-Linux-Mint-Debian-Edition-Cinnamon-Setup/Wallpapers/Wildebeest-and-Penguin-in-Deep-Sea.jpg /usr/share/backgrounds/popular-iconic
    [ -e /usr/share/backgrounds/popular-iconic/Wildebeest-and-Penguin-in-Deep-Sea.jpg ] && echo "/usr/share/backgrounds/popular-iconic/Wildebeest-and-Penguin-in-Deep-Sea.jpg exist" || "/usr/share/backgrounds/popular-iconic/Wildebeest-and-Penguin-in-Deep-Sea.jpg not exist"
    ```

    * copy .desktop collection to "~/.local/share/applications"
    ```

    cp -r ~/Documents/Lenovo-ThinkPad-Linux-Mint-Debian-Edition-Cinnamon-Setup/.local-share-applications/. ~/.local/share/applications
    ```



Part 5 - Theming

    * Download Actions:
        * Copy Path To Clipboard and xclip
        * Restart Cinnamon

    * Download Applets:
        * Cinnamenu
        * Cassia Window List
        * Enhanced Sound applet

    * Replace default Applets
        * Menu -> Cinnamenu
            * Layout
                * Apllications view mode = Grid
                * ON <- Show sidebar
                * Sidebar location = Bottom
                * Show favorites on sidebar = None
                * Application description placement = Tootltips
                * ON <- Show categories
                * OFF <- Show bookmarks and places
                * OFF <- Show recent items
                * ON <- Show favorite apps category
                * OFF <- Show home folder
                * OFF <- Show emoji category
            * Behavior
                * OFF <- Open menu on hover
                * OFF <- Use menu animations
                * ON <- Activate categories on click
                * Open menu on category = Favorite apps
                * OFF <- Enable autoscrolling
                * OFF <- Show hidden files
            * Search
                * OFF <- Emoji search
                * Web search opton = None
                * OFF <- Web search suggestion
                * OFF <- Search home folder
                * OFF <- Web history search
                * OFF <- Web bookmarks search
                * OFF <- Wikipedia search
            * Appearance
                * ON <- Use a custom icon
                * Panel icon = linuxmint-logo-filled-badge
                * OFF <- Use a custom icon size
                * Panel text = ""
            * Menu
                * Category icon size (pixels) = 20
                * Application list icon size (pixels) = 20
                * Application grid icon size (pixels) = 60
                * Sidebar icon size (pixels) = 28
                * OFF <- Use sidebar box style
                * ON <- Use tile style
        * Grouped window list -> Cassia Window List
            * General
                * Window list behavior style = Grouped
                * Pinning of window list buttons = Common across workspaces
                * OFF <- Icon animation when launching new windows
                * OFF <- Only show windows on the same monitor
                * OFF <- Includes windows from all workspaces
                * OFF <- Allow prioritizing window list button order
                * ON <- Show tooltips for window list buttons
                * Spacing between buttons (pixels) = 0
                * OFF <- Show a full size window preview when hovering over a button
                * OFF <- Automatic focus change when leaving the panel
            * Mouse
                * Left button action for grouped buttons = Show thumbnail menu
                * Middle button action = Do nothing
                * Back button action = Do nothing
                * Forward button action = Do nothing
                * Scroll wheel action = Do nothing
            * Labels
                * Label contents = Window title
                * Display labels for generic window list buttons = Never
                * Display labels for pinned buttons = Never
                * Hide labels for = None
                * Display status indicators = None
                * OFF <- Animate label
                * Icon overlay label contents = Application group window count
                * ON <- Only display label when needed
                * Display window progress information (%) = Using icon overlay label
            * Thumbnails
                * ON <- Show window thumbnails in the popup window list menu
                * Default thumbnail window size = Medium
                * OFF <- Sort grouped button thumbnail menu items
                * OFF <- Show a full size window preview when hovering over a thumbnail
                * OFF <- Automatic focus change when leaving the thumbnail menu
                * ON <- Show on hover
                * Adjust the thumbnail window sizes using the scroll wheel = Off
                * Thumbnail window middle button action = Do nothing
                * Thumbnail window back button action = Do nothing
                * Thumbnail window forward button action = Do nothing
            * Advanced
                * Fade animation effect duration (milliseconds) = 0
        * Sound -> Enhanced Sound applet
            * Menus
                * OFF <- Control Players
                * OFF <- Keep the player controller selector open
                * OFF <- Avoid displaying controllers twice
                * ON <- Do not show any cover art in the menu
                * Shorten Artist and Title = None
                * ON <- Do not use playerctl
                * ON <- Keep the App selector open
                * ON <- Keep the Output Device selector open
                * ON <- Keep the Input Device selector open
                * OFF <- Keep the Command selector open
            * Behavior
                * OFF <- Keep the album art as an icon when adjusting the volume
                * OFF <- Hide system tray icons for compatible players
                * ON <- Show volume in tooltip
                * OFF <- Show player in tooltip
                * OFF <- Show song artist and title in tooltip
            * Icon
                * OFF <- Keep the album art as an icon when adjusting the volume
                * OFF <- Display volume level near icon
                * ON <- Display icon indicating that the microphone is muted, if applicable
                * ON <- Display icon indicating that the microphone is activated, if applicable

    * Hide Applets
        * Printers
        * Favorites
        * Keyboard
    * Applets order
        1. Cinnamenu
        2. Separator
        3. Cassia Window List
        4. Removable drives
        5. System Tray
        6. Network Manager
        7. XApp Status Applet (Bluetooth and Update Manager)
        8. Enhanced Sound applet
        9. Power Manager
        10. Calendar (Taskbar clock)
        11. Notifications
        12. Corner bar

    * Login Window
        * Appearance
            * Background = "/usr/share/backgrounds/popular-iconic/Wildebeest-and-Penguin-in-Deep-Sea.jpg"
            * Background color = black
            * GTK theme = Mint-Y Grey
            * Icon theme = Mint-Y Sand
            * Mouse pointer = DMZ-White
        * Settings
            * ON <- Hostname
            * ON <- Accesbility options
            * ON <- Battery power
            * OFF <- Keyboard layout
            * ON <- Quit menu
            * ON <- Clock
            * Clock format = (%m/12 month) | %a, %d %b %Y | %H:%M:%S | %I:%M %p

    * Install Qogir-Light theme in Themes (cinnamon-settings themes)

    * Themes (cinnamon-settings themes)
        * Mouse Pointer = DMZ-White
        * Applications = Qogir-Light
        * Icons = Mint-Y Sand
        * Desktop = Mint-Y

    * Copy "~/.themes/Qogir-Light" to "~/.local/share/themes"
        ```

        [ -e ~/.local/share/themes/Qogir-Light ] && echo "~/.local/share/themes/Qogir-Light exist" || "~/.local/share/themes/Qogir-Light not exist"
        mkdir -p ~/.local/share/themes && cp -r ~/.themes/Qogir-Light ~/.local/share/themes
        [ -e ~/.local/share/themes/Qogir-Light ] && echo "~/.local/share/themes/Qogir-Light exist" || "~/.local/share/themes/Qogir-Light not exist"
        xed ~/.local/share/themes/Qogir-Light/gtk-3.0/gtk.css
        xed ~/.local/share/themes/Qogir-Light/gtk-3.0/gtk-dark.css
        ```

    * Add this at the end of "~/.local/share/themes/Qogir-Light/gtk-3.0/gtk.css"
        ```css

        /* === make close button looks like minimize/maximize button === */

        headerbar button.titlebutton.close:hover, .titlebar button.titlebutton.close:hover {
                background-color: rgba(74, 76, 89, 0.2);
                color: #4a4c59;
        }

        headerbar button.titlebutton.close:active, .titlebar button.titlebutton.close:active {
                background-color: rgba(74, 76, 89, 0.2);
                color: #4a4c59;
        }
        ```

    * Add this at the end of "~/.local/share/themes/Qogir-Light/gtk-3.0/gtk-dark.css"
        ```css

        /* === make close button looks like minimize/maximize button === */

        headerbar button.titlebutton.close:hover, .titlebar button.titlebutton.close:hover {
                background-color: rgba(224, 229, 235, 0.2);
                color: #e0e5eb;
        }

        headerbar button.titlebutton.close:active, .titlebar button.titlebutton.close:active {
                background-color: rgba(224, 229, 235, 0.2);
                color: #e0e5eb;
        }
        ```

    * Copy "/usr/share/themes/Mint-Y" to "~/.local/share/themes"
        ```

        [ -e ~/.local/share/themes/Mint-Y ] && echo "~/.local/share/themes/Mint-Y exist" || "~/.local/share/themes/Mint-Y not exist"
        mkdir -p ~/.local/share/themes && cp -r /usr/share/themes/Mint-Y ~/.local/share/themes
        [ -e ~/.local/share/themes/Mint-Y ] && echo "~/.local/share/themes/Mint-Y exist" || "~/.local/share/themes/Mint-Y not exist"
        xed ~/.local/share/themes/Mint-Y/cinnamon/cinnamon.css
        ```

    * Add this at the end of "~/.local/share/themes/Mint-Y/cinnamon/cinnamon.css"
        ```css

        /* custom override */

        .prompt-dialog-password-entry:focus, .run-dialog-entry:focus, #menu-search-entry:focus, .popup-menu #notification StEntry:focus, .prompt-dialog-password-entry:hover, .run-dialog-entry:hover, #menu-search-entry:hover, .popup-menu #notification StEntry:hover {
          border: 1px solid #70737a; }
        .grouped-window-list-item-box {
          margin-right: 3px; }
        .grouped-window-list-item-box.top {
          border-top-width: 3px; }
        .grouped-window-list-item-box.bottom {
          border-bottom-width: 3px; }
        .grouped-window-list-item-box.right {a
          border-right-width: 3px; }
        .grouped-window-list-item-box.left {
          border-left-width: 3px; }
        ```



Part 6 - Download or install apps

    * Brave Web Browser
    * Google Chrome
    * Spotify and https://github.com/SpotX-Official/SpotX-Bash
    * Zen Browser
    * Visual Studio Code
    * Zed
    * ONLYOFFICE Desktop Editors
    * RustDesk
    * OBS Studio
    * Audacity
    * LocalSend
    * KDE Connect
    * Shotcut
    * Inkscape
    * GIMP
    * Krita
    * Jitsi Meet
    * Zoom
    * drawio
    * Betterbird / Evolution
    * Balena Etcher
    * Ventoy
    * fresh-text-editor
    * btop



Part 7 - Download and install libraries

    * ttf-mscorefonts-installer



Part 8 - Setup web apps

    * Google Keep
    * Whatsapp
    * Telegram K
    * ChatGPT
    * Google Gemini
    * Microsoft Copilot
    * Deepseek
    * Google Drive
    * Zoom
    * Google Meet
    * Microsoft Teams
    * Excalidraw



Part 9 - Setup preinstalled apps

    * LibreOffice Writer
        * TODO
    * LibreOffice Calc
        * TODO
    * LibreOffice Impress
        * TODO




Part 10 - Finishing

    * Cinnamenu sidebar categories order
        1. Favorite apps
        2. All applications
        3. Internet
        4. Programming
        5. Office
        6. Graphics
        7. Sound & Video
        8. Accessories
        9. Administration
        10. Preferences

    * Cinnamenu Favorite apps order
        * Terminal
        * Google Keep
        * Whatsapp
        * Telegram K
        * ChatGPT
        * Google Gemini
        * Microsoft Copilot
        * Deepseek
        * Grok
        * Claude
        * Meta
        * Brave Web Browser
        * Google Chrome
        * Spotify
        * Files
        * Zed
        * Visual Studio Code
        * Text Editor
        * ONLYOFFICE Document
        * ONLYOFFICE Spreadsheet
        * ONLYOFFICE Presentation
        * RustDesk
        * OBS Studio
        * Audacity
        * LocalSend
        * KDE Connect
        * Google Drive
        * Shotcut
        * Inkscape
        * GIMP
        * Krita
        * Jitsi Meet
        * Zoom
        * Google Meet
        * Microsoft Teams
        * LibreOffice Draw
        * drawio
        * Excalidraw
        * Betterbird / Evolution
        * System Monitor
        * Software Manager
        * Update Manager
        * System Settings

    * Cassia Window List pinned item order
        * System Monitor / btop
        * Terminal
        * File Explorer
        * Spotify
        * youtube-audio-only music streaming // TODO
        * Google Keep
        * Google Chrome (for web development)
        * Brave Web Browser (for primary web browsing)
        * Zed


    * Preferred Applications
        * Web = Brave Web Browser
        * Mail = Evolution / Betterbird
        * Word = ONLYOFFICE Desktop Editors Document
        * Spreadsheet = ONLYOFFICE Desktop Editors Spreadsheet
        * PDF = ONLYOFFICE Desktop Editors

    * Startup Applications
        * OFF <- Print Queue Applet
        * Add Startup Program
            * Terminal
                * Name = Terminal
                * Command = gnome-terminal
                * Comment = Use the command line
                * Startup delay = 0

    * Keyboard
        * Shortcuts
            * Remove
                * Ctrl + Shift + Alt + Up
                * Ctrl + Shift + Alt + Down
                * Ctrl + Shift + Up
                * Ctrl + Shift + Down
                * TODO

    * Visual Studio Code
        * Copy settings-user.json
        * Copy keybindings-user.json
