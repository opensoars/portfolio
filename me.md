---
layout: page
title: Me
permalink: /me/
---



{{ site.description }}



## Current occupation

Currently I'm mainly focussing on improving the following of my skills:

- Math
- Functional programming
- ES7+
- OpenGL
- WebGL
- GLSL
- C# (language used at university)
- Embedded systems
- Electronics
- Artificial intelligence

Some of the skills I always improve on the side:

- Epic workflows & development environments
- Software architecture design
- Collaboration (through maintainability)

Regarding the current educational cource I'm following; I study computer science in Leeuwarden, at the NHL Hogeschool, my mentor there is Fiona Sariedine and I'm in group 1B. My previous study, which I completed in July 2016, was Application Development at the Friesland College institute. I'm planning to study abroad in the near future, feel free to let me know if you've got tips ;).


At the moment I'm mainly focussing on on studying. Nevertheless, I'm always up for special projects to work on, so if you want me to help you with that special kind of (tech) project, don't hesitate to contact me!

## Sam?

Besides all the tech stuff: I'm in my early twenties, I love nature and travelling, I'm social, and I love (creating) music. Currently im located in Leeuwarden, the Netherlands.

Here's a picture of me which I used whilst experimenting with fragment shaders. The shader used on this image was used to make videos look like an oldschool movie. The effects of the shader were imitating materialilstic imperfections due to for example dust particles.

{:.me .working}
![me-shaders](/portfolio/assets/img/me-shaders.jpg)

I love to write code for fun that utilizes features which aren't normaly used for a specific purpose, JavaScript is a great language for this. Take for example the lazy evaluation demo below, which utilizes the `undefined` value that a `forEach` method returns. It also demonstrates the use of default arguments in order to put a variable in a function its scope.

{:.custom-code}
{% highlight javascript %}
const makeLazy = (f, r = null) =>
  r = (...a) => (...na) => !na.length ? f(a) : r(...a, ...na);
  
const add = (ns, s = 0) => ns.forEach(n => s += n) || s;

makeLazy(add)(1, 2)(3)(3)();
{% endhighlight %}

Whether I write code like the above or not depends on the situation. Taking things into consideration like: what am I writing the code for, who is going to read this code, etc. Depending on the situation, I might write the above logic like this:

{:.custom-code}
{% highlight javascript %}
const make_lazy = function makeLazy(f) {
  return function recurse(...args) {
    return function (...newArgs) {
      if (newArgs.length === 0)
        return f(args);
      else
        return recurse(...args, ...newArgs);
    };
  };
};

const add = (nums) => {
  let sum = 0;
  nums.forEach(num => sum += num);
  return sum;
};

makeLazy(add)(1, 2)(3)(3)();
{% endhighlight %}