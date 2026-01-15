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
        * Titlebar
            * Action on titlebar middle-click = None 
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
        * First day of the week = Monday

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
        gsettings set org.gnome.gnome-screenshot default-file-type "jpg"
        gsettings get org.gnome.gnome-screenshot default-file-type
        ```

    14. Change default screenshot save directory to "~/Pictures/Screenshots"
        ```
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
    * install git
    * clone https://github.com/willyhorizont/Lenovo-ThinkPad-Linux-Mint-Debian-Edition-Cinnamon-Setup to "~/Documents"
    * copy fastfetch config.jsonc to "~/.config/fastfetch/config.jsonc"
    * copy icon collection to "~/Icons"
    * copy font collection to "~/.local/share/fonts"
    * create "~/Pictures/Screenshots"
    * copy wallpaper collection to "~/Pictures/Wallpapers"



Part 5 - Theming

    * Download Actions:
        * Copy Path To Clipboard
        * Restart Cinnamon

    * Download Applets:
        * Cinnamenu
        * Cassia Window List
        * Enhanced Sound applet

    * Replace default Applets
        * Menu -> Cinnamenu
        * Grouped window list -> Cassia Window List
        * Sound -> Enhanced Sound applet

    * Create "/usr/share/backgrounds/popular-iconic"

    * Login Window
        * Appearance
            * Background = "/usr/share/backgrounds/popular-iconic/Wildebeest and Penguin in Deep Sea.jpg"
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
        .grouped-window-list-item-box.right {
          border-right-width: 3px; }
        .grouped-window-list-item-box.left {
          border-left-width: 3px; }
        ```

    * Applets > Enhanced Sound applet
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
            * ON <- Show volume in tooltip
            * OFF <- Show player in tooltip
            * OFF <- Show song artist and title in tooltip
        * Icon
            * OFF <- Display volume level near icon
            * ON <- Display icon indicating that the microphone is muted, if applicable
            * ON <- Display icon indicating that the microphone is activated, if applicable



Part 6 - Download or install apps

    * Brave Web Browser
    * Google Chrome
    * Spotify
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



Part 7 - Copy .desktop collection to "~/.local/share/applications"

    * cinnamon-menu-editor.desktop
    * webapp-manager.desktop
    * restart-cinnamon.desktop
    * betterbird.desktop
    * onlyoffice-desktopeditors-document.desktop
    * onlyoffice-desktopeditors-presentation.desktop
    * onlyoffice-desktopeditors-spreadsheet.desktop



Part 8 - Download and install libraries

    * xclip
    * ttf-mscorefonts-installer
    * fastfetch



Part 9 - Setup web apps

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



Part 10 - Setup preinstalled apps

    * Terminal
        * Cursor shape = I-Beam
    * Text Editor
        * ON <- Use dark theme variant (if available)
        * Theme = Oblivion
    * LibreOffice Writer
        * TODO
    * LibreOffice Calc
        * TODO
    * LibreOffice Impress
        * TODO




Part 11 - Finishing

    * Applets > Cinnamenu
        * Layout
            * Apllications view mode = Grid
            * ON <- Show sidebar
            * Sidebar location = bottom
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
            * OFF <- Activate categories on click
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
        * Sidebar categories order
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
        * Favorite apps
            1. Terminal
            2. Google Keep
            3. Whatsapp
            4. Telegram K
            5. ChatGPT
            6. Google Gemini
            7. Microsoft Copilot
            8. Deepseek
            9. Brave Web Browser
            10. Google Chrome
            11. Spotify
            12. Zen Browser
            13. Files
            14. Visual Studio Code
            15. Zed
            16. Text Editor
            17. ONLYOFFICE Document
            18. ONLYOFFICE Spreadsheet
            19. ONLYOFFICE Presentation
            20. RustDesk
            21. LibreOffice Writer
            22. LibreOffice Calc
            23. LibreOffice Impress
            24. OBS Studio
            25. Audacity
            26. LocalSend
            27. KDE Connect
            28. Google Drive
            29. Shotcut
            30. Inkscape
            31. GIMP
            32. Krita
            33. Jitsi Meet
            34. Zoom
            35. Google Meet
            36. Microsoft Teams
            37. LibreOffice Draw
            38. drawio
            39. Excalidraw
            40. Betterbird / Evolution
            41. System Monitor
            42. Software Manager
            43. Update Manager
            44. System Settings

    * Applets > Cassia Window List
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
        * Pinned app
            1. System Monitor
            2. Terminal
            3. File Explorer
            4. Spotify
            5. Zen Web Browser (for youtube-audio-only music streaming)
            6. Google Keep
            7. Google Chrome (for web development)
            8. Brave Web Browser (for primary web browsing)
            9. VSCode
            10. Zed

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
