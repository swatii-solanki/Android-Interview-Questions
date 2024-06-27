# Android-Interview-Questions
1. #### What is Activity ?
   An Activity is the part of the android components & it's the starting point of the application. An activity provides the window in which the app draws its UI.
   
2. #### Explain Activity Lifecycle 
   There are 7 states of the activity lifecycle
   
   **onCreate()** - this is the first callback which fires when the system first creates the activity. In this callback perform basic application startup logic that happens only once 
   for the entire life of the activity.
   
   **onStart()** - This call makes the activity visible to the user as the app prepares for the activity to enter the foreground and become interactive.
   
   **onResume()** - when it comes to the foreground, and the system invokes the onResume() callback. This is the state in which the app interacts with the user.
   
   **onPause()** - It indicates that the activity is no longer in the foreground, but it is still visible if the user is in multi-window mode.
   
   **onStop()** - When your activity is no longer visible to the user, The system also calls onStop() when the activity finishes running and is about to be terminated.
   
   **onDestroy()** - destroying the activity due to a configuration change, such as device rotation or entering multi-window mode, user completely dismissing the activity or due to        finish() being called on the activity.
   
3. #### What will be the activity lifecycle when the user puts the app in the background and then returns to the foreground?
   suppose we launch Activity A, then the callback methods would be:

   ``` Activity A - onCreate() > onStart() > onResume() ```
   
   When we put the app in the background, the callback methods would be:

   ``` Activity A - onPause() > onStop() ```
   
   When we bring the app to the foreground, the callback methods would be:

   ``` Activity A - onRestart() > onStart() > onResume() ```

4. #### What will be the activity lifecycle when the user launches a new activity from the existing activity?

   Below are the lifecycle callbacks when we launch Activity A, and after that, from Activity A, we launch Activity B.

   ``` Activity A - onCreate() > onStart() > onResume() > onPause() ```

   ``` Activity B - onCreate() > onStart() > onResume() ```
   
   ``` Activity A - onStop() ```
   
   Below are the lifecycle callbacks when we press back from Activity B and return to Activity A again.

   ``` Activity B - onPause() ```

   ``` Activity A - onRestart() > onStart() > onResume() > onPause() ```
   
   ``` Activity B - onStop() > onDestroy() ```

5. #### What is onSavedInstanceState and onRestoreInstanceState in activity?
   onSaveInstanceState() and onRestoreInstanceState() are two important methods in the activity lifecycle that help in preserving the activity's state during configuration changes        like screen rotations or when the system kills the activity to reclaim memory.
   #### onSavedInstanceState() 
   - Called before the activity is paused or stopped.
   - Used to save the data to a Bundle object.
   #### onRestoreInstanceState() 
   - Called after onStart() and before onResume() when the activity is being re-initialized from a previously saved state.
   - Used to restore the data from the Bundle object.

6. #### Explain launch modes
   there are 5 types of launch modes
   
   **standard** - The system always creates a new instance of the activity in the task. this is the default launch mode.
    
   **singleTop** - If the activity already exists at the top of the current task, the system call to its onNewIntent() method.
   
   ``` [D = singleTop] A-B-C-D >> A-B-C-D ```
   
   If the activity is not top of the current task, it will again create the new instance of the activity.
   
   ``` [C = singleTop] A-B-C-D >> A-B-C-D-C ```
   
   **singleTask** - If the activity already exists in the task, the system call to its onNewIntent() method. on top of that all other activity will be destroyed.
   
   ``` [C = singleTask] A-B-C-D >> A-B-C ```
   
   **singleInstance** - It's similar to singleTask expect it will be create the new instance of the activity in separate task & the system doesn't launch any other activity in that        task.
   
   ``` [D = singleInstance]  A-B-C-D >> Task 1 [A-B-C]  >> Task 2 [D] ```
   
   **singleInstancePerTask** - This mode is similar to singleInstance mode, but the only difference is that muliple instances of the activity can be created in different tasks.

   Note: **"singleTask"** and **"singleInstancePerTask"** remove all activities that are above the starting activity from the task.

7. #### When the user press on the “Back” button will onDestroy() be called?
    when the user presses the “Back” button inside of activity it will call finish() which will close activity.
   
8. #### When only onDestroy() is called for an activity without onPause() and onStop()?
    if we call finish() from activity onCreate() method, in this case onPause() and onStop() will never called.
   
9. #### What is Affinity?
    An affinity indicates which task an activity "prefers" to belong to. By default, all the activities from the same app have an affinity for each other.
    
10. #### When you show dialog on a activity which lifecycle method will be called?
    when an AlertDialog or DialogFragment is used, it will never call OnPause(), since they are a part of the activity.
    
11. #### When you get a call on your phone which life cycle method will be called?
    Your app goes into the background when the user receives a phone call. The activity goes through the onPause() and onStop() methods.
    
12. #### Which method is called when Android system kills the activity due to memory issue?
    When Android decides to kill our app, our activities will call onDestroy() method. But before that, one more method will be also called and that is onSaveInstanceState(Bundle). 

13. #### What is the difference between Serializable and Parcelable?
   - Serializable uses reflection to serialize and deserialize the object, which can be slow and inefficient, while Parcelable generates code to do the same thing, resulting in faster      and more efficient serialization and deserialization.
   - Parcelable requires more boilerplate code to implement, as it requires writing custom code to serialize and deserialize each field in the object, while Serializable can be             implemented with just a marker interface.
   - Serializable can be used with any Java class, while Parcelable can only be used with classes that implement the Parcelable interface.
