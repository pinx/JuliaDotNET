# JULIA.Net

Allows C# To Call Julia

Example Usage:

```csharp
  Julia.Init();
  Console.WriteLine(Julia.Eval("2.0 * 2.0").UnboxFloat64());   //Version 0.0.0
  
  
  //Version 0.0.1
  Julia.Eval("t(x) = x * 2");
  Julia.GetFunction(JLModule.Main, "t").Invoke(new JLVal(5)).Println();

  //Version 0.0.2
  JLFun fun = Julia.Eval("t(x) = x * 2");
  fun.Invoke(5).Println();

  //Version 0.0.3
  JLFun fun = Julia.Eval("t(x) = x * 2");
  fun.Invoke(5).Println();   //Exception Checking
  fun.UnsafeInvoke(5).Println();   //No Exception Checking
  
  //Version 0.0.4
  JLFun fun = Julia.Eval("t(x) = sqrt(x)");
  double result = (double) fun.Invoke(2);
  object dotNetObject = fun.Invoke(3).Value;

  Julia.Exit(0);  
```


WARNING: IN DEEP DEVELOPMENT AT THE MOMENT



TODO: Implement Exception Handling??
