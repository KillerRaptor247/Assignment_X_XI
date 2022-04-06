1. The logger is different from the console as the logger contains the FINER level messages that the console does not output.

2. The line comes from the Tester.java class as it is a notification that for the JUnit tests that we are not using the @Disabled
interface. It tells us that the JUnit cannot find @Disabled for any of the testing methods.

3. Assertions.assertThrows is a statement that tests to make sure the code being tested is throwing an exception of a specific type

4.
	a.) A serialVersionUID is a version number which is used during a deserialization of an object to verify that a sender
and a reciever of a serialized object have classes that are compatible via the comparison of a serialVersionUID. We need it because
it ensure that we are testing two identical classes with regards to their serialVersionUID. Java auto compiles a serialVersionUID if one
is not specified, but due to compiler settings two instances of the same class may have different serialVersionUIDs. If two classes have
different serialVersionUIDs, an InvalidClassException is thrown during deserialization of the class object.
	b.) Class Exception is a Serializable object. Since we are testing for an assertThrows of a TimerException class, we must overload
the constructors so that they have the TimerException serialVersionUID we defined for comparison, instead of the auto compiled Exception serialVersionUID.
	c.) There is no need to override the other Exception methods as they do not require comparisons with the serialVersionUID. These methods will not
cause an instance of a TimerException class to auto-default for a serialVersionUID, so they can be safely derived from the Exception class.