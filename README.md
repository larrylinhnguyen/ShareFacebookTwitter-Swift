# ShareFacebookTwitterSwift
How to create a share to Facebook & Twitter in iOS in Swift.
Easy Copy and Paste code to add a UIActionSheet to your Swift app.

<h3>INSTALLATION</h3>
<h4>Swift 2</h4>
Step 1: Add the Social Framework to your App (General > Linked Frameworks and Libraries). <br>
Step 2: Add the UIActionSheetDelegate to you class declaration. <br>
Step 3: Add "Import Social" to your viewcontroller
Step 4: Create your IBAction. <br>
Step 5: Add the code: <br>

  
        let alert = UIAlertController(title: "Share", message: "Share the app", preferredStyle: UIAlertControllerStyle.ActionSheet)
        let twBtn = UIAlertAction(title: "Twitter", style: UIAlertActionStyle.Default) { (alert) -> Void in
            if SLComposeViewController.isAvailableForServiceType(SLServiceTypeTwitter){
                let twitterSheet:SLComposeViewController = SLComposeViewController(forServiceType: SLServiceTypeTwitter)
                twitterSheet.setInitialText("Share on Twitter")
                self.presentViewController(twitterSheet, animated: true, completion: nil)
            } else {
                let alert = UIAlertController(title: "Accounts", message: "Please login to a Twitter account to share.", preferredStyle: UIAlertControllerStyle.Alert)
                alert.addAction(UIAlertAction(title: "OK", style: UIAlertActionStyle.Default, handler: nil))
                self.presentViewController(alert, animated: true, completion: nil)
            }
        }
        
        let fbBtn = UIAlertAction(title: "Facebook", style: UIAlertActionStyle.Default) { (alert) -> Void in
            if SLComposeViewController.isAvailableForServiceType(SLServiceTypeFacebook){
                let facebookSheet:SLComposeViewController = SLComposeViewController(forServiceType: SLServiceTypeFacebook)
                facebookSheet.setInitialText("Share on Facebook")
                self.presentViewController(facebookSheet, animated: true, completion: nil)
            } else {
                let alert = UIAlertController(title: "Accounts", message: "Please login to a Facebook account to share.", preferredStyle: UIAlertControllerStyle.Alert)
                alert.addAction(UIAlertAction(title: "OK", style: UIAlertActionStyle.Default, handler: nil))
                self.presentViewController(alert, animated: true, completion: nil)
            }
        }
        let cancelButton = UIAlertAction(title: "Cancel", style: UIAlertActionStyle.Cancel) { (alert) -> Void in
            print("Cancel Pressed")
        }
        
        alert.addAction(twBtn)
        alert.addAction(fbBtn)
        alert.addAction(cancelButton)
        self.presentViewController(alert, animated: true, completion: nil)


<h4>Swift 1</h4>
Step 1: Add the Social Framework to your App (General > Linked Frameworks and Libraries). <br>
Step 2: Add the UIActionSheetDelegate to you class declaration. <br>
Step 3: Add "Import Social" to your viewcontroller
Step 4: Create your IBAction. <br>
Step 5: Add the code: <br>

         
        let alert = UIAlertController(title: "Share", message: "Share the app", preferredStyle: UIAlertControllerStyle.ActionSheet)
        let twBtn = UIAlertAction(title: "Twitter", style: UIAlertActionStyle.Default) { (alert) -> Void in
            if SLComposeViewController.isAvailableForServiceType(SLServiceTypeTwitter){
                var twitterSheet:SLComposeViewController = SLComposeViewController(forServiceType: SLServiceTypeTwitter)
                twitterSheet.setInitialText("Share on Twitter")
                self.presentViewController(twitterSheet, animated: true, completion: nil)
            } else {
                var alert = UIAlertController(title: "Accounts", message: "Please login to a Twitter account to share.", preferredStyle: UIAlertControllerStyle.Alert)
                alert.addAction(UIAlertAction(title: "OK", style: UIAlertActionStyle.Default, handler: nil))
                self.presentViewController(alert, animated: true, completion: nil)
            }
        }
    
        let fbBtn = UIAlertAction(title: "Facebook", style: UIAlertActionStyle.Default) { (alert) -> Void in
            if SLComposeViewController.isAvailableForServiceType(SLServiceTypeFacebook){
                var facebookSheet:SLComposeViewController = SLComposeViewController(forServiceType: SLServiceTypeFacebook)
                facebookSheet.setInitialText("Share on Facebook")
                self.presentViewController(facebookSheet, animated: true, completion: nil)
            } else {
                var alert = UIAlertController(title: "Accounts", message: "Please login to a Facebook account to share.", preferredStyle: UIAlertControllerStyle.Alert)
                alert.addAction(UIAlertAction(title: "OK", style: UIAlertActionStyle.Default, handler: nil))
                self.presentViewController(alert, animated: true, completion: nil)
            }
        }
        let cancelButton = UIAlertAction(title: "Cancel", style: UIAlertActionStyle.Cancel) { (alert) -> Void in
            println("Cancel Pressed")
        }
        
        alert.addAction(twBtn)
        alert.addAction(fbBtn)
        alert.addAction(cancelButton)
        self.presentViewController(alert, animated: true, completion: nil)



<a href="http://opensource.org/licenses/MIT">MIT License</a>
