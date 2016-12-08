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
# annotations and names

```
//@formatter:off
@ValidateWithCoyoteMethod.List({
@ValidateWithCoyoteMethod("validatePaymentCount"),
@ValidateWithCoyoteMethod("validatePaymentMandant"),
@ValidateWithCoyoteMethod("validatePaymentAmountForProductOption"),
@ValidateWithCoyoteMethod("validatePaymentCategory") })
@XmlElement
private List<Payment> payments = newArrayList();
//@formatter:on

@NeitherNullNorEmpty(when = "js: _this.isProductOptionCatalogCategory()")
@ValidateWithCoyoteMethod("validateFiltersForProductOptionCatalog")
public List<FilterParamValue> filters = newArrayList();
```

# unit conversion

```
private int convertToKm(Double distance) {
distance = (distance / 1000);
return new BigDecimal(distance).setScale(0, RoundingMode.HALF_UP).intValue();
}
```

# roll my own instance cache

```
public OrgPersonSalaryDay getDay(String date) {

  OrgPersonSalaryDay day = this.sicknessDays.get(date);
  if (day == null) {
    day = new OrgPersonSalaryDay(date);
    this.sicknessDays.put(date, day);
   }
   this.sicknessDays.put(date, day);

   return day;
}
```
# clean code at its best

```
public String createResponseSubject() {
  String[] subjectParts = subject.split(SUBJECT_SEPARATOR);
  if (subjectParts.length == 5) {
    String temp = subjectParts[4];
    subjectParts[4] = subjectParts[3];
    subjectParts[3] = temp;
  }
  subjectParts[0] = PortMessageParser.PORT_RESPONSE_TAG;
  return StringUtils.join(subjectParts, SUBJECT_SEPARATOR);
}
```
