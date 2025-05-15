
* Ensure target app is running and also frida server is runnign then Identify the Package Name:

``` bash 
frida-ps -Ua
```

* frida trace
```bash
frida-trace -U -j 'io.hextree.*!*' FridaTarget
```
- installing frida server

```bash
unxz frida-server-16.7.19-android-x86_64.xz
mv frida-server-16.7.19-android-x86_64 frida-server
adb push frida-server /data/local/tmp
adb shell "chmod 755 /data/local/tmp/frida-server"
adb shell "/data/local/tmp/frida-server &"

#onliner
unxz -c frida-server-16.7.19-android-x86_64.xz > frida-server && adb push frida-server /data/local/tmp/ && adb shell "chmod 755 /data/local/tmp/frida-server && /data/local/tmp/frida-server &"

```

- objection hooking
`objection --gadget <package_name> explore`
`android sslpinning disable`
* Objection Exploration:

Once you're in the Objection REPL, you can use various commands to explore the app:

- `android hooking list classes`: Lists classes within the package.
- `android hooking list class_methods <class_name>`: Lists methods of a specific class.
- `android hooking watch class <class_name>`: Hooks a class to intercept method calls.
- `android hooking set breakpoint <class_name>.<method_name>`: Sets a breakpoint on a specific method.
- `android hooking trace function <class_name>.<method_name>`: Traces function calls and arguments.
- `android hooking set return_value <class_name>.<method_name> <value>`: Modifies the return value of a function.
- `android hooking disable`: Disables all hooks.
- `android hooking enable`: Enables all hooks.

* command to screenrecord the application
- `adb shell screenrecord --bit-rate 8000000 /sdcard/my_recording.mp4`

- `adb pull /sdcard/my_recording.mp4 `

