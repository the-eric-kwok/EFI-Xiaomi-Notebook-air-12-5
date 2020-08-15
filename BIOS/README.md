# README

### Tutorial to modify BIOS  

* I would like make a script or others methods but this tutorial is like OpenCore method.  

* Soon I upload a csv with all xiaomi laptops that I have on the github with hexadecimal variables to unlock CFG Lock, MC Lock, SpeedShift and more.    

* ## THIS TUTORIAL IS AN EXAMPLE, NOT GET THE VALUES AND VARIABLES

## First of all, I am not responsible for what can happen to your laptop  

1- Boot with OpenCore  
2- Click on space key on keyboard.  
3- Select partition Mod Grub Shell  
4- Write a command method, for example to unlock cfg lock: `setup_var 0x3C 0x00`  **Again, this is an example, do not use this value!**
Other example, SpeedShift to enable: `setup_var 0xB 0x01`  **This is an example, do not use this value!**
it is possible that for example, SpeedShift is enabled before.     

* ### Explanation:  

  setup_var is to call method function.  
  0x3C is the location memory on bios that is variable CFG Lock.    
  0x00 is to disable and 0x01 is to enable. I put the example here.  
  (default) is how the variable is when you install a BIOS, that is, by the manufacturer.  

One Of: CFG Lock, VarStoreInfo (VarOffset/VarName): 0x3C, VarStore: 0x3, QuestionId: 0x146, Size: 1, Min:   0x0, Max 0x1, Step: 0x0 {05 91 8A 02 8B 02 46 01 03 00 3C 00 10 10 00 01 00}  
0x149413 			One Of Option: Disabled, Value (8 bit): 0x0 {09 07 04 00 00 00 00}  
0x14941A 			One Of Option: Enabled, Value (8 bit): 0x1 (default) {09 07 03 00 30 00 01}  
0x149421 		End One Of {29 02}  

5- You can set up more variables to modify Bios. If you want exit, you must write reboot and click enter on keyboard.  

6- You can verify the CFG is unlocked or other parametres like SpeedShift is enabled in hackintool, section Utilities and press button Get AppleIntelInfo.  

# Disclaimer!

Use these files and this howto at your own risk. I'm not responsible in any way for lost data, damage to software or hardware or anything else that might go wrong. This works for me but might not for you.



**You are warned about the risk of flashing you BIOS!**

If you do wanna flash it, double click that TR100A09.zip and run that exe file under Windows or Windows PE. 

After unlocking you CFG lock, you can uncheck *AppleCpuPmCfgLock* and *AppleXcpmCfgLock* in OC/config.plist - Kernel. But please back up **before** you do so! If you didn't unlock it successfully you will be blocked out of macOS!

