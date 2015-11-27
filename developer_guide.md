---
title: Developer guide
layout: default
---

# Developer guide

# Source Code Management
Jajuk uses GIT since 2011. All inscriptions can be found at the [Git](git.html) page.

### Natural Language
Jajuk team communication, code and comments have to be in English natural language only.

### Copyright
- A single moral entity named "The Jajuk Team" owns the copyright on all sources, please do not set your name in the file headers (BTW, make sure to use the provided code generation template, see bellow).
- Note that your credits are still available from various members lists and from the SCM system anyway.

### Developers mailing Lists
- [Jajuk developer mailing list](mailto:jajuk-developers@lists.sourceforge.net) is the project main communication stream. Subscription form is[here](http://lists.sourceforge.net/mailman/listinfo/jajuk-developers). Note that the Reply-to is directed to the original sender, not the list so please use the "Reply all" button from you e-mail client to reply to the list.

### Java version
- Jajuk has to run on every JVM &gt;= 1.6
- Prefer using Java 5+ classes and features (like collection for instead of iterators or, autoboxing, enums). Using generics is mandatory.

### IDE
We recommend the [Eclipse](http://www.eclipse.org/) platform. All following documentation is applicable to Eclipse only.
We use basically Eclipse built-in formater configuration with : 

- Line length = 100 (instead of 80 by default)
- Tabs = 4 spaces.
- Indentation : 2 spaces.
- No blank line inside a block.
- Formatter profile should be "Unmanaged" (this profile means you use the SCM conf file). To change the profile and share the changes, the only way we know is to hand-edit the .settings/<file> and commit/push it.
Only use UTF-8 and Unix-flavor new file carriage return for your source (Project -> Properties -> Text file encoding : UTF-8). Check these setting by selecting the project in the Package explorer -> Properties.

To launch jajuk from Eclipse, create a run configuration with :

- Name : ``jajuk``
- Main class : ``org.jajuk.Main``
- Program arguments : ``-ide -test`` 
- VM arguments are currently: `` -client -Xms20M -Xmx512M -XX:MinHeapFreeRatio=5 -XX:MaxHeapFreeRatio=10 -Djava.library.path=lib``

<div class='info'>
 <li>- ide argument tells jajuk that it is executing inside an IDE (probably Eclipse) . This changes the resources path (images, doc...).</li>
 <li>-test argument tells jajuk to use the ~/.jajuk_debug repository and not the ~/.jajuk, reserved for stable releases (this way a jajuk developer can use a stable release of jajuk when working on a new release) .</li>
</div>

### Code conventions

#### Eclipse formatter and templates

- Defaults templates are provided as Eclipse preference with the project. They are mainly Eclipse defaults templates with the Jajuk header for new files
- Defaults code formatter configuration is provided as well with the Eclipse project preferences. It is the Eclipse default template except a 100 for line max length.
- Don't use one line statement without braces: use ``if (){..one line..}``, not ``if (...)`` on a single line
- Note that the release packager applies source and import formatting over all the code at each release to make sure the formatting is always applied

#### String externalization

- All application labels have to be externalized (see [Translator Guide](/translator_guide.html)) with key names : &lt;Class name&gt;.&lt;number from 0&gt; .
- For common labels like OK, Cancel... we use generic externalized labels (see ``jajuk.properties``). Please keep number of generic labels to minimum and when creating new generic labels, keep in mind that some language (French, German...) are gender-specific in opposition to English.
- Do not reuse existing label ids but always increment a new number for new strings because removed labels can still be present in out-of-date langpacks. For the same reason, leave a comment in the English langpack if your remove the last label of a class (to avoid another developer to use the same ID). For exemple if a class ``Foo`` contains 15 labels ``Foo.0``, ``Foo.1``... ``Foo.14`` and if you have to remove ``Foo.14``, leave a comment #Do not use ``Foo.14``, continue to ``Foo.15``.
- Make sure to cleanup useless labels to reduce translators work.
- Debug logs are not externalized string but raw English strings.

#### Interfaces
Begin interfaces with a upper ' I '. The 'i' is not taken into account for variables naming: ``IPerspectiveManager pm;``

#### XML
- Avoid to use PCDATA values, use attributes instead : it's faster to parse and easier to code
- Use single quotes, not double quotes.

#### Comments
- For formatting reasons, use ``/* */`` for long comments in the methods, not several ``//``

#### Dead code
Please remove any dead code, SCM helps to recover any previous code anyway.
Tip : install the [http://www.ucdetector.org](http://www.ucdetector.org) eclipse plugin.

#### Class headers
- Please use the standard Jajuk header (see Eclipse templates configuration). Please do not use your own copyright but keep "The Jajuk Team" as owner.
- Make sure to use the template provided as Eclipse project preference

#### Code quality
Please keep Eclipse standard level of warnings (imports, static context...) and make sure to cleanup imports (Control-Alt-o).
Check the [Sonar analysis](http://nemo.sonarqube.org/dashboard/index/org.jajuk:jajuk), you may want to install the local Sonar plugin as well.

