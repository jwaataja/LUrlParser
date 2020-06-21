**Lightweight URL & URI parser (RFC 1738, RFC 3986)**

(C) Sergey Kosarevsky, 2015-2020

@corporateshark sk@linderdaum.com

http://www.linderdaum.com

http://blog.linderdaum.com

=============================

A tiny and lightweight URL & URI parser (RFC 1738, RFC 3986) written in C++.

=============================

Usage example:

	#include "LUrlParser.h"
	
	const auto URL = LUrlParser::ParseURL::parseURL( "https://John:Dow@github.com:80/corporateshark/LUrlParser" );

	if ( URL.isValid() )
	{
		cout << "Scheme    : " << URL.scheme_ << endl;
		cout << "Host      : " << URL.host_ << endl;
		cout << "Port      : " << URL.port_ << endl;
		cout << "Path      : " << URL.path_ << endl;
		cout << "Query     : " << URL.query_ << endl;
		cout << "Fragment  : " << URL.fragment_ << endl;
		cout << "User name : " << URL.userName_ << endl;
		cout << "Password  : " << URL.password_ << endl;
	}

=============================

To use the library in your project, the easiest way is to add it as a git
submodule. In the project root directory, run
```bash
git submodule add https://github.com/jwaataja/LUrlParser.git extern/LUrlParser
```

Then, in your `CMakeLists.txt` file, add
```cmake
add_subdirectory(${PROJECT_SOURCE_DIR}/extern/LUrlParser)
```

You can then link against the library with
```cmake
target_link_libraries(my_target PRIVATE LUrlParser)
```

=============================
