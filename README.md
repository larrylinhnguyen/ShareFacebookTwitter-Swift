# ShareFacebookTwitterSwift
Easy Copy and Paste code to add a sharing UIActionSheet to oyr Swift app


<b>INSTALLATION</b>

Step 1: Add the Social Framework to your App (General > Linked Frameworks and Libraries). <br>
Step 2: Add the UIActionSheetDelegate to you class declaration. <br>
Step 3: Create your IBAction. <br>
Step 4: Add the code: <br>

         let alert = UIAlertController(title: "Share", message: "Deel de PaasPop app", preferredStyle: UIAlertControllerStyle.ActionSheet)
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
