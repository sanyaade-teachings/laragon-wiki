With Laragon, adding another Node.js version is very easy.

1. Download Node.js Windows Binary (.zip) (suppose you want to use **Node.js version 10.5.0 64-bit**):
<https://nodejs.org/dist/v10.5.0/node-v10.5.0-win-x64.zip>

2. Extract the downloaded to: C:\laragon\bin\nodejs\node-v10.5.0 (If there is no **nodejs** dir in **bin**, just create it and you can set name **node-v10** if you prefer)
```text
C:\laragon
-- bin
   -- nodejs
      -- node-v10.5.0
      -- .............
```

3. Close Laragon, then open it again (to refresh the Menu). Select the version at: Laragon **Menu > Node.js > Version > node-v10.5.0**

Now, open Terminal (**Ctrl - Alt - T**) and type:

```shell
node --version
```

You should see something like that: **v10.5.0**

```shell
npm --version
```

You should see something like that: **6.1.0**

Congrats! Your Laragon now has Node.js!

Very easy huh. That's all forks!

### Source

Since this article was originally written, node and NPM have moved along quite a bit, of course.
You can search through the latest releases of node on <https://nodejs.org/dist/>