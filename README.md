This project provides a `Python` script `show` for visualizing 3D image volume, tensor field, vector field, large number of curves, and meshes.

It can be useful for people who analyze medical images in `Matlab` but would like to visualize large data set efficiently elsewhere.

The basic work flow is to

    - save data in `Matlab` in `mat` format
    - run `show` in a terminal or in a `ipython` interpreter to visualize the data


## Install Mayavi 
- on windows via [Anaconda Python distribution](http://continuum.io/downloads)
    - download and install Anaconda
    - on windows cmd prompt or Anaconda Command Prompt: 

        ```
        > conda install mayavi
        ```
- on linux, search mayavi in software center 
- on mac, via [macports](https://www.macports.org/ports.php?by=name&substr=mayavi)

    ```bash
    sudo port install vtk +python35
    sudo port install py35-mayavi
    ```

## in matlab

```matlab
load('test_data')

savePaths4mayaviRGBchu('~/f', fibers)
saveTensorScalarSlices4mayavi('~/t', noise_free_data, 10)
saveImageVolum3d4mayavi('~/i', noise_free_data.intensity, 1)
saveVectors4mayavi('~/v', test_data, 1) % single color
```

## to use `show`
- on command line

    ```bash
    $ show -ft f.mat
    $ show -t t.mat
    $ show -i i.mat
    $ show -fl f.mat -i i.mat -t t.mat
    ```

- in ipython interpreter

    ```python
    In [1]: %run show_with_full_path -i i.mat

    ```
    
Note: user interaction with Mayavi window can be recorded as Python code, which could be useful for later use, e.g., creating other functions.
