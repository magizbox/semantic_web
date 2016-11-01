# Create Unit Test in Visual Studio 2013

## Step 1. Create `TDDLab` Solution

**1.1** Open Visual Studio 2013

**1.2** `File` ->  `New Project...` ->

* Click `Visual C++` -> `Win32`

* Choose `Win32 Console Application`

* Fill to `Name` input text: **TDDLab**

* Click `OK` -> `Next`

**1.3** In project settings, remove options:

* `Precompiled Header`
* `Securirty Develoment Lifecyde(SQL) check`

**1.4** Click `Finish`

## Step 2. Create `Counter` Class

**2.1** Right-click `TDDLab` -> `Add` -> `Class...`

**2.2** Choose `Visual C++` -> `C++ Class` -> `Add`

**2.3** Fill in `Class name` box **Counter** -> `Finish`

**2.4** In `Counter.h` file, add this below function

```cpp
int add(int a, int b);
```

**2.5** In `Counter.cpp`, add this below function

```cpp
int Counter::add(int a, int b) {
  return a+b;
}
```

Your `Counter` class should look like this

![](https://lh3.googleusercontent.com/MeGn9mLmTTdYtcc-F1HeS7cm5v5QhmmLpPKa35QUeIqDOaKWHhqHlYZilL-sDIFH4993R0dgck4ZfQ=w745-h434-no)

## Step 3. Create `TDDLabTest` Project

**3.1** Right-click `Solution 'TDDLab'` -> `Add` -> `New Project...`

**3.2** Choose `Visual C++` -> `Test`

**3.3** Choose `Native Unit Test Project`

**3.4** Fill to `Name` input text: **TDDLabTest**

## Step 4. Write unit test

**4.1**  In `unittest1.cpp`, add header of `Counter` class

```cpp
#include "../TDDLab/Counter.h"
```

**4.2** In `TEST_METHOD` function

```cpp
{
  Counter counter;
  Assert::AreEqual(2, counter.add(1, 1));
}
```

**4.3** Click `TEST` in menu bar -> `Run` -> `All Test (Ctrl + R, A)

## Step 5. Fix error `LNK 2019: unresolved external symbol`

**5.1** Change `Configuration Type` of `TDDLab` project

* Right click  `TDDLab` project -> `Properties`
* `General` -> `Configuration Type` -> `Static library (.lib)` -> `OK`

**5.2** Add Reference to `TDDLabTest` project

* Right click `TDDLabTest` solution -> `Properties` -> `Common Properties` -> `Add New Reference `
* Choose `TDDLab` -> `OK` -> `OK`

## Step 6. Run Tests

Click `TEST` in menu bar -> `Run` -> `All Test (Ctrl + R, A)

Test should be passed.

![](https://lh3.googleusercontent.com/OePw8s2rRtk1ygSbCyOOGx7TQAL1tiJoE4cBM1_YTtauTP4Gcb0KhsR9PWInbAxaGLJDg8W7HsDumQ=w747-h434-no)

