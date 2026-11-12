# WhatsApp PBX — Rebranding Changes & Notes

This document logs all changes made to rebrand the vanilla MicroSIP-3.22.16 source code into **WhatsApp PBX**.

---

## 1. Modified Files Overview

| # | File | Path | Description |
| :- | :--- | :--- | :--- |
| 1 | `const.h` | `const.h` | Changed application global name `_GLOBAL_NAME` to `"WhatsApp PBX"` and company to `"Softcents"` |
| 2 | `define.h` | `define.h` | Replaced MicroSIP links with Softcents and project GitHub repository URLs |
| 3 | `res/main.rc2` | `res/main.rc2` | Updated Windows file version info and legal copyright text |
| 4 | `microsip.vcxproj` | `microsip.vcxproj` | Updated RootNamespace to `WhatsAppPBX` and set `<TargetName>WhatsApp PBX</TargetName>` |
| 5 | `mainDlg.cpp` | `mainDlg.cpp` | Updated comment reference for STUN / help page |
| 6 | `README.md` | `README.md` | Added project introduction and build instructions |

---

## 2. Detailed Code Diffs

### const.h
```diff
--- a/const.h
+++ b/const.h
@@ -26,2 +26,2 @@
-#define _GLOBAL_NAME "MicroSIP"
-#define _GLOBAL_COMPANY "www.microsip.org"
+#define _GLOBAL_NAME "WhatsApp PBX"
+#define _GLOBAL_COMPANY "Softcents"
```
**Effect:** Controls the application window title, taskbar icon tooltip, registered window class name, user-agent SIP string (`WhatsApp PBX/3.22.16`), local config folder (`%APPDATA%\WhatsApp PBX`), and registry key (`HKCU\Software\WhatsApp PBX`).

---

### define.h
```diff
--- a/define.h
+++ b/define.h
@@ -66,6 +66,6 @@
-#define _GLOBAL_MENU_WEBSITE "https://www.microsip.org/"
-#define _GLOBAL_MENU_DOWNLOADS "https://www.microsip.org/downloads"
-#define _GLOBAL_MENU_ISSUES "https://www.microsip.org/issues"
-#define _GLOBAL_MENU_HELP "https://www.microsip.org/help"
-#define _GLOBAL_HELP_WEBSITE "https://www.microsip.org/help"
-#define _GLOBAL_URL_CHECK_VERSION "https://www.microsip.org/check-version?ver="
+#define _GLOBAL_MENU_WEBSITE "https://softcents.com/"
+#define _GLOBAL_MENU_DOWNLOADS "https://github.com/softcents/WhatsApp-BD-PBX-Windows-Apps"
+#define _GLOBAL_MENU_ISSUES "https://github.com/softcents/WhatsApp-BD-PBX-Windows-Apps/issues"
+#define _GLOBAL_MENU_HELP "https://github.com/softcents/WhatsApp-BD-PBX-Windows-Apps#readme"
+#define _GLOBAL_HELP_WEBSITE "https://github.com/softcents/WhatsApp-BD-PBX-Windows-Apps#readme"
+#define _GLOBAL_URL_CHECK_VERSION "https://softcents.com/check-version?ver="
```
**Effect:** Directs in-app links (Website, Help, Issues, Downloads) to Softcents and GitHub repository rather than MicroSIP servers.

---

### res/main.rc2
```diff
--- a/res/main.rc2
+++ b/res/main.rc2
@@ -98,1 +98,1 @@
-            VALUE "LegalCopyright", "Copyright (c) 2011-2025, MicroSIP (www.microsip.org). All rights reserved."
+            VALUE "LegalCopyright", "Copyright (c) 2011-2026, WhatsApp PBX. All rights reserved."
```
**Effect:** Updates Windows binary file properties (Details tab) and product copyright.

---

### microsip.vcxproj
```diff
--- a/microsip.vcxproj
+++ b/microsip.vcxproj
@@ -33,1 +33,1 @@
-    <RootNamespace>microsip</RootNamespace>
+    <RootNamespace>WhatsAppPBX</RootNamespace>
@@ -104,2 +104,3 @@
   <PropertyGroup>
     <_ProjectFileVersion>14.0.25431.1</_ProjectFileVersion>
+    <TargetName>WhatsApp PBX</TargetName>
   </PropertyGroup>
```
**Effect:** Visual Studio build outputs `WhatsApp PBX.exe` directly.

---

## 3. Git Commits
- `f8554ff`: Initial commit from MicroSIP-3.22.16 source
- `812bf68`: Rebrand application to WhatsApp PBX
