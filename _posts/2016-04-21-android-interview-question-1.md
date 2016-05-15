---
layout: post  
title: Compiled Android Interview Questions  
tags: [android, professional, hiring, interview, development]  
fb-img: http://d287f0h5fel5hu.cloudfront.net/blog/wp-content/uploads/2014/02/Android-Interview-Questions.jpg
published: false

---

<br>

I have been through a major Job search saga for mid-level Android Developer position in Germany during end of last year. It was exhausting but a very interesting & exhilarating experience as well because I learned a lot about hiring processes. It was my first hands-on experience with head hunters and recruiting agencies (mostly from UK) regarding tech positions. I also tried different techniques on how to manage applications and to track interviews and their status. I would share about my approaches and learnings about hiring process some other time. This post is more focused on technical questions I faced during my interviews. I used to document them once done with an interview and it helped me for the coming ones. Most of the questions would be well known and expected by Android Devs but still sometimes it's just convenient to go through a list of them during preparation. 

I would like to re-iterate that I applied for mid-level Android Dev position so questions included are all related to Java and Android domain.

# Questions related to Java 

### Question #1

**Explain the code shown below line by line.**

	public class ListHelper<E> {
		
		private final List<E> list = new ArrayList<E>();

		public synchronized void putIfAbsent(E item){
    		if (!list.contains(item)){
        		list.add(item);
    		}
		}

		public List<E> getList(){
    		return list;
    	}
    }
    
			
Hints: 

* What are *Generic* classes?
* How specifying *final* would effect object?
* Is it ok to use *List* on left side and not *ArrayList*?
* Why *synchronized* keyword used?
* Can *ListHelper* object have two different copies of member *list*?


### Question #2

**What are common functions of Java *Object* class and what do you know about *Object* class?**

Hints:

* The Object class, in the java.lang package, sits at the top of the class hierarchy tree.
* Every class is a descendant, direct or indirect, of the Object class.
* Briefly describe the purpose and use of common functions including clone(), equals(), hashcode(), getCLass(), finalize() and toString().

### Question #3

**What is Information Hiding and give example?**

Hints:

* Explain How Information Hiding is achieved in Object Oriented Programming.
* Should be able to explain Abstraction, Encapsulation and difference between them.

### Question #4

**What are Access Specifiers and what is default one?**

Hints:

* The default is package private. (Trust me, not many devs can actually recall this!)
* This [Stackoverflow answer](http://stackoverflow.com/a/3530161/1016544) explains it very well.


### Question #5

**What is Reflection in Java and why would you use it?**

Hints:

* Reflection is often used as part of software testing, such as for the runtime creation/instantiation of mock objects.
* In Java, Reflection can be used to override member accessibility rules. For example, reflection makes it possible to change the value of a field marked "private" in a third-party library's class.


### Question #6

**What is Inheritance, Diamond problem and difference between Inheritance and Sub-typing?**

Hints:

* You can read about Diamond Problem [here](http://www.programmerinterview.com/index.php/java-questions/java-diamond-problem/).
* Subsequent question can ask about how Diamond problem gets influenced with The default interface method capability in Java 8.
* Normally “extends” means Inheritance and “implements” means Subtyping.

	
### Question #7

**What is Static and when to use and when not to use ?**

Hints:

* It belongs to the class, not any particular object of that class. Static is class level variable, which is common and only one copy exists for all instances of that class. 
* One common use of static is to create a constant value that's attached to a class. The only change we need to make to the above example is to add the keyword final in there.
* Why evil? It violates the principle that data is encapsulated in objects, Code can’t be easily unit tested, When a thread dies, a static object doesn’t get reset or garbage collected.


### Question #8

**How to implement concurrency in Java?**

Hints:

* The sole purpose of using _Synchronized_ keyword is to only allow one thread at a time into a particular section of code.
* Additionally, _Volatile_ is used to indicate that a variable's value will be modified by different threads.

### Question #9

**How to make Java code thread safe? Give some suggestions.**

Hints:

* Immutable objects are by default thread-safe because there state can not be modified once created.
* Read only or final variables in Java are also thread-safe in Java.
* Locking is one way of achieving thread-safety in Java.
* In order to avoid thread-safety issue minimize sharing of objects between multiple thread.
* Using Synchronized keyword.

### Question #10

**Difference between Boolean and boolean?**

Hints:

* boolean is a java primitive type whereas Boolean is an object/reference type that wraps a boolean.
* Read about Boxing and Unboxing
* When can a Boolean be appropriately used? Read Lazy Loading.






# Questions related to Android 

