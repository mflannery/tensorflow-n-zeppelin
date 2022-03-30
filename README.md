# tensorflow in Apache Zeppelin
How I got tensorflow running in Apache Zeppelin running on Fedora 35

First - Install the correct version of Python that will work with Apache Zeppelin. I haved found that python 3.7 works well.
```
sudo dnf install -y python3.7
```
Next - Ensure pip will work in python 3.7
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
