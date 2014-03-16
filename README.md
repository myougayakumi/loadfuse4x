# What is this?
Load "fuse4x.kext" kernel extension when OS X start.

# How to use?
Before using this script, you must install fuse4x.
(If you install s3fs at brew, fuse4x will be .)
% sudo cp -rfX /usr/local/Cellar/fuse4x-kext/$FUSE4X_VERSION/Library/Extensions/fuse4x.kext /System/Library/Extensions/
% sudo chmod +s /System/Library/Extensions/fuse4x.kext/Support/load_fuse4x
Please replace $FUSE4X_VERSION to fuse4x-kext installed.

Type following commands:
% plutil -convert binary1 net.myouga.loadfuse4x.plist
% sudo mv net.myouga.loadfuse4x.plist /Library/LaunchDaemons/
% sudo launchctl load -w /Library/LaunchDaemons/net.myouga.loadfuse4x.plist

You can check whether it'll be loaded.
% launchctl list | grep net.myouga.loadfuse4x

#References
http://qiita.com/isaoshimizu/items/1f894ffa682f6d0f6376
http://superuser.com/questions/47233/how-can-i-force-a-mac-os-x-kext-to-load-prior-to-login
