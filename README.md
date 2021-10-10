# HomeScreenShortcut  
**[Expose commonly used functionality with static or dynamic 3D Touch Home Screen quick actions.
](https://developer.apple.com/documentation/uikit/menus_and_shortcuts/add_home_screen_quick_actions)**  
> On the Home screen of a device running iOS 13 or later, apps can display Home Screen quick actions when users touch and hold the app icon (on a 3D Touch device, users press briefly on the icon)

<img src="https://user-images.githubusercontent.com/47273077/136684846-e57b27f7-9e34-44a7-82e9-5e14fae8a403.png" width="200"> 

## Preview 
<img src="https://user-images.githubusercontent.com/47273077/136684846-e57b27f7-9e34-44a7-82e9-5e14fae8a403.png" width="200"> 

## Where to get SF Symbols
Apple Developer website: https://developer.apple.com/sf-symbols

## How to use
1 . Export > choose destination folder for exported templated
<img width="1021" alt="Info_plist" src="https://user-images.githubusercontent.com/47273077/136687095-59a1ce14-330e-4bbc-98cf-75cc5f28dcfc.png">

2 . Copy files that were exported into your project’s assets
<img width="1021" alt="Info_plist" src="https://user-images.githubusercontent.com/47273077/136687095-59a1ce14-330e-4bbc-98cf-75cc5f28dcfc.png">

## set static quick actions
### Use these icons as values for the UIApplicationShortcutItemIconFile field inside the app icon section of the Info.plist(static quick actions)　

<img width="1021" alt="Info_plist" src="https://user-images.githubusercontent.com/47273077/136687095-59a1ce14-330e-4bbc-98cf-75cc5f28dcfc.png">

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
### Add the following method in the SceneDelegate.swift file 
```swift 
    func sceneWillResignActive(_ scene: UIScene) {
        let application = UIApplication.shared
        application.shortcutItems = [
            UIApplicationShortcutItem(type: "trash", localizedTitle: "Trash", localizedSubtitle: nil, icon: UIApplicationShortcutIcon(systemImageName: "trash.slash.circle"))]
        
    }
```

## Implementation 
### Add the following method in the SceneDelegate.swift file 
```swift 
    func windowScene(_ windowScene: UIWindowScene,
                     performActionFor shortcutItem: UIApplicationShortcutItem,
                     completionHandler: @escaping (Bool) -> Void) {
        
        switch shortcutItem.type {
        case "send", "trash":
            DispatchQueue.main.asyncAfter(deadline: DispatchTime.now()) {
                self.window?.rootViewController = UIStoryboard(name: "Main", bundle: nil).instantiateInitialViewController()
                let alert = UIAlertController(title: "Hey", message: "Your quick action works!", preferredStyle: .alert)
                let action = UIAlertAction(title: "OK", style: .default, handler: nil)
                alert.addAction(action)
                self.window?.rootViewController?.present(alert, animated: true, completion: nil)
            }
        default: break
        }
    }

``` 

