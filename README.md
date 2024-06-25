# Android-Interview-Questions

1. What is Activity ?
    An Activity is the part of the android components & it's the starting point of the application. An activity provides the window in which the app draws its UI. 
2. Explain Activity Lifecycle 
    There are 7 states of the activity lifecycle
    onCreate - this is the first callback which fires when the system first creates the activity. In this callback perform basic application startup logic that happens only once for the entire life of the activity.
    onStart - This call makes the activity visible to the user as the app prepares for the activity to enter the foreground and become interactive.
    onResume - when it comes to the foreground, and the system invokes the onResume() callback. This is the state in which the app interacts with the user. 
    onPause - It indicates that the activity is no longer in the foreground, but it is still visible if the user is in multi-window mode. 
    onStop - When your activity is no longer visible to the user, The system also calls onStop() when the activity finishes running and is about to be terminated.
    onDestroy - destroying the activity due to a configuration change, such as device rotation or entering multi-window mode, user completely dismissing the activity or due to            finish() being called on the activity.
4.  Explain launch modes
    there are 5 types of launchmodes
    standard - The system always creates a new instance of the activity in the task. this is the default launch mode.
    singleTop - If the activity already exists at the top of the current task, the system call to its onNewIntent() method.
                Ex. [D = singleTop]  A-B-C-D >> A-B-C-D
                If the activity is not top of the current task, it will again create the new instance of the activity.
                Ex. [C = singleTop]  A-B-C-D >> A-B-C-D-C
    singleTask - If the activity already exists in the task, the system call to its onNewIntent() method. on top of that all other activity will be destroyed.
                Ex. [C = singleTask]  A-B-C-D >> A-B-C
    singleInstance - It's similar to singleTask expect it will be create the new instance of the activity in separate task & the system doesn't launch any other activity in that task.
                Ex. [D = singleInstance]  A-B-C-D >> Task 1 [A-B-C]  >> Task 2 [D]
    singleInstancePerTask - This mode is similar to singleInstance mode, but the only difference is that muliple instances of the activity can be created in different tasks.
    Note: "singleTask" and "singleInstancePerTask" remove all activities that are above the starting activity from the task.
5. 
