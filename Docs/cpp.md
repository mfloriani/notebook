
# C++

## Optimization

[Tips](https://github.com/facontidavide/CPP_Optimizations_Diary)

## Variadic Templates

### Parameter Pack

Types:
```
template <class... Ts>                    //Ts is a list of type parameters
template <unsigned... Ns>                 //Ns is a list of non-type parameters (unsigned)
template <template <class T>... class Us> //Us is a list of template template parameters
```

Example of a template and function parameter pack:
```
template <class... Args>                //Args is the template parameter pack
void f(int i, Args... args) {  //... }  //args is the function parameter pack
```

### Pack Expansion

```
template <class... Args>
void f(int i, Args... args) {
  //expand template parameter pack Args first, then function parameter pack args
  std::tuple<Args...> argsTuple{args...}; 
  //...
}

f(21, 54.3, "foo", 47u);
```

The template parameter pack Args will be the list of the types `double`, `char const*` and `unsigned`, while the function parameter pack args will be the list of the values 54.3, "foo" and 47u.

Refs: 
[Simplify C++ Article](https://arne-mertz.de/2016/11/modern-c-features-variadic-templates/)

More pack expansion

```
template <class... Args>
void f(int i, Args&&... args) {
  std::tuple<Args...> argsTuple{std::forward<Args>(args)...}; 
  //...
}
```

`sizeof...`

It simply returns the number of pack elements and works on both template parameter packs and function parameter packs



