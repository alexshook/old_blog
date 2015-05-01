---
layout: post
title: "Learn Ruby the Hard Way (Again)"
date: 2015-04-29 23:27:15 -0400
comments: true
categories: [ruby, learn ruby the hard way]
---
It's been more than a year since I last did [Learn Ruby the Hard Way](http://learnrubythehardway.org/book/). Now that Ruby is at version 2.2, I've been thinking that it's probably a good time for a basics refresher. I only got through Exercise 34 or so before WDI started, and I remember it being one of the more difficult beginning Ruby things that I did.

It's really interesting to see how I look at things now compared to 1+ years ago. <!-- more -->

I started off with [Exercise 1](http://learnrubythehardway.org/book/ex1.html), which is pretty basic. All you do in Exercise 1 is `puts` a bunch of strings. I predicted that I would move through the early exercises quickly.

I haven't. I completed Exercise 1 on Monday and haven't even gotten to Exercise 2 yet. While I was putsing the Exercise 1 strings, I started thinking about what C actually has to do to give us something as nice as typing `puts 'Hello!'` to get `Hello!` to appear in the console.

Compared to Java's `public class blah blah System.out.println` or even PHP's `echo` (which I always thought was vaguely unclear), `puts` is fantastically beautiful. And I never cared about it at all until now.

Where does it come from? How does it do what it does?

Puts is a kernel method, and it's [listed in I/O](http://ruby-doc.org/core-2.2.2/IO.html#method-i-puts) in the Ruby documentation. Until I read the documentation, I never knew you could `puts` like this:

`puts("this", "is", "a", "test")`

with strings separated by commas. I can't think of anything I'd ever want to use that for, but it's still interesting. Things got even more interesting when I took a look at the source code. Here's what C does when you `puts` in Ruby:

```
               VALUE
rb_io_puts(int argc, const VALUE *argv, VALUE out)
{
    int i;
    VALUE line;

    /* if no argument given, print newline. */
    if (argc == 0) {
        rb_io_write(out, rb_default_rs);
        return Qnil;
    }
    for (i=0; i<argc; i++) {
        if (RB_TYPE_P(argv[i], T_STRING)) {
            line = argv[i];
            goto string;
        }
        if (rb_exec_recursive(io_puts_ary, argv[i], out)) {
            continue;
        }
        line = rb_obj_as_string(argv[i]);
      string:
        rb_io_write(out, line);
        if (RSTRING_LEN(line) == 0 ||
            !str_end_with_asciichar(line, '\n')) {
            rb_io_write(out, rb_default_rs);
        }
    }

    return Qnil;
}
```

Looks kind of crazy. I think I got about 50% of that post-Google, and that's probably on the optimistic side. I did learn that a `Qnil` is the C constant for Ruby's nil value. That might come in handy if I ever get ambitious and want to write an extension.

I was going to start [Learn C the Hard Way](http://c.learncodethehardway.org/book/) after I finished with Ruby, but instead I think I'm going to start right away.
