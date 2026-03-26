# Install docker desktop on your computer
https://docs.docker.com/desktop/

# Test docker installations

Type the following in your terminal
```bash
docker --version
docker run hello-world
```

# Clone the class github repo

To view all the class materials, clone the class github repo. See `installations_github` file for details and set it up.
Make sure you are in the `intro-to-python` github repo directory, before going forward to the other steps listed below. You
can ensure that by running the command below:

```bash
cd intro-to-python
```

# Run a pre-built image

Run this command in your terminal. Explanation is provided below.

```bash
docker run -p 8888:8888 -v $(pwd):/workspace aartiv/intro-to-python-course
```

When you run the command above in your terminal, the image `aartiv/intro-to-python-course` will be pulled.
You will get a URL of the type `http://127.0.0.1:8888/lab?token=XYZ...` that you can copy (right-click -> copy) and paste into a browser window 
to open `jupyterlab`. Make sure to not cancel the `docker run..` command in the terminal during copy-paste!

The `-v` command mounts the directory where you issue the command from
onto the `/workspace` path in the container. So that means which ever directory you issue this command from,
all the files in that directory will be visible for you in `jupyterlab`

Note: The `-p 8888:8888` command refers to the port from the host computer that is exposed to the docker, in the order
 `host port: docker port`. If you get an error of the type `port is already allocated`, it usually means you have the command
running in a different terminal window. Try close that command using (Ctrl-C) on a Mac, or equivalent in windows. Alternately, try specifying a different
host port number (e.g. 8889 instead of 8888). See full command below:

```bash
docker run -p 8889:8888 -v $(pwd):/workspace aartiv/intro-to-python-course
```
If everything works successfully, you should see the class materials in jupyterlab. Verify against gitub. Example `class_1` files listed in jupyterlab should match `https://github.com/aartivnkt/intro-to-python/tree/main/class_1`.

# If issues running the pre-built image, build your own image

This section is for those who had issues running the pre-built image. This is mostly those using Windows OSX, or incompatible Mac OS.

In your terminal (git bash if using windows), you need to first change directory to `class_1` in the github repo `intro-to-python` that you cloned. See instructions below:

```bash
cd class_1
docker build -t intro-to-python-course .
```

## Run the image

Following command is for Windows

```bash
docker run -p 8888:8888 -v "$(pwd -W):/workspace" intro-to-python-course
```
This will show you a link of the type `http://127.0.0.1...`. Right click it to copy, and paste in a browser window. Make sure to not cancel this command in the terminal (Ctrl-C)!
Running it in a browser should show you all the materials in the `class_1` directory. Verify by checking against github `https://github.com/aartivnkt/intro-to-python/tree/main/class_1`.

For Mac OSX, run the following command:

```bash
docker run -p 8888:8888 -v $(pwd):/workspace intro-to-python-course
```

# Token authentication is enabled page
If you see a "Token authentication is enabled" page from jupyter, try the following:

At the top of the page, there is a `Password or token:` field, with a box to type this in, along with a `Log in` button. Type the token in there. You can get the token from the URL that comes up in your terminal. See example below. You will need to replace "XYZ..." with the actual value in your URL.

http://127.0.0.1:8888/lab?token=XYZ....

Copy the token value (the `XYZ..` part) by right-click-> copy. Leave the command running in the terminal, ensure it is not killed by Ctrl-C! Paste the token value in the box and hit "Log in" to authenticate.

If you still get errors like "invalid credentials", go to Docker Desktop and delete all the containers that are running to start from a clean slate. Then re-run the following command:

```bash
docker run -p 8888:8888 -v $(pwd):/workspace aartiv/intro-to-python-course
```

# Issues with mounting the right files in docker

If you don't see the right files mounted in jupyterlab, go to Docker Desktop and delete all the containers that are running to start from a clean slate. Then re-run the following command:

```bash
docker run -p 8888:8888 -v $(pwd):/workspace aartiv/intro-to-python-course
```
If you are still unable to see them, some system-specific changes may be needed to ensure $(pwd) is expanded correctly. You could force jupyter to start in `/workspace` by running the command below:

```bash
docker run -p 8888:8888 -v "$PWD:/workspace" -w /workspace aartiv/intro-to-python-course
```
# What to do before each class

Before each class, you need to "pull" the latest changes from the class github and run the `docker run` command that works for you.

```bash
cd intro-to-python
git pull origin main
docker run.... # replace with the command that works for you
```


