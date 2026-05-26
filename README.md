AHK Codes to adjust positioning of the pip automatically : 

; --- PiP Fixed Position On Top Right , TOP ---
SetTitleMatchMode, 2
GroupAdd, PiPWindows, Picture in picture  ; Chrome/Edge English
GroupAdd, PiPWindows, Resim içinde resim  ; Chrome/Edge Turkish
GroupAdd, PiPWindows, Picture-in-Picture  ; Firefox
SetTimer, CheckPiP, 500
return ; Ends the auto-execute section cleanly here
CheckPiP:
current_id := WinExist("ahk_group PiPWindows")
if (current_id && current_id != last_pip_id) {
    WinMove, ahk_group PiPWindows,, 1355, 119
    last_pip_id := current_id
}
if (!current_id)
    last_pip_id := 0
return
; --- PiP Fixed Position On Top Right , BOTTOM ---
