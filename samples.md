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

got this as Response for a service call

```
Internal error (The method [com.xyz.ruleengine.engine.RuleEngine.process] raised exception [java.lang.RuntimeException]. java.lang.RuntimeException? java.lang.NullPointerException)
```

