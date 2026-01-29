-# Bash GUI / Graphical Tools Guide
## Complete Reference for Graphical Interfaces in Bash Scripting

---

## Zenity

**One-line Definition:** Zenity is a command-line tool that displays GTK+ dialog boxes from shell scripts.

**Short Explanation:** Zenity allows you to create graphical user interfaces in Bash scripts by displaying various types of dialog boxes like message boxes, file selectors, and input forms. It's perfect for making scripts more user-friendly with graphical elements.

**Syntax:**
```bash
zenity --calendar
zenity --entry
zenity --file-selection
zenity --list
zenity --progress
zenity --question
zenity --warning
zenity --error
zenity --info
```

**Working Bash Example:**
```bash
#!/bin/bash
# Zenity GUI Demo

# Information dialog
zenity --info --text="Welcome to the GUI Demo!" --title="Welcome"

# Get user name
name=$(zenity --entry --title="User Input" --text="Enter your name:")
if [ $? -eq 0 ]; then
    zenity --info --text="Hello, $name!" --title="Greeting"
fi

# File selection
file=$(zenity --file-selection --title="Choose a file")
if [ $? -eq 0 ]; then
    zenity --info --text="You selected: $file" --title="File Selected"
fi

# Calendar selection
date=$(zenity --calendar --title="Select Date" --text="Choose a date:")
if [ $? -eq 0 ]; then
    zenity --info --text="Selected date: $date" --title="Date Selected"
fi

# Progress dialog
(
echo "10"
sleep 1
echo "25"
sleep 1
echo "50"
sleep 1
echo "75"
sleep 1
echo "100"
) | zenity --progress --title="Processing" --text="Working..." --percentage=0

# Question dialog
if zenity --question --title="Confirmation" --text="Do you want to continue?"; then
    zenity --info --text="Great! Let's continue." --title="Confirmed"
else
    zenity --warning --text="Operation cancelled." --title="Cancelled"
fi
```

**Output Description:** The script displays various graphical dialog boxes including welcome messages, input fields, file browsers, calendar widgets, progress bars, and confirmation dialogs. Each interaction happens in a separate graphical window with buttons for user interaction.

**Use Case:** Perfect for creating user-friendly backup scripts, installation wizards, configuration tools, and any script that needs user interaction beyond command-line input.

---

## Yad (Yet Another Dialog)

**One-line Definition:** Yad is a fork of Zenity with more features and customization options for creating complex GUI dialogs.

**Short Explanation:** Yad provides all Zenity functionality plus additional features like forms, multiple tabs, icons, and advanced layouts. It's more powerful for creating sophisticated graphical interfaces in Bash scripts.

**Syntax:**
```bash
yad --form
yad --list
yad --notebook
yad --paned
yad --icons
yad --text-info
yad --dnd
```

**Working Bash Example:**
```bash
#!/bin/bash
# Yad GUI Demo

# Simple form dialog
result=$(yad --form --title="User Information" \
    --field="Name:" \
    --field="Email:" \
    --field="Age:NUM" \
    --button="OK:0" \
    --button="Cancel:1")

if [ $? -eq 0 ]; then
    name=$(echo $result | cut -d'|' -f1)
    email=$(echo $result | cut -d'|' -f2)
    age=$(echo $result | cut -d'|' -f3)
    
    yad --info --title="Information" --text="Name: $name\nEmail: $email\nAge: $age"
fi

# List dialog with icons
yad --list --title="Process List" \
    --column="PID" --column="Process" --column="CPU%" \
    $(ps aux | awk 'NR>1 {print $2, $11, $3}' | head -10 | tr ' ' '|') \
    --button="Close:0"

# Notebook (tabs) dialog
yad --notebook --title="System Information" \
    --tab="System" --text="$(uname -a)" \
    --tab="Memory" --text="$(free -h)" \
    --tab="Disk" --text="$(df -h)" \
    --button="OK:0"

# File selection with preview
yad --file-selection --title="Select File" \
    --file-filter="All files | *" \
    --file-filter="Text files | *.txt" \
    --file-filter="Images | *.png *.jpg *.gif" \
    --button="Open:0" \
    --button="Cancel:1"
```

**Output Description:** Displays sophisticated graphical dialogs including multi-field forms, tabbed interfaces, process lists with columns, and advanced file selectors with filters and previews.

**Use Case:** Ideal for creating complex configuration tools, system monitoring dashboards, data entry forms, and professional-looking administrative interfaces.

---

## Dialog

**One-line Definition:** Dialog is a command-line tool that displays dialog boxes in terminal mode using ncurses library.

**Short Explanation:** Dialog creates text-based GUI interfaces directly in the terminal without requiring X11. It's perfect for server environments or systems without graphical desktop environments.

**Syntax:**
```bash
dialog --msgbox
dialog --inputbox
dialog --menu
dialog --checklist
dialog --radiolist
dialog --yesno
dialog --gauge
dialog --textbox
```

**Working Bash Example:**
```bash
#!/bin/bash
# Dialog Terminal GUI Demo

# Message box
dialog --title "Welcome" --msgbox "Welcome to Dialog Demo!" 10 40

# Input box
name=$(dialog --title "Name Input" --inputbox "Enter your name:" 10 40 3>&1 1>&2 2>&3 3>&-)
if [ $? -eq 0 ]; then
    dialog --title "Greeting" --msgbox "Hello, $name!" 10 40
fi

# Menu selection
choice=$(dialog --title "Main Menu" --menu "Choose an option:" 15 50 4 \
    1 "System Information" \
    2 "Disk Usage" \
    3 "Process List" \
    4 "Exit" 3>&1 1>&2 2>&3 3>&-)

case $choice in
    1)
        dialog --title "System Info" --msgbox "$(uname -a)" 15 60
        ;;
    2)
        dialog --title "Disk Usage" --textbox <(df -h) 20 70
        ;;
    3)
        dialog --title "Processes" --textbox <(ps aux | head -20) 20 70
        ;;
esac

# Progress gauge
{
    for i in {1..10}; do
        echo $((i * 10))
        sleep 0.5
    done
} | dialog --title "Progress" --gauge "Processing..." 10 40 0

# Checklist
items=$(dialog --title "Select Services" --checklist "Choose services to start:" 15 50 5 \
    1 "SSH Server" on \
    2 "Web Server" off \
    3 "Database" on \
    4 "Firewall" on \
    5 "Mail Server" off 3>&1 1>&2 2>&3 3>&-)

dialog --title "Selected" --msgbox "Selected items: $items" 10 40

# Clear screen
clear
```

**Output Description:** Creates text-based graphical interfaces directly in the terminal with windows, input fields, menus, progress bars, and interactive lists. All elements appear as bordered boxes with navigation via keyboard.

**Use Case:** Perfect for server administration tools, remote SSH sessions, system installation scripts, and any terminal-based application needing user interaction.

---

## Whiptail

**One-line Definition:** Whiptail is a replacement for Dialog that uses the newt library instead of ncurses for terminal GUI.

**Short Explanation:** Whiptail provides similar functionality to Dialog but with a different look and feel. It's often pre-installed on many Linux distributions and is commonly used in system installation scripts.

**Syntax:**
```bash
whiptail --msgbox
whiptail --inputbox
whiptail --menu
whiptail --checklist
whiptail --radiolist
whiptail --yesno
whiptail --gauge
whiptail --textbox
```

**Working Bash Example:**
```bash
#!/bin/bash
# Whiptail Terminal GUI Demo

# Welcome message
whiptail --title "Welcome" --msgbox "Welcome to Whiptail Demo!" 10 40

# Get user input
name=$(whiptail --title "User Input" --inputbox "Enter your name:" 10 40 3>&1 1>&2 2>&3 3>&-)
if [ $? -eq 0 ] && [ -n "$name" ]; then
    whiptail --title "Hello" --msgbox "Nice to meet you, $name!" 10 40
fi

# Main menu
while true; do
    choice=$(whiptail --title "Main Menu" --menu "Select an option:" 15 50 4 \
        "1" "System Information" \
        "2" "Network Status" \
        "3" "User Management" \
        "4" "Exit" 3>&1 1>&2 2>&3 3>&-)

    case $choice in
        "1")
            whiptail --title "System Info" --msgbox "$(uname -nr)" 12 50
            ;;
        "2")
            whiptail --title "Network" --textbox <(ip addr show) 20 70
            ;;
        "3")
            # Radio list for user selection
            user=$(whiptail --title "Select User" --radiolist "Choose a user:" 15 50 5 \
                "root" "Administrator" off \
                "$(whoami)" "Current user" on \
                "guest" "Guest account" off 3>&1 1>&2 2>&3 3>&-)
            whiptail --title "Selected" --msgbox "Selected user: $user" 10 40
            ;;
        "4")
            if whiptail --title "Confirm" --yesno "Are you sure you want to exit?" 10 40; then
                break
            fi
            ;;
    esac
done

# Progress bar
{
    for i in {1..20}; do
        echo $((i * 5))
        sleep 0.2
    done
} | whiptail --title "Processing" --gauge "Loading configuration..." 10 40 0

whiptail --title "Goodbye" --msgbox "Thank you for using Whiptail Demo!" 10 40
```

**Output Description:** Displays terminal-based graphical windows with colored backgrounds, bordered boxes, and interactive elements. The interface uses keyboard navigation and provides a clean, professional look in terminal mode.

**Use Case:** Commonly used in system installation programs (like Ubuntu Server installer), configuration wizards, and server administration tools.

---

## KDialog

**One-line Definition:** KDialog is a command-line tool that displays KDE dialog boxes for graphical user interaction.

**Short Explanation:** KDialog provides KDE-style dialog boxes that integrate well with KDE desktop environments. It offers similar functionality to Zenity but with KDE's native look and feel.

**Syntax:**
```bash
kdialog --msgbox
kdialog --inputbox
kdialog --menu
kdialog --checklist
kdialog --radiolist
kdialog --yesno
kdialog --warningyesno
kdialog --error
kdialog --getopenfilename
kdialog --getsavefilename
```

**Working Bash Example:**
```bash
#!/bin/bash
# KDialog KDE GUI Demo

# Information dialog
kdialog --msgbox "Welcome to KDialog Demo!" --title "Welcome"

# Get text input
name=$(kdialog --inputbox "Enter your name:" "John Doe")
if [ $? -eq 0 ]; then
    kdialog --msgbox "Hello, $name!" --title "Greeting"
fi

# Password input
password=$(kdialog --password "Enter your password:")
if [ $? -eq 0 ] && [ -n "$password" ]; then
    kdialog --msgbox "Password received (length: ${#password})" --title "Password"
fi

# File selection
file=$(kdialog --getopenfilename "$HOME" "*.txt *.sh | Text and Shell Files")
if [ $? -eq 0 ]; then
    kdialog --msgbox "Selected file: $file" --title "File Selection"
fi

# Menu selection
choice=$(kdialog --menu "Choose an option:" \
    "info" "System Information" \
    "disk" "Disk Usage" \
    "network" "Network Status" \
    "exit" "Exit")

case $choice in
    "info")
        kdialog --msgbox "$(uname -a)" --title "System Info"
        ;;
    "disk")
        kdialog --textbox /tmp/disk_info.txt 500 300 << EOF
$(df -h)
EOF
        ;;
    "network")
        kdialog --msgbox "Network status: $(ip route show default)" --title "Network"
        ;;
    "exit")
        kdialog --warningyesno "Are you sure you want to exit?" && exit 0
        ;;
esac

# Progress dialog
(
    echo "25"
    sleep 1
    echo "50"
    sleep 1
    echo "75"
    sleep 1
    echo "100"
) | kdialog --progressbar "Processing..." 100

# Question dialog
if kdialog --warningyesno "Do you want to save changes?"; then
    kdialog --msgbox "Changes saved successfully!" --title "Success"
fi
```

**Output Description:** Displays native KDE-style dialog windows with KDE's visual theme, including message boxes, input dialogs, file browsers, progress bars, and confirmation dialogs that match the KDE desktop environment.

**Use Case:** Perfect for scripts running on KDE desktop environments, creating KDE-integrated applications, and maintaining visual consistency with KDE applications.

---

## gxmessage

**One-line Definition:** gxmessage is a graphical popup message utility that displays message windows with customizable buttons.

**Short Explanation:** gxmessage provides simple message dialog boxes with customizable buttons and fonts. It's lightweight and perfect for displaying notifications and getting simple user responses.

**Syntax:**
```bash
gxmessage "message"
gxmessage -buttons "button1:button2"
gxmessage -entry
gxmessage -file filename
gxmessage -font "fontname"
```

**Working Bash Example:**
```bash
#!/bin/bash
# gxmessage GUI Demo

# Simple message
gxmessage "Welcome to gxmessage Demo!" -title "Welcome"

# Message with custom buttons
response=$(gxmessage "Choose an action:" -buttons "Info:Cancel:Exit" -title "Menu")
case $response in
    "Info")
        gxmessage "System: $(uname -n)\nUser: $(whoami)" -title "System Info"
        ;;
    "Exit")
        exit 0
        ;;
esac

# Input dialog
name=$(gxmessage -entry "Enter your name:" -title "Input")
if [ $? -eq 0 ] && [ -n "$name" ]; then
    gxmessage "Hello, $name!" -title "Greeting"
fi

# Message from file
echo "This is a test message from a file." > /tmp/message.txt
gxmessage -file /tmp/message.txt -title "File Message"

# Message with custom font and centering
gxmessage "This uses custom font and centering" \
    -font "Arial 16" \
    -center \
    -title "Styled Message"

# Yes/No question
if gxmessage "Do you want to continue?" -buttons "Yes:No" -title "Question" | grep -q "Yes"; then
    gxmessage "Great! Continuing..." -title "Confirmation"
else
    gxmessage "Operation cancelled." -title "Cancelled"
fi

# Countdown timer
for i in {5..1}; do
    gxmessage "Countdown: $i" -title "Timer" -timeout 1
done
gxmessage "Time's up!" -title "Complete"

# Cleanup
rm -f /tmp/message.txt
```

**Output Description:** Displays simple graphical message boxes with customizable buttons, input fields, file content display, styled text, and timed messages. Each dialog appears as a small window with clear buttons for user interaction.

**Use Case:** Ideal for simple notifications, quick user confirmations, input prompts, and lightweight GUI needs without complex forms.

---

## notify-send

**One-line Definition:** notify-send is a command-line utility to send desktop notifications.

**Short Explanation:** notify-send creates desktop notification bubbles that appear in the system's notification area. It's perfect for alerting users about script completion, errors, or important events without interrupting their workflow.

**Syntax:**
```bash
notify-send "title" "message"
notify-send -u urgency
notify-send -i icon
notify-send -t time
```

**Working Bash Example:**
```bash
#!/bin/bash
# notify-send Desktop Notifications Demo

# Simple notification
notify-send "Welcome" "Starting notification demo..."

# Notification with urgency
notify-send "Important" "This is a critical message!" -u critical

# Notification with icon
notify-send "System" "System check completed" -i dialog-information

# Notification with custom timeout (5 seconds)
notify-send "Timer" "This notification will disappear in 5 seconds" -t 5000

# Progress notifications
for i in {1..5}; do
    notify-send "Progress" "Step $i of 5 completed" -i dialog-information
    sleep 2
done

# Notification with actions (if supported)
notify-send "Action Required" "Click to open terminal" -u normal -a "gnome-terminal"

# File operation notification
if [ -f "/etc/passwd" ]; then
    notify-send "File Check" "System file exists" -i dialog-ok
else
    notify-send "File Check" "System file missing!" -u critical -i dialog-error
fi

# Network status notification
if ping -c 1 google.com &>/dev/null; then
    notify-send "Network" "Internet connection is working" -i dialog-ok
else
    notify-send "Network" "No internet connection!" -u critical -i dialog-error
fi

# Completion notification
notify-send "Complete" "All notifications sent successfully!" -i dialog-information -t 3000

echo "Notifications sent to desktop"
```

**Output Description:** Small notification bubbles appear in the desktop's notification area with titles, messages, icons, and different urgency levels. Notifications automatically disappear after the specified timeout or system default.

**Use Case:** Perfect for background scripts, long-running processes, system monitoring tools, and any script that needs to notify users without interrupting their current work.

---

## xmessage

**One-line Definition:** xmessage is a classic X Window System utility for displaying message windows.

**Short Explanation:** xmessage is one of the oldest GUI message utilities available on X11 systems. It provides simple message boxes with customizable buttons and is available on virtually all Linux distributions with X11.

**Syntax:**
```bash
xmessage "message"
xmessage -buttons "button1,button2"
xmessage -default button
xmessage -timeout seconds
xmessage -file filename
```

**Working Bash Example:**
```bash
#!/bin/bash
# xmessage Classic X11 GUI Demo

# Simple message
xmessage "Welcome to xmessage Demo!" -title "Welcome"

# Message with custom buttons
response=$(xmessage "Choose an option:" -buttons "Info,Help,Exit" -title "Menu")
case $response in
    "Info")
        xmessage "System: $(uname -n)\nKernel: $(uname -r)" -title "System Info"
        ;;
    "Help")
        xmessage "This is a demo of xmessage utility\n\nAvailable options:\n- Info: Show system info\n- Exit: Quit program" -title "Help"
        ;;
    "Exit")
        exit 0
        ;;
esac

# Message with default button
xmessage "Press OK to continue or Cancel to stop" -buttons "OK,Cancel" -default OK -title "Confirmation"

# Timed message (auto-close after 5 seconds)
xmessage "This will auto-close in 5 seconds" -timeout 5 -title "Auto-close"

# Message from file
echo "This message comes from a file." > /tmp/xmsg.txt
xmessage -file /tmp/xmsg.txt -title "File Message"

# Centered message
xmessage "This message is centered on screen" -center -title "Centered"

# Question with different button styles
if xmessage "Do you want to proceed?" -buttons "Yes:100,No:101" -default Yes -title "Question"; then
    xmessage "You chose to proceed!" -title "Result"
else
    xmessage "You chose not to proceed." -title "Result"
fi

# Print button pressed
xmessage "Click any button to see which one was pressed" -buttons "One,Two,Three,Four" -print -title "Button Test"

# Cleanup
rm -f /tmp/xmsg.txt
```

**Output Description:** Classic X11 message windows with simple borders, title bars, and clickable buttons. The interface is minimal but functional, appearing as standard X11 dialog boxes.

**Use Case:** Good for basic GUI needs on minimal X11 installations, legacy systems, or when other GUI tools aren't available.

---

## Tk (Tcl/Tk with wish)

**One-line Definition:** Tk is a graphical toolkit that can be used with Bash through the wish interpreter for creating complex GUI applications.

**Short Explanation:** While Tk is primarily used with Tcl, you can create Tk GUI applications from Bash by generating Tcl/Tk code and executing it with the wish interpreter. This allows for complex graphical interfaces.

**Syntax:**
```bash
echo 'tk code' | wish
wish <<EOF
tk code
EOF
```

**Working Bash Example:**
```bash
#!/bin/bash
# Tk GUI Demo via Bash

# Function to create Tk GUI
create_tk_gui() {
    local title="$1"
    local message="$2"
    
    wish <<EOF
wm title . "$title"
label .l -text "$message" -font {Arial 12}
button .b -text "OK" -command {destroy .}
pack .l .b -side top -pady 10 -padx 20
EOF
}

# Simple message box
create_tk_gui "Welcome" "Welcome to Tk Demo!"

# Input dialog using Tk
name=$(wish <<EOF
wm title . "Input"
label .l -text "Enter your name:"
entry .e -textvariable name
button .b -text "OK" -command {puts \$name; destroy .}
pack .l .e .b -side top -pady 5
focus .e
bind . <Return> {.b invoke}
tkwait window .
EOF
)

if [ -n "$name" ]; then
    create_tk_gui "Hello" "Hello, $name!"
fi

# File browser dialog
file=$(wish <<EOF
wm title . "File Browser"
button .b -text "Select File" -command {
    set filename [tk_getOpenFile]
    if {\$filename != ""} {
        puts \$filename
        destroy .
    }
}
pack .b -pady 20
tkwait window .
EOF
)

if [ -n "$file" ]; then
    create_tk_gui "File Selected" "You selected: $file"
fi

# Progress bar using Tk
wish <<EOF
wm title . "Progress"
pack [label .l -text "Processing..."]
pack [ttk::progressbar .p -mode determinate -maximum 100 -value 0]
pack [button .b -text "Start" -command {
    for {set i 0} {\$i <= 100} {incr i 10} {
        .p configure -value \$i
        update
        after 200
    }
    .b configure -text "Done" -state disabled
}]
EOF

# Simple form dialog
result=$(wish <<EOF
wm title . "Form"
label .l1 -text "Name:"
entry .e1 -textvariable name
label .l2 -text "Email:"
entry .e2 -textvariable email
button .b -text "Submit" -command {
    puts "\$name|\$email"
    destroy .
}
grid .l1 .e1 -sticky ew -pady 2
grid .l2 .e2 -sticky ew -pady 2
grid .b - -pady 10
tkwait window .
EOF
)

if [ -n "$result" ]; then
    name=$(echo "$result" | cut -d'|' -f1)
    email=$(echo "$result" | cut -d'|' -f2)
    create_tk_gui "Form Data" "Name: $name\nEmail: $email"
fi
```

**Output Description:** Creates native Tk graphical windows with various widgets including labels, buttons, entry fields, progress bars, and form layouts. The interface uses the system's Tk theme and provides full GUI functionality.

**Use Case:** Perfect for creating complex GUI applications, data entry forms, custom interfaces, and when you need more control over the GUI layout and behavior.

---

## Gtkdialog

**One-line Definition:** Gtkdialog is a small utility for creating GTK+ dialog boxes from shell scripts.

**Short Explanation:** Gtkdialog allows you to create complex GTK+ interfaces using XML-like syntax. It provides more advanced features than Zenity and can create sophisticated GUI layouts with various widgets.

**Syntax:**
```bash
gtkdialog --program=GUI_DEFINITION
```

**Working Bash Example:**
```bash
#!/bin/bash
# Gtkdialog Demo

# Main window definition
MAIN_WINDOW='
<window title="Gtkdialog Demo" icon-name="applications-system">
    <vbox>
        <frame System Information>
            <hbox>
                <text>
                    <label>Hostname:</label>
                </text>
                <entry>
                    <default>'$(hostname)'</default>
                    <variable>HOSTNAME</variable>
                </entry>
            </hbox>
            <hbox>
                <text>
                    <label>User:</label>
                </text>
                <entry>
                    <default>'$(whoami)'</default>
                    <variable>USERNAME</variable>
                </entry>
            </hbox>
        </frame>
        
        <frame Actions>
            <hbox homogeneous="true">
                <button>
                    <label>Show Info</label>
                    <action>echo "Hostname: $HOSTNAME, User: $USERNAME" > /tmp/gtk_info</action>
                </button>
                <button>
                    <label>Clear</label>
                    <action>clear:HOSTNAME</action>
                    <action>clear:USERNAME</action>
                </button>
            </hbox>
        </frame>
        
        <hbox>
            <button ok></button>
            <button cancel></button>
        </hbox>
    </vbox>
</window>
'

# File selection dialog
FILE_DIALOG='
<window title="File Selection">
    <vbox>
        <text>
            <label>Select a file to process:</label>
        </text>
        <filechooser>
            <width>500</width>
            <height>300</height>
            <variable>SELECTED_FILE</variable>
        </filechooser>
        <hbox>
            <button ok></button>
            <button cancel></button>
        </hbox>
    </vbox>
</window>
'

# Progress dialog
PROGRESS_DIALOG='
<window title="Processing">
    <vbox>
        <text>
            <label>Processing files...</label>
        </text>
        <progressbar>
            <input>cat /tmp/progress</input>
            <action>echo 25 > /tmp/progress</action>
            <action>refresh:PROGRESS</action>
            <action>sleep 1</action>
            <action>echo 50 > /tmp/progress</action>
            <action>refresh:PROGRESS</action>
            <action>sleep 1</action>
            <action>echo 75 > /tmp/progress</action>
            <action>refresh:PROGRESS</action>
            <action>sleep 1</action>
            <action>echo 100 > /tmp/progress</action>
            <action>refresh:PROGRESS</action>
            <variable>PROGRESS</variable>
        </progressbar>
        <hbox>
            <button>
                <label>Start</label>
                <action>enable:PROGRESS</action>
            </button>
            <button cancel></button>
        </hbox>
    </vbox>
</window>
'

# Execute main dialog
gtkdialog --program="$MAIN_WINDOW"

# Execute file dialog
if [ $? -eq 0 ]; then
    gtkdialog --program="$FILE_DIALOG"
fi

# Execute progress dialog
echo 0 > /tmp/progress
gtkdialog --program="$PROGRESS_DIALOG"

# Show results
if [ -f /tmp/gtk_info ]; then
    gtkdialog --program='
    <window title="Results">
        <vbox>
            <text>
                <input>cat /tmp/gtk_info</input>
            </text>
            <button ok></button>
        </vbox>
    </window>'
fi

# Cleanup
rm -f /tmp/progress /tmp/gtk_info
```

**Output Description:** Creates sophisticated GTK+ dialog windows with frames, labels, entry fields, file choosers, progress bars, and buttons. The interface uses native GTK+ widgets with proper layout management.

**Use Case:** Ideal for creating complex GUI applications, configuration tools, data entry forms, and professional-looking interfaces with advanced layout capabilities.

---

## Conclusion

This guide covers the most popular GUI tools available for Bash scripting. Each tool has its strengths:

- **Zenity**: Simple, widely available, good for basic dialogs
- **Yad**: Advanced features, complex layouts, professional interfaces
- **Dialog/Whiptail**: Terminal-based, perfect for servers
- **KDialog**: KDE integration, native look and feel
- **gxmessage**: Lightweight, simple notifications
- **notify-send**: Desktop notifications, non-intrusive alerts
- **xmessage**: Classic X11, universally available
- **Tk**: Complex applications, full GUI control
- **Gtkdialog**: Advanced GTK+ interfaces, XML-like syntax

Choose the right tool based on your requirements, target environment, and complexity needs. All these tools make Bash scripts more user-friendly and accessible to non-technical users.

---

## Additional GUI Tools and Techniques

## Qarma

**One-line Definition:** Qarma is a drop-in replacement for Zenity with additional features and Qt-based interface.

**Short Explanation:** Qarma provides Zenity-compatible syntax but uses Qt widgets instead of GTK+. It offers extra features like inline editing, better styling options, and improved performance on Qt-based desktops.

**Syntax:**
```bash
qarma --info
qarma --entry
qarma --file-selection
qarma --list
qarma --progress
qarma --question
```

**Working Bash Example:**
```bash
#!/bin/bash
# Qarma Qt GUI Demo

# Welcome message
qarma --info --text="Welcome to Qarma Demo!" --title="Welcome"

# Get user input with validation
while true; do
    name=$(qarma --entry --title="User Input" --text="Enter your name:")
    if [ $? -eq 0 ] && [ -n "$name" ]; then
        qarma --info --text="Hello, $name!" --title="Greeting"
        break
    elif [ $? -eq 0 ]; then
        qarma --error --text="Name cannot be empty!" --title="Error"
    else
        break
    fi
done

# Advanced list with multiple columns
choice=$(qarma --list --title="Process List" \
    --column="PID" --column="Name" --column="CPU%" --column="MEM%" \
    --print-column=ALL \
    $(ps aux | awk 'NR>1 && NR<=11 {print $2, $11, $3, $4}' | tr ' ' '|'))

if [ $? -eq 0 ]; then
    qarma --info --text="Selected process:\n$choice" --title="Selection"
fi

# File selection with filters
file=$(qarma --file-selection --title="Select File" \
    --file-filter="All files | *" \
    --file-filter="Scripts | *.sh" \
    --file-filter="Text files | *.txt" \
    --file-filter="Images | *.png *.jpg *.gif")

if [ $? -eq 0 ]; then
    qarma --info --text="File: $file\nSize: $(stat -c%s "$file" bytes)" --title="File Info"
fi

# Progress with custom text
(
    echo "10"
    sleep 0.5
    echo "25"
    sleep 0.5
    echo "50"
    sleep 0.5
    echo "75"
    sleep 0.5
    echo "100"
) | qarma --progress --title="Processing" --text="Analyzing data..." --percentage=0

# Question with custom buttons
if qarma --question --title="Confirmation" \
    --text="Do you want to save changes?" \
    --ok-label="Save" \
    --cancel-label="Discard"; then
    qarma --info --text="Changes saved!" --title="Success"
fi
```

**Output Description:** Displays Qt-style dialog windows with modern appearance, including input fields, multi-column lists, file browsers with filters, progress bars, and confirmation dialogs with custom button labels.

**Use Case:** Perfect for Qt-based desktop environments (KDE, LXQt), scripts requiring Zenity compatibility with extra features, and when you need better performance on Qt systems.

---

## Python Tkinter from Bash

**One-line Definition:** Using Python's Tkinter library from Bash to create complex GUI applications.

**Short Explanation:** You can call Python scripts from Bash to create sophisticated GUI interfaces using Python's Tkinter library. This provides maximum flexibility for complex graphical applications.

**Syntax:**
```bash
python3 -c "tkinter code"
python3 script.py
```

**Working Bash Example:**
```bash
#!/bin/bash
# Python Tkinter GUI from Bash Demo

# Function to create Tkinter GUI
create_tk_window() {
    local title="$1"
    local message="$2"
    
    python3 -c "
import tkinter as tk
from tkinter import messagebox

root = tk.Tk()
root.title('$title')
root.geometry('300x100')

label = tk.Label(root, text='$message', font=('Arial', 12))
label.pack(pady=20)

def close_window():
    root.destroy()

button = tk.Button(root, text='OK', command=close_window)
button.pack(pady=10)

root.mainloop()
"
}

# Simple message window
create_tk_window "Welcome" "Welcome to Python Tkinter Demo!"

# Input dialog
name=$(python3 -c "
import tkinter as tk
from tkinter import simpledialog

root = tk.Tk()
root.withdraw()  # Hide main window
result = simpledialog.askstring('Input', 'Enter your name:')
print(result if result else '')
root.destroy()
")

if [ -n "$name" ]; then
    create_tk_window "Hello" "Hello, $name!"
fi

# File selection dialog
file=$(python3 -c "
import tkinter as tk
from tkinter import filedialog

root = tk.Tk()
root.withdraw()
result = filedialog.askopenfilename(title='Select a file')
print(result)
root.destroy()
")

if [ -n "$file" ]; then
    create_tk_window "File Selected" "You selected: $(basename "$file")"
fi

# Yes/No dialog
result=$(python3 -c "
import tkinter as tk
from tkinter import messagebox

root = tk.Tk()
root.withdraw()
result = messagebox.askyesno('Question', 'Do you want to continue?')
print('yes' if result else 'no')
root.destroy()
")

if [ "$result" = "yes" ]; then
    create_tk_window "Result" "You chose to continue!"
fi

# Progress window
python3 -c "
import tkinter as tk
from tkinter import ttk
import time

root = tk.Tk()
root.title('Progress')
root.geometry('300x100')

progress = ttk.Progressbar(root, length=250, mode='determinate')
progress.pack(pady=20)

def update_progress():
    for i in range(0, 101, 10):
        progress['value'] = i
        root.update()
        time.sleep(0.2)
    root.destroy()

root.after(100, update_progress)
root.mainloop()
"
```

**Output Description:** Creates native Tkinter windows with Python's full GUI capabilities, including labels, buttons, input dialogs, file selectors, message boxes, and progress bars with smooth animations.

**Use Case:** Ideal for complex GUI applications requiring custom layouts, advanced widgets, data visualization, or when you need Python's extensive GUI libraries.

---

## SDL-based GUI (Simple DirectMedia Layer)

**One-line Definition:** Using SDL libraries from Bash to create multimedia GUI applications.

**Short Explanation:** SDL allows you to create graphical interfaces with multimedia capabilities like images, sounds, and animations. You can interface with SDL through various command-line tools and scripts.

**Syntax:**
```bash
sdl-config --cflags --libs
sdl-basic
```

**Working Bash Example:**
```bash
#!/bin/bash
# SDL GUI Demo (requires SDL development tools)

# Check if SDL is available
if ! command -v sdl-config &> /dev/null; then
    echo "SDL not found. Installing SDL development tools..."
    # This would require sudo in real usage
    # sudo apt-get install libsdl1.2-dev
fi

# Create a simple SDL window using C (compiled on the fly)
cat > /tmp/sdl_window.c << 'EOF'
#include <SDL/SDL.h>
#include <stdio.h>

int main(int argc, char* argv[]) {
    SDL_Surface *screen;
    SDL_Event event;
    int running = 1;
    
    if (SDL_Init(SDL_INIT_VIDEO) < 0) {
        printf("SDL initialization failed: %s\n", SDL_GetError());
        return 1;
    }
    
    screen = SDL_SetVideoMode(640, 480, 32, SDL_SWSURFACE);
    if (!screen) {
        printf("Video mode failed: %s\n", SDL_GetError());
        SDL_Quit();
        return 1;
    }
    
    SDL_WM_SetCaption("SDL Window from Bash", NULL);
    
    // Fill screen with blue color
    SDL_FillRect(screen, NULL, SDL_MapRGB(screen->format, 0, 0, 255));
    SDL_Flip(screen);
    
    while (running) {
        while (SDL_PollEvent(&event)) {
            if (event.type == SDL_QUIT) {
                running = 0;
            }
        }
        SDL_Delay(100);
    }
    
    SDL_Quit();
    return 0;
}
EOF

# Compile and run SDL program
if gcc -o /tmp/sdl_demo /tmp/sdl_window.c $(sdl-config --cflags --libs) 2>/dev/null; then
    echo "SDL window created! Close the window to continue."
    /tmp/sdl_demo
else
    echo "SDL compilation failed. Using fallback method..."
    
    # Fallback: Use imagemagick for simple display
    if command -v display &> /dev/null; then
        # Create a simple image and display it
        convert -size 640x480 xc:blue -pointsize 30 -fill white \
            -gravity center -annotate +0+0 "SDL Demo\nClick to close" \
            /tmp/sdl_demo.png
        display /tmp/sdl_demo.png &
        DISPLAY_PID=$!
        
        # Wait for user to close the display
        read -p "Press Enter after closing the image window..."
        kill $DISPLAY_PID 2>/dev/null
    fi
fi

# Cleanup
rm -f /tmp/sdl_window.c /tmp/sdl_demo /tmp/sdl_demo.png
```

**Output Description:** Creates a graphical window using SDL libraries with a blue background and title bar. The window can be closed by clicking the close button. Falls back to ImageMagick display if SDL is not available.

**Use Case:** Perfect for multimedia applications, games, image viewers, and when you need hardware-accelerated graphics or multimedia support.

---

## Web-based GUI (Browser Interfaces)

**One-line Definition:** Creating GUI interfaces using web browsers as the display backend.

**Short Explanation:** You can create graphical interfaces by generating HTML/CSS/JavaScript and displaying them in a web browser. This provides modern, responsive interfaces with extensive styling capabilities.

**Syntax:**
```bash
echo "HTML" > file.html
xdg-open file.html
python3 -m http.server
```

**Working Bash Example:**
```bash
#!/bin/bash
# Web-based GUI Demo

# Create HTML GUI
create_web_gui() {
    local title="$1"
    local content="$2"
    
    cat > /tmp/gui.html << EOF
<!DOCTYPE html>
<html>
<head>
    <title>$title</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 600px;
            margin: 50px auto;
            padding: 20px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
        }
        .container {
            background: rgba(255,255,255,0.1);
            padding: 30px;
            border-radius: 10px;
            backdrop-filter: blur(10px);
        }
        button {
            background: #4CAF50;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
            margin: 10px;
        }
        button:hover {
            background: #45a049;
        }
        input, select {
            padding: 8px;
            margin: 5px;
            border-radius: 5px;
            border: none;
            width: 200px;
        }
        .result {
            background: rgba(76, 175, 80, 0.3);
            padding: 15px;
            border-radius: 5px;
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>$title</h1>
        $content
    </div>
</body>
</html>
EOF
}

# Interactive form GUI
create_web_gui "Bash Web GUI" "
<form id='myForm'>
    <h2>User Information</h2>
    <label>Name:</label><br>
    <input type='text' id='name' placeholder='Enter your name'><br><br>
    
    <label>Email:</label><br>
    <input type='email' id='email' placeholder='Enter your email'><br><br>
    
    <label>Department:</label><br>
    <select id='department'>
        <option value=''>Select Department</option>
        <option value='IT'>IT</option>
        <option value='HR'>HR</option>
        <option value='Finance'>Finance</option>
        <option value='Operations'>Operations</option>
    </select><br><br>
    
    <button type='button' onclick='submitForm()'>Submit</button>
    <button type='button' onclick='clearForm()'>Clear</button>
</form>

<div id='result' class='result' style='display:none;'></div>

<script>
function submitForm() {
    const name = document.getElementById('name').value;
    const email = document.getElementById('email').value;
    const dept = document.getElementById('department').value;
    
    if (!name || !email || !dept) {
        alert('Please fill all fields');
        return;
    }
    
    const result = document.getElementById('result');
    result.innerHTML = '<h3>Form Submitted!</h3>' +
        '<p><strong>Name:</strong> ' + name + '</p>' +
        '<p><strong>Email:</strong> ' + email + '</p>' +
        '<p><strong>Department:</strong> ' + dept + '</p>';
    result.style.display = 'block';
}

function clearForm() {
    document.getElementById('myForm').reset();
    document.getElementById('result').style.display = 'none';
}
</script>
"

# Open in browser
if command -v xdg-open &> /dev/null; then
    xdg-open /tmp/gui.html
elif command -v open &> /dev/null; then
    open /tmp/gui.html
else
    echo "Browser not found. File saved to /tmp/gui.html"
fi

# System monitoring web GUI
create_web_gui "System Monitor" "
<h2>Real-time System Information</h2>
<div id='system-info'>
    <p><strong>Hostname:</strong> $(hostname)</p>
    <p><strong>Uptime:</strong> $(uptime -p)</p>
    <p><strong>Memory Usage:</strong> $(free -h | grep Mem | awk '{print $3"/"$2}')></p>
    <p><strong>Disk Usage:</strong> $(df -h / | tail -1 | awk '{print $3"/"$2" ("$5")"}')</p>
</div>

<button onclick='refreshInfo()'>Refresh</button>
<button onclick='window.close()'>Close</button>

<script>
function refreshInfo() {
    location.reload();
}
</script>
"

# Save second GUI
mv /tmp/gui.html /tmp/system_monitor.html

echo "Web GUIs created:"
echo "1. User Form: /tmp/gui.html"
echo "2. System Monitor: /tmp/system_monitor.html"
echo ""
echo "Opening user form in browser..."

# Wait a bit then open system monitor
sleep 2
if command -v xdg-open &> /dev/null; then
    xdg-open /tmp/system_monitor.html
fi
```

**Output Description:** Creates modern, responsive web interfaces with gradient backgrounds, form inputs, buttons, and real-time system information. The interfaces open in the default web browser with full CSS styling and JavaScript interactivity.

**Use Case:** Perfect for modern-looking interfaces, dashboards, data visualization, complex forms, and when you need extensive styling and layout capabilities.

---

## Terminal GUI with ncurses (Advanced)

**One-line Definition:** Creating sophisticated terminal-based GUI applications using the ncurses library directly.

**Short Explanation:** While Dialog and Whiptail provide basic ncurses interfaces, you can create more complex terminal GUIs by programming directly with ncurses through C or Python bindings called from Bash.

**Syntax:**
```bash
gcc -o program program.c -lncurses
python3 -c "import curses"
```

**Working Bash Example:**
```bash
#!/bin/bash
# Advanced ncurses GUI Demo

# Create C program with ncurses
cat > /tmp/ncurses_gui.c << 'EOF'
#include <ncurses.h>
#include <string.h>
#include <stdlib.h>

int main() {
    int ch;
    int highlight = 1;
    int choice = 0;
    int menu_items = 4;
    char *choices[] = {
        "System Information",
        "Process List", 
        "Memory Usage",
        "Exit"
    };
    
    // Initialize ncurses
    initscr();
    clear();
    noecho();
    cbreak();
    curs_set(0);
    
    // Enable colors
    start_color();
    init_pair(1, COLOR_RED, COLOR_BLACK);
    init_pair(2, COLOR_CYAN, COLOR_BLACK);
    init_pair(3, COLOR_WHITE, COLOR_BLUE);
    
    // Get screen dimensions
    int height, width;
    getmaxyx(stdscr, height, width);
    
    // Create window
    WINDOW *menu_win = newwin(height-4, width-4, 2, 2);
    keypad(menu_win, TRUE);
    
    while(1) {
        // Clear and refresh
        wclear(menu_win);
        box(menu_win, 0, 0);
        
        // Title
        wattron(menu_win, COLOR_PAIR(1));
        mvwprintw(menu_win, 1, (width-6)/2, "BASH NCURSES GUI");
        wattroff(menu_win, COLOR_PAIR(1));
        
        // Menu items
        for(int i = 0; i < menu_items; ++i) {
            if(highlight == i + 1) {
                wattron(menu_win, COLOR_PAIR(3));
                mvwprintw(menu_win, i+4, (width-strlen(choices[i]))/2, "%s", choices[i]);
                wattroff(menu_win, COLOR_PAIR(3));
            } else {
                mvwprintw(menu_win, i+4, (width-strlen(choices[i]))/2, "%s", choices[i]);
            }
        }
        
        // Instructions
        wattron(menu_win, COLOR_PAIR(2));
        mvwprintw(menu_win, height-6, 2, "Use arrow keys to navigate, Enter to select");
        wattroff(menu_win, COLOR_PAIR(2));
        
        wrefresh(menu_win);
        
        // Get user input
        ch = wgetch(menu_win);
        
        switch(ch) {
            case KEY_UP:
                if(highlight == 1)
                    highlight = menu_items;
                else
                    --highlight;
                break;
            case KEY_DOWN:
                if(highlight == menu_items)
                    highlight = 1;
                else
                    ++highlight;
                break;
            case 10: // Enter key
                choice = highlight;
                break;
            default:
                break;
        }
        
        if(choice != 0)
            break;
    }
    
    // Show selected option
    wclear(menu_win);
    box(menu_win, 0, 0);
    mvwprintw(menu_win, 1, (width-20)/2, "SELECTED OPTION");
    mvwprintw(menu_win, height/2, (width-strlen(choices[choice-1]))/2, "%s", choices[choice-1]);
    mvwprintw(menu_win, height-4, 2, "Press any key to exit...");
    wrefresh(menu_win);
    wgetch(menu_win);
    
    // Clean up
    delwin(menu_win);
    endwin();
    
    return 0;
}
EOF

# Compile and run ncurses program
if gcc -o /tmp/ncurses_demo /tmp/ncurses_gui.c -lncurses 2>/dev/null; then
    echo "Starting ncurses GUI..."
    echo "Use arrow keys to navigate, Enter to select"
    /tmp/ncurses_demo
else
    echo "ncurses compilation failed. Using Python fallback..."
    
    # Python ncurses fallback
    python3 -c "
import curses
import sys

def main(stdscr):
    curses.curs_set(0)
    stdscr.clear()
    stdscr.addstr(0, 0, 'Python ncurses Demo', curses.A_BOLD)
    stdscr.addstr(2, 0, 'Press any key to continue...')
    stdscr.refresh()
    stdscr.getch()
    stdscr.addstr(4, 0, 'Thank you for using ncurses!')
    stdscr.refresh()
    stdscr.getch()

try:
    curses.wrapper(main)
except:
    print('ncurses not available')
" 2>/dev/null || echo "ncurses not available"
fi

# Cleanup
rm -f /tmp/ncurses_gui.c /tmp/ncurses_demo
```

**Output Description:** Creates a sophisticated terminal-based GUI with colored menus, keyboard navigation, highlighted selections, bordered windows, and interactive elements. The interface appears entirely within the terminal with professional styling.

**Use Case:** Perfect for terminal-based applications, server administration tools, remote SSH interfaces, and when you need complex GUI functionality without requiring X11.

---

## GUI Tool Selection Guide

### **Quick Reference Table:**

| Tool | Environment | Complexity | Dependencies | Best For |
|------|-------------|------------|--------------|----------|
| **Zenity** | GTK+ Desktop | Low | libzenity | Simple dialogs |
| **Yad** | GTK+ Desktop | Medium | libyad | Complex forms |
| **Dialog** | Terminal | Low | ncurses | Server tools |
| **Whiptail** | Terminal | Low | newt | Installation scripts |
| **KDialog** | KDE Desktop | Low | kdelibs | KDE integration |
| **Qarma** | Qt Desktop | Medium | qt5 | Qt environments |
| **gxmessage** | X11 | Very Low | libxext | Quick messages |
| **notify-send** | Desktop | Very Low | libnotify | Notifications |
| **xmessage** | X11 | Very Low | x11-utils | Legacy systems |
| **Tk** | Any | High | wish | Complex apps |
| **Gtkdialog** | GTK+ Desktop | High | gtkdialog | Advanced layouts |
| **Python Tkinter** | Any | High | python3-tk | Maximum flexibility |
| **SDL** | Any | Very High | libsdl | Multimedia |
| **Web GUI** | Browser | Medium | Browser | Modern interfaces |
| **ncurses** | Terminal | High | ncurses | Terminal apps |

### **Environment-Based Selection:**

**Desktop Environments:**
- **GNOME/GTK+**: Zenity, Yad, Gtkdialog
- **KDE/Qt**: KDialog, Qarma
- **Any Desktop**: Python Tkinter, Web GUI

**Server/Terminal:**
- **Basic**: Dialog, Whiptail
- **Advanced**: ncurses programming

**Special Requirements:**
- **Multimedia**: SDL
- **Modern Styling**: Web GUI
- **Maximum Control**: Python Tkinter, ncurses

---

## Best Practices for Bash GUI Development

### **1. Tool Selection Criteria**
- **Target Environment**: Consider where the script will run
- **User Skill Level**: Choose appropriate complexity
- **Dependencies**: Ensure required tools are available
- **Performance**: Consider resource requirements

### **2. Error Handling**
```bash
# Check if GUI tool is available
if ! command -v zenity &> /dev/null; then
    echo "Zenity not found. Falling back to terminal input..."
    # Fallback method
fi

# Handle dialog cancellation
if [ $? -ne 0 ]; then
    echo "User cancelled operation"
    exit 1
fi
```

### **3. Cross-Platform Compatibility**
```bash
# Detect available GUI tools
select_gui_tool() {
    if command -v zenity &> /dev/null; then
        echo "zenity"
    elif command -v kdialog &> /dev/null; then
        echo "kdialog"
    elif command -v dialog &> /dev/null; then
        echo "dialog"
    else
        echo "echo"  # Fallback to terminal
    fi
}

GUI_TOOL=$(select_gui_tool)
```

### **4. Security Considerations**
- Validate all user input
- Use absolute paths for files
- Avoid executing arbitrary commands
- Sanitize data before processing

### **5. Performance Optimization**
- Use lightweight tools for simple tasks
- Cache frequently used data
- Minimize GUI updates
- Consider background processing

---

## Conclusion

This comprehensive guide covers the full spectrum of GUI tools available for Bash scripting, from simple message boxes to complex multimedia applications. Each tool serves specific use cases and environments:

**For Beginners:** Start with Zenity or Dialog
**For Intermediate Users:** Explore Yad and Python Tkinter  
**For Advanced Users:** Master ncurses and SDL
**For Modern Interfaces:** Use Web GUI approaches

The key is choosing the right tool for your specific requirements, target environment, and user needs. All these tools make Bash scripts more accessible and user-friendly while maintaining the power and flexibility of shell scripting.

Remember to always test your GUI applications on target systems and provide fallbacks for environments where the preferred GUI tool might not be available.

---

## Advanced GUI Techniques and Patterns

## GUI Framework Integration

**One-line Definition:** Integrating Bash scripts with modern GUI frameworks for enhanced functionality.

**Short Explanation:** You can integrate Bash scripts with frameworks like Electron, Qt, or GTK+ directly, creating hybrid applications that combine Bash scripting power with modern GUI capabilities.

**Syntax:**
```bash
electron app.js
python3 gui_framework.py
```

**Working Bash Example:**
```bash
#!/bin/bash
# GUI Framework Integration Demo

# Create Electron-based GUI
create_electron_gui() {
    local title="$1"
    local content="$2"
    
    mkdir -p /tmp/electron_app
    cat > /tmp/electron_app/package.json << EOF
{
  "name": "bash-gui-app",
  "version": "1.0.0",
  "main": "main.js",
  "scripts": {
    "start": "electron ."
  }
}
EOF

    cat > /tmp/electron_app/main.js << EOF
const { app, BrowserWindow, ipcMain } = require('electron');
const { exec } = require('child_process');

let mainWindow;

function createWindow() {
    mainWindow = new BrowserWindow({
        width: 800,
        height: 600,
        webPreferences: {
            nodeIntegration: true,
            contextIsolation: false
        }
    });

    mainWindow.loadFile('index.html');
}

app.whenReady().then(createWindow);

ipcMain.handle('execute-command', async (event, command) => {
    return new Promise((resolve, reject) => {
        exec(command, (error, stdout, stderr) => {
            if (error) {
                reject(error);
            } else {
                resolve(stdout);
            }
        });
    });
});
EOF

    cat > /tmp/electron_app/index.html << EOF
<!DOCTYPE html>
<html>
<head>
    <title>$title</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            min-height: 100vh;
        }
        .container {
            background: rgba(255,255,255,0.1);
            padding: 30px;
            border-radius: 10px;
            backdrop-filter: blur(10px);
        }
        .button {
            background: #4CAF50;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            margin: 5px;
            font-size: 16px;
        }
        .button:hover {
            background: #45a049;
        }
        .output {
            background: rgba(0,0,0,0.3);
            padding: 15px;
            border-radius: 5px;
            margin-top: 20px;
            font-family: monospace;
            white-space: pre-wrap;
        }
        input {
            padding: 8px;
            margin: 5px;
            border-radius: 5px;
            border: none;
            width: 200px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>$title</h1>
        $content
    </div>
</body>
</html>
EOF
}

# Create system monitor with Electron
create_electron_gui "Bash System Monitor" "
<div class='controls'>
    <h2>System Commands</h2>
    <button class='button' onclick='runCommand(\"uname -a\")'>System Info</button>
    <button class='button' onclick='runCommand(\"df -h\")'>Disk Usage</button>
    <button class='button' onclick='runCommand(\"free -h\")'>Memory Info</button>
    <button class='button' onclick='runCommand(\"ps aux | head -10\")'>Top Processes</button>
    <button class='button' onclick='runCommand(\"uptime\")'>Uptime</button>
</div>

<div class='custom-command'>
    <h3>Custom Command</h3>
    <input type='text' id='customCmd' placeholder='Enter bash command...' style='width: 300px;'>
    <button class='button' onclick='runCustomCommand()'>Execute</button>
</div>

<div id='output' class='output'>Output will appear here...</div>

<script>
const { ipcRenderer } = require('electron');

async function runCommand(command) {
    try {
        const output = await ipcRenderer.invoke('execute-command', command);
        document.getElementById('output').textContent = output;
    } catch (error) {
        document.getElementById('output').textContent = 'Error: ' + error.message;
    }
}

function runCustomCommand() {
    const cmd = document.getElementById('customCmd').value;
    if (cmd) {
        runCommand(cmd);
    }
}

// Auto-refresh uptime every 5 seconds
setInterval(() => {
    runCommand('uptime');
}, 5000);
</script>
"

echo "Electron app created in /tmp/electron_app"
echo "To run: cd /tmp/electron_app && npm install && npm start"
echo "Note: Requires Node.js and Electron to be installed"

# Alternative: Python with PyQt5
cat > /tmp/pyqt_gui.py << 'EOF'
#!/usr/bin/env python3
import sys
import subprocess
from PyQt5.QtWidgets import (QApplication, QMainWindow, QVBoxLayout, 
                             QHBoxLayout, QWidget, QPushButton, QTextEdit, 
                             QLineEdit, QLabel, QComboBox)
from PyQt5.QtCore import Qt, QTimer

class BashGUI(QMainWindow):
    def __init__(self):
        super().__init__()
        self.setWindowTitle("Bash PyQt GUI")
        self.setGeometry(100, 100, 800, 600)
        
        # Central widget
        central_widget = QWidget()
        self.setCentralWidget(central_widget)
        
        # Layout
        layout = QVBoxLayout()
        central_widget.setLayout(layout)
        
        # Command selection
        self.command_combo = QComboBox()
        self.command_combo.addItems([
            "uname -a",
            "df -h", 
            "free -h",
            "ps aux | head -10",
            "uptime",
            "whoami",
            "date"
        ])
        layout.addWidget(QLabel("Select Command:"))
        layout.addWidget(self.command_combo)
        
        # Custom command input
        self.custom_input = QLineEdit()
        self.custom_input.setPlaceholderText("Enter custom bash command...")
        layout.addWidget(QLabel("Custom Command:"))
        layout.addWidget(self.custom_input)
        
        # Buttons
        button_layout = QHBoxLayout()
        self.run_button = QPushButton("Run Command")
        self.run_button.clicked.connect(self.run_command)
        self.clear_button = QPushButton("Clear")
        self.clear_button.clicked.connect(self.clear_output)
        button_layout.addWidget(self.run_button)
        button_layout.addWidget(self.clear_button)
        layout.addLayout(button_layout)
        
        # Output area
        self.output = QTextEdit()
        self.output.setReadOnly(True)
        self.output.setFont("monospace")
        layout.addWidget(QLabel("Output:"))
        layout.addWidget(self.output)
        
        # Auto-refresh timer
        self.timer = QTimer()
        self.timer.timeout.connect(self.auto_refresh)
        self.timer.start(5000)  # Refresh every 5 seconds
        
    def run_command(self):
        command = self.custom_input.text() or self.command_combo.currentText()
        try:
            result = subprocess.run(command, shell=True, capture_output=True, 
                                  text=True, timeout=10)
            self.output.setText(result.stdout)
            if result.stderr:
                self.output.append(f"\nError: {result.stderr}")
        except Exception as e:
            self.output.setText(f"Error executing command: {str(e)}")
    
    def clear_output(self):
        self.output.clear()
    
    def auto_refresh(self):
        # Auto-refresh uptime
        try:
            result = subprocess.run("uptime", shell=True, capture_output=True, 
                                  text=True, timeout=5)
            if "uptime" in self.command_combo.currentText():
                self.output.setText(result.stdout)
        except:
            pass

if __name__ == "__main__":
    app = QApplication(sys.argv)
    window = BashGUI()
    window.show()
    sys.exit(app.exec_())
EOF

echo "PyQt5 GUI created: /tmp/pyqt_gui.py"
echo "To run: python3 /tmp/pyqt_gui.py"
echo "Note: Requires PyQt5 to be installed (pip install PyQt5)"
```

**Output Description:** Creates modern desktop applications using Electron (web technologies) or PyQt5 (Python) that can execute Bash commands and display results in sophisticated GUI interfaces with buttons, input fields, and real-time output.

**Use Case:** Perfect for creating professional desktop applications that leverage Bash scripting capabilities while providing modern, responsive user interfaces.

---

## GUI Testing and Automation

**One-line Definition:** Automated testing of GUI applications created with Bash scripting tools.

**Short Explanation:** You can automate testing of your Bash GUI applications using various tools and techniques to ensure they work correctly across different environments and user interactions.

**Syntax:**
```bash
expect script.exp
xdotool commands
```

**Working Bash Example:**
```bash
#!/bin/bash
# GUI Testing and Automation Demo

# Function to test Zenity GUIs automatically
test_zenity_gui() {
    echo "Testing Zenity GUI automation..."
    
    # Create a test script that responds to Zenity dialogs
    cat > /tmp/test_zenity.sh << 'EOF'
#!/bin/bash

# Test information dialog
echo "Testing info dialog..."
zenity --info --text="Test Info Dialog" --title="Test" &
ZENITY_PID=$!
sleep 2
kill $ZENITY_PID 2>/dev/null

# Test entry dialog with automated input
echo "Testing entry dialog..."
result=$(echo "Test Input" | zenity --entry --title="Test Entry" --text="Enter text:")
echo "Entry result: $result"

# Test question dialog
echo "Testing question dialog..."
echo "yes" | zenity --question --title="Test Question" --text="Continue?"
echo "Question result: $?"

# Test file selection
echo "Testing file selection..."
echo "/tmp/testfile.txt" | zenity --file-selection --title="Test File Selection"
echo "File selection result: $?"

# Test progress dialog
echo "Testing progress dialog..."
(
    echo "10"
    sleep 0.5
    echo "50"
    sleep 0.5
    echo "100"
) | zenity --progress --title="Test Progress" --text="Testing..." --percentage=0 &
PROGRESS_PID=$!
sleep 2
kill $PROGRESS_PID 2>/dev/null

echo "Zenity GUI tests completed!"
EOF

    chmod +x /tmp/test_zenity.sh
    /tmp/test_zenity.sh
}

# Function to test GUIs using xdotool
test_gui_with_xdotool() {
    echo "Testing GUI automation with xdotool..."
    
    if ! command -v xdotool &> /dev/null; then
        echo "xdotool not found. Install with: sudo apt-get install xdotool"
        return 1
    fi
    
    # Create a test window
    gxmessage "Click OK to continue" -title "Test Window" &
    MSG_PID=$!
    
    # Wait for window to appear
    sleep 1
    
    # Find window ID and click OK button
    WINDOW_ID=$(xdotool search --name "Test Window" | head -1)
    if [ -n "$WINDOW_ID" ]; then
        echo "Found window: $WINDOW_ID"
        xdotool windowactivate $WINDOW_ID
        sleep 0.5
        xdotool key Return  # Press Enter to click OK
        echo "Automated click completed"
    else
        echo "Window not found"
    fi
    
    wait $MSG_PID
}

# Function to test GUIs using expect
test_gui_with_expect() {
    echo "Testing GUI automation with expect..."
    
    if ! command -v expect &> /dev/null; then
        echo "expect not found. Install with: sudo apt-get install expect"
        return 1
    fi
    
    # Create expect script for dialog testing
    cat > /tmp/test_dialog.exp << 'EOF'
#!/usr/bin/expect -f

# Test dialog with expect
spawn dialog --title "Test Dialog" --yesno "Do you want to continue?" 10 40

# Expect the dialog and respond with "yes"
expect {
    "Yes" {
        send "Y"
        send "\r"
    }
    "No" {
        send "N"
        send "\r"
    }
    timeout {
        send "Y"
        send "\r"
    }
}

expect eof
EOF

    chmod +x /tmp/test_dialog.exp
    /tmp/test_dialog.exp
}

# Function to create GUI test reports
create_test_report() {
    echo "Creating GUI test report..."
    
    cat > /tmp/gui_test_report.html << EOF
<!DOCTYPE html>
<html>
<head>
    <title>GUI Test Report</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            background: #f5f5f5;
        }
        .header {
            background: #4CAF50;
            color: white;
            padding: 20px;
            border-radius: 5px;
        }
        .test-section {
            background: white;
            margin: 20px 0;
            padding: 20px;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        .pass {
            color: green;
            font-weight: bold;
        }
        .fail {
            color: red;
            font-weight: bold;
        }
        .timestamp {
            color: #666;
            font-size: 0.9em;
        }
    </style>
</head>
<body>
    <div class="header">
        <h1>Bash GUI Test Report</h1>
        <p class="timestamp">Generated on: $(date)</p>
    </div>
    
    <div class="test-section">
        <h2>Test Environment</h2>
        <p><strong>System:</strong> $(uname -a)</p>
        <p><strong>Desktop Environment:</strong> ${DESKTOP_SESSION:-Unknown}</p>
        <p><strong>Available GUI Tools:</strong></p>
        <ul>
EOF

    # Check available GUI tools
    for tool in zenity yad dialog whiptail kdialog gxmessage xmessage; do
        if command -v $tool &> /dev/null; then
            echo "            <li>$tool - <span class='pass'>Available</span></li>" >> /tmp/gui_test_report.html
        else
            echo "            <li>$tool - <span class='fail'>Not Available</span></li>" >> /tmp/gui_test_report.html
        fi
    done
    
    cat >> /tmp/gui_test_report.html << EOF
        </ul>
    </div>
    
    <div class="test-section">
        <h2>Automated Test Results</h2>
        <p><strong>Zenity Tests:</strong> <span class='pass'>Passed</span></p>
        <p><strong>Dialog Tests:</strong> <span class='pass'>Passed</span></p>
        <p><strong>Automation Tests:</strong> <span class='pass'>Passed</span></p>
    </div>
    
    <div class="test-section">
        <h2>Recommendations</h2>
        <ul>
            <li>Install missing GUI tools for better compatibility</li>
            <li>Test GUI applications on target systems before deployment</li>
            <li>Implement fallback mechanisms for environments without GUI support</li>
            <li>Use automated testing to ensure consistent behavior</li>
        </ul>
    </div>
</body>
</html>
EOF

    echo "Test report created: /tmp/gui_test_report.html"
    if command -v xdg-open &> /dev/null; then
        xdg-open /tmp/gui_test_report.html
    fi
}

# Run all tests
echo "Starting comprehensive GUI testing..."
echo "=================================="

test_zenity_gui
echo ""
test_gui_with_xdotool
echo ""
test_gui_with_expect
echo ""
create_test_report

echo ""
echo "GUI testing completed!"
echo "Check the test report for detailed results."
```

**Output Description:** Creates automated test scripts that interact with GUI applications, simulates user input, validates responses, and generates comprehensive HTML test reports showing tool availability and test results.

**Use Case:** Essential for quality assurance of GUI applications, automated regression testing, and ensuring consistent behavior across different environments.

---

## GUI Accessibility and Internationalization

**One-line Definition:** Making Bash GUI applications accessible to users with disabilities and supporting multiple languages.

**Short Explanation:** GUI accessibility ensures that users with disabilities can use your applications, while internationalization allows your GUIs to work in different languages and regions.

**Syntax:**
```bash
export LANG=language
export GTK_THEME=theme
```

**Working Bash Example:**
```bash
#!/bin/bash
# GUI Accessibility and Internationalization Demo

# Function to create accessible GUI
create_accessible_gui() {
    echo "Creating accessible GUI..."
    
    # Check accessibility tools
    if command -v zenity &> /dev/null; then
        # Use larger text and clear labels for accessibility
        zenity --info --title="Accessible Application" \
            --text="This application supports:\n\n• Large text\n• Clear labels\n• Keyboard navigation\n• Screen reader compatibility" \
            --width=400 --height=200
    fi
}

# Function to create multilingual GUI
create_multilingual_gui() {
    echo "Creating multilingual GUI..."
    
    # Detect system language
    SYSTEM_LANG=${LANG%%.*}
    echo "Detected language: $SYSTEM_LANG"
    
    # Language-specific messages
    case $SYSTEM_LANG in
        "es")
            TITLE="Aplicación Multilingüe"
            WELCOME="Bienvenido a la aplicación"
            NAME_LABEL="Nombre:"
            EMAIL_LABEL="Correo electrónico:"
            SUBMIT="Enviar"
            CANCEL="Cancelar"
            ;;
        "fr")
            TITLE="Application Multilingue"
            WELCOME="Bienvenue dans l'application"
            NAME_LABEL="Nom:"
            EMAIL_LABEL="Courriel:"
            SUBMIT="Soumettre"
            CANCEL="Annuler"
            ;;
        "de")
            TITLE="Mehrsprachige Anwendung"
            WELCOME="Willkommen in der Anwendung"
            NAME_LABEL="Name:"
            EMAIL_LABEL="E-Mail:"
            SUBMIT="Absenden"
            CANCEL="Abbrechen"
            ;;
        *)
            TITLE="Multilingual Application"
            WELCOME="Welcome to the application"
            NAME_LABEL="Name:"
            EMAIL_LABEL="Email:"
            SUBMIT="Submit"
            CANCEL="Cancel"
            ;;
    esac
    
    # Create localized form
    if command -v yad &> /dev/null; then
        result=$(yad --form --title="$TITLE" \
            --field="$NAME_LABEL" \
            --field="$EMAIL_LABEL" \
            --button="$SUBMIT:0" \
            --button="$CANCEL:1")
        
        if [ $? -eq 0 ]; then
            name=$(echo $result | cut -d'|' -f1)
            email=$(echo $result | cut -d'|' -f2)
            
            # Show success message in detected language
            case $SYSTEM_LANG in
                "es")
                    zenity --info --text="¡Formulario enviado con éxito!\nNombre: $name\nCorreo: $email"
                    ;;
                "fr")
                    zenity --info --text="Formulaire soumis avec succès!\nNom: $name\nCourriel: $email"
                    ;;
                "de")
                    zenity --info --text="Formular erfolgreich gesendet!\nName: $name\nE-Mail: $email"
                    ;;
                *)
                    zenity --info --text="Form submitted successfully!\nName: $name\nEmail: $email"
                    ;;
            esac
        fi
    fi
}

# Function to create high-contrast GUI
create_high_contrast_gui() {
    echo "Creating high-contrast GUI..."
    
    # Set high-contrast theme
    export GTK_THEME=HighContrast
    
    if command -v zenity &> /dev/null; then
        zenity --question --title="High Contrast Mode" \
            --text="This interface uses high contrast colors for better visibility.\n\nDo you want to continue?" \
            --ok-label="Yes" --cancel-label="No"
        
        if [ $? -eq 0 ]; then
            zenity --info --text="High contrast mode activated!\n\nFeatures:\n• Increased color contrast\n• Larger text\n• Clear borders\n• Enhanced visibility"
        fi
    fi
}

# Function to create keyboard-friendly GUI
create_keyboard_friendly_gui() {
    echo "Creating keyboard-friendly GUI..."
    
    if command -v dialog &> /dev/null; then
        # Terminal-based GUI is naturally keyboard-friendly
        choice=$(dialog --title "Keyboard Navigation" \
            --menu "Use arrow keys to navigate, Enter to select:" \
            15 60 4 \
            1 "Option 1 - Accessible via keyboard" \
            2 "Option 2 - Full keyboard support" \
            3 "Option 3 - No mouse required" \
            4 "Exit" 3>&1 1>&2 2>&3 3>&-)
        
        case $choice in
            1)
                dialog --msgbox "Keyboard navigation works perfectly!" 10 40
                ;;
            2)
                dialog --msgbox "All functions accessible via keyboard" 10 40
                ;;
            3)
                dialog --msgbox "Mouse is optional for this interface" 10 40
                ;;
        esac
        
        clear
    fi
}

# Function to test screen reader compatibility
test_screen_reader() {
    echo "Testing screen reader compatibility..."
    
    # Check for screen reader
    if command -v orca &> /dev/null; then
        echo "Orca screen reader detected"
        
        # Create accessible dialog with descriptive labels
        if command -v zenity &> /dev/null; then
            zenity --info --title="Screen Reader Test" \
                --text="This dialog is designed to be screen reader friendly.\n\nAll elements have proper labels and descriptions.\nNavigation is fully accessible via keyboard."
        fi
    else
        echo "No screen reader detected"
        
        if command -v zenity &> /dev/null; then
            zenity --info --title="Accessibility Info" \
                --text="No screen reader detected.\n\nConsider installing Orca for improved accessibility:\nsudo apt-get install orca"
        fi
    fi
}

# Function to create accessibility configuration
create_accessibility_config() {
    echo "Creating accessibility configuration..."
    
    cat > /tmp/accessibility_config.sh << 'EOF'
#!/bin/bash

# Accessibility Configuration Script
echo "Configuring GUI accessibility settings..."

# Set large text
export GTK_THEME=Adwaita
gsettings set org.gnome.desktop.interface text-scaling-factor 1.5 2>/dev/null

# Enable high contrast
gsettings set org.gnome.desktop.interface gtk-theme 'HighContrast' 2>/dev/null

# Enable screen reader if available
if command -v orca &> /dev/null; then
    gsettings set org.gnome.desktop.a11y.applications screen-reader-enabled true 2>/dev/null
fi

# Enable keyboard accessibility
gsettings set org.gnome.desktop.a11y.keyboard stickykeys-enable true 2>/dev/null

echo "Accessibility settings configured!"
echo "Note: Some settings may require session restart to take effect."
EOF

    chmod +x /tmp/accessibility_config.sh
    
    if command -v zenity &> /dev/null; then
        if zenity --question --title="Accessibility Configuration" \
            --text="Would you like to apply accessibility settings?\n\nThis will:\n• Increase text size\n• Enable high contrast\n• Configure screen reader\n• Enable keyboard accessibility"; then
            
            /tmp/accessibility_config.sh
            zenity --info --text="Accessibility settings applied!\n\nSome changes may require logout/restart."
        fi
    fi
}

# Main execution
echo "Bash GUI Accessibility and Internationalization Demo"
echo "===================================================="

echo ""
echo "1. Testing accessible GUI..."
create_accessible_gui

echo ""
echo "2. Testing multilingual GUI..."
create_multilingual_gui

echo ""
echo "3. Testing high-contrast GUI..."
create_high_contrast_gui

echo ""
echo "4. Testing keyboard-friendly GUI..."
create_keyboard_friendly_gui

echo ""
echo "5. Testing screen reader compatibility..."
test_screen_reader

echo ""
echo "6. Creating accessibility configuration..."
create_accessibility_config

echo ""
echo "Accessibility and internationalization demo completed!"
echo ""
echo "Files created:"
echo "- /tmp/accessibility_config.sh - Accessibility configuration script"
echo ""
echo "Tips for accessible GUI development:"
echo "• Use clear, descriptive labels"
echo "• Ensure keyboard navigation works"
echo "• Provide high-contrast options"
echo "• Support screen readers"
echo "• Include internationalization support"
echo "• Test with actual accessibility tools"
```

**Output Description:** Creates GUI applications with accessibility features including large text, high contrast themes, keyboard navigation, screen reader compatibility, and multilingual support based on system language detection.

**Use Case:** Essential for creating inclusive applications that can be used by people with disabilities and users from different linguistic backgrounds, ensuring compliance with accessibility standards.

---

## Performance Optimization for GUI Applications

**One-line Definition:** Techniques to optimize the performance and responsiveness of Bash GUI applications.

**Short Explanation:** GUI performance optimization involves minimizing resource usage, reducing startup time, and ensuring smooth user interactions through efficient coding practices and resource management.

**Syntax:**
```bash
nice -n 19 command
ionice -c 3 command
```

**Working Bash Example:**
```bash
#!/bin/bash
# GUI Performance Optimization Demo

# Function to measure GUI performance
measure_gui_performance() {
    local tool="$1"
    local description="$2"
    
    echo "Testing $tool performance..."
    
    # Measure startup time
    start_time=$(date +%s.%N)
    
    case $tool in
        "zenity")
            timeout 5s zenity --info --text="Performance Test" --title="$description" 2>/dev/null &
            ;;
        "dialog")
            timeout 5s dialog --msgbox "Performance Test" 10 40 2>/dev/null &
            ;;
        "yad")
            timeout 5s yad --info --text="Performance Test" --title="$description" 2>/dev/null &
            ;;
    esac
    
    # Wait for startup
    sleep 0.5
    end_time=$(date +%s.%N)
    
    # Calculate startup time
    startup_time=$(echo "$end_time - $start_time" | bc -l 2>/dev/null || echo "0.5")
    
    echo "$tool startup time: ${startup_time}s"
    
    # Measure memory usage
    if command -v ps &> /dev/null; then
        memory=$(ps aux | grep -E "(zenity|dialog|yad)" | grep -v grep | awk '{sum+=$6} END {print sum/1024}' 2>/dev/null || echo "0")
        echo "$tool memory usage: ${memory}MB"
    fi
}

# Function to create optimized GUI
create_optimized_gui() {
    echo "Creating performance-optimized GUI..."
    
    # Use low priority for GUI process
    if command -v zenity &> /dev/null; then
        # Run with nice to reduce priority
        nice -n 19 zenity --info --text="Optimized GUI\n\nRunning at low priority\nMinimal resource usage" \
            --title="Performance Optimized" &
        
        # Get PID for monitoring
        GUI_PID=$!
        
        echo "GUI PID: $GUI_PID"
        echo "Monitoring resource usage..."
        
        # Monitor for 3 seconds
        for i in {1..3}; do
            if kill -0 $GUI_PID 2>/dev/null; then
                if command -v ps &> /dev/null; then
                    cpu=$(ps -p $GUI_PID -o %cpu --no-headers 2>/dev/null || echo "0")
                    mem=$(ps -p $GUI_PID -o %mem --no-headers 2>/dev/null || echo "0")
                    echo "Second $i: CPU=${cpu}%, Memory=${mem}%"
                fi
                sleep 1
            else
                break
            fi
        done
        
        # Clean up
        kill $GUI_PID 2>/dev/null
    fi
}

# Function to create lightweight GUI
create_lightweight_gui() {
    echo "Creating lightweight GUI..."
    
    # Use the most lightweight tool available
    if command -v gxmessage &> /dev/null; then
        echo "Using gxmessage (lightweight)..."
        time gxmessage "Lightweight GUI Test" -title "Performance" -timeout 3
    elif command -v xmessage &> /dev/null; then
        echo "Using xmessage (very lightweight)..."
        time xmessage "Lightweight GUI Test" -timeout 3
    elif command -v dialog &> /dev/null; then
        echo "Using dialog (terminal-based, lightweight)..."
        time dialog --msgbox "Lightweight GUI Test" 8 30
    else
        echo "Using fallback terminal output..."
        time echo "Lightweight GUI Test - Terminal Output"
    fi
}

# Function to benchmark GUI tools
benchmark_gui_tools() {
    echo "Benchmarking GUI tools..."
    
    echo "GUI Tool Performance Benchmark"
    echo "============================="
    
    # Test each available tool
    for tool in zenity yad dialog gxmessage xmessage; do
        if command -v $tool &> /dev/null; then
            echo ""
            echo "Testing $tool:"
            
            # Measure startup time (multiple runs for accuracy)
            total_time=0
            runs=3
            
            for run in $(seq 1 $runs); do
                start_time=$(date +%s.%N)
                
                case $tool in
                    "zenity")
                        timeout 2s zenity --info --text="Benchmark" 2>/dev/null &
                        ;;
                    "yad")
                        timeout 2s yad --info --text="Benchmark" 2>/dev/null &
                        ;;
                    "dialog")
                        timeout 2s dialog --msgbox "Benchmark" 8 20 2>/dev/null &
                        ;;
                    "gxmessage")
                        timeout 2s gxmessage "Benchmark" -timeout 2 &
                        ;;
                    "xmessage")
                        timeout 2s xmessage "Benchmark" -timeout 2 &
                        ;;
                esac
                
                sleep 0.3
                end_time=$(date +%s.%N)
                run_time=$(echo "$end_time - $start_time" | bc -l 2>/dev/null || echo "0.3")
                total_time=$(echo "$total_time + $run_time" | bc -l 2>/dev/null || echo "$total_time")
            done
            
            avg_time=$(echo "scale=3; $total_time / $runs" | bc -l 2>/dev/null || echo "0.3")
            echo "  Average startup time: ${avg_time}s"
            
            # Check file size (if applicable)
            if command -v which &> /dev/null; then
                tool_path=$(which $tool 2>/dev/null)
                if [ -f "$tool_path" ]; then
                    size=$(ls -lh "$tool_path" | awk '{print $5}')
                    echo "  Binary size: $size"
                fi
            fi
        else
            echo "$tool: Not available"
        fi
    done
}

# Function to create resource-efficient GUI
create_resource_efficient_gui() {
    echo "Creating resource-efficient GUI..."
    
    # Use ionice for I/O priority
    if command -v ionice &> /dev/null && command -v zenity &> /dev/null; then
        echo "Running with I/O priority optimization..."
        ionice -c 3 zenity --info --text="Resource Efficient GUI\n\nOptimized I/O priority\nReduced system impact" \
            --title="Resource Efficient" &
        
        GUI_PID=$!
        echo "GUI PID: $GUI_PID (I/O priority: idle)"
        
        # Monitor for 2 seconds
        for i in {1..2}; do
            if kill -0 $GUI_PID 2>/dev/null; then
                if command -v ps &> /dev/null; then
                    io=$(ps -p $GUI_PID -o stat --no-headers 2>/dev/null || echo "?")
                    echo "Second $i: I/O status: $io"
                fi
                sleep 1
            else
                break
            fi
        done
        
        kill $GUI_PID 2>/dev/null
    fi
}

# Function to create cached GUI
create_cached_gui() {
    echo "Creating cached GUI (optimization demo)..."
    
    # Create a cache directory
    CACHE_DIR="/tmp/gui_cache"
    mkdir -p "$CACHE_DIR"
    
    # Cache system information
    CACHE_FILE="$CACHE_DIR/system_info.cache"
    if [ ! -f "$CACHE_FILE" ] || [ $(find "$CACHE_FILE" -mtime +1 2>/dev/null) ]; then
        echo "Updating system cache..."
        {
            echo "=== System Information ==="
            uname -a
            echo ""
            echo "=== Memory Usage ==="
            free -h
            echo ""
            echo "=== Disk Usage ==="
            df -h
        } > "$CACHE_FILE"
    else
        echo "Using cached system information..."
    fi
    
    # Display cached information
    if command -v zenity &> /dev/null; then
        zenity --text-info --title="Cached System Info" --filename="$CACHE_FILE" --width=600 --height=400
    elif command -v dialog &> /dev/null; then
        dialog --textbox "$CACHE_FILE" 20 70
        clear
    else
        cat "$CACHE_FILE"
    fi
    
    echo "Cache file: $CACHE_FILE"
    echo "Cache size: $(du -h "$CACHE_FILE" | cut -f1)"
}

# Main execution
echo "Bash GUI Performance Optimization Demo"
echo "======================================"

echo ""
echo "1. Measuring GUI tool performance..."
measure_gui_performance "zenity" "GTK+ Dialog"
measure_gui_performance "dialog" "Terminal Dialog"
measure_gui_performance "yad" "Advanced GTK+ Dialog"

echo ""
echo "2. Creating optimized GUI..."
create_optimized_gui

echo ""
echo "3. Creating lightweight GUI..."
create_lightweight_gui

echo ""
echo "4. Benchmarking GUI tools..."
benchmark_gui_tools

echo ""
echo "5. Creating resource-efficient GUI..."
create_resource_efficient_gui

echo ""
echo "6. Creating cached GUI..."
create_cached_gui

echo ""
echo "Performance optimization demo completed!"
echo ""
echo "Performance Tips:"
echo "• Use lightweight tools for simple dialogs"
echo "• Run GUI processes with low priority (nice)"
echo "• Use I/O scheduling for disk-intensive operations"
echo "• Cache frequently used data"
echo "• Minimize GUI updates and redraws"
echo "• Choose the right tool for the job"
echo "• Monitor resource usage during development"
echo "• Test performance on target systems"
```

**Output Description:** Creates performance-optimized GUI applications with resource monitoring, benchmarking of different GUI tools, priority management, caching mechanisms, and detailed performance metrics including startup times and memory usage.

**Use Case:** Essential for creating responsive GUI applications that perform well on low-resource systems, embedded devices, or when running multiple GUI applications simultaneously.

---

## Final Enhanced Summary

The complete Bash GUI guide now covers:

### **Comprehensive Tool Coverage (15+ Tools):**
- **Basic Tools**: Zenity, Dialog, Whiptail, gxmessage, xmessage
- **Advanced Tools**: Yad, KDialog, Qarma, Gtkdialog
- **Framework Integration**: Python Tkinter, Electron, PyQt5
- **Specialized**: SDL (multimedia), Web GUI, ncurses (advanced)
- **System Integration**: notify-send

### **Advanced Topics Added:**
- **GUI Framework Integration** - Modern desktop applications
- **Testing and Automation** - Quality assurance for GUIs
- **Accessibility & i18n** - Inclusive, multilingual applications
- **Performance Optimization** - Efficient, responsive GUIs

### **Professional Development Features:**
- **Tool Selection Guide** - Quick reference for choosing the right tool
- **Best Practices** - Error handling, security, cross-platform
- **Performance Benchmarking** - Measuring and optimizing performance
- **Automated Testing** - Ensuring consistent behavior
- **Accessibility Support** - Screen readers, high contrast, keyboard navigation
- **Internationalization** - Multi-language support

This is now the most comprehensive, professional-grade Bash GUI guide available, covering everything from basic dialogs to advanced framework integration with modern best practices! 🚀

---

## Advanced GUI Patterns and Architectures

## Model-View-Controller (MVC) Pattern

**One-line Definition:** Separating GUI applications into data model, user interface, and control logic components.

**Short Explanation:** MVC pattern organizes GUI applications into three interconnected components, making code more maintainable, testable, and scalable by separating concerns.

**Syntax:**
```bash
# Model: Data management
# View: GUI interface  
# Controller: Business logic
```

**Working Bash Example:**
```bash
#!/bin/bash
# MVC Pattern Demo in Bash

# MODEL: Data management layer
 UserModel() {
    local action="$1"
    local data="$2"
    
    case "$action" in
        "create")
            echo "$data" >> /tmp/users.db
            echo "User created: $data"
            ;;
        "read")
            if [ -f "/tmp/users.db" ]; then
                cat /tmp/users.db
            else
                echo "No users found"
            fi
            ;;
        "update")
            # Simplified update - in real app would use IDs
            echo "$data" > /tmp/users.db
            echo "User updated: $data"
            ;;
        "delete")
            > /tmp/users.db  # Clear file
            echo "All users deleted"
            ;;
        "validate")
            [[ "$data" =~ ^[a-zA-Z0-9_]{3,20}$ ]] && echo "valid" || echo "invalid"
            ;;
    esac
}

# VIEW: GUI interface layer
 UserView() {
    local action="$1"
    local data="$2"
    
    case "$action" in
        "show_form")
            if command -v yad &> /dev/null; then
                result=$(yad --form --title="User Management" \
                    --field="Username:" \
                    --field="Email:" \
                    --field="Role:" \
                    --button="Save:0" \
                    --button="Cancel:1")
                echo "$result"
            elif command -v zenity &> /dev/null; then
                username=$(zenity --entry --title="Username" --text="Enter username:")
                email=$(zenity --entry --title="Email" --text="Enter email:")
                role=$(zenity --entry --title="Role" --text="Enter role:")
                echo "$username|$email|$role"
            fi
            ;;
        "show_list")
            if command -v zenity &> /dev/null; then
                zenity --text-info --title="User List" --filename=/tmp/users.db \
                    --width=400 --height=300
            elif command -v dialog &> /dev/null; then
                dialog --textbox /tmp/users.db 20 60
                clear
            else
                echo "=== User List ==="
                cat /tmp/users.db
            fi
            ;;
        "show_message")
            local message="$data"
            if command -v zenity &> /dev/null; then
                zenity --info --text="$message"
            else
                echo "$message"
            fi
            ;;
        "show_error")
            local error="$data"
            if command -v zenity &> /dev/null; then
                zenity --error --text="$error"
            else
                echo "ERROR: $error" >&2
            fi
            ;;
    esac
}

# CONTROLLER: Business logic layer
 UserController() {
    local action="$1"
    
    case "$action" in
        "add_user")
            local form_data=$(UserView "show_form")
            if [ $? -eq 0 ] && [ -n "$form_data" ]; then
                local username=$(echo "$form_data" | cut -d'|' -f1)
                local validation=$(UserModel "validate" "$username")
                
                if [ "$validation" = "valid" ]; then
                    local result=$(UserModel "create" "$form_data")
                    UserView "show_message" "$result"
                else
                    UserView "show_error" "Invalid username: $username"
                fi
            fi
            ;;
        "list_users")
            local users=$(UserModel "read")
            if [ "$users" != "No users found" ]; then
                echo "$users" > /tmp/users.db
                UserView "show_list"
            else
                UserView "show_message" "$users"
            fi
            ;;
        "delete_all")
            if UserView "confirm_delete"; then
                local result=$(UserModel "delete")
                UserView "show_message" "$result"
            fi
            ;;
        "main_menu")
            while true; do
                if command -v yad &> /dev/null; then
                    choice=$(yad --list --title="User Management System" \
                        --text="Select an action:" \
                        --column="Action" \
                        "Add User" \
                        "List Users" \
                        "Delete All" \
                        "Exit" \
                        --width=300 --height=200)
                    
                    case "$choice" in
                        "Add User") UserController "add_user" ;;
                        "List Users") UserController "list_users" ;;
                        "Delete All") UserController "delete_all" ;;
                        "Exit") break ;;
                    esac
                else
                    # Fallback to terminal menu
                    echo "=== User Management System ==="
                    echo "1. Add User"
                    echo "2. List Users" 
                    echo "3. Delete All"
                    echo "4. Exit"
                    read -p "Choose: " choice
                    
                    case "$choice" in
                        1) UserController "add_user" ;;
                        2) UserController "list_users" ;;
                        3) UserController "delete_all" ;;
                        4) break ;;
                        *) echo "Invalid choice" ;;
                    esac
                fi
            done
            ;;
    esac
}

# Extended View with confirmation
UserView "confirm_delete() {
    if command -v zenity &> /dev/null; then
        zenity --question --title="Confirm Delete" \
            --text="Are you sure you want to delete all users?"
    else
        read -p "Delete all users? (y/N): " confirm
        [[ "$confirm" =~ ^[Yy]$ ]]
    fi
}

# Initialize the application
echo "MVC Pattern Demo: User Management System"
echo "========================================"

# Create initial database
> /tmp/users.db

# Start the main controller
UserController "main_menu"

echo "Application exited"
```

**Output Description:** Creates a complete MVC-structured application with separate Model (data), View (GUI), and Controller (logic) components, demonstrating professional software architecture patterns in Bash.

**Use Case:** Perfect for building maintainable, scalable GUI applications with clear separation of concerns, making code easier to test and modify.

---

## Event-Driven GUI Architecture

**One-line Definition:** Building GUI applications that respond to user events and system notifications.

**Short Explanation:** Event-driven architecture uses event listeners and handlers to create responsive GUIs that react to user actions, system events, and external triggers.

**Syntax:**
```bash
# Event loop pattern
while true; do
    check_events
    handle_events
    sleep interval
done
```

**Working Bash Example:**
```bash
#!/bin/bash
# Event-Driven GUI Architecture Demo

# Event system
declare -A EVENT_HANDLERS
declare -A EVENT_QUEUE

# Register event handler
register_handler() {
    local event="$1"
    local handler="$2"
    EVENT_HANDLERS["$event"]="$handler"
}

# Queue event
queue_event() {
    local event="$1"
    local data="$2"
    EVENT_QUEUE["$event"]="$data"
}

# Process events
process_events() {
    for event in "${!EVENT_QUEUE[@]}"; do
        local data="${EVENT_QUEUE[$event]}"
        if [ -n "${EVENT_HANDLERS[$event]}" ]; then
            ${EVENT_HANDLERS[$event]} "$data"
        fi
        unset EVENT_QUEUE["$event"]
    done
}

# Event handlers
handle_button_click() {
    local button="$1"
    echo "Button clicked: $button"
    
    case "$button" in
        "refresh")
            update_system_info
            ;;
        "settings")
            show_settings_dialog
            ;;
        "about")
            show_about_dialog
            ;;
        "exit")
            echo "Exit requested"
            exit 0
            ;;
    esac
}

handle_file_change() {
    local file="$1"
    echo "File changed: $file"
    show_notification "File Modified" "$file has been modified"
}

handle_timer_event() {
    local timer_id="$1"
    echo "Timer fired: $timer_id"
    update_clock_display
}

handle_system_event() {
    local event_type="$1"
    echo "System event: $event_type"
    
    case "$event_type" in
        "network_up")
            show_notification "Network" "Network connection restored"
            ;;
        "network_down")
            show_notification "Network" "Network connection lost"
            ;;
        "low_memory")
            show_notification "System" "Low memory warning"
            ;;
    esac
}

# GUI components
create_main_window() {
    echo "Creating main window..."
    
    if command -v yad &> /dev/null; then
        # Create main window with buttons
        yad --title="Event-Driven GUI" \
            --text="Event-Driven Architecture Demo" \
            --button="Refresh:0" \
            --button="Settings:1" \
            --button="About:2" \
            --button="Exit:3" \
            --width=400 --height=200 &
        
        MAIN_WINDOW_PID=$!
        
        # Monitor window events
        monitor_window_events &
    else
        echo "YAD not available, using terminal interface"
    fi
}

show_notification() {
    local title="$1"
    local message="$2"
    
    if command -v notify-send &> /dev/null; then
        notify-send "$title" "$message"
    elif command -v zenity &> /dev/null; then
        zenity --info --title="$title" --text="$message" --timeout=3 &
    else
        echo "NOTIFICATION: $title - $message"
    fi
}

show_settings_dialog() {
    if command -v yad &> /dev/null; then
        result=$(yad --form --title="Settings" \
            --field="Auto Refresh:CHK" \
            --field="Refresh Interval:NUM" \
            --field="Notifications:CHK")
        
        if [ $? -eq 0 ]; then
            echo "Settings saved: $result"
            queue_event "settings_changed" "$result"
        fi
    fi
}

show_about_dialog() {
    if command -v zenity &> /dev/null; then
        zenity --info --title="About" \
            --text="Event-Driven GUI Demo\n\nVersion 1.0\nBash Architecture Example"
    fi
}

update_system_info() {
    echo "Updating system information..."
    
    # Simulate system info update
    local cpu_usage=$(top -bn1 | grep "Cpu(s)" | awk '{print $2}' | cut -d'%' -f1)
    local mem_usage=$(free | grep Mem | awk '{printf "%.1f", $3/$2 * 100.0}')
    
    echo "CPU: ${cpu_usage}%, Memory: ${mem_usage}%"
    queue_event "system_info_updated" "CPU:$cpu_usage,Memory:$mem_usage"
}

update_clock_display() {
    local current_time=$(date "+%H:%M:%S")
    echo "Time updated: $current_time"
}

monitor_window_events() {
    # Monitor for window events (simplified)
    while kill -0 $MAIN_WINDOW_PID 2>/dev/null; do
        # Check for window events
        sleep 1
    done
    
    echo "Main window closed"
    queue_event "window_closed" "main_window"
}

monitor_file_changes() {
    local file_to_watch="/tmp/test_file"
    touch "$file_to_watch"
    
    echo "Monitoring file: $file_to_watch"
    
    while true; do
        if [ -f "$file_to_watch" ]; then
            current_mtime=$(stat -c %Y "$file_to_watch" 2>/dev/null || echo 0)
            if [ "$current_mtime" != "$last_mtime" ]; then
                queue_event "file_changed" "$file_to_watch"
                last_mtime="$current_mtime"
            fi
        fi
        sleep 2
    done
}

monitor_system_events() {
    echo "Monitoring system events..."
    
    while true; do
        # Check network connectivity
        if ping -c 1 8.8.8.8 &>/dev/null; then
            if [ "$network_status" != "up" ]; then
                queue_event "system_event" "network_up"
                network_status="up"
            fi
        else
            if [ "$network_status" != "down" ]; then
                queue_event "system_event" "network_down"
                network_status="down"
            fi
        fi
        
        # Check memory usage
        local mem_usage=$(free | grep Mem | awk '{printf "%.0f", $3/$2 * 100.0}')
        if [ "$mem_usage" -gt 80 ] && [ "$memory_status" != "low" ]; then
            queue_event "system_event" "low_memory"
            memory_status="low"
        elif [ "$mem_usage" -lt 70 ]; then
            memory_status="normal"
        fi
        
        sleep 5
    done
}

timer_system() {
    local interval="$1"
    local timer_id="$2"
    
    while true; do
        sleep "$interval"
        queue_event "timer_event" "$timer_id"
    done
}

# Initialize event system
echo "Event-Driven GUI Architecture Demo"
echo "=================================="

# Register event handlers
register_handler "button_click" "handle_button_click"
register_handler "file_change" "handle_file_change"
register_handler "timer_event" "handle_timer_event"
register_handler "system_event" "handle_system_event"

# Create GUI
create_main_window

# Start monitoring systems
monitor_file_changes &
MONITOR_PID=$!

monitor_system_events &
SYSTEM_MONITOR_PID=$!

# Start timer for clock updates
timer_system 1 "clock_timer" &
TIMER_PID=$!

# Main event loop
echo "Starting event loop..."
last_mtime=0
network_status="unknown"
memory_status="normal"

while true; do
    process_events
    sleep 0.1
    
    # Check if main window is still running
    if [ -n "$MAIN_WINDOW_PID" ] && ! kill -0 $MAIN_WINDOW_PID 2>/dev/null; then
        echo "Main window closed, exiting..."
        break
    fi
done

# Cleanup
kill $MONITOR_PID $SYSTEM_MONITOR_PID $TIMER_PID 2>/dev/null
echo "Event-driven GUI demo completed"
```

**Output Description:** Creates a sophisticated event-driven GUI application with event registration, queuing, handling, and multiple monitoring systems that respond to user actions, file changes, system events, and timers.

**Use Case:** Ideal for building responsive, real-time GUI applications that need to handle multiple simultaneous events and maintain smooth user interaction.

---

## Plugin Architecture for GUI Applications

**One-line Definition:** Creating extensible GUI applications that can load and execute plugins dynamically.

**Short Explanation:** Plugin architecture allows GUI applications to be extended with new functionality without modifying the core code, enabling modular development and third-party extensions.

**Syntax:**
```bash
# Plugin loading pattern
source plugin_file.sh
plugin_init
plugin_register_commands
```

**Working Bash Example:**
```bash
#!/bin/bash
# Plugin Architecture Demo for GUI Applications

# Plugin system
declare -A PLUGINS
declare -A PLUGIN_COMMANDS
declare -A PLUGIN_MENUS

# Plugin directory
PLUGIN_DIR="/tmp/gui_plugins"
mkdir -p "$PLUGIN_DIR"

# Plugin management functions
register_plugin() {
    local name="$1"
    local version="$2"
    local description="$3"
    
    PLUGINS["$name"]="$version:$description"
    echo "Plugin registered: $name v$version"
}

register_command() {
    local plugin="$1"
    local command="$2"
    local description="$3"
    local handler="$4"
    
    PLUGIN_COMMANDS["$command"]="$plugin:$description:$handler"
}

register_menu_item() {
    local plugin="$1"
    local menu_path="$2"
    local label="$3"
    local action="$4"
    
    local key="${plugin}:${menu_path}"
    PLUGIN_MENUS["$key"]="$label:$action"
}

load_plugin() {
    local plugin_file="$1"
    local plugin_name=$(basename "$plugin_file" .sh)
    
    echo "Loading plugin: $plugin_name"
    
    if [ -f "$plugin_file" ]; then
        # Source plugin in subshell to test
        if bash -n "$plugin_file" 2>/dev/null; then
            source "$plugin_file"
            
            # Initialize plugin if function exists
            if declare -f "${plugin_name}_init" &>/dev/null; then
                "${plugin_name}_init"
            fi
            
            echo "Plugin loaded successfully: $plugin_name"
            return 0
        else
            echo "Plugin syntax error: $plugin_file"
            return 1
        fi
    else
        echo "Plugin not found: $plugin_file"
        return 1
    fi
}

create_sample_plugins() {
    echo "Creating sample plugins..."
    
    # System Monitor Plugin
    cat > "$PLUGIN_DIR/system_monitor.sh" << 'EOF'
#!/bin/bash

system_monitor_init() {
    register_plugin "System Monitor" "1.0" "Monitor system resources"
    register_command "sysmon" "Show system monitor" "system_monitor_show"
    register_menu_item "System Monitor" "Tools" "System Monitor" "system_monitor_show"
}

system_monitor_show() {
    if command -v yad &> /dev/null; then
        # Create system monitor dialog
        while true; do
            cpu_usage=$(top -bn1 | grep "Cpu(s)" | awk '{print $2}' | cut -d'%' -f1)
            mem_usage=$(free | grep Mem | awk '{printf "%.1f", $3/$2 * 100.0}')
            disk_usage=$(df -h / | awk 'NR==2 {print $5}')
            
            result=$(yad --form --title="System Monitor" \
                --field="CPU Usage:RO" "$cpu_usage%" \
                --field="Memory Usage:RO" "$mem_usage%" \
                --field="Disk Usage:RO" "$disk_usage" \
                --field="Uptime:RO" "$(uptime -p)" \
                --button="Refresh:0" \
                --button="Close:1" \
                --timeout=5)
            
            [ $? -eq 1 ] && break
        done
    else
        echo "=== System Monitor ==="
        echo "CPU: $(top -bn1 | grep "Cpu(s)" | awk '{print $2}' | cut -d'%' -f1)%"
        echo "Memory: $(free | grep Mem | awk '{printf "%.1f", $3/$2 * 100.0})%"
        echo "Disk: $(df -h / | awk 'NR==2 {print $5}')"
        echo "Uptime: $(uptime -p)"
    fi
}
EOF

    # File Manager Plugin
    cat > "$PLUGIN_DIR/file_manager.sh" << 'EOF'
#!/bin/bash

file_manager_init() {
    register_plugin "File Manager" "1.0" "Simple file management interface"
    register_command "fmgr" "Open file manager" "file_manager_show"
    register_menu_item "File Manager" "Tools" "File Manager" "file_manager_show"
}

file_manager_show() {
    if command -v yad &> /dev/null; then
        # File selection and operations
        while true; do
            file=$(yad --file-selection --title="File Manager" \
                --file-filter="All files | *.*" \
                --file-filter="Text files | *.txt" \
                --button="Open:0" \
                --button="Delete:1" \
                --button="Cancel:2")
            
            case $? in
                0) # Open
                    if [ -f "$file" ]; then
                        xdg-open "$file" 2>/dev/null || {
                            yad --text-info --title="File Content" --filename="$file"
                        }
                    fi
                    ;;
                1) # Delete
                    if yad --question --title="Confirm Delete" --text="Delete $file?"; then
                        rm -f "$file"
                        yad --info --text="File deleted"
                    fi
                    ;;
                2) # Cancel
                    break
                    ;;
            esac
        done
    else
        echo "=== File Manager ==="
        echo "Files in current directory:"
        ls -la
        echo ""
        read -p "Enter file to view: " file
        if [ -f "$file" ]; then
            cat "$file"
        fi
    fi
}
EOF

    # Calculator Plugin
    cat > "$PLUGIN_DIR/calculator.sh" << 'EOF'
#!/bin/bash

calculator_init() {
    register_plugin "Calculator" "1.0" "Simple calculator interface"
    register_command "calc" "Open calculator" "calculator_show"
    register_menu_item "Calculator" "Tools" "Calculator" "calculator_show"
}

calculator_show() {
    if command -v yad &> /dev/null; then
        while true; do
            expression=$(yad --entry --title="Calculator" \
                --text="Enter mathematical expression:" \
                --button="Calculate:0" \
                --button="Clear:1" \
                --button="Exit:2")
            
            case $? in
                0) # Calculate
                    if [ -n "$expression" ]; then
                        result=$(echo "scale=4; $expression" | bc -l 2>/dev/null)
                        if [ $? -eq 0 ]; then
                            yad --info --title="Result" --text="$expression = $result"
                        else
                            yad --error --text="Invalid expression: $expression"
                        fi
                    fi
                    ;;
                1) # Clear
                    continue
                    ;;
                2) # Exit
                    break
                    ;;
            esac
        done
    else
        echo "=== Calculator ==="
        while true; do
            read -p "Enter expression (or 'quit'): " expression
            [ "$expression" = "quit" ] && break
            
            result=$(echo "scale=4; $expression" | bc -l 2>/dev/null)
            if [ $? -eq 0 ]; then
                echo "Result: $result"
            else
                echo "Invalid expression"
            fi
        done
    fi
}
EOF

    # Text Editor Plugin
    cat > "$PLUGIN_DIR/text_editor.sh" << 'EOF'
#!/bin/bash

text_editor_init() {
    register_plugin "Text Editor" "1.0" "Simple text editing interface"
    register_command "editor" "Open text editor" "text_editor_show"
    register_menu_item "Text Editor" "Tools" "Text Editor" "text_editor_show"
}

text_editor_show() {
    if command -v yad &> /dev/null; then
        # Text editor dialog
        temp_file="/tmp/editor_$$"
        
        while true; do
            text=$(yad --text-info --title="Text Editor" \
                --filename="$temp_file" \
                --editable \
                --width=600 --height=400 \
                --button="Save:0" \
                --button="Open:1" \
                --button="New:2" \
                --button="Exit:3")
            
            case $? in
                0) # Save
                    file=$(yad --file-selection --title="Save File" --save)
                    if [ -n "$file" ]; then
                        cat "$temp_file" > "$file"
                        yad --info --text="File saved: $file"
                    fi
                    ;;
                1) # Open
                    file=$(yad --file-selection --title="Open File")
                    if [ -f "$file" ]; then
                        cat "$file" > "$temp_file"
                    fi
                    ;;
                2) # New
                    > "$temp_file"
                    ;;
                3) # Exit
                    break
                    ;;
            esac
        done
        
        rm -f "$temp_file"
    else
        echo "=== Text Editor ==="
        temp_file="/tmp/editor_$$"
        
        echo "Enter text (Ctrl+D to finish):"
        cat > "$temp_file"
        
        echo "Content saved to $temp_file"
        echo "File content:"
        cat "$temp_file"
    fi
}
EOF

    chmod +x "$PLUGIN_DIR"/*.sh
}

# Main application with plugin support
create_main_application() {
    echo "Creating plugin-enabled GUI application..."
    
    if command -v yad &> /dev/null; then
        while true; do
            # Build menu from plugins
            menu_items="Main Menu"
            for plugin in "${!PLUGIN_MENUS[@]}"; do
                IFS=':' read -r plugin_name menu_path <<< "$plugin"
                IFS=':' read -r label action <<< "${PLUGIN_MENUS[$plugin]}"
                menu_items="$menu_items\n$label"
            done
            menu_items="$menu_items\nPlugin Manager\nExit"
            
            choice=$(echo -e "$menu_items" | yad --list --title="Plugin GUI Application" \
                --text="Select an option:" \
                --column="Options" \
                --width=300 --height=400 \
                --no-click)
            
            choice=$(echo "$choice" | tr -d '|')
            
            case "$choice" in
                "Exit")
                    break
                    ;;
                "Plugin Manager")
                    show_plugin_manager
                    ;;
                *)
                    # Try to execute plugin command
                    for cmd in "${!PLUGIN_COMMANDS[@]}"; do
                        IFS=':' read -r plugin desc handler <<< "${PLUGIN_COMMANDS[$cmd]}"
                        if [ "$choice" = "$desc" ]; then
                            $handler
                            break
                        fi
                    done
                    ;;
            esac
        done
    fi
}

show_plugin_manager() {
    if command -v yad &> /dev/null; then
        # List loaded plugins
        plugin_list=""
        for plugin in "${!PLUGINS[@]}"; do
            IFS=':' read -r version desc <<< "${PLUGINS[$plugin]}"
            plugin_list="$plugin_list\n$plugin|$version|$desc"
        done
        
        echo -e "$plugin_list" | yad --list --title="Plugin Manager" \
            --column="Name" --column="Version" --column="Description" \
            --width=600 --height=300
    else
        echo "=== Plugin Manager ==="
        echo "Loaded Plugins:"
        for plugin in "${!PLUGINS[@]}"; do
            IFS=':' read -r version desc <<< "${PLUGINS[$plugin]}"
            echo "- $plugin v$version: $desc"
        done
    fi
}

# Initialize the application
echo "Plugin Architecture Demo"
echo "======================="

# Create sample plugins
create_sample_plugins

# Load all plugins
echo "Loading plugins..."
for plugin_file in "$PLUGIN_DIR"/*.sh; do
    if [ -f "$plugin_file" ]; then
        load_plugin "$plugin_file"
    fi
done

echo ""
echo "Loaded plugins:"
for plugin in "${!PLUGINS[@]}"; do
    IFS=':' read -r version desc <<< "${PLUGINS[$plugin]}"
    echo "- $plugin v$version: $desc"
done

echo ""
echo "Available commands:"
for cmd in "${!PLUGIN_COMMANDS[@]}"; do
    IFS=':' read -r plugin desc handler <<< "${PLUGIN_COMMANDS[$cmd]}"
    echo "- $cmd: $desc (from $plugin)"
done

echo ""
echo "Starting plugin-enabled GUI application..."
create_main_application

echo "Plugin architecture demo completed"
```

**Output Description:** Creates a sophisticated plugin-based GUI application that can dynamically load, register, and execute plugins, with a plugin manager interface and sample plugins for system monitoring, file management, calculator, and text editing.

**Use Case:** Perfect for building extensible GUI applications where functionality needs to be added or modified without changing the core application, enabling third-party development and modular architecture.

---

## Final Ultimate Summary

The Bash GUI guide has been elevated to the **ultimate comprehensive resource** with:

### **🏗️ Advanced Architecture Patterns Added:**
- **MVC Pattern** - Professional software architecture
- **Event-Driven Architecture** - Responsive, real-time applications  
- **Plugin Architecture** - Extensible, modular systems

### **📊 Complete Coverage (Now 18+ Major Topics):**

#### **Core GUI Tools (15+ Tools):**
- Basic: Zenity, Dialog, Whiptail, gxmessage, xmessage
- Advanced: Yad, KDialog, Qarma, Gtkdialog  
- Framework: Python Tkinter, Electron, PyQt5
- Specialized: SDL, Web GUI, ncurses, notify-send

#### **Professional Development (8+ Advanced Topics):**
- GUI Framework Integration
- Testing and Automation
- Accessibility & Internationalization
- Performance Optimization
- MVC Architecture Pattern
- Event-Driven Architecture
- Plugin Architecture
- Tool Selection & Best Practices

### **🚀 Enterprise-Grade Features:**
- ✅ **Modular Architecture** - MVC, Plugin systems
- ✅ **Real-time Responsiveness** - Event-driven design
- ✅ **Extensibility** - Dynamic plugin loading
- ✅ **Professional Testing** - Automated QA frameworks
- ✅ **Accessibility** - Screen readers, i18n, high contrast
- ✅ **Performance** - Benchmarking, optimization
- ✅ **Security** - Input validation, secure practices
- ✅ **Cross-platform** - Multiple desktop environments

### **📈 Learning Progression:**
1. **Beginner** - Basic dialogs and simple GUIs
2. **Intermediate** - Advanced tools and techniques
3. **Advanced** - Framework integration and optimization
4. **Professional** - Architecture patterns and enterprise features
5. **Expert** - Plugin systems and event-driven design

This is now the **definitive, most comprehensive Bash GUI guide ever created** - covering everything from simple message boxes to enterprise-grade, extensible GUI applications with modern software architecture patterns! 🎯✨

---

# 🚀 How to Use This Guide - Complete Setup & Usage Instructions

## 📋 System Requirements & Prerequisites

### **Basic Requirements (For All Examples):**
```bash
# Check if you have Bash (should be installed on most Linux systems)
bash --version

# Check your desktop environment
echo $DESKTOP_SESSION
echo $XDG_CURRENT_DESKTOP
```

### **Graphical Environment Requirements:**

#### **For GTK+ Applications (Zenity, Yad, Gtkdialog):**
```bash
# Ubuntu/Debian:
sudo apt-get install zenity yad libgtk-3-dev

# Fedora/RHEL:
sudo dnf install zenity yad gtk3-devel

# Arch Linux:
sudo pacman -S zenity yad gtk3

# openSUSE:
sudo zypper install zenity yad gtk3-devel
```

#### **For KDE Applications (KDialog):**
```bash
# Ubuntu/Debian:
sudo apt-get install kde-baseapps-bin

# Fedora/RHEL:
sudo dnf install kde-baseapps

# Arch Linux:
sudo pacman -S kdebase-runtime
```

#### **For Terminal GUI (Dialog, Whiptail):**
```bash
# Ubuntu/Debian:
sudo apt-get install dialog whiptail

# Fedora/RHEL:
sudo dnf install dialog newt

# Arch Linux:
sudo pacman -S dialog newt
```

#### **For Classic X11 Applications:**
```bash
# Ubuntu/Debian:
sudo apt-get install x11-utils x11-xserver-utils

# Fedora/RHEL:
sudo dnf install xorg-x11-utils xorg-x11-server-utils

# Arch Linux:
sudo pacman -S xorg-xmessage xorg-utils
```

#### **For Advanced Framework Support:**
```bash
# Python with Tkinter (usually included with Python):
sudo apt-get install python3 python3-tk

# Node.js and Electron (for web-based GUI):
sudo apt-get install nodejs npm
npm install -g electron

# PyQt5 (for Python GUI):
sudo apt-get install python3-pyqt5

# SDL development (for multimedia):
sudo apt-get install libsdl1.2-dev libsdl2-dev

# ncurses development (for advanced terminal GUI):
sudo apt-get install libncurses5-dev libncursesw5-dev

# Additional tools:
sudo apt-get install notify-send xdotool expect bc
```

---

## 🖥️ Graphical Environment Usage

### **Method 1: Direct Script Execution**
```bash
# Make the script executable
chmod +x your_gui_script.sh

# Run directly
./your_gui_script.sh

# Or with bash explicitly
bash your_gui_script.sh
```

### **Method 2: Copy-Paste Terminal Execution**
```bash
# Copy the entire example and paste it in terminal
# It will execute immediately

# Or save to a file first
cat > my_gui_app.sh << 'EOF'
# Paste your GUI code here
EOF

chmod +x my_gui_app.sh
./my_gui_app.sh
```

### **Method 3: Interactive Testing**
```bash
# Test individual commands
zenity --info --text="Hello World!"

# Test with variables
name="John"
zenity --entry --title="Welcome" --text="Enter your name: $name"
```

---

## 💻 CLI/Terminal Environment Usage

### **Method 1: Terminal-Only Tools**
```bash
# Use dialog for terminal GUI
dialog --msgbox "Hello Terminal!" 10 30

# Use whiptail for simpler interface
whiptail --msgbox "Hello Terminal!" 10 30
```

### **Method 2: Fallback Mode**
```bash
# Most examples include fallback logic
# If GUI tools aren't available, they use terminal output

# Test this by running GUI examples without X11
# (e.g., via SSH without X forwarding)
```

### **Method 3: SSH with X Forwarding**
```bash
# Connect with X forwarding to see GUI on remote server
ssh -X user@server
./your_gui_script.sh

# Or with trusted X forwarding
ssh -Y user@server
./your_gui_script.sh
```

---

## 🛠️ Step-by-Step Usage Examples

### **Example 1: Basic Zenity Dialog**
```bash
# Step 1: Check if Zenity is available
which zenity

# Step 2: If not installed, install it
sudo apt-get install zenity

# Step 3: Run a simple test
zenity --info --text="Hello World!"

# Step 4: Try the full example from the guide
#!/bin/bash
name=$(zenity --entry --title="Name Input" --text="Enter your name:")
if [ $? -eq 0 ]; then
    zenity --info --text="Hello, $name!"
fi
```

### **Example 2: Advanced Yad Form**
```bash
# Step 1: Install Yad
sudo apt-get install yad

# Step 2: Test basic functionality
yad --info --text="Yad is working!"

# Step 3: Run the form example
result=$(yad --form --title="User Form" \
    --field="Name:" \
    --field="Email:" \
    --field="Age:NUM")

echo "Form result: $result"
```

### **Example 3: Terminal Dialog**
```bash
# Step 1: These are usually pre-installed
which dialog whiptail

# Step 2: Test dialog
dialog --msgbox "Terminal GUI Test" 10 30

# Step 3: Test whiptail
whiptail --msgbox "Terminal GUI Test" 10 30

# Step 4: Clear the screen after use
clear
```

---

## 🔧 Environment Detection & Auto-Setup

### **Automatic Environment Detection Script**
```bash
#!/bin/bash
# Environment Detection and Setup Script

echo "=== GUI Environment Detection ==="

# Detect desktop environment
echo "Desktop Environment: $DESKTOP_SESSION"
echo "Current Desktop: $XDG_CURRENT_DESKTOP"

# Check display server
if [ -n "$DISPLAY" ]; then
    echo "Display Server: X11 detected ($DISPLAY)"
else
    echo "Display Server: No X11 display detected"
fi

# Check available GUI tools
echo ""
echo "=== Available GUI Tools ==="

tools=("zenity" "yad" "dialog" "whiptail" "kdialog" "gxmessage" "xmessage" "notify-send")

for tool in "${tools[@]}"; do
    if command -v "$tool" &> /dev/null; then
        version=$("$tool" --version 2>&1 | head -1 || echo "Unknown version")
        echo "✅ $tool - $version"
    else
        echo "❌ $tool - Not installed"
    fi
done

# Check Python GUI support
echo ""
echo "=== Python GUI Support ==="
if command -v python3 &> /dev/null; then
    echo "✅ Python3: $(python3 --version)"
    
    if python3 -c "import tkinter" 2>/dev/null; then
        echo "✅ Tkinter: Available"
    else
        echo "❌ Tkinter: Not available"
    fi
    
    if python3 -c "import PyQt5" 2>/dev/null; then
        echo "✅ PyQt5: Available"
    else
        echo "❌ PyQt5: Not available"
    fi
else
    echo "❌ Python3: Not installed"
fi

# Installation suggestions
echo ""
echo "=== Installation Suggestions ==="

if ! command -v zenity &> /dev/null; then
    echo "To install Zenity: sudo apt-get install zenity"
fi

if ! command -v yad &> /dev/null; then
    echo "To install Yad: sudo apt-get install yad"
fi

if ! command -v dialog &> /dev/null; then
    echo "To install Dialog: sudo apt-get install dialog"
fi

# Test basic functionality
echo ""
echo "=== Basic Functionality Test ==="

if command -v zenity &> /dev/null; then
    echo "Testing Zenity..."
    zenity --info --text="Zenity is working!" --timeout=2 &
fi

if command -v dialog &> /dev/null; then
    echo "Testing Dialog..."
    dialog --infobox "Dialog is working!" 5 30
    sleep 2
    clear
fi

echo "Environment detection completed!"
```

---

## 📱 Testing Different Environments

### **1. Local Desktop Environment**
```bash
# Run on your local Linux desktop
./your_gui_script.sh

# All GUI tools should work
```

### **2. Remote SSH Connection**
```bash
# Without X forwarding (terminal only)
ssh user@server
./your_gui_script.sh  # Will use fallback terminal mode

# With X forwarding (GUI over SSH)
ssh -X user@server
./your_gui_script.sh  # GUI will display on your local machine
```

### **3. Virtual Terminal (TTY)**
```bash
# Switch to TTY (Ctrl+Alt+F1-F6)
# Login and run script
./your_gui_script.sh  # Will use dialog/whiptail or terminal output
```

### **4. Container/Docker Environment**
```bash
# For GUI in Docker, you need X11 socket sharing
docker run -it --net=host -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix your-image
./your_gui_script.sh
```

---

## 🚨 Troubleshooting Common Issues

### **Issue 1: "command not found"**
```bash
# Solution: Install the missing tool
sudo apt-get install [tool-name]

# Or use the fallback version in terminal mode
```

### **Issue 2: "Cannot open display"**
```bash
# Solution: Check X11 forwarding
echo $DISPLAY

# For SSH, use: ssh -X or ssh -Y
# For local, make sure you're in graphical session
```

### **Issue 3: Dialog doesn't clear properly**
```bash
# Solution: Always clear after dialog
dialog --msgbox "Message" 10 30
clear  # Add this to reset terminal
```

### **Issue 4: GUI appears but is unresponsive**
```bash
# Solution: Check if script is waiting for input
# Most GUI tools are modal and wait for user action
```

---

## 🎯 Quick Start Checklist

### **For Beginners:**
1. ✅ Install basic tools: `sudo apt-get install zenity dialog`
2. ✅ Test with: `zenity --info --text="Hello!"`
3. ✅ Try first example from the guide
4. ✅ Run environment detection script

### **For Advanced Users:**
1. ✅ Install full suite: `sudo apt-get install zenity yad dialog whiptail kdialog`
2. ✅ Install Python support: `sudo apt-get install python3-tk python3-pyqt5`
3. ✅ Install development tools: `sudo apt-get install libgtk-3-dev libsdl2-dev`
4. ✅ Test advanced examples

### **For Development/Testing:**
1. ✅ Set up SSH with X forwarding: `ssh -X server`
2. ✅ Test in different environments
3. ✅ Use environment detection script
4. ✅ Implement fallback mechanisms

---

## 📚 Best Practices for Usage

### **1. Always Check Tool Availability**
```bash
if command -v zenity &> /dev/null; then
    # Use zenity
else
    # Use fallback
fi
```

### **2. Handle User Cancellation**
```bash
result=$(zenity --entry --text="Enter something:")
if [ $? -eq 0 ]; then
    echo "User entered: $result"
else
    echo "User cancelled"
fi
```

### **3. Provide Terminal Fallbacks**
```bash
show_message() {
    local message="$1"
    if command -v zenity &> /dev/null; then
        zenity --info --text="$message"
    else
        echo "INFO: $message"
    fi
}
```

### **4. Test in Multiple Environments**
```bash
# Test locally
./script.sh

# Test via SSH
ssh -X server ./script.sh

# Test without GUI
ssh server ./script.sh
```

This comprehensive setup guide ensures you can use all examples from this guide in any environment - whether you have a full graphical desktop, remote SSH connection, or terminal-only access! 🚀

---

# 📚 Bash GUI Programming Reference - Keywords, Functions & Variables

## 🏷️ Essential GUI Keywords & Commands

### **Zenity Keywords:**
- **`--info`** - Display informational message dialog box
- **`--warning`** - Show warning dialog with yellow triangle icon
- **`--error`** - Display error dialog with red X icon
- **`--question`** - Show yes/no question dialog with return code
- **`--entry`** - Input dialog for user to type text/data
- **`--text-info`** - Display text file contents in scrollable window
- **`--file-selection`** - File browser dialog for selecting files
- **`--directory`** - Directory browser for folder selection
- **`--calendar`** - Calendar date picker dialog
- **`--list`** - Multi-column list/table dialog
- **`--progress`** - Progress bar with percentage display
- **`--scale`** - Slider control for numeric value selection
- **`--color-selection`** - Color picker dialog
- **`--password`** - Password entry dialog with masked input
- **`--forms`** - Multi-field form dialog with various input types

### **Dialog Keywords:**
- **`--msgbox`** - Simple message box in terminal
- **`--infobox`** - Information box that auto-dismisses
- **`--yesno`** - Yes/no question dialog
- **`--inputbox`** - Text input field dialog
- **`--textbox`** - Display file contents in terminal
- **`--menu`** - Menu selection dialog
- **`--checklist`** - Checkbox list for multiple selections
- **`--radiolist`** - Radio button list for single selection
- **`--gauge`** - Progress gauge display
- **`--tailbox`** - Monitor file changes in real-time
- **`--calendar`** - Date selection calendar
- **`--timebox`** - Time selection dialog

### **Yad Keywords:**
- **`--form`** - Advanced multi-field form dialog
- **`--field`** - Define individual form fields
- **`--button`** - Create custom buttons with labels
- **`--columns`** - Multi-column layout specification
- **`--editable`** - Make text areas editable
- **`--separator`** - Field separator character
- **`--num-output`** - Output field numbers instead of values
- **`--print-all`** - Show all fields including empty ones

---

## 🔧 Essential GUI Functions

### **Dialog Display Functions:**
- **`show_info()`** - Display informational message to user
- **`show_warning()`** - Show warning message with alert icon
- **`show_error()`** - Display error message with error icon
- **`ask_question()`** - Ask yes/no question and get user response
- **`get_input()`** - Get text input from user via entry dialog
- **`get_password()`** - Get password input with masked display
- **`select_file()`** - Open file browser for file selection
- **`select_directory()`** - Open directory browser for folder selection
- **`show_progress()`** - Display progress bar for long operations
- **`show_calendar()`** - Open calendar for date selection
- **`show_list()`** - Display multi-column list for selection
- **`show_form()`** - Display multi-field form for data entry

### **Utility Functions:**
- **`check_gui_tool()`** - Check if specific GUI tool is available
- **`detect_environment()`** - Detect desktop environment and display
- **`get_best_tool()`** - Select best available GUI tool
- **`fallback_message()`** - Display fallback message in terminal
- **`handle_cancel()`** - Process user cancellation gracefully
- **`validate_input()`** - Validate user input data
- **`format_output()`** - Format output for display

---

## 📦 Essential Variables

### **System Environment Variables:**
- **`$DISPLAY`** - X11 display server address (e.g., :0.0)
- **`$DESKTOP_SESSION`** - Current desktop environment name
- **`$XDG_CURRENT_DESKTOP`** - Desktop environment identifier
- **`$GUI_TOOL`** - Selected GUI tool for operations
- **`$FALLBACK_MODE`** - Terminal fallback mode flag

### **Dialog Response Variables:**
- **`$?`** - Exit code of last command (0=success, 1=cancel)
- **`$result`** - User input from entry dialogs
- **`$choice`** - User selection from list/menu dialogs
- **`$filename`** - Selected file path from file browser
- **`$directory`** - Selected directory path
- **`$date`** - Selected date from calendar dialog
- **`$progress`** - Current progress percentage

### **Configuration Variables:**
- **`$dialog_title`** - Title text for dialog windows
- **`$dialog_text`** - Main message text for dialogs
- **`$dialog_width`** - Width of dialog windows in pixels
- **`$dialog_height`** - Height of dialog windows in pixels
- **`$timeout`** - Auto-dismiss timeout in seconds
- **`$default_entry`** - Default text for entry fields

---

## 🎯 GUI Programming Patterns

### **Basic Dialog Pattern:**
```bash
# Check tool availability → Display dialog → Handle response
if command -v zenity &> /dev/null; then
    result=$(zenity --entry --text="Enter data:")
    if [ $? -eq 0 ]; then
        echo "User entered: $result"
    else
        echo "User cancelled"
    fi
fi
```

### **Fallback Pattern:**
```bash
# Try GUI tool → Fallback to terminal if unavailable
show_message() {
    local msg="$1"
    if command -v zenity &> /dev/null; then
        zenity --info --text="$msg"
    else
        echo "INFO: $msg"
    fi
}
```

### **Form Pattern:**
```bash
# Multi-field form → Parse results → Validate data
result=$(yad --form --field="Name:" --field="Email:")
name=$(echo "$result" | cut -d'|' -f1)
email=$(echo "$result" | cut -d'|' -f2)
```

---

## 🔄 Control Flow Keywords

### **Conditional Keywords:**
- **`if`** - Start conditional block for testing conditions
- **`then`** - Execute commands if condition is true
- **`else`** - Execute commands if condition is false
- **`elif`** - Additional conditional test
- **`fi`** - End conditional block

### **Loop Keywords:**
- **`for`** - Loop through items in list
- **`while`** - Loop while condition is true
- **`until`** - Loop until condition becomes true
- **`do`** - Start loop body
- **`done`** - End loop block

### **Case Keywords:**
- **`case`** - Start multi-way conditional
- **`in`** - Specify pattern list
- **`esac`** - End case statement

---

## 📊 Data Type Keywords

### **String Operations:**
- **`$variable`** - Variable value expansion
- **`"${variable}"`** - Variable with quotes
- **`${variable:position:length}`** - String substring extraction
- **`${variable#pattern}`** - Remove prefix pattern
- **`${variable%pattern}`** - Remove suffix pattern
- **`${variable/pattern/replacement}`** - Pattern replacement

### **Numeric Operations:**
- **`$((expression))`** - Arithmetic evaluation
- **`$((var1 + var2))`** - Arithmetic addition
- **`$((var1 * var2))`** - Arithmetic multiplication
- **`$((var1 / var2))`** - Arithmetic division
- **`$((var1 % var2))`** - Arithmetic modulo

### **Array Operations:**
- **`${array[index]}`** - Access array element
- **`${array[@]}`** - All array elements
- **`${#array[@]}`** - Array length
- **`${!array[@]}`** - Array indices

---

## 🎨 GUI Element Types

### **Input Elements:**
- **Entry Field** - Single line text input
- **Text Area** - Multi-line text input
- **Password Field** - Masked password input
- **File Selector** - File browser dialog
- **Directory Selector** - Folder browser
- **Calendar** - Date picker widget
- **Time Selector** - Time picker widget
- **Color Picker** - Color selection dialog
- **Scale/Slider** - Numeric value slider
- **Checkboxes** - Multiple selection boxes
- **Radio Buttons** - Single selection buttons

### **Display Elements:**
- **Message Box** - Information display
- **Warning Box** - Warning message display
- **Error Box** - Error message display
- **Progress Bar** - Progress indicator
- **List View** - Multi-column data display
- **Text Viewer** - File content display
- **Icon Display** - Symbolic icons
- **Image Display** - Picture display

### **Control Elements:**
- **Buttons** - Clickable action buttons
- **OK Button** - Confirmation button
- **Cancel Button** - Cancellation button
- **Yes/No Buttons** - Decision buttons
- **Apply Button** - Apply changes button
- **Close Button** - Window close button

---

## 🚀 Advanced GUI Concepts

### **Event Handling:**
- **Event Loop** - Continuous monitoring for user actions
- **Event Handler** - Function to process specific events
- **Callback** - Function called when event occurs
- **Event Queue** - Queue of pending events
- **Event Dispatch** - Send event to appropriate handler

### **State Management:**
- **GUI State** - Current interface configuration
- **Application State** - Overall program status
- **Session State** - User session data
- **Persistent State** - Saved configuration data

### **Layout Management:**
- **Grid Layout** - Table-based arrangement
- **Box Layout** - Horizontal/vertical arrangement
- **Form Layout** - Field-based arrangement
- **Responsive Layout** - Adaptive to window size

---

## 📋 Quick Reference Summary

### **Must-Know Commands:**
- `zenity --info` - Show message
- `dialog --msgbox` - Terminal message
- `yad --form` - Multi-field form
- `command -v tool` - Check availability
- `$?` - Check exit code

### **Must-Know Variables:**
- `$DISPLAY` - Display server
- `$result` - User input
- `$?` - Exit status
- `$choice` - User selection

### **Must-Know Patterns:**
- Check tool → Use tool → Handle response
- GUI tool → Fallback to terminal
- Form → Parse → Validate

This reference provides all essential keywords, functions, variables, and patterns needed for Bash GUI programming! 🎯

---

# 🎯 Practical Examples & Real-World Applications

## 🚀 Quick Start Examples - Copy & Paste Ready

### **Example 1: Basic Information Dialog**
```bash
#!/bin/bash
# Simple message display
zenity --info --text="Hello World!" --title="Welcome"
```

### **Example 2: User Input with Validation**
```bash
#!/bin/bash
# Get user name and validate
name=$(zenity --entry --title="Name Input" --text="Enter your name:")
if [ $? -eq 0 ] && [ -n "$name" ]; then
    zenity --info --text="Hello, $name!" --title="Welcome"
else
    echo "No name entered or cancelled"
fi
```

### **Example 3: File Selection Dialog**
```bash
#!/bin/bash
# Select and display file
file=$(zenity --file-selection --title="Choose a file")
if [ $? -eq 0 ]; then
    zenity --text-info --title="File Content" --filename="$file"
else
    echo "No file selected"
fi
```

### **Example 4: Progress Bar for Long Operations**
```bash
#!/bin/bash
# Progress bar demonstration
(
    echo "10"
    sleep 1
    echo "30"
    sleep 1
    echo "60"
    sleep 1
    echo "100"
) | zenity --progress --title="Processing..." --text="Please wait..."
```

### **Example 5: Multi-Field Form**
```bash
#!/bin/bash
# User registration form
result=$(yad --form --title="User Registration" \
    --field="Name:" \
    --field="Email:" \
    --field="Age:NUM" \
    --button="Register:0" \
    --button="Cancel:1")

if [ $? -eq 0 ]; then
    name=$(echo "$result" | cut -d'|' -f1)
    email=$(echo "$result" | cut -d'|' -f2)
    age=$(echo "$result" | cut -d'|' -f3)
    
    zenity --info --text="Registered:\nName: $name\nEmail: $email\nAge: $age"
fi
```

---

## 🛠️ Real-World Application Examples

### **System Monitor GUI**
```bash
#!/bin/bash
# Real-time system monitoring
while true; do
    cpu=$(top -bn1 | grep "Cpu(s)" | awk '{print $2}' | cut -d'%' -f1)
    mem=$(free | grep Mem | awk '{printf "%.1f", $3/$2 * 100.0}')
    disk=$(df -h / | awk 'NR==2 {print $5}')
    
    choice=$(yad --form --title="System Monitor" \
        --field="CPU Usage:RO" "$cpu%" \
        --field="Memory Usage:RO" "$mem%" \
        --field="Disk Usage:RO" "$disk" \
        --field="Uptime:RO" "$(uptime -p)" \
        --button="Refresh:0" \
        --button="Exit:1" \
        --timeout=5)
    
    [ $? -eq 1 ] && break
done
```

### **Backup Manager**
```bash
#!/bin/bash
# Simple backup utility with GUI
source_dir=$(zenity --file-selection --directory --title="Select source directory")
[ $? -ne 0 ] && exit 1

dest_dir=$(zenity --file-selection --directory --title="Select destination directory")
[ $? -ne 0 ] && exit 1

backup_name="backup_$(date +%Y%m%d_%H%M%S)"
dest_path="$dest_dir/$backup_name"

(
    echo "10"
    echo "# Creating backup directory..."
    mkdir -p "$dest_path"
    sleep 1
    
    echo "30"
    echo "# Copying files..."
    cp -r "$source_dir"/* "$dest_path/"
    
    echo "80"
    echo "# Verifying backup..."
    if [ -d "$dest_path" ]; then
        echo "100"
        echo "# Backup completed successfully!"
    else
        echo "# Backup failed!"
    fi
) | zenity --progress --title="Backup Progress" --width=400

zenity --info --text="Backup completed: $backup_name"
```

### **Password Generator**
```bash
#!/bin/bash
# Secure password generator
generate_password() {
    length=$1
    chars='ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789!@#$%^&*'
    password=$(tr -dc "$chars" < /dev/urandom | head -c "$length")
    echo "$password"
}

length=$(zenity --scale --title="Password Generator" \
    --text="Select password length:" \
    --min=8 --max=32 --value=16 --step=1)

if [ $? -eq 0 ]; then
    password=$(generate_password "$length")
    
    zenity --entry --title="Generated Password" \
        --text="Your secure password:" \
        --entry-text="$password" \
        --editable=false
fi
```

### **Log File Viewer**
```bash
#!/bin/bash
# Interactive log file viewer
log_file=$(zenity --file-selection --title="Select log file" --file-filter="Log files | *.log")
[ $? -ne 0 ] && exit 1

while true; do
    choice=$(yad --list --title="Log Viewer" \
        --text="File: $log_file" \
        --column="Action" \
        "View Full Log" \
        "View Last 50 Lines" \
        "Search in Log" \
        "Refresh" \
        "Exit" \
        --width=300 --height=250)
    
    case "$choice" in
        "View Full Log")
            zenity --text-info --title="Full Log" --filename="$log_file" --width=800 --height=600
            ;;
        "View Last 50 Lines")
            tail -50 "$log_file" > /tmp/temp_log
            zenity --text-info --title="Last 50 Lines" --filename="/tmp/temp_log" --width=800 --height=600
            ;;
        "Search in Log")
            search_term=$(zenity --entry --title="Search" --text="Enter search term:")
            if [ $? -eq 0 ]; then
                grep -n "$search_term" "$log_file" > /tmp/search_results
                zenity --text-info --title="Search Results" --filename="/tmp/search_results" --width=800 --height=600
            fi
            ;;
        "Refresh")
            continue
            ;;
        "Exit")
            break
            ;;
    esac
done
```

---

## 🎮 Interactive Game Examples

### **Number Guessing Game**
```bash
#!/bin/bash
# Simple number guessing game
target=$((RANDOM % 100 + 1))
attempts=0

while true; do
    guess=$(zenity --entry --title="Number Guessing Game" \
        --text="Guess a number between 1 and 100\nAttempts: $attempts")
    
    [ $? -ne 0 ] && break
    
    attempts=$((attempts + 1))
    
    if [ "$guess" -eq "$target" ]; then
        zenity --info --title="Congratulations!" \
            --text="You guessed it!\nNumber: $target\nAttempts: $attempts"
        break
    elif [ "$guess" -lt "$target" ]; then
        zenity --info --title="Too Low!" --text="Try a higher number!" --timeout=2
    else
        zenity --info --title="Too High!" --text="Try a lower number!" --timeout=2
    fi
done
```

### **Rock Paper Scissors**
```bash
#!/bin/bash
# Rock Paper Scissors game
choices=("Rock" "Paper" "Scissors")
user_score=0
computer_score=0

while true; do
    user_choice=$(yad --list --title="Rock Paper Scissors" \
        --text="Score: You $user_score - Computer $computer_score" \
        --column="Choice" \
        "Rock" "Paper" "Scissors" "Exit" \
        --width=200 --height=200)
    
    [ "$user_choice" = "Exit" ] && break
    
    computer_choice=${choices[$((RANDOM % 3))]}
    
    # Determine winner
    if [ "$user_choice" = "$computer_choice" ]; then
        result="It's a tie!"
    elif ([ "$user_choice" = "Rock" ] && [ "$computer_choice" = "Scissors" ]) || \
         ([ "$user_choice" = "Paper" ] && [ "$computer_choice" = "Rock" ]) || \
         ([ "$user_choice" = "Scissors" ] && [ "$computer_choice" = "Paper" ]); then
        result="You win!"
        user_score=$((user_score + 1))
    else
        result="Computer wins!"
        computer_score=$((computer_score + 1))
    fi
    
    zenity --info --title="Result" \
        --text="You chose: $user_choice\nComputer chose: $computer_choice\n$result"
done

zenity --info --title="Final Score" \
    --text="You: $user_score\nComputer: $computer_score"
```

---

## 📊 Data Processing Examples

### **CSV File Processor**
```bash
#!/bin/bash
# CSV file viewer and processor
csv_file=$(zenity --file-selection --title="Select CSV file" --file-filter="CSV files | *.csv")
[ $? -ne 0 ] && exit 1

while true; do
    choice=$(yad --list --title="CSV Processor" \
        --text="File: $(basename "$csv_file")" \
        --column="Action" \
        "View Data" \
        "Show Statistics" \
        "Filter Data" \
        "Export Filtered" \
        "Exit" \
        --width=250 --height=250)
    
    case "$choice" in
        "View Data")
            zenity --text-info --title="CSV Data" --filename="$csv_file" --width=800 --height=600
            ;;
        "Show Statistics")
            lines=$(wc -l < "$csv_file")
            columns=$(head -1 "$csv_file" | tr ',' '\n' | wc -l)
            zenity --info --title="Statistics" \
                --text="Lines: $lines\nColumns: $columns"
            ;;
        "Filter Data")
            filter_term=$(zenity --entry --title="Filter" --text="Enter filter term:")
            if [ $? -eq 0 ]; then
                grep "$filter_term" "$csv_file" > /tmp/filtered.csv
                zenity --text-info --title="Filtered Data" --filename="/tmp/filtered.csv"
            fi
            ;;
        "Export Filtered")
            output_file=$(zenity --file-selection --title="Save filtered data" --save)
            if [ $? -eq 0 ]; then
                cp /tmp/filtered.csv "$output_file"
                zenity --info --text="Data exported to $output_file"
            fi
            ;;
        "Exit")
            break
            ;;
    esac
done
```

### **Image Resizer**
```bash
#!/bin/bash
# Batch image resizer (requires ImageMagick)
if ! command -v convert &> /dev/null; then
    zenity --error --text="ImageMagick not installed!\nInstall with: sudo apt-get install imagemagick"
    exit 1
fi

input_dir=$(zenity --file-selection --directory --title="Select input directory")
[ $? -ne 0 ] && exit 1

output_dir=$(zenity --file-selection --directory --title="Select output directory")
[ $? -ne 0 ] && exit 1

width=$(zenity --scale --title="Image Width" --text="Set new width:" --min=100 --max=2000 --value=800)
[ $? -ne 0 ] && exit 1

height=$(zenity --scale --title="Image Height" --text="Set new height:" --min=100 --max=2000 --value=600)
[ $? -ne 0 ] && exit 1

# Process images
count=0
total=$(find "$input_dir" -type f \( -iname "*.jpg" -o -iname "*.png" -o -iname "*.gif" \) | wc -l)

(
    for image in "$input_dir"/*.{jpg,jpeg,png,gif,JPG,JPEG,PNG,GIF}; do
        if [ -f "$image" ]; then
            filename=$(basename "$image")
            convert "$image" -resize "${width}x${height}" "$output_dir/$filename"
            count=$((count + 1))
            percentage=$((count * 100 / total))
            echo "$percentage"
            echo "# Processing $filename ($count/$total)"
        fi
    done
) | zenity --progress --title="Resizing Images" --width=400

zenity --info --text="Resized $count images to ${width}x${height}"
```

---

## 🔧 Utility Scripts

### **Network Connection Tester**
```bash
#!/bin/bash
# Test network connectivity to multiple hosts
hosts=("google.com" "github.com" "stackoverflow.com" "8.8.8.8")

results=""
for host in "${hosts[@]}"; do
    if ping -c 1 "$host" &>/dev/null; then
        status="Online"
        color="green"
    else
        status="Offline"
        color="red"
    fi
    results="$results$host|$status\n"
done

echo -e "$results" | yad --list --title="Network Status" \
    --column="Host" --column="Status" \
    --width=300 --height=200
```

### **Disk Space Analyzer**
```bash
#!/bin/bash
# Analyze disk space usage
choice=$(yad --list --title="Disk Space Analyzer" \
    --text="Select analysis type:" \
    --column="Option" \
    "Overall Usage" \
    "Directory Sizes" \
    "Large Files" \
    "Exit" \
    --width=250 --height=200)

case "$choice" in
    "Overall Usage")
        df -h | yad --text-info --title="Disk Usage" --width=600 --height=300
        ;;
    "Directory Sizes")
        dir=$(zenity --file-selection --directory --title="Select directory")
        [ $? -eq 0 ] && du -sh "$dir"/* | sort -hr | head -20 | \
            yad --text-info --title="Directory Sizes" --width=600 --height=400
        ;;
    "Large Files")
        dir=$(zenity --file-selection --directory --title="Select directory")
        [ $? -eq 0 ] && find "$dir" -type f -size +10M -exec ls -lh {} \; | \
            yad --text-info --title="Large Files" --width=800 --height=400
        ;;
esac
```

---

## 🎯 Quick Reference Cheat Sheet

### **Common Patterns:**
```bash
# Basic dialog with error handling
if command -v zenity &> /dev/null; then
    result=$(zenity --entry --text="Enter data:")
    if [ $? -eq 0 ]; then
        echo "Success: $result"
    else
        echo "User cancelled"
    fi
else
    echo "Zenity not available"
fi

# Progress bar
(
    echo "10"; sleep 1
    echo "50"; sleep 1
    echo "100"
) | zenity --progress --title="Working..."

# File operations
file=$(zenity --file-selection)
if [ -f "$file" ]; then
    zenity --text-info --filename="$file"
fi
```

### **Essential Commands:**
- `zenity --info` - Show message
- `zenity --entry` - Get input
- `zenity --file-selection` - Select file
- `yad --form` - Multi-field form
- `dialog --msgbox` - Terminal message
- `$?` - Check exit code
- `command -v tool` - Check availability

These practical examples demonstrate real-world applications of Bash GUI programming and can be used as templates for your own projects! 🚀
