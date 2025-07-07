## litmos-training: an AutoHotkey Script for Ctrl + Alt + `.` Every 3 Minutes

- **Install AutoHotkey:**  
  Go to [autohotkey.com](https://www.autohotkey.com/), click **"Download"**, then choose **"Download AutoHotkey v2.0"**.  
  Open the file and select **"Express Installation"**.

- **Create the Script File:**  
  Right-click on your **Desktop** or in any folder, choose **"New" > "AutoHotkey Script"**, and name the file `AutoPress.ahk`.

- **Add the Script Code:**  
  Right-click the new file and select **"Edit Script"**.  
  Delete everything in the file and paste in the code below.  
  Save and close the file.

  ```ahk
  #Requires AutoHotkey v2.0
  toggle := false
  timerInterval := 180000  ; 3 minutes in milliseconds

  ; Set up hotkey
  F9:: {
      global toggle
      toggle := !toggle
      if toggle {
          SetTimer(PressKeys, timerInterval)
          ToolTip("Auto key press ON")
      } else {
          SetTimer(PressKeys, 0)  ; Disable timer
          ToolTip("Auto key press OFF")
      }
      SetTimer(RemoveToolTip, -1000)
  }

  PressKeys() {
      Send("^!.")  ; Ctrl + Alt + .
  }

  RemoveToolTip() {
      ToolTip()
  }


-  **Run the Script:**
Double-click AutoPress.ahk. A green "H" icon will appear in your system tray.
Press F9 to start or stop the automatic key press.

-  **Exit the Script:**
Right-click the green "H" icon in the tray and choose "Exit" to stop the script completely.

##Done✅
