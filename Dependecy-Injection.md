1. #### What is Hilt, and why is it used in Android development?
   Hilt is a dependency injection library for Android that simplifies and automates the process of injecting dependencies into Android components like activities, fragments, and
   ViewModels. It is used in Android development to enhance code maintainability, improve testability, and adhere to best practices. Hilt reduces the boilerplate code typically
   associated with Dagger 2 and provides a consistent way to perform dependency injection.

2. #### What is @ HiltAndroidApp ?
   The @HiltAndroidApp annotation designates the application class as the entry point for Hilt. It's typically placed on your application class, and it serves as the starting point for
   Hilt's setup in your Android app. When you use @HiltAndroidApp, Hilt takes care of generating the necessary Dagger components and modules for dependency injection.

3. #### What is @ AndroidEntryPoint?
   The @AndroidEntryPoint annotation designates Android components, such as activities, fragments, and services, as injectable. It simplifies the injection process for these
   components. When you use @AndroidEntryPoint, Hilt generates the necessary Dagger components for the annotated components, and you can inject dependencies without manually creating
   Dagger components.

4. #### What is @ Inject?
   The @Inject annotation is a key component of the dependency injection framework. It is used to indicate to Hilt that a particular dependency needs to be provided by the dependency
   injection framework. When Hilt encounters the @Inject annotation, it knows to fulfill that dependency either by providing an instance of the requested object or by creating and
   managing its dependencies.

5. #### What is @ Module?
   - Hilt modules are classes or objects annotated with @Module that provide dependencies to your application. These modules define how to create and provide instances of objects that
   can be injected into your app's classes.
   - Hilt modules can be customized with the @InstallIn annotation to specify the component scope they are installed in, such as SingletonComponent, ActivityRetainedComponent, or
     others.

6. #### What is InstallIn(SingletonCompoenent::Class)?
   The use of InstallIn(SingletonComponent: class) is particularly valuable when dealing with dependencies that are expensive to create or should be shared across the entire
   application. By scoping such dependencies within the Singleton Component, Dagger Hilt ensures that they are created only once and reused throughout the application’s lifespan. This
   optimization can greatly improve performance and resource usage, especially in scenarios such as Retrofit calls or heavy object creation.

7. #### What is @ Binds?
   By utilizing @Binds, developers can streamline the process of binding interfaces to their respective implementations. Unlike traditional methods that involve using @Provides and
   creating instances within modules, @Binds eliminates the need for instantiating the implementation class explicitly. Instead, it establishes a direct binding between the interface
   and the implementation, reducing boilerplate code and simplifying the overall configuration.

8. #### What is @HiltViewModel:
   It helps in integrating ViewModel classes with dependency injection. It automatically injects dependencies into ViewModel classes, reducing boilerplate code and making it easier to
   manage dependencies.

