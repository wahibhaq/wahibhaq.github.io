---
layout: post  
title: Compiled Android Interview Questions  
tags: [android, professional, hiring, interview, development]  
fb-img: http://d287f0h5fel5hu.cloudfront.net/blog/wp-content/uploads/2014/02/Android-Interview-Questions.jpg
published: true

---

<br>

I have been through a major Job search saga for Android Developer position in Germany in 2015. It was exhausting but a very interesting & exhilarating experience as well. I had to revise basics and grasp more deeper understanding of fundamental topics. This post is more focused on technical questions I faced during my interviews. I used to document them once done with an interview and this practise helped me for the upcoming ones. Most of the questions would be well known and expected by Android Devs but still sometimes it's just convenient to go through few of them during preparation. 

I would like to re-iterate that I applied for mid-level Android Dev position so questions included are all related to Java and Android domain. More importantly, it's practically impossible to cover all potential quetions so just sharing those which I can remember while writing this post. A lot has changed since then as Android like any other Technology is always evolving :)

&nbsp;

&nbsp;

# Questions related to Java 

&nbsp;

#### Explain the code shown below line by line.

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
    
			
**Hints:** 

* What are *Generic* classes?
* How specifying *final* would effect object?
* Is it ok to use *List* on left side and not *ArrayList*?
* Why *synchronized* keyword used?
* Can *ListHelper* object have two different copies of member *list*?

&nbsp;

#### What are common functions of Java Object class and what do you know about Object class? 
<br>
**Hints:**

* The *Object* class, in the java.lang package, sits at the top of the class hierarchy tree.
* Every class is a descendant, direct or indirect, of the *Object* class.
* Briefly describe the purpose and use of common functions including clone(), equals(), hashcode(), getCLass(), finalize() and toString().

&nbsp;

#### What is Information Hiding and give example?
<br>
**Hints:**

* Explain How Information Hiding is achieved in Object Oriented Programming.
* Should be able to explain Abstraction, Encapsulation and difference between them.

&nbsp;

#### What are Access Specifiers and what is default one?
<br>
**Hints:**

* The default is package private. (Trust me, not many devs can actually recall this!)
* This [Stackoverflow answer](http://stackoverflow.com/a/3530161/1016544) explains it very well.

&nbsp;

#### What is *Reflection* in Java and why would you use it?
<br>
**Hints:**

* Reflection is often used as part of software testing, such as for the runtime creation/instantiation of mock objects.
* In Java, Reflection can be used to override member accessibility rules. For example, reflection makes it possible to change the value of a field marked "private" in a third-party library's class.

&nbsp;

#### What is Inheritance, Diamond problem and difference between Inheritance and Sub-typing?
<br>
**Hints:**

* You can read about Diamond Problem [here](http://www.programmerinterview.com/index.php/java-questions/java-diamond-problem/).
* Subsequent question can ask about how Diamond problem gets influenced with The default interface method capability in Java 8.
* Normally “extends” means Inheritance and “implements” means Subtyping.

&nbsp;

#### What is Static and when to use and when not to use ?
<br>
**Hints:**

* It belongs to the class, not any particular object of that class. Static is class level variable, which is common and only one copy exists for all instances of that class. 
* One common use of static is to create a constant value that's attached to a class. The only change we need to make to the above example is to add the keyword final in there.
* Why evil? It violates the principle that data is encapsulated in objects, Code can’t be easily unit tested, When a thread dies, a static object doesn’t get reset or garbage collected.

&nbsp;

#### How to implement concurrency in Java?
<br>
**Hints:**

* The sole purpose of using _Synchronized_ keyword is to only allow one thread at a time into a particular section of code.
* Additionally, _Volatile_ is used to indicate that a variable's value will be modified by different threads.

&nbsp;

#### How to make Java code thread safe? Give some suggestions.
<br>
**Hints:**

* Immutable objects are by default thread-safe because there state can not be modified once created.
* Read only or final variables in Java are also thread-safe in Java.
* Locking is one way of achieving thread-safety in Java.
* In order to avoid thread-safety issue minimize sharing of objects between multiple thread.
* Using Synchronized keyword.

&nbsp;

#### Difference between Boolean and boolean?
<br>
**Hints:**

* boolean is a java primitive type whereas Boolean is an object/reference type that wraps a boolean.
* Read about *Boxing* and *Unboxing*
* When can a Boolean be appropriately used? Read Lazy Loading.




&nbsp;

&nbsp;

# Questions related to Android 

&nbsp;

#### What is Activity, Fragment and their association?
<br>
**Hints:**

* You should know about the lifecycle and purpose of both.
* A fragment is an independent Android component which can be used by an activity. A fragment encapsulates functionality so that it is easier to reuse within activities and layouts.
* Possible to have a fragment without UI? Read about Headless Fragments and their usecase
* Fragment transaction refers to the operation with fragments via fragment manager. either adding, removing or replacing a fragment in the fragment holder. 

&nbsp;

#### What is *Handler* used for and why? other alternatives?
<br>
**Hints:**

* A handler allows you to post runnables to execute on a specific thread. For instance, asynchronous code in a runnable can run on a threadpool, or a dedicated thread.
* In the event that the code executing in a thread needs to interact with the user interface e.g animation, it must do so by synchronizing with the main UI thread. This is achieved by creating a handler within the main thread, which, in turn, receives messages from another thread and updates the user interface accordingly. 
* Few of the ways to have the non-UI thread send UI update requests to be executed on the UI thread.
	* Use runOnUiThread( ) method call
	* Use post( ) method call
	* Use the Handler framework
	* Use a Broadcasts and BroadcastReceiver (optionally with 	  LocalBroadcastManager)
	* Use an AsyncTask’s onProgressUpdate( ) method
 

&nbsp;

#### What is ANR and how do you prevent it?
<br>
**Hints:**

* Long running work should never be done on main UI thread and instead your application must create other threads and put such work on non-UI threads.
* You can create and start your own java.lang.Thread.  You can create and start an AsyncTask – Android’s own thread simplification mechanism.
* Problem ? non-UI thread can’t communication with the UI thread.

&nbsp;

#### Describe MVP pattern for Android and it's benefits
<br>
**Hints:**

* MVP is not an architectural pattern, it’s only responsible for the presentation layer.
* View is a layer that displays data and reacts to user actions. On Android, this could be an Activity, a Fragment, an android.view.View or a Dialog.
Model is a data access layer such as database API or remote server API.
Presenter is a layer that provides View with data from Model. Presenter also handles background tasks.
* MVP is a way to separate background tasks from activities/views/fragments to make them independent of most lifecycle-related events.
* Application becomes simpler, overall application reliability increases up to 10 times, application code becomes shorter, code maintainability becomes better and  significantly easier to test code.
* You'll find many amazing resources but [this](http://macoscope.com/blog/model-view-presenter-architecture-in-android-applications/) can give a good start.

&nbsp;

#### How to find the sections of app or actions which are not smooth from UX perspective? what are most common scenarios to test?
<br>
**Hints:**

* *Allocation Tracker* in Memory Monitor is a good handy tool for this which helps in tracking memory allocation.
* It can be useful not only for looking at specific uses of memory, but also to analyze critical code paths in an app such as scrolling & helps in improving the overall smoothness of the UI.
* Possible scenarios can be rotating screens mutiple times in different activity states to detect if Activty, Context or View object causing leaks. Also try to switch between apps e.g navigate to home screen and come back again.

&nbsp;

#### What is an improved way for implementing List Views offered by Android and why?
<br>
**Hints:**

* RecyclerView is an advanced form introduced in Lollipop.
* It allows to reuse(recycle) views depending on which one is visible to the user. A view previously used to display data for a specific adapter position may be placed in a cache for later reuse to display the same type of data again later. This can drastically improve performance by skipping initial layout inflation or construction.

&nbsp;

#### How would you implement your own drawing in a Custom View?
<br>
**Hints:**

* By extending the View class or one of its subclasses you can create your custom view.
* For drawing view use the onDraw() method. In this method you receive a Canvas object which allows you to perform drawing operations on it, e.g. draw lines, circle, text or bitmaps.
* If the view should be re-drawn you call the invalidate() method which triggers a call to the onDraw() method of this view.

&nbsp;

#### What are different types of Services?
<br>
**Hints:**

* Started Service : Started services are launched by other application components (such as an activity or even a broadcast receiver) and potentially run indefinitely in the background until the service is stopped, or is destroyed by the Android runtime system in order to free up resources.
* IntentService : The IntentService class is a convenience class (subclassed from the Service class) that sets up a worker thread for handling background tasks and handles each request in an asynchronous manner. Once the service has handled all queued requests, it simply exits.
* Bount Service : A bound service is similar to a started service with the exception that a started service does not generally return results or permit interaction with the component that launched it. A bound service, on the other hand, allows the launching component to interact with, and receive results from, the service.

&nbsp;

#### How would you perform standard Asynchronous operations in Android?
<br>
**Hints:**

* Normally you can use Loader or *AsyncTask*. Loader performs asynchronous loading of data. While Loaders are active they should monitor the source of their data and deliver new results when the contents change. AsynTask is used to perfrom time consuming , short duration operation so that main UI thread don’t get the burden.
* In more advanced approaches, RxJava is used to perform various kinds of Async operations. 

&nbsp;

#### Is there a more optimized alternative available for HashMap in Android?
<br>
**Hints:**

* Yes, it's called SparseArrays.
* Why? SparseArrays map integers to Objects. Unlike a normal array of Objects, there can be gaps in the indices. It is intended to be more memory efficient than using a HashMap to map Integers to Objects, both because it avoids auto-boxing keys and its data structure doesn't rely on an extra entry object for each mapping. 

&nbsp;

#### How can we avoid memory usage in our apps?
<br>
**Hints:**

* Avoid using enum and non-static inner classes.
* Use SparseArrays instead of HashMaps.
* Take care with using ‘abstraction’ design matter because as a side effect it might cause more code to execute.
* If using Services, it shouldn't run more than required & background service process must not touch any UI; otherwise, the memory allocation will be doubled or tripled.

&nbsp;

#### How to avoid memory leaks?
<br>
**Hints:**

* Remember to call unregisterReceiver() after calling registerReceiver().
* Reference to an activity should have the same life cycle as the activity itself and take special care in case of change in screen orientation.
* In an Activity. In Java, non-static anonymous classes hold an implicit reference to their enclosing class. Instead use static inner class and make a weakreference to activity.
* Be very careful when using Threads.
* Do your best to make extended Runnables static, if they must be inner classes.
Runnables has to know about it’s container so holds reference to Activity if defined in Activity or View. After orientation(Activity kill!) it retains that reference because it runs on a separate thread and not dependent on the lifecycle of Activity. thus activity is not garbage collected.

&nbsp;

#### Ever heard of Dependency Injection design patter? What is it about? Have you used it via any framework?
<br>
**Hints:**

* Dependency injection is basically providing the objects that an object needs (its dependencies) instead of having it construct them itself.
* It's a very useful technique for testing, since it allows dependencies to be mocked or stubbed out.
* Interviewer wants you to say Dagger. Explore Dagger2 if you don't know.

&nbsp;

#### In Unit Testing, what is referred by Unit & Testing? What is Test Driven Development (TDD) & what are advantages?
<br>
**Hints:**

* A unit is a method that does one thing and one thing only. 
* A test provides a useful assertion of the correctness of the unit. 
* TDD  can be defined as such Write a failing unit test, Make the unit test pass & Refactor.
* Advantages to a test-driven approach is that the process instills the discipline of unit testing, writing the unit tests first, enforces a kind of architecture and clean code.

&nbsp;

#### What are the options of 3rd party libs/frameworks do we have or the ones you have used for various tasks in app development?
<br>
**Hints:**

* UI Tests: Espresso
* Unit Testing: Robo Electric
* Networking: Volley
* Binding UI with Java: ButterKnife
* JSON parsing: Jackson
* Async Communication between components: EventBus, RxJava
* Image downloading and caching library: Picasso
* Mocking unit tests: Mockito
* Dependency Injection: Dagger2
* API Integration: OkHttp, Retrofit

This [resource](https://github.com/codepath/android_guides/wiki/Must-Have-Libraries) lists down most commonly used libs.

P.S : Be prepared to explain the usecase of the ones you mention and technical questions related to them.

&nbsp;

#### How do you implement Internationalization for an app to be available in multiple countries?
<br>
**Hints:**

* Make multiple resource folders with language codes e.g res/values-de
* Define one language e.g English as fallback plan in res/values/strings.xml
* Suggest to have translations before starting implementing a UI. Better use a tool to make it efficient like Transifex.

&nbsp;

#### What are your favourite most common channels to keep yourself up-to-date with what's happening in Android ecosystem?
<br>
**Hints:**

* I have listed few of the most famous ones [here](https://github.com/wahibhaq/ultimate-resources-android-devs/blob/master/README.md#regular-updates-banter--articles).
* If you were not serious about it then maybe you should.

&nbsp;

&nbsp;

# Other Valuable Resources

* [Top 50 Android Interview Questions](http://www.itechaleart.com/2013/05/top-50-android-interview-questions_10.html)
* [Toptal Interview Questions](http://www.toptal.com/android/interview-questions)
* [Android Hiring Guide](http://www.toptal.com/android#hiring-guide)
* [SkillGun Q&A](http://skillgun.com/android/interview-questions-and-answers)
* [Top 10 Algorithms for Coding Interview](http://www.programcreek.com/2012/11/top-10-algorithms-for-coding-interview/)
* [Very good resource to revise](http://zeroturnaround.com/rebellabs/android-the-platform-the-framework-and-the-way-of-life/)
* [100 Android Questions & Answers](http://100androidquestionsandanswers.com)
* [Ultimate Resources for Android Devs](https://github.com/wahibhaq/ultimate-resources-android-devs)
* [How to pass a programmer interview](http://blog.triplebyte.com/how-to-pass-a-programming-interview)



























