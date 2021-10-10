# HomeScreenShortcut
<img src="https://user-images.githubusercontent.com/47273077/136684846-e57b27f7-9e34-44a7-82e9-5e14fae8a403.png" width="200"> 

## Where to get SF Symbols
Apple Developer website: https://developer.apple.com/sf-symbols

## How to use
1 . Export > choose destination folder for exported templated


2 . Copy files that were exported into your project’s assets

3 . Use these icons as values for the UIApplicationShortcutItemIconFile field inside the app icon section of the Info.plist

<img width="943" alt="Info_plist_—_Edited_と_HomeScreenShortcut_README_md_at_main_·_YamamotoDesu_HomeScreenShortcut" src="https://user-images.githubusercontent.com/47273077/136685234-0584705b-1549-4de9-9fe1-af93a2f011a9.png">

・　Define UIApplicationShortcutItems, an array of every shortcut we want to use.　

・　For each child element: UIApplicationShortcutItemIconType to display a native icon.　

・　UIApplicationShortcutItemTitle is the main title of your shortcut and can be localized.　

・　UIApplicationShortcutItemSubtitle describes an optional subtitle and can also be localized.　

・　UIApplicationShortcutItemType can be used as a unique identifier to your shortcut.　

・　UIApplicationShortcutItemUserInfo can include any other informations related to your shortcut.　

