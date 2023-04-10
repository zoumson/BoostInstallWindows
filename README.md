# Boost Installation in Windows System

Install c++ boost libraries in Windows and use them in Visual Studio IDE

1. Download
* [Download](https://www.boost.org/doc/libs/1_81_0/more/getting_started/windows.html#build-from-the-visual-studio-ide) `boost` compressed `zip` file, ` boost_1_81_0.zip`
* Extract the files in `Downloads` folder to the specified folder, `boost_1_81_0`

2. Folder management 
* Create an empty folder in the `C:` directory named `MyBoost` in "Program Files"(C:\"Program Files"\MyBoost)
* Copy all the files from `boost_1_81_0` in Download folder to the newly created folder `MyBoost`

3. Compilation 
* Click the Windows button and search for `x64 Native Tools Command Prompt`
* Change the directory to the Boost folder using the command `cd C:\"Program Files"\MyBoost`
* Run `bootstrap.bat` to compile the libraries 
```
C:\"Program Files"\MyBoost\bootstrap.bat
```
* Install the libraries inside the default folder `C:\Boost`
```
C:\"Program Files"\MyBoost\b2 install
```
* Install the libraries inside a customized folder `MyCustomPath`
```
b2 install --prefix=MyCustomPath
```
4. Visual studio

* Create a new `c++` project,  `ConsoleApp` with `Hello World` project as starting 
* Click on Project > Solution > Right click > Properties
* In configurations choose All Platforms (Win32/x64)
* C/C++, edit "Additional Include Directories" to add `C:\Boost\include\`boost_1_81`
* Linker, edit "Additional Library Directories" to add C:\Boost\lib
* Build and Run the sample code, replace the `Hello World` code with 
```
#include <boost/array.hpp>
#include <iostream>
    
using namespace std;
int main()
{
    boost::array<int, 10> arr
        = { { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 } };
    for (int i = 0; i < 10; i++) 
    {
        cout << "Zouma is a genius :" << arr[i] << "*"<< "\n";
    }
    return 0;
}
```
