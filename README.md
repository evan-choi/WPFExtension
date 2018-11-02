# WPF Extension
WPF Extension

A library help to WPF Programming

# [Nuget](https://www.nuget.org/packages/WPFExtension/)
PM> Install-Package WPFExtension

# Support Register Methods
| Methods                         | Need Property |
| ------------------------------- |:-------------:|
| Register()                      | YES           |
| Register\<T\>()                 | NO            |
| RegisterReadOnly()              | YES           |
| RegisterReadOnly\<T\>()         | NO            |
| RegisterAttached()              | YES           |
| RegisterAttached\<T\>()         | NO            |
| RegisterAttachedReadOnly()      | YES           |
| RegisterAttachedReadOnly\<T\>() | NO            |

# Basic usage

**Using namespace**
```cs
using WPFExtension;
```

## DependencyHelper
**Basic Register**
```cs
// Basic Register Dependency Property
public static DependencyProperty TextProperty =
        DependencyHelper.Register();
        
public string Text
{
    get { return (string)GetValue(TextProperty); }
    set { SetValue(TextProperty, value); }
}
```

**Basic Register - Exception Sample**
```cs
// Throw DependencyHelperException
public static DependencyProperty TextProperty =
        DependencyHelper.Register();
        
public string Title
{
    get { return (string)GetValue(TextProperty); }
    set { SetValue(TextProperty, value); }
}
```

**Register only**
```cs
// Register Only Dependency Property
public static DependencyProperty TextProperty =
        DependencyHelper.Register<string>();
        
// It is not necessary string property.
```

**Add Value Changed from DependencyPropertyDescriptor**
```cs
// Add Event
<DependencyProperty>.AddValueChanged(<Parent(DependencyObject)>, <EventHandler>);

// Remove Event
<DependencyProperty>.RemoveValueChanged(<Parent(DependencyObject)>, <EventHandler>);
```
