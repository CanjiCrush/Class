# cpp  string類別(class)及其方法實測:

>* http://www.cplusplus.com/reference/string/

>* http://www.cplusplus.com/reference/string/string/

>* https://www.geeksforgeeks.org/c-string-class-and-its-applications/

# cpp  string類別(class)的方法:

>* length()
>* size()
>* at(2)
>* front()
>* back()
>* begin() 
>* end()
>* replace()
>* find()

# Example:
```
// C++ program to demonstrate various function string class
#include <bits/stdc++.h>
using namespace std;

int main()
{
	// various constructor (建構子) of string class (不同的建構子)

	// initialization by raw string
	string str1("first string"); 在第一個字串中放入 first string

	// initialization by another string  //使用字串物件
	string str2(str1); 在第二個字串中放入物件第一字串=first string

	// initialization by character with number of occurence
	string str3(5, '#'); 在第三字串中放入指定數值5，指定字元#

	// initialization by part of another string
	string str4(str1, 6, 3); // from 6th index (second parameter) 在第四字串中放入指令，此指令為從第一字串的第六個字元開始取3位
							// 6 characters (third parameter)

	// initialization by part of another string : iteartor version
	string str5(str2.begin(), str2.begin() + 5); 在第五字串中放入指令，此指令為從第二字串第一個字元開始取5位

	cout << str1 << endl;  // 會輸出 first string
	cout << str2 << endl;  // 會輸出 first string
	cout << str3 << endl;  // 會輸出 #####
	cout << str4 << endl;  // 會輸出 str
	cout << str5 << endl;  // 會輸出 first

	// assignment operator
	string str6 = str4; // 會計算第四字串之內容的總長度

	// clear function deletes all character from string
	str4.clear(); // 會將第四字串之內容清除以#呈現

	// both size() and length() return length of string and
	// they work as synonyms
	int len = str6.length(); // Same as "len = str6.size();"

	cout << "Length of string is : " << len << endl;

	// a particular character can be accessed using at /
	// [] operator
	char ch = str6.at(2); // Same as "ch = str6[2];"


	cout << "third character of string is : " << ch << endl;

	// front return first character and back returns last charcter
	// of string

	char ch_f = str6.front(); // Same as "ch_f = str6[0];"
	char ch_b = str6.back(); // Same as below
							// "ch_b = str6[str6.length() - 1];"

	cout << "First char is : " << ch_f << ", Last char is : "
		<< ch_b << endl;

	// c_str returns null terminated char array version of string
	const char* charstr = str6.c_str();
	printf("%s\n", charstr);

	// append add the argument string at the end
	str6.append(" extension");
	// same as str6 += " extension"

	// another version of appends, which appends part of other
	// string
	str4.append(str6, 0, 6); // at 0th position 6 character

	cout << str6 << endl;
	cout << str4 << endl;

	// find returns index where pattern is found.
	// If pattern is not there it returns predefined
	// constant npos whose value is -1

	if (str6.find(str4) != string::npos)
		cout << "str4 found in str6 at " << str6.find(str4)
			<< " pos" << endl;
	else
		cout << "str4 not found in str6" << endl;

	// substr(a, b) function returns a substring of b length
	// starting from index a
	cout << str6.substr(7, 3) << endl;

	// if second argument is not passed, string till end is
	// taken as substring
	cout << str6.substr(7) << endl;

	// erase(a, b) deletes b character at index a
	str6.erase(7, 4);
	cout << str6 << endl;

	// iterator version of erase
	str6.erase(str6.begin() + 5, str6.end() - 3);
	cout << str6 << endl;

	str6 = "This is a examples";

	// replace(a, b, str) replaces b character from a index by str
	str6.replace(2, 7, "ese are test");

	cout << str6 << endl;

	return 0;
}
```
