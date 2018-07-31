# add-Lena-to-`scipy.misc`
Since the latest version of scipy (1.1.0) removes Lena from misc, this repository offers simple guides to get her back into `scipy.misc`. Long story short, here are several steps to take:

- find your directory path of `scipy.misc` :

  you can get that by running python script:

  ```python
  import scipy.misc
  print(scipy.misc.__file__)  
  ```

  or you can directly run the command in your terminal (if you downloaded `scipy` from `pip`) to find where `scipy` is located first:

  ```bash
  pip show scipy | grep "Location"
  ```

- feel free to download `lena.dat` from this repository and move it into the directory where  `scipy.misc` is in.

- modify the contents in `common.py` in this directory:

  - append `"lena"` to `__all__` list, which can be seen from the top several lines.

  - add the following definition of function `lena()`

    ```python
    def lena():
        import pickle, os
        fname = os.path.join(os.path.dirname(file),'lena.dat')
        f = open(fname,'rb')
        lena = array(pickle.load(f))
        f.close()
        return lena
    
    ```

  - save this file.
