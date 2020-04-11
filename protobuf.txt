Protobuf native installation (10-50x faster for Python)

$ brew install --build-from-source --with-python3 -vd protobuf
(installs from source - got this from http://caffe.berkeleyvision.org/install_osx.html)

$ protoc --version
$ pip install protobuf==3.5.1 --install-option="--cpp_implementation"

($ pip install protobuf==3.5.1 --install-option="--cpp_implementation" may not work...)
