Download the zip-file rpi_cam_pub.zip onto your pc.

SSH into the rpi using powershell/command prompt

```ssh ubuntu@<RPI IP ADDR>```
Enter the password when prompted & say yes to any rsa fingerprint (if it is the first time connecting)

Create the folder for the rpi_cam

```mkdir ws_rpi/src```

Copy and unzip the zip flie into the rpi (using another powershell terminal)

```scp <PATH TO ZIP FILE> ubuntu@<RPI IP ADDR>:~/ws_rpi/src```

Switch back to the rpi terminal and unzip the file:

<code>
  cd ~/ws_rpi/src\n
  unzip rpi_cam_pub.zip
</code>

Ok, because the rpi does not seem to have sufficient memory to run the pkg, we need to use swap memory which utlises some of the local storage as memory. Please follow the instructions [here](https://www.codegrepper.com/code-examples/shell/add+swap+ubuntu+20.04)

Return to the workspace directory run the package:


<code>
  cd ~/ws_rpi\n
  catkin_make -j1
</code>


