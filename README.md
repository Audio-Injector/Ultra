# Auto Setup

Coming soon !

# Manual Setup

Make sure you have a recent enough firmware which includes the Ultra 2 machine driver + cs4265 codec driver updates :

```
sudo rpi-update
```

Edit your /boot/config.txt file to disable dtparam=audio (the # below comments it out):
```
#dtparam=audio
```

Edit your /boot/config.txt file to enable the Ultra's device tree overlay :
```
dtoverlay=audioinjector-ultra
```  

# Manual Setup bash command script :
```
sudo rpi-update
# firstly disable PWM audio
sudo bash -c "sed -i \"s/^\s*dtparam=audio/#dtparam=audio/\" /boot/config.txt"
# now check to see the correct device tree overlay is loaded ...
cnt=`grep -c audioinjector-ultra /boot/config.txt`
if [ "$cnt" -eq "0" ]; then
  echo '# enable the AudioInjector.net sound card
  dtoverlay=audioinjector-ultra' >> /boot/config.txt
fi
```

# Hardware Assembly
A video showing how to assemble the Ultra 2 sound card :

[![Audio Injector Ultra 2 assembly video](https://ksr-ugc.imgix.net/assets/021/896/505/1ec8b145a3c9a519dcd3fc8f703b829d_original.jpg?ixlib=rb-1.1.0&w=680&fit=max&v=1531538985&auto=format&gif-q=50&q=92&s=8250699b5e636f4a57907524fc1e19cf)](https://www.youtube.com/watch?v=5aJgab891BE&feature=youtu.be "Audio Injector Ultra 2 assembly video")

Check out our other products :

http://audioinjector.net

https://shop.audioinjector.net
