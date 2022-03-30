# tensorflow in Apache Zeppelin
How I got tensorflow running in Apache Zeppelin running on Fedora 35

First - Install the correct version of Python that will work with Apache Zeppelin. I haved found that python 3.7 works well. Other versions of python can be installed. For example, on my Fedora 35 system I have python 3.10, 3.9 and 3.7 installed. I have /usr/bin/python in $PATH but this is a symbolic link to /usr/bin/python3 which in turn is a symbolic link to /usr/bin/python3.10. This is the default python version that will be used when executing python without any trailing numbers.  To use python version 3.7, add "3.7" to the end of the python executable as seen in the examples below.
```
sudo dnf install -y python3.7
```
Next - Ensure pip will work in python 3.7 and then install pip in python 3.7
```
python3.7 -m ensurepip
python3.7 -m pip install
```
Next - Install matplotlib, numpy and tensorflow
```
python3.7 -m pip install matplotlib
python3.7 -m pip install numpy
python3.7 -m pip install tensorflow
```
Next - Configure Zeppelin to use python 3.7.x
Click on the user name in the upper right hand corner of the zeppelin page and then choose "Interpreter" from the drop down list:

![image](https://user-images.githubusercontent.com/19158771/160841566-e73e4db6-f4d0-4944-9cb9-c9d2fe7f7e96.png)

In the Interpreter page, scroll down to the Python section and click the "Edit" button in the top right corner of the section. Change the value of zeppelin.python from "python" to "python3.7" and then click the "Save" button in the bottom left corner of the python section:

![image](https://user-images.githubusercontent.com/19158771/160842452-388cca15-515d-4640-9c37-baacbd330f91.png)

Now, you should be able to import matplotlib, numpy and tensorflow into your python code in Zeppelin. 

An alternative would be to run IPython in a docker or podman container as per [these instructions](https://zeppelin.apache.org/docs/latest/interpreter/python.html#ipython-interpreter-pythonipython-recommended).
