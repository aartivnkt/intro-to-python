# Install docker desktop on your computer
https://docs.docker.com/desktop/

# Test docker installations

Type the following in your terminal
```bash
docker --version
docker run hello-world
```
# Run a pre-built image

When you run the command below in your terminal, the image `aartiv/intro-to-python-course` will be pulled.
You will get a URL of the type `http://127.0.0.1:8888/lab?token=XYZ...` that you can click
and open `jupyterlab`. The `-v` command mounts the directory where you issue the command from
onto the `/workspace` path in the container. So that means which ever directory you issue this command from,
all the files in that directory will be visible for you in `jupyterlab`

```bash
docker run -p 8888:8888 -v $(pwd):/workspace aartiv/intro-to-python-course
```

Note: The `-p 8888:8888` command refers to the port from the host computer that is exposed to the docker, in the order
 `host port: docker port`. If you get an error of the type `port is already allocated`, it usually means you have the command
running in a different terminal window. Try close that command using (Ctrl-C) on a Mac, or equivalent in windows. Alternately, try specifying a different
host port number (e.g. 8889 instead of 8888). See full command below:

```bash
docker run -p 8889:8888 -v $(pwd):/workspace aartiv/intro-to-python-course
```

# Run the pre-built image from class github repo

To view all the class materials, clone the class github repo. See `installations_github.md` file for details and set it up.

Run the same docker run command as above, from the `intro-to-python` directory.


# If issues running this image, build your own image
```bash
cd intro-to-python/class_1
docker build -t intro-to-python-course .
```

# Run the image
```bash
docker run -p 8888:8888 -v $(pwd):/workspace intro-to-python-course
```
