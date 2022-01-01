//# friend-function-and-friend-class
//friend function and friend class, oop c++
#include<iostream>
#include<string>

using  namespace std;
class teacher;
class student{
	int id;
	string name;
	public:
	//friend function declaration 
	friend int set_id(student s);
	friend string set_name(student s);
	//friend class declaration 

	friend class teacher;
	
	 student(){
	 	id=0;
	 	name=" ";}
	 	
}; 
	//friend function 
	 int set_id(student s){
		cout<<"Enter student ID :"<<endl;
		cin>>s.id;
		cout<<"ID = ";cout<<s.id<<endl;

		return s.id;
	}
	 string set_name(student s){
		cout<<"Enter student Name :"<<endl;
		cin>>s.name;
		cout<<"ID = ";cout<<s.name<<endl;
		return s.name;
		
	}
class teacher{
	public:
		void show_data(student s){
		set_id(s);
		set_name(s); 
			
		}
	
};
int main(){
	student s1;
	teacher t1;
	cout<<"Accessing data members through friend class :"<<endl;
	t1.show_data(s1);
	cout<<"Accessing data memebers through Friend function :"<<endl;
	set_id(s1);
	set_name(s1);
	
	return 0;
}
