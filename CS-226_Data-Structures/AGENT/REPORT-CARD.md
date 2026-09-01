# CS-226 Report Card

## 2026-08-30 — Java crash course, session 1

### Accomplished

- Read and traced a basic Java class with fields, a constructor, and instance methods.
- Distinguished constructor parameters from instance fields and used `this.field` to resolve shadowing.
- Distinguished primitive-value copying from reference copying and correctly traced aliased objects and arrays.
- Covered `null`, runtime `NullPointerException`, fixed array length, default array values, and bounds checking.
- Distinguished logical size from capacity in a dynamic-array representation.
- Distinguished instance fields from shared `static` fields.
- Distinguished compile-time type checking from runtime failures, including invalid method calls and failed casts.
- Began generics: type parameters, type substitution, wrapper type `Integer`, autoboxing/unboxing, and compile-time type safety.

### Demonstrated strengths

- Strong transfer from C++ class syntax: quickly recognized constructors, private fields, methods, and `void`.
- Accurately traced object state, array state, and separate instances.
- Correctly reasoned about valid array indices and compile-time versus runtime cast behavior once the declared-type rule was established.
- Can substitute concrete types for `T` and determine which generic method calls compile.

### Errors and points of focus

- **Recall:** Initially expected ordinary object assignment to copy an object. Reinforce that Java assignment copies a reference; it does not invoke an implicit copy constructor or deep-copy the object.
- **Recall:** Initially uncertain whether arrays default-initialize elements and whether `length` means capacity or populated entries. Recall: `int` array entries begin at `0`, and `array.length` is fixed capacity.
- **Recall:** Initially treated the runtime object's type as the type used for all method checking. Reinforce that the compiler checks available methods using the variable's declared type.
- **Recall:** Generics remain the main weak point. The core model is becoming clearer: for `Box<String>`, substitute `String` for every `T`; incompatible values are rejected at compile time.
- **Application:** Generic implementation details (`Object[]`, casts, type erasure, and why `new T[]` is prohibited) were introduced too quickly and are not yet secure.

### Next session

- Resume slowly with the boundary between a generic class's public type guarantee and its private storage.
- Then review generic dynamic-array storage and casts with one small trace at a time.
