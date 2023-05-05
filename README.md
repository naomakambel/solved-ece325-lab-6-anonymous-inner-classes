Download Link: https://assignmentchef.com/product/solved-ece325-lab-6-anonymous-inner-classes
<br>
Anonymous classes in Java are more accurately known as anonymous inner classes. Inner class means that a class is defined inside another class. An anonymous inner class is an inner class that is declared without using a class name at all. That is, of course is why it’s called an anonymous class.

The anonymous inner classes are very useful in some situations. For example, consider a situation where you need to create the only instance of a class, without creating subclasses or performing additional tasks such as method overloading.

Regular usage of inner class in java:

<table width="691">

 <tbody>

  <tr>

   <td width="691"><strong>public</strong> <strong>class</strong> <strong>OuterClass</strong> <strong>{</strong><em>// …</em>     <strong>public</strong> <strong>class</strong> <strong>InnerClass</strong> <strong>{</strong><em>// …</em><strong>}</strong><strong>public</strong> <strong>static</strong> <strong>void</strong> <strong>main</strong><strong>(</strong>String<strong>[]</strong> args<strong>)</strong> <strong>{</strong>         OuterClass outerObj <strong>=</strong> <strong>new</strong> OuterClass<strong>();</strong>OuterClass<strong>.</strong>InnerClass innerObj <strong>=</strong> outerObj<strong>.</strong>new <strong>InnerClass</strong><strong>();</strong>     <strong>}</strong><strong>}</strong></td>

  </tr>

 </tbody>

</table>

And the usage of the anonymous inner class in Java:

<strong>new</strong> SomeSuperType<strong>().</strong>method<strong>();</strong>

<table width="88">

 <tbody>

  <tr>

   <td width="88">SomeSuperType</td>

  </tr>

 </tbody>

</table>

Here,  can be an interface, and then this anonymous inner class implements that interface; or it can be a class, and then the anonymous inner class extends that class.

To understand how to define and use such kind of classes, it would be better to walk through an example.

<strong>class</strong> <strong>SomeClass</strong> <strong>{</strong>     <strong>public</strong> <strong>void</strong> <strong>method</strong><strong>()</strong> <strong>{</strong>

System<strong>.</strong>out<strong>.</strong>println<strong>(</strong>“Hello World!”<strong>);</strong>

<strong>}</strong>

<strong>}</strong>




<strong>public</strong> <strong>class</strong> <strong>OuterClass</strong> <strong>{</strong>

<strong>public</strong> <strong>static</strong> <strong>void</strong> <strong>main</strong><strong>(</strong>String<strong>[]</strong> args<strong>)</strong> <strong>{</strong>

<strong>new</strong> SomeClass<strong>()</strong> <strong>{</strong>                       <em>// This is not an instance of SomeClass, </em>             @Override <strong>public</strong> <strong>void</strong> <strong>method</strong><strong>()</strong> <strong>{</strong>    <em>// but an instance of the sub class of SomeClass</em>

System<strong>.</strong>out<strong>.</strong>println<strong>(</strong>“Anonymous Hello World!”<strong>);</strong>

<strong>}</strong>

<strong>}.</strong>method<strong>();</strong>

<strong>}</strong>

<strong>}</strong>

<table width="263">

 <tbody>

  <tr>

   <td width="61">SomeClass</td>

   <td width="34"> and</td>

   <td width="68">OuterClass</td>

   <td width="38">. The</td>

   <td width="61">SomeClass</td>

  </tr>

 </tbody>

</table>

In the code above, you can see that we have two classes,  is

<table width="28">

 <tbody>

  <tr>

   <td width="28">main</td>

  </tr>

 </tbody>

</table>

pretty straightforward — just has a simple method that prints a piece of text. In the  method an anonymous inner class is defined (new SomeClass() { … }) and invoked (new SomeClass() { … }.method();).

<h2>1.2  Purpose of Anonymous Inner Class</h2>

You have seen now that by creating an anonymous inner class, we create a sub class that extends some super class. But as we can do such thing in the regular style, what is the advantage of using anonymous inner class? Well:

<ol>

 <li>First of all, it is faster to just write an anonymous inner class rather than create a new separate class.</li>

</ol>

<table width="35">

 <tbody>

  <tr>

   <td width="35">final</td>

  </tr>

 </tbody>

</table>

<ol start="2">

 <li>Anonymous inner classes are especially useful when you need and only need one instance of a class, especially such instance is immutable ().</li>

 <li>We want to avoid creating extra classes without good reasons. The more classes which exist, the more difficult it is to find the one you want!</li>

</ol>

<h2>1.3  Anonymous Inner Classes Implementing Interfaces</h2>

The following example shows an anonymous inner class that implements an interface. It is similar with the previous example. Remember this is the typical usage of anonymous inner classes.

<table width="691">

 <tbody>

  <tr>

   <td width="691"><strong>interface</strong> <strong>SomeInterface</strong> <strong>{</strong>     <strong>public</strong> <strong>void</strong> <strong>method</strong><strong>();</strong><strong>}</strong><strong>public</strong> <strong>class</strong> <strong>OuterClass</strong> <strong>{</strong><strong>public</strong> <strong>static</strong> <strong>void</strong> <strong>main</strong><strong>(</strong>String<strong>[]</strong> args<strong>)</strong> <strong>{</strong>         <strong>new</strong> SomeInterface<strong>()</strong> <strong>{</strong>@Override <strong>public</strong> <strong>void</strong> <strong>method</strong><strong>()</strong> <strong>{</strong>System<strong>.</strong>out<strong>.</strong>println<strong>(</strong>“Hello World!”<strong>);</strong><strong>}</strong><strong>}.</strong>method<strong>();</strong><strong>}</strong><strong>}</strong></td>

  </tr>

 </tbody>

</table>

<table width="88">

 <tbody>

  <tr>

   <td width="88">SomeInterface</td>

  </tr>

 </tbody>

</table>

<table width="88">

 <tbody>

  <tr>

   <td width="88"><strong>SomeInterface</strong></td>

  </tr>

 </tbody>

</table>

In the example, we need a class that implements the  and an instance of such class. What’s more, we only need such instance only once. So we <strong>created an instance of an anonymous inner class that implements </strong>.

<table width="669">

 <tbody>

  <tr>

   <td colspan="3" width="669">Note this is the only time in Java you can see such syntax: a class implementing an interface without using</td>

  </tr>

  <tr>

   <td width="83">the keyword</td>

   <td width="68">implements</td>

   <td width="518">.</td>

  </tr>

 </tbody>

</table>

<h1>2  Java Reflection</h1>

Unlike Python, JavaScript, etc., Java is not a <em>dynamic programming language</em>. It relies heavily on the type of each class/variable. However, dynamically loading classes at runtime is important for object oriented programming. So, is it possible for Java to figure out attributes and methods of some random class? And is it possible to access these attributes, or invoke these methods? The answer is yes — the reflection guarantees such requests. It can:

<ul>

 <li>recognize any class <strong>at runtime</strong>;</li>

 <li>construct an instance of any class <strong>at runtime</strong>;  recognize the attributes and method <strong>at runtime</strong>;          invoke methods of an instance <strong>at runtime</strong>.</li>

</ul>

<table width="691">

 <tbody>

  <tr>

   <td width="299">Here is a quick example — you have used the</td>

   <td width="94">SimpleWriter1L</td>

   <td width="297"> in Lab 1 like this:</td>

  </tr>

  <tr>

   <td colspan="3" width="691"><strong>import</strong> components.simplewriter.SimpleWriter1L<strong>;</strong>SimpleWriter1L out <strong>=</strong> <strong>new</strong> SimpleWriter1L<strong>();</strong>      <em>// Initialize</em> out<strong>.</strong>println<strong>(</strong>“Hello World!”<strong>);</strong>                    <em>// Invoke</em> out<strong>.</strong>close<strong>();</strong></td>

  </tr>

 </tbody>

</table>

But to use reflection, you do it like this:

<table width="691">

 <tbody>

  <tr>

   <td width="691">Class<strong>&lt;?&gt;</strong> simpleWriter1L <strong>=</strong> Class<strong>.</strong>forName<strong>(</strong>“components.simplewriter.SimpleWriter1L”<strong>);</strong>  <em>// Load</em>Object out <strong>=</strong> simpleWriter1L<strong>.</strong>newInstance<strong>();</strong>                                          <em>// Initialize</em> Method println <strong>=</strong> simpleWriter1L<strong>.</strong>getDeclaredMethod<strong>(</strong>“println”<strong>,</strong> String<strong>.</strong>class<strong>);</strong>         <em>// Invoke</em> println<strong>.</strong>invoke<strong>(</strong>out<strong>,</strong> “Hello World!”<strong>);</strong>Method close <strong>=</strong> simpleWriter1L<strong>.</strong>getDeclaredMethod<strong>(</strong>“close”<strong>);</strong> close<strong>.</strong>invoke<strong>(</strong>out<strong>);</strong></td>

  </tr>

 </tbody>

</table>

It seems reflection is more complicated, but why do we need it? One of the answers can be found in Deliverable 2. So let’s start do it.

<h1>3  Deliverable 1 — Cuboid</h1>

Suppose we have an array of cuboids:

Cuboid<strong>[]</strong> Cuboids <strong>=</strong> <strong>new</strong> Cuboid<strong>[</strong>5<strong>];</strong>

<table width="41">

 <tbody>

  <tr>

   <td width="41">Cuboid</td>

  </tr>

 </tbody>

</table>

We want to sort a them: (1) by length; (2) by area; (3) by volume; and lastly (4) by length first and then area. We don’t want to change the  class.

<table width="140">

 <tbody>

  <tr>

   <td width="140">java.util.Arrays.sort</td>

  </tr>

 </tbody>

</table>

<ol>

 <li>For each sorting procedure, sse the method;</li>

</ol>

<table width="481">

 <tbody>

  <tr>

   <td width="140">java.util.Arrays.sort</td>

   <td width="207"> method a class that implements</td>

   <td width="134">java.util.Comparator</td>

  </tr>

 </tbody>

</table>

<ol start="2">

 <li>Supply each ;</li>

</ol>

Write and run your code.

<strong>DEMO this deliverable to the lab instructor (10 points).</strong>

<h1>4  Deliverable 2 — Last Call: Fix the Design Pattern</h1>

In lab 3, you were presented with a design pattern. While the pattern represented a great idea, our implementation of that idea stunk! Big time!!

<table width="68">

 <tbody>

  <tr>

   <td width="68">AnimalType</td>

  </tr>

 </tbody>

</table>

Specifically, if you look at the class  … the code sucks!!! It has two massive problems:

<ol>

 <li>The conditional structure (Line 29 to Line 34) — this requires to be updated every time a new animal type enters the system (it also needs to be updated if an animal type leaves the code base — yes, those todo’s causing problems again). That is, the conditional structure is inflexible and needs to be removed.</li>

</ol>

<table width="68">

 <tbody>

  <tr>

   <td width="68">AnimalType</td>

  </tr>

 </tbody>

</table>

<table width="68">

 <tbody>

  <tr>

   <td width="68">new Lion()</td>

  </tr>

 </tbody>

</table>

<ol start="2">

 <li>needs to know about the animal types — crazy! It needs to know that mice are small — insane!! And it needs to know how to create each animal ( for example) — madness!!!</li>

</ol>

<table width="68">

 <tbody>

  <tr>

   <td width="68">AnimalType</td>

  </tr>

 </tbody>

</table>

Rewrite :

<ol>

 <li>to avoid using a conditional structure;</li>

</ol>

<table width="68">

 <tbody>

  <tr>

   <td width="68">AnimalType</td>

  </tr>

 </tbody>

</table>

<ol start="2">

 <li>so it knows NOTHING about the animals it handles. It may still need to accommodate a variable that stores different animal types, but the code in must remain CONSTANT whenever animal types are changed. <strong>HINT</strong>: think <a href="https://docs.oracle.com/javase/tutorial/reflect/"><em>reflection</em></a><a href="https://docs.oracle.com/javase/tutorial/reflect/">.</a></li>

</ol>