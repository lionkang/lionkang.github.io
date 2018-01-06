---
layout: page
title: About 
permalink: /about/
---

~~~java
public class AboutSample {
    interface Basic {void info (String key, String value);}
    public static void main(String[]args) {
        Basic basic = (String key, String value) -> System.out.println(key + " : " + value);
        basic.info("name", "lion kang");
        basic.info("work", "software engineer by naver");
        basic.info("mail", "lionkang &#64; gmail.com");
    }
}
~~~

~~~python
if __name__ == "Meaning of Life" : 
	print("enjoy life");
	print("pleasure together");
	print("dreaming of an altruistic life");
~~~

