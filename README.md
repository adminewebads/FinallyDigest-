# FinallyDigest-
$String = "The quick brown fox jumps over the lazy dog" $Digest = DllStructCreate("byte[16]") DllCall("md5.dll", "str", "md5", "str", $String, "uint", StringLen($String), "ptr", DllStructGetPtr($Digest)) $Hash = DllStructGetData($Digest, 1) $Digest = 0 MsgBox(0, 'MD5 Hash', $Hash)   ; ---------------------------------------------------------------------------- ; ; Step 2: Use MemoryDllGen.au3 to convert the DLL to script form and paste it. ; ; ----------------------------------------------------------------------------  Dim $DllBinary = ''; this line is too long to omit, check the attachment  ; -------------------------------------------------------------------------------- ; ; Step 3: Replace DllCall to MemoryDllCall, and use $DllBinary instead of dll name ; ; --------------------------------------------------------------------------------  #Include "MemoryDll.au3" MemoryDllInit()  $String = "The quick brown fox jumps over the lazy dog" $Digest = DllStructCreate("byte[16]") MemoryDllCall($DllBinary, "str", "md5", "str", $String, "uint", StringLen($String), "ptr", DllStructGetPtr($Digest)) $Hash = DllStructGetData($Digest, 1) $Digest = 0 MsgBox(0, 'MD5 Hash', $Hash)  MemoryDllExit()   ; ------------------------------------------------------------------------- ; ; Step 4: Finally, you have the functions in Pure AutoIt Scirpt. Have fun ! ; ; -------------------------------------------------------------------------
