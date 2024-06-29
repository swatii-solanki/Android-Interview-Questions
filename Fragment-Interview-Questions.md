1. #### What is a Fragment in Android?
   A Fragment is a modular section of an Android activity, representing a part of the UI or behavior in an activity.

2. #### How is a Fragment different from an Activity?
   An Activity represents a single screen with a user interface, while a Fragment is a reusable component within an activity.

3. #### Explain the lifecycle of a Fragment.
   **onAttach**: This method is called when a fragment is first attached to its hosting activity. It can be used to retrieve data from the activity and initialize any resources needed     by the fragment.

   **onCreate**: This method is called to create the fragment and its user interface. It sets up any views or data needed by the fragment.

   **onCreateView**: This method is called to inflate the fragment’s layout. It returns the view hierarchy that should be displayed in the fragment.

   **onActivityCreated**: This method is called when the hosting activity’s onCreate() method has completed. It can be used to access views in the activity or to load data into the
   fragment.

   **onStart**: This method is called when the fragment becomes visible to the user.

   **onResume**: This method is called when the fragment becomes the active fragment and has user focus.

   **onPause**: This method is called when the fragment is no longer the active fragment.

   **onStop**: This method is called when the fragment is no longer visible to the user.

   **onDestroyView**: This method is called to clean up the fragment’s view hierarchy.

   **onDestroy**: This method is called to finalize the fragment’s resources.

   **onDetach**: This method is called when the fragment is detached from its hosting activity. It can be used to release any resources associated with the fragment.

