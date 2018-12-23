# Sniper 7.1 Installation
Notice: The official website of Sniper has a guide of installation. However, it is out of date. It only fits old Sniper versions. If you choose Sniper 7.1, do not follow their instruction.  
# Environment  
Ubuntu 18.04  
Sniper 7.1  
gcc 7.3  
g++ 7  
# Installing
* Download Sniper 7.1 from their official website http://snipersim.org/w/Download  
* Download Pin kit 3.7 https://software.intel.com/en-us/articles/pin-a-binary-instrumentation-tool-downloads  
* Extract Pin into sniper/pin_kit  
$sudo apt-get install libc6-dev-i386  
$g++ --version, to get your_g++_version  
$sudo apt-get install g++-your_g++_version-multilib  
$sudo apt-get install lib32z1-dev  
$make  
* If make failed, there will be a notice for the missing part, install those missing part.  
* If "usr/bin/env: ‘python’: No such file or directory", check your environment. Usually, if your python version is higher, it cannot be detected. Use following command to install python  
$sudo apt-get install python-minimal  
# Test
$cd test/fft  
$make run  
# Bug fix 
* Sniper 7.1 has bugs for simulator large number of cores. Use patch to fix it. Patch is provided by Sniper Author.  
$patch -p1 < sniper-7.1-shmemperf-and-maxthreads-fix-v2.patch  
$make clean  
$make  
