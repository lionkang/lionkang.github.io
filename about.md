---
layout: default
title: About
---

<div class="post">
	<h1 class="pageTitle">About Lion</h1>
	<center><img src="{{ '/assets/img/lion.jpg' | prepend: site.baseurl }}" alt=""></center>
	<p class="intro"></p>
  <h2>Activity</h2>
  <ul>
    <li>2007.04 ~ <a href="https://www.navercorp.com" target="_blank">NAVER</a> Software Enigneer, News Service</li>
    <li>2001.12 ~ Snowboarding, High1</li>
    <li>2013.04 ~ Scuba Diving, <a href="https://www.gue.com" target="_blank">GUE</a></li>
  </ul>
	<h2>Meaning of Life</h2>
	<ul>
		<li>Enjoy Life</li>
		<li>Pleasure Together</li>
    <li>Dreaming of an Altruistic Life</li>
	</ul>
</div>

<!--
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
  print("");
  print("pleasure together");
  print("dreaming of an altruistic life");
~~~
-->