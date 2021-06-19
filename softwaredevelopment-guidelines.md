The C0derulez
=============

The № 1 rule
------------

§1. Stickt to these rules, but occasionally break them where common sense requires. If you do, explain it, so that others can follow your thoughts.

Team building
-------------
§2. Occupy the team leadership twice from the beginning. The two should work in a team and share the management tasks. Nothing is more
cumbersome than a team leader who lacks for weeks. Designate one to be the responsible and make the decision in case of dispute.

§3. Recruit team leaders who have enough experience to not only know the rules of good programming, but also to have a sense of when to responsibly
break those rules. A good rule of thumb is a minimum of five years of work experience.

Team leading
------------

§4. It is your task to have understood all concepts in essence. Keep a wiki and document them there.

§5. Question the requirements. Understand the underlying goal before you start to create something.

§6. Ask about performance requirements.

§7. Establish rules and communicate them actively. You cannot count on everyone to notice rules that are anywhere in a file, especially not
for changes. If you do not like something, but it does not contradict any rule, accept it first. Then complete the rules according to your
ideas, communicate the changes, and then let the unsightly be patched up. Do not refuse other people’s work just because it does not meet
your expectations, which you did not communicate before. Believe that the contributor has done his best to fulfill the task, and that it
breaks his heart if his work is rejected due to violated secret rules.

Good Workmenship
----------------

§8. Design interfaces fair. A class should represent what its name describes, and a method should do what its name implies, nothing else and
nothing more.

§9. Follow the technical progress. Use new concepts, techniques and tools. Do not stick to old things, just so that others do not have to
learn anything new. They have to learn it anyway sooner or later.

ASCII files
-----------

§10. Be a professional programmer. Use unix line endings.

§11. Make use of UTF-8. Do not escape or replace characters just in fear that some tool might not properly support them. If that still
happens nowadays, the tool should be considered broken and needs to be fixed.

§12. The only allowed white character in text files is space. Do not use tabs. Escape all other white characters, for example in strings.

§13. Each file must end with a newline.

Programming
-----------

§14. Never try to do date and time calculation yourself. There are far too many exceptions to deal with, and it would be a safe bet that you
overlook one. Use a well-known library that has been reviewed by specialists.

§15. Always process collections with parallel streams, and explain cases that cannot be parallelized (unless they are completely obvious).

§16. Annotate fields and parameters that are `@Nullable` and methods whose result you or others need to `@CheckForNull`.

§17. Always use timeouts. Even if the sun has turned into a red dwarf, it is still a long way to infinity.

§18. Make case distinctions so that the `if`-block has fewer lines than the `else`-block.

§19. Describe the method contract with assert statements and make sure that they are checked in development operation.

§20. Implement an error barrier. Do not randomly catch `Exception` or `RuntimeException`, but *do so* on the topmost level of your code.
(For web applications, these are the form classes.) Not catching `RuntimeException` *at all* because “they should never happen” will bring
you into a bugfixing nightmare if a strange exception case happens on a live site and you are under pressure to fix it as fast as possible,
because of the business impact.

§21. Don’t misuse getters to generate some derived data. Data should generally be generated in the constructor, or in the method modifying
something, be stored in a field, and the getter should only return it. You would be surprised how often some frameworks invoke the getters
on classes. So keep your getters light-weight.

§22. Use static code analysis tools and try to understand what they are complaining about. Then use common sense to decide what you should 
change. Same is true for code style checkers. Think about what the tool complains about, but don’t let style checkers dictate you a rule
where it doesn’t make sense and, in the end, reduces the readability of your code.

Documentation
-------------

§23. Your code should explain itself. Give your fields and methods self-describing names. Never use systems hungarian notation!

§24. Write your code and documentation in American English. Put commas in your sentences. German developers: Read about how hyphens are used
in English—which is completely different from German—and stick to those rules.

§25. Import packages, not single classes. The list of packages gives the reader a first impression on what your class is dealing with. But,
the human brain is limited, and nobody reads a two-screens-long list of classes. (Import single classes only to resolve ambiguities.)

§26. Name boolean fields so that they mentally complete a sentence with the verb ‘to be’. (“This object is …”) Example: `havingLegs`. Not:
`legs` or `hasLegs`.

§27. Document a lot and explain in particular the non-obvious. Packages, classes and methods should generally be documented, but you do not
need to explain what “utils” are or why I/O exceptions can be thrown. Explain on getters what the field is for that can be read here. Note
on setters if the value to be set is subject to restrictions. Remember, a comment on the (typically `private`) field does not make it into
the final Javadoc.

§28. Each comment should start with a phrase (an expression that is starting with the verb, not a sentence) that summarizes the
functionality of the method and ends with a period. These are transferred to the overview page, where they will appear next to the name.
Example: “Gets a link.” Not: “Here links are retrieved.”

§29. If you’re referring to other classes, methods, or fields in comments, use the `{@link}` syntax, except in the first sentence. In the
first sentence, use the `{@code}` syntax.

Database
--------

§30. Never use blob fields for data that has a sensible representation as a string. They are a maintenance nightmare. Blob fields should
only be used for binary data. But imagine the size of the database dump and think twice about whether you really want to store the binary
data in the database.

§31. Use only lower case and underscore characters for table and field names. Mixed case is a migration obstacle when changing platforms.

§32. Define fields as `NOT NULL` if possible.

Tests
-----

§33. Use assert descriptions and phrase them so that they begin with the word “should”, mentally completing the sentence “The
function/result should …”. Example: “should return all employees”.

§34. Use Hamcrest matchers with JUnit because they produce better readable assert statements and especially better error messages on assert
violations.

Commits
-------

§35. Formulate commit messages so that they mentally complete the sentence: “If this commit will be merged, it will”. Example: “Remove dead
code”. Not: “Removes dead code”, nor “Some clean-up”. Use the text box to describe what the change does and for what purpose. Example:
“Removes the empty seats from the airplane so that no food is ordered for them.”

---
<small>Version: 2  
Contributors: Matthias Ronge ‹matthias.ronge@freenet.de›  
License: Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)</small>
