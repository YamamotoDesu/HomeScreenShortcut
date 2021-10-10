# HomeScreenShortcut  
**[Expose commonly used functionality with static or dynamic 3D Touch Home Screen quick actions.
](https://developer.apple.com/documentation/uikit/menus_and_shortcuts/add_home_screen_quick_actions)**  
> On the Home screen of a device running iOS 13 or later, apps can display Home Screen quick actions when users touch and hold the app icon (on a 3D Touch device, users press briefly on the icon)

<img src="https://user-images.githubusercontent.com/47273077/136684846-e57b27f7-9e34-44a7-82e9-5e14fae8a403.png" width="200"> 

## Where to get SF Symbols
Apple Developer website: https://developer.apple.com/sf-symbols

## How to use
1 . Export > choose destination folder for exported templated


2 . Copy files that were exported into your project’s assets


## set static quick actions
### Use these icons as values for the UIApplicationShortcutItemIconFile field inside the app icon section of the Info.plist(static quick actions)　

<img width="943" alt="Info_plist_—_Edited_と_HomeScreenShortcut_README_md_at_main_·_YamamotoDesu_HomeScreenShortcut" src="https://user-images.githubusercontent.com/47273077/136685234-0584705b-1549-4de9-9fe1-af93a2f011a9.png">

UIApplicationShortcutItemType (required): 
> A unique string that identifies the Quick Action. For example: com.mediumproject.helloWorld. 

UIApplicationShortcutItemTitle (required): 
> The Quick Action title displayed to the user.

UIApplicationShortcutItemSubtitle (optional): 
> 　The Quick Action’s subtitle. 

UIApplicationShortcutItemIconType (optional): 
>  Here you can set a predefined icon made by Apple.

UIApplicationShortcutItemIconFile (optional): 
>  Use to set a custom icon.

UIApplicationShortcutItemUserInfo (optional): 
> A dictionary to save data.

## Set dynamic quick actions 
### Create Custom Quick Actions 

4 . Define our shortcut either from UIMutableApplicationShortcutItem or UIApplicationShortcutItem 

## Implementation 


