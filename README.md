# GenericLocalPersistence

GenericLocalPersistence is a clean and easy-to-use code that is useful for integrating local storage like, 

* UserDefaults
* plist
* Keychain

## Installation

From CocoaPods
First, add the following line to your Podfile 

```bash
pod install 'GenericLocalPersistence', '~> 0.0.1’

pod 'GenericLocalPersistence', :git => 'https://github.com/Riddhi-mi/GenericLocalPersistence.git'
```


# Usage of UserDefault

import GenericLocalPersistence

### Set & Get value from User Default

```python
DefaultManager().saveValueInDefault(value: "TestValue", using: "TestKey")
let valueFetch:String = DefaultManager().getValue("TestKey") ?? ""
```

# Usage of Plist

import GenericLocalPersistence

### Set & Get value from plist file
Replace "userDetails" with custom name for creating plist file to store data 

```python
private let managerPlist = plistManager(named: "userDetails")
```

```python
managerPlist?.saveDatatoPlist(value: "TestString Value", using: "TestKey")
let stringValue :String = managerPlist?.getDictionary(key: "TestKey") ?? ""
```

## Usage of KeyChain
import GenericLocalPersistence

### Set & Get value from KeyChain file

```python
KeyChainManager()?.setPasscode(identifier: "com.appBundleID.password", passcode:textPassword?.text ?? "");
let passwordValue = KeyChainManager()?.getPasscode(identifier: "com.appBundleID.password") ?? ""

KeyChainManager()?.setPasscode(identifier: "com.appBundleID.email", passcode:textUserName?.text ?? "");
let userNameValue = KeyChainManager()?.getPasscode(identifier: "com.appBundleID.email") ?? ""

```

## NOTE
```python
Replace "com.appBundleID" with your project bundleID for KeyChain integration
Define the dataType in which you want to fetch the value and that’s the way you can get the stored value.
```



## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)
