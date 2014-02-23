// English
This is a class for operating *.ini configure file.
It's very convenient to get or set data from ini files (by using CString).
There are just some simple method, and you can change and add your own methods.
The class only can be used in Visual C++.
File Map:
	Ini.h: the declare of CIni class.
	Ini.h: define methods of CIni class
	Demo.h: show how to ues the class

//// If you have any problem, please contect Aran (gchinaran@gmail.com)


// ����
����һ������ini�����ļ�����,��ʵ�Ƕ�VC�е�GetPrivateProfileString��WritePrivateProfileString�����·�װ��Aran��CString����ϲ������
ע�ص��Ƿ���ͼ�࣬û�����������ԣ����д�Ҫ�󣬿������޸ģ���
����ӦӦ����Visual C++ ������

����������ο�Ini.h�ļ���
������ʵ��ΪIni.cpp�ļ�������ļ�����û��ע�ͣ���
ʹ��ʾ����Demo.cpp�ļ�

//// �������⣬����ϵ��Ȼ gchinaran@gmail.com


///////// Demo.h
/*
* show how to used the ini operate methods
*/

#include "Ini.h"
#include <iostream>
using namespace std;

int main(void)
{
	CIni cIni("D:/iniTest.ini");

	// set values
	CString sNode = "TestNode"; // node name
	cIni.SetInt(sNode, "IntKey", -123);
	cIni.SetDouble(sNode, "DoubleKey", 123.0987);
	cIni.SetFloat(sNode, "FloatKey", -56.2f);
	cIni.SetCstring(sNode, "CStringKey", CString("hello, ini!"));
	cIni.SetPchar(sNode, "PcharKey", "Can you feel me?");

	// get key values
	cout << "show key values:" << endl;
	cout << "IntKey = " << cIni.GetInt(sNode, "IntKey") << endl;
	cout << "DoubleKey = " << cIni.GetDouble(sNode, "DoubleKey") << endl;
	cout << "FloatKey = " << cIni.GetFloat(sNode, "FloatKey") << endl;
	cout << "CStringKey = " << cIni.GetCString(sNode, "CStringKey") << endl;
	CString str = cIni.GetCString(sNode, "PcharKey");
	char *pch = (LPSTR)(LPCTSTR)str;
	cout << "PcharKey = " << pch << endl;

	return 0;
}