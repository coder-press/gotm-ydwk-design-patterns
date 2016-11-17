# Works most of the time.. 

```java
public @interface TestSmell {
  enum Reason {
    /** @deprecated don't annotate flipping tests. Fix it - or delete it! */
    @Deprecated
    Flipping
  }

  Reason reason();
}
```

# stringly typed

```java
  public OrgXYZ(String positionId,String homeOrgId,String personId,String validStart,String validEnd,
    OrgXYZType xyzType,String xyzId,String xyzOrgId,String orgPermissionType,int levelNo) {
      ...
  }
```

# If you got a strange response message

got this as response for a service call and the service is not hosted by xyz.. so this exception is from a service which is called by the service we call..

```
Internal error (The method [com.xyz.ruleengine.engine.RuleEngine.process] raised exception [java.lang.RuntimeException]. java.lang.RuntimeException? java.lang.NullPointerException)
```
-.. and this ...

```
A validation occurred while parsing?: validation error?: data "" is not: a valid int. A valid example is "-1, 0, 126789675, ?+100000". ({com:.abc.xml.validation}SIMPLE_E_INVALID_VALUE_FOR_TYPE) at /CreateCusto:merContact_In[1]/Body[1]/CreateCustomerContact_In[1]/customerId[1] com:.abc.xml.validation.exception.ValueParseException?: data "" is not a 
```

# behavior obfuscation

Guess what this means. And guess what you will get as a result...

```
public interface XYZ {
  ...
  String beforeInsert(UserRow userRow);
  ...
}
```
Answer: It is the error message if anything goes wrong, null if all went well.

# sql query builder magic

```
new StringBuilder()
				.append(format("select m.%s", MyEntityWrapper.col_id)).append('\n')
  ...
```
