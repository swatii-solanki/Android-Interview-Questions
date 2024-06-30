1. #### What is Hilt, and why is it used in Android development?
   Hilt is a dependency injection library for Android that simplifies and automates the process of injecting dependencies into Android components like activities, fragments, and
   ViewModels. It is used in Android development to enhance code maintainability, improve testability, and adhere to best practices. Hilt reduces the boilerplate code typically
   associated with Dagger 2 and provides a consistent way to perform dependency injection.

2. #### What is @HiltAndroidApp ?
   The @HiltAndroidApp annotation designates the application class as the entry point for Hilt. It's typically placed on your application class, and it serves as the starting point for
   Hilt's setup in your Android app. When you use @HiltAndroidApp, Hilt takes care of generating the necessary Dagger components and modules for dependency injection.

3. #### What is @AndroidEntryPoint?
   The @AndroidEntryPoint annotation designates Android components, such as activities, fragments, and services, as injectable. It simplifies the injection process for these
   components. When you use @AndroidEntryPoint, Hilt generates the necessary Dagger components for the annotated components, and you can inject dependencies without manually creating
   Dagger components.

4. #### What is @Inject?
   The @Inject annotation is a key component of the dependency injection framework. It is used to indicate to Hilt that a particular dependency needs to be provided by the dependency
   injection framework. When Hilt encounters the @Inject annotation, it knows to fulfill that dependency either by providing an instance of the requested object or by creating and
   managing its dependencies.

5. #### What is @Module?
   - Hilt modules are classes or objects annotated with @Module that provide dependencies to your application. These modules define how to create and provide instances of objects that
   can be injected into your app's classes.
   - Hilt modules can be customized with the @InstallIn annotation to specify the component scope they are installed in, such as SingletonComponent, ActivityRetainedComponent, or
     others.

6. #### What is InstallIn(SingletonCompoenent::Class)?
   The use of InstallIn(SingletonComponent: class) is particularly valuable when dealing with dependencies that are expensive to create or should be shared across the entire
   application. By scoping such dependencies within the Singleton Component, Dagger Hilt ensures that they are created only once and reused throughout the application’s lifespan. This
   optimization can greatly improve performance and resource usage, especially in scenarios such as Retrofit calls or heavy object creation.

7. #### What is @Binds?
   By utilizing @Binds, developers can streamline the process of binding interfaces to their respective implementations. Unlike traditional methods that involve using @Provides and
   creating instances within modules, @Binds eliminates the need for instantiating the implementation class explicitly. Instead, it establishes a direct binding between the interface
   and the implementation, reducing boilerplate code and simplifying the overall configuration.

8. #### What is @HiltViewModel?
   It helps in integrating ViewModel classes with dependency injection. It automatically injects dependencies into ViewModel classes, reducing boilerplate code and making it easier to
   manage dependencies.

9. #### Provides vs binds
   - The @Inject annotation is used to indicate that a particular constructor, field, or method should be used for dependency injection. It is used to indicate that a particular class
   should be used as a dependency for another class. The @Inject annotation can be used on constructors, fields, and methods.

   - The @Provides annotation is used to indicate that a particular method should be used to provide a dependency. It is used to indicate that a particular method should be used t
   provide a dependency for another class. The @Provides annotation can only be used on methods.

   - The main difference between the two annotations is that the @Inject annotation is used to indicate that a particular class should be used as a dependency, while the @Provide
   annotation is used to indicate that a particular method should be used to provide a dependency.

10. #### How do you handle circular dependencies when using Dagger?
    When using Dagger, circular dependencies can be handled by using a custom scope. A custom scope is a way to limit the object graph that Dagger creates. This allows us to break the
    circular dependency by creating a scope that is only used for the objects that are part of the circular dependency.

    For example, if we have two classes, A and B, that depend on each other, we can create a custom scope called “CircularScope” and annotate both classes with this scope. This will
    tell Dagger to create a separate object graph for these two classes, which will break the circular dependency.

    We can also use a Subcomponent to break the circular dependency. A Subcomponent is a component that is created within another component. This allows us to create a separate object
    graph for the objects that are part of the circular dependency.

    Finally, we can use a Provider to break the circular dependency. A Provider is a class that provides an instance of an object. This allows us to create a separate object graph for
    the objects that are part of the circular dependency.

    By using one of these methods, we can break the circular dependency and allow Dagger to create the object graph correctly.

11. #### What is an entry point?
    An entry point is the boundary between code that is managed by Hilt and code that is not. It is the point where code first enters into the graph of objects that Hilt manages. Entry
    points allow Hilt to use code that Hilt does not manage to provide dependencies within the dependency graph.

    For example, Hilt doesn't directly support content providers. If you want a content provider to use Hilt to get some dependencies, you need to define an interface that is annotated
    with @EntryPoint for each binding type that you want and include qualifiers. Then add @InstallIn to specify the component in which to install the entry point as follows:

12. #### What is Lazy Injection?
    Lazy<T> is a Dagger2 construct that allows deferred creation of a dependency.

13. #### Why use Lazy Injection?
    - Deferred Initialization: If a dependency is heavy and you don’t need it immediately after the component is created, you can delay its instantiation.
    - Single Instantiation: The dependency is created only once, the first time it’s requested. Subsequent requests will return the same instance.


