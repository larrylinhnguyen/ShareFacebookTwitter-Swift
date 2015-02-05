# ShareFacebookTwitterSwift
Easy Copy and Paste code to add a sharing UIActionSheet to your Swift app.
This wil create a UIActionSheet with a share to Facebook and Twitter button.


<h3>INSTALLATION</h3>

Step 1: Add the Social Framework to your App (General > Linked Frameworks and Libraries). <br>
Step 2: Add the UIActionSheetDelegate to you class declaration. <br>
Step 3: Create your IBAction. <br>
Step 4: Add the code: <br>

         let alert = UIAlertController(title: "Share", message: "Share the app", preferredStyle: UIAlertControllerStyle.ActionSheet)
           let twBtn = UIAlertAction(title: "Twitter", style: UIAlertActionStyle.Default) { (alert) -> Void in
               if SLComposeViewController.isAvailableForServiceType(SLServiceTypeTwitter){
                 var twitterSheet:SLComposeViewController = SLComposeViewController(forServiceType: SLServiceTypeTwitter)
                twitterSheet.setInitialText("Deel de PaasPop app op twitter")
                self.presentViewController(twitterSheet, animated: true, completion: nil)
            } else {
                var alert = UIAlertController(title: "Account", message: "Log alstublieft in met twitter.", preferredStyle: UIAlertControllerStyle.Alert)
                alert.addAction(UIAlertAction(title: "Oke", style: UIAlertActionStyle.Default, handler: nil))
                self.presentViewController(alert, animated: true, completion: nil)
            }
        }
    
        let fbBtn = UIAlertAction(title: "Facebook", style: UIAlertActionStyle.Default) { (alert) -> Void in
            if SLComposeViewController.isAvailableForServiceType(SLServiceTypeFacebook){
                var facebookSheet:SLComposeViewController = SLComposeViewController(forServiceType: SLServiceTypeFacebook)
                facebookSheet.setInitialText("Deel de PaasPop app op Facebook")
                self.presentViewController(facebookSheet, animated: true, completion: nil)
            } else {
                var alert = UIAlertController(title: "Account", message: "Log alstublieft in met Facebook.", preferredStyle: UIAlertControllerStyle.Alert)
                alert.addAction(UIAlertAction(title: "Oke", style: UIAlertActionStyle.Default, handler: nil))
                self.presentViewController(alert, animated: true, completion: nil)
            }
        }
        let cancelButton = UIAlertAction(title: "Cancel", style: UIAlertActionStyle.Cancel) { (alert) -> Void in
            println("Cancel pressed")
        }
        
        alert.addAction(twBtn)
        alert.addAction(fbBtn)
        alert.addAction(cancelButton)
        self.presentViewController(alert, animated: true, completion: nil)



<a href="http://opensource.org/licenses/MIT">MIT License</a>
