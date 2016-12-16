# Meta-Ento
A Java Entity framework to create Entity frameworks

## Introduction
*Meta-Endo* allows for the creation of entity frameworks. The resulting frameworks are domain-specific, that is, they operate within a defined application domain. For example, *Meta-Endo* can be used to represent HTML in a Java object graph. "HTML" is the domain (because it means something), where as "Entity" is superfluous. 
*Meta-Endo* incorporates several patterns: observer, visitor, command, and delegate, to name a few. These patterss are exposed to the application developer and are not exclusively used by the framework. For example, given an Entity myEntity and myEntityChild, you can perform composition, delegation and observation:

[*NOTE: The following is pseudo-code*]
```
//Defining your domain framework...
Entity myEntity = new Entity() {
    @Override
    public void stopDelegation(Entity entity) {
       //react to "entity's" request to stop delegation
    }
};

Entity myChildEntity = new Entity() {
    @Override
    public void delegation() {
       //do something "delegate-y"
       stopDelegation();
    }
};

//...used in your application...
myEntity.addChild(myEntityChild);
myEntity.delegate(); //this method is usually augmented within a domain implementation
```
