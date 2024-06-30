1. #### What is a Fragment in Android?
   A Fragment is a modular section of an Android activity, representing a part of the UI or behavior in an activity.

2. #### How is a Fragment different from an Activity?
   An Activity represents a single screen with a user interface, while a Fragment is a reusable component within an activity.

3. #### Explain the lifecycle of a Fragment.
   **onAttach()**: This method is called when a fragment is first attached to its hosting activity. It can be used to retrieve data from the activity and initialize any resources
   needed by the fragment.

   **onCreate()**: This method is called to create the fragment and its user interface. It sets up any views or data needed by the fragment.

   **onCreateView()**: This method is called to inflate the fragment’s layout. It returns the view hierarchy that should be displayed in the fragment.

   **onActivityCreated()**: This method is called when the hosting activity’s onCreate() method has completed. It can be used to access views in the activity or to load data into the
   fragment.

   **onStart()**: This method is called when the fragment becomes visible to the user.

   **onResume()**: This method is called when the fragment becomes the active fragment and has user focus.

   **onPause()**: This method is called when the fragment is no longer the active fragment.

   **onStop()**: This method is called when the fragment is no longer visible to the user.

   **onDestroyView()**: This method is called to clean up the fragment’s view hierarchy.

   **onDestroy()**: This method is called to finalize the fragment’s resources.

   **onDetach()**: This method is called when the fragment is detached from its hosting activity. It can be used to release any resources associated with the fragment.

5. #### How can you communicate between Fragments?
   Communication between Fragments can be achieved through interfaces, shared ViewModel, or using the FragmentManager.

6. #### Explain the difference between FragmentTransaction add, replace, and remove methods.
   - **add:** Adds a Fragment to the container without removing existing Fragments.
   - **replace:** Replaces the existing Fragment with a new one.
   - **remove:** Detaches an existing Fragment from the UI.

7. #### What is the purpose of setRetainInstance(true) in a Fragment?
   It retains the instance of the Fragment across configuration changes, like screen rotations, preserving its state.

8. #### How can you dynamically add a Fragment to an activity?
   Use FragmentManager to begin a transaction and then use add or replace methods to add the Fragment.

9. #### How can you perform a FragmentTransaction?
   Use FragmentManager to begin a transaction, perform desired operations (add, replace, remove), and then commit the transaction.

10. #### What is the significance of addToBackStack in a FragmentTransaction?
    It adds the transaction to the back stack, allowing the user to navigate back to the previous state using the device’s back button.

11. #### Explain the back stack in the context of Fragments.
    The back stack is a record of Fragment transactions that allows users to navigate back to previous states using the device’s back button.

13. #### Explain the difference between commit and commitNow in FragmentTransactions.
    - commit: Schedules the transaction to be executed on the next frame.
    - commitNow: Executes the transaction immediately on the calling thread.

14. #### How can you handle Fragment transactions in a ViewPager?
    Use a FragmentPagerAdapter or FragmentStatePagerAdapter and manage transactions through the adapter.

15. #### How can you pop the back stack programmatically?
     Use popBackStack() or popBackStackImmediate() methods of FragmentManager.

16. #### What is the difference between popBackStack and popBackStackImmediate?
    - popBackStack: Asynchronously pops entries off the back stack.
    - popBackStackImmediate: Synchronously pops entries off the back stack.

17. #### Explain how to handle back button presses within a Fragment.
    Override onBackPressed in the hosting Activity or use OnBackPressedDispatcher within the Fragment.

18. #### What is the purpose of FragmentManager.BackStackEntry?
    It represents an entry in the back stack, providing information about the FragmentTransaction.

19. #### What is the role of ViewModel in the context of Fragments?
    ViewModel helps store and manage UI-related data in a lifecycle-conscious way, surviving configuration changes.

20. #### How can you share data between Fragments using a shared ViewModel?
    Create a shared ViewModel and access it from both Fragments, observing data changes.

21. #### Explain the concept of ViewModel scope in a Fragment.
    The ViewModel is scoped to the Fragment's lifecycle, ensuring that it is only retained as long as the Fragment is alive.

22. #### What is the purpose of by viewModels() delegate in a Fragment?
    It is a property delegate that creates a ViewModel tied to the Fragment's lifecycle.

23. #### How can you handle communication between Fragments using ViewModel and LiveData?
    Use a shared ViewModel with a LiveData object to observe changes in one Fragment triggered by another.

24. #### How can you handle configuration changes in Fragments?
    Use setRetainInstance(true), ViewModels, or handle configuration changes manually by saving and restoring state.

25. #### Explain the role of onConfigurationChanged in a Fragment.
    onConfigurationChanged is called when a configuration change occurs, allowing the Fragment to respond accordingly.

26. #### Explain the use of FragmentFactory in creating Fragments.
    FragmentFactory allows you to customize the process of creating Fragments, useful for dependency injection.

27. #### How can you optimize Fragment transactions for better performance?
    Use commitNow() for immediate execution, avoid nested transactions, and batch multiple operations into a single transaction.

28. #### When you show dialog on a fragment/activity which lifecycle method will be called?
    No lifecycle method is called.





