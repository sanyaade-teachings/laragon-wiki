With Laragon, adding another Python version is very easy.

1.Download Python Zip package from my github repo:
   You can download **Python 2.7**:
   <https://github.com/leokhoa/laragon/releases/download/portable/python-2.7.13.zip>
   or **Python 3.6**:
   <https://github.com/leokhoa/laragon/releases/download/portable/python-3.6.1.zip>

2. Note that you can download and use both (just switch version). Suppose you download Python 2.7. Extract the downloaded to: C:\laragon\bin\python\python-2.7 (If there is no **python** dir in **bin**, just create it)
```text
C:\laragon
-- bin
   -- python
      -- python-2.7
      -- .............
```
3. Close Laragon, then open it again (to refresh the Menu). Select the version at: **Laragon Menu > Python > Version > python-2.7**
Now, open Terminal (Ctrl - Alt - T) and type:

```shell
python --version
```

you should see something like that: **Python 2.7.13**

```shell
pip --version
```

you should see something like that: **pip 9.0.1 ...............**

Congrats! Your Laragon now has Python!

Very easy huh. That's all forks!

### Latest Python

The zip version of Python from python.org does not include pip!

Download the Download the latest version of Python <https://www.python.org/downloads/>

When installing Python select custom install and choose **Customize install location** by clicking **Browse** and navigate to your laragon directory > bin > python, make folder **python-3.12** and select it:

![image](https://github.com/leokhoa/laragon/assets/40126936/195bed81-65ec-4cbc-8f42-5716cb1b7bce)

Laragon will then allow the versions to be switched.

<img width="503" alt="image" src="https://github.com/leokhoa/laragon/assets/40126936/01336b81-aea3-446e-9c36-ef159d63ab37">

![image](https://github.com/leokhoa/laragon/assets/40126936/e8a3262b-2dfe-478b-93f3-05e3d2378f22)

You can now switch versions to Python 3.12 and Laragon will automatically update the path:

![image](https://github.com/leokhoa/laragon/assets/40126936/65994f1f-8e5c-4741-a56c-22181d4ceeb9)

Note: You may need to close the Terminal and re-open the Terminal (**Ctrl - Alt - T**).

### Troubleshooting

If you have any problems check the **python.exe** is in the correct directory:

```sh
C:\laragon\bin\python\python-3.12\python.exe --version
Python 3.12.3
```

If **python.exe** isn't in the correct directory, check the structure. Use cut and paste to move the folder so it is the correct structure:


```text
C:\laragon  
   ----- bin  
      ---- python  
         ---- python-3.11
             ---- ......
             ---- python.exe  
             ---- ......
         ---- python-3.12
             ---- ......
             ---- python.exe  
             ---- ......
```

If this still fails, use the Windows add or remove programs to uninstall it, then use the latest Python installer to install it again.
