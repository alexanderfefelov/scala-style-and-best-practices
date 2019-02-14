# Scala Style and Best Practices

- [Databricks Scala Guide](https://github.com/databricks/scala-style-guide)  - Databricks

    > With over 1000 contributors, Apache Spark is to the best of our knowledge the largest open-source project in Big Data and the most active project written in Scala. This guide draws from our experience coaching and working with engineers contributing to Spark as well as our Databricks engineering team.
    >
    > Code is written once by its author, but read and modified multiple times by lots of other engineers. As most bugs actually come from future modification of the code, we need to optimize our codebase for long-term, global readability and maintainability. The best way to achieve this is to write simple code.
    >
    > Scala is an incredibly powerful language that is capable of many paradigms. We have found that the following guidelines work well for us on projects with high velocity. Depending on the needs of your team, your mileage might vary.

- [Scala Best Practices](https://github.com/alexandru/scala-best-practices) - Alexandru Nedelcu

    > A collection of best practices, friendly to people that want to contribute.

- [Scala Best Practices](https://nrinaudo.github.io/scala-best-practices/) - Nicolas Rinaudo

    > I often find myself, both professionaly and otherwise, having to explain bits of Scala to newcomers to the language (but usually not new to programming).
    >
    > Something that’s becoming increasingly obvious is that Scala developers follow a certain set of unspoken rules without really thinking about them, and never really explain them to beginners. This is not helping Scala’s reputation as a hard to learn language, which is unfortunate - it’s a language I enjoy and wish more people would learn.
    >
    > This site is meant to address that, by listing and explaining all these rules I wish someone’d told me about when I was learning the language.
    >
    > Comments, suggestions, … are welcome! I’m clearly not the best Scala developer out there and might have gotten things wrong, or right for the wrong reasons. If you see areas that could be improved on, feel free to open an issue!

## Type Safety

- [Strings are not the type you are looking for](https://pedrorijo.com/blog/strings-as-types/) - Pedro Rijo

    > Statically vs dynamically typed languages is one of those eternal wars among developers.
    >
    > One of the arguments that statically typed programming language developers (like Java, Scala, and Haskell) often use when arguing to defend their choice, is that the type system helps catching many bugs before the code goes into production.
    >
    > I don’t want to discuss if you should use statically or dynamically typed languages, but I would like to show that we don’t always leverage the type system as much as we could on statically typed languages. The common pitfall happens by using the type java.lang.String to encode many different concepts, allowing some easy-to-prevent bugs.

- [Strategic Scala Style: Practical Type Safety](http://www.lihaoyi.com/post/StrategicScalaStylePracticalTypeSafety.html) - Li Haoyi

    > This post explores how you can make use of the type-safety of the Scala programming language to help catch the mistakes you make when writing Scala programs.
    >
    > While Scala is has a compiler that can help you catch errors, and many call it "type-safe", there is in fact a whole range of ways you can write Scala that provide greater- or lesser- amounts of safety. We will discuss various techniques that you can use to shift your code to the "safer" side of the spectrum. We'll consciously ignore the theoretical side of things with it's absolute proofs and logic, and focus on the practical side of how to make the Scala compiler catch more of your dumb bugs.

- [To tag a type](https://medium.com/iterators/to-tag-a-type-88dc344bb66c) - Marcin Rzeźnicki

    > A common need in type-safe code is the ability to tell various values apart. This is done to have the high degree of certainty that a value is used in a context where it is supposed to be used. On the most basic level types serve this exact purpose — val x: A and val y: B may be the most obvious example of separating values by labeling them with a type. But once programs start to get bigger, the inevitable thing happens — the types get re-used. This is especially a problem with common types like String or Int. The textbook example of this problem is a database id. Usually, the internal representation of such a value is, in fact, a number or UUID — so at some level it is correct to say case class User(id: Long, …). But the specifics of internal representation quickly stop to adhere to the meaning being attached to the value. Once you have case class User(id: Long, …) co-existing with case class Transaction(id: Long, …), both ids start to become interchangeable, by the principle of having the same type, while clearly they should not be because, logically, id-of-transaction has no meaning as id-of-user and vice-versa. The bigger the domain, the more values share the same representation (after all, almost anything can be thought of as string) but do not share the same meaning.
