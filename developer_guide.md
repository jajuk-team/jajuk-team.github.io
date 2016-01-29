---
title: Developer guide
layout: default
---

# Developer guide

# Source Code Management
See the [Git](git.html) page.

### Copyright
- We have a single moral entity named "The Jajuk Team" that owns the copyright on all sources, please do not set your name in the file headers (BTW, make sure to use the provided code generation template, see bellow).
- Note that your credits are still available from various members lists, from the SCM system anyway and from [this page](/members.html).

### Developers mailing Lists
- [Jajuk developer mailing list](mailto:jajuk-developers@lists.sourceforge.net) is the project main communication stream. Note that the Reply-to is directed to the original sender, not the list so please use the "Reply all" button from you e-mail client to reply to the list.

### Java version
- Jajuk has to run on every JVM &gt;= 1.7
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

#### GUI threading conventions
- Every widget creation or change has to be done inside the EDT (Event Dispatching Thread). For more details, check  [this page](http://en.wikipedia.org/wiki/Event_dispatching_thread). This is currently endorsed through the Substance look and feel.
- Tasks that takes half a second or more to run (for a large collection) have to be done outside the EDT.
- When an operation requires long operations (done outside the EDT) and GUI updates afterwards (like downloading a picture and then displaying it), you have to use a the SwingWorker class.
- For views that provides a populate mechanism, use the Jajuk "TwoStepsDisplayable" pattern that abstracts the SwingWorker and makes code easier :
    - Your view shall implement the ``TwoStepsDisplayable`` interface and provide ``longCall()`` and ``shortCall()`` methods for actions done respectively outside and inside the EDT.
    - Use the ``UtilGUI.populate(TwoStepsDisplayable)`` method to populate the view and run the underlying SwingWorker.

#### Documentation
- Please document your features in English on this website.
- You may want to add new tips of the day in ``jajuk_properties`` file.

#### Layout Manager
- Jajuk official layout manager is the excellent [MigLayout](http://www.miglayout.com/). Please read the quick start guide and the [cheat sheet](http://www.migcalendar.com/miglayout/cheatsheet.html).
- Please use MigLayout in priority for every layout need, even simple cases as the resulting code is extremely simple to write, read and maintain. There are very few cases where you have to use others layout managers (like an Horizontal alignment between two items) or special cases (FlowLayout in CatalogView for ie)
- An excellent [Cheat Sheet](http://www.migcalendar.com/miglayout/cheatsheet.html) is available.
- Please read the Tutorial at [http://www.miglayout.com/](http://www.miglayout.com/)
- MigLayout is *really* powerful and simple. Even if it supports cell-kind layout management (like grid bag or TableLayout), Please try avoid to use them when possible (what happens when you want to add a widgets among existing elements in the future ?) but use the regular ``wrap`` mode instead (tell explicitly that you reached the end of a row), ``split`` and ``span``.
- In 99% of cases you don't need any inner panel
- MigLayout saves a lot of swing code like ``insets``, ``setMaxSize``, set horizontal/vertical gaps with Box etc... All of these information have to be set as MigLayout string constraints mainly within its constructor.

#### Validation
- To validation fields in forms, we use [Simple-validation](http://kenai.com/projects/simplevalidation), that's pretty good and non-intrusive.

#### Wizards
- Use [QDWizard](http://github.com/bflorat/qdwizard) to write complex wizards (see ``DJWizard`` as a example)
- Note that QDWizard contains its own error messages and validation scheme, we normally don't have to use an external validation lib when writing a wizard.

### Unit Testing
- Jajuk uses JUnit unit testing which is well integrated into Eclipse (Development IDE), [Jenkins (Continuous integration server)](http://integration.jajuk.info/) and Sonar (Code Quality Checking tool)

#### General Guidelines
The following guidelines should be observed when committing code changes:

- Each class ``src/main/java/...`` should have its corresponding test case in the same Java package under ``src/test/java/...``
- When implementing new features, please also create corresponding unit test cases or even better, follow [Test Driven Development principles](http://en.wikipedia.org/wiki/Test-driven_development).
- When changing existing classes, run related unit tests before checking in.
- It is not mandatory to run all tests manually on your machine, however please take a look at the [Jenkins build server](http://integration.jajuk.info/) after the next automated build and test run (usually done overnight) to ensure that no other test is broken now.
- Fix any unit test broken by your commit ASAP to avoid lengthy periods of broken Jenkins builds!

#### Utility classes/Helper methods
There is one class available as part of the current tests that provides basic helper methods: ``JUnitHelpers``. This class can be used for a number of small tasks that are often necessary when writing Unit Tests, it provides the following:

- ``createSessionDirectory()``: Creates a temporary working directory for Jajuk which can then be used for Workspace related tests.
- ``testPrivateConstructor()``: In some cases we add a private constuctor to classes that only have static members to prevent this class from being instantiated (which makes no sense at all). In order to get coverage for this constructor, we have a small helper:

{% highlight java %}
   // helper method to emma-coverage of the unused constructor
   public void testPrivateConstructor() throws Exception {
     JUnitHelpers.executePrivateConstructor([yourclass].class); 
   }
{% endhighlight %}
- ``EqualsTest()/CompareToTest()/ToStringTest()/CloneTest()/HashCodeTest()/EnumTest()``: These are helpers for testing the standard methods that are available in many classes, e.g. EqualsTest will verify many general "rules" on equalness that are specified by the Java language definition and which can have side effects if not implemented correctly.
- ``clearSwingUtilitiesQueue()/waitForThreadToFinish()/waitForAllWorkToFinishAndCleanup()``: Helpers when testing Swing-related code. They allow to clean out the queue of asynchronous events and also to wait for threads and other things that are started. This avoid hard to trace errors in tests when things are started in the background by some classes.
- ``getFile()``: creates and registers a music-file.
- ``getTrack()``: creates and registers a music-track.
- ``MockPlayer``: A helper class that implements the Player interface.

Additionally we provide a class ``JajukTestCase`` which calls the ``waitForAllWorkToFinishAndCleanup()``. This is useful when testing classes that always require cleanup before starting tests.

#### Headless mode
- In order to have Unit tests running on Continuous Integration platforms like Jenkins, all unit tests must run without UI interaction and without accessing any of the UI functionality from AWT/Swing. Naturally this prevents some things from being tested via unit tests, but on the other hand it ensures that all tests execute without popping up a message box and waiting endlessly for the user to press a button, something that is not useful for unit tests at all.
- In order to run the unit tests locally with the same setting to disable UI support in Java, please add the following setting to the run-configuration of Eclipse or any tool used to execute unit tests: ``-Djava.awt.headless=true`` 
As result of this, any place where UI is used will throw an "HeadlessException" that we need to ignore for tests, i.e. the test should still succeed, even if the HeadlessException is thrown.

### Development hits and available features

#### Guava
We use Guava, the excellent toolbox from Google. Don't hesitate to use features from Guava (Jajuk 1.9 uses Guava R11) to reduce the number of code lines and increase the code quality. Check [Guava javadoc](http://code.google.com/p/guava-libraries/).

#### Using managers
Managers are the only way to access (list or change) items (Track, File, Type, Directory, Playlist, PlaylistFile, Device, Artist, album and Genre). For example, listing devices is done this way:

{% highlight java %}
DeviceManager.getInstance.getDevices()
{% endhighlight %}

Note that ``getXXXs()`` methods return copies that can be changed safely.

#### Anonymizer
- For any private data (track name, user info...), use double braces in logs. Example for Cover URL search:
{% highlight java %}
Log.debug({% raw %}"Search URL: {{" + sURL + "}}");{% endraw %}
{% endhighlight %}

- All strings between ``{{`` and ``}}`` are automatically replaced by ``***`` in quality agent.
- Use this method to get a list of tracks for a given item like an artist or an album : ``TrackManager.getAssociatedTracks()``

#### Utilities features
- The ``org.jajuk.utils.Util*`` classes contain many useful methods. Please check it to avoid reinventing the wheel but don't hesitate to add new features by yourself.

#### Files filters
- Jajuk provides a powerful ``JajukFileFilter`` class to filter files. Example: to keep only audio files or directories:

{% highlight java %}
new JajukFilter(false,JajukFileFilter.DirectoryFilter.getInstance(),
   JajukFileFilter.AudioFilter.getInstance());
{% endhighlight %}
- Jajuk provides several predefined filters: ``Audio``, ``NotAudio``, ``Playlist``, ``Directory``, ``KnownType``, ``AnyFile`` than can be used in conjunction using a ``AND`` or an ``OR`` between them.

#### Collection filters
- Jajuk uses Jakarta Commons-Collections features to filter collections. Filtering is done by using decorated iterators using Predicates. Example:
{% highlight java %}
Iterator it = new FilterIterator(tracks.iterator(),
  new JajukPredicates.AgePredicate(ConfigurationManager.getInt(CONF_OPTIONS_NOVELTIES_AGE)));
{% endhighlight %}

allows to iterate only on items of given age.

- New predicates should be centralized into the ``JajukPredicates`` class

#### Accessing to configuration files
- The Jajuk workspace (the directory where Jajuk stores all configuration files and indexes) is variable (by default ~/.jajuk in production and ~/.jajuk_test_&lt;version&gt; in developement mode - ie using the -test option). This is why you have to access configuration files this way:

{% highlight java %}
File fConfig = Util.getConfFileByPath(FILE_xxx);
{% endhighlight %}

and not trying to build the file path on your own

#### Design patterns

##### Singleton [GOF]
- Some Jajuk classes (mainly in ``org.jajuk.base``) are singletons, most of the time for serious reasons.
- Please avoid making a class a singleton if you have no good reason for that

##### Observer [GOF]
- Jajuk provides a full featured observer pattern implementation (supports details, is fully asynchronous, has a cache, an overflow controller, etc.)
- To register to events, a view has to implement Observer interface and provide a list of observed events this way:

{% highlight java %}
public Set<JajukEvents> getRegistrationKeys() {
  HashSet<EventSubject> eventSubjectSet = new HashSet<JajukEvents>();
  eventSubjectSet.add(JajukEvents.EVENT_DEVICE_MOUNT);
  eventSubjectSet.add(JajukEvents.EVENT_DEVICE_UNMOUNT);
  return eventSubjectSet;
}
{% endhighlight %}

- To handle events, look at this sample :
{% highlight java %}
public void update(JajukEvent event) {
  JajukEvents subject = event.getSubject();
  if (JajukEvents.EVENT_DEVICE_MOUNT.equals(subject)) {
    SwingUtilities.invokeLater(new Runnable() {
      public void run() {
	Util.waiting();
	refreshDevices();
	Util.stopWaiting();
    }
  });
}
{% endhighlight %}
- To notify an event :
{% highlight java %}
ObservationManager.notify(new JajukEvent(JajukEvents.DEVICE_MOUNT));
{% endhighlight %}

- If you want to make sure that a observer is updated before others, implements ``HighPriorityObserver`` instead of ``Observer`` (of course, you can set only a single high priority observer per subject).
<div class='warning'>
Do not notify more than a single event for one action (for performances and to avoid difficult concurrency issues in views that registrated all these events, we cannot ensure events ordering)
</div>

### D-Bus
See [these archives](/archives/D-Bus.html)

## Howtos

### How to get tracks for a given artist, album, year or genre ?
{% highlight java %}
TrackManager.getAssociatedTracks()
{% endhighlight %}

### How to get playable files for any item (logical or physical)?
{% highlight java %}
Util.getPlayableFiles()
{% endhighlight %}

### How to filter a list of items ?
{% highlight java %}
Filter.filterItems(&lt;list&gt;,&lt;property name&gt;,&lt;value&gt;)
{% endhighlight %}

### How to get the number of items (track, files...) ?
{% highlight java %}
[item type]Manager.getInstance().getElementCount()
{% endhighlight %}

### How to add a new option ?
- Add the option name in ``org.jajuk.util.Const``:

{% highlight java %}
public static final String CONF_AUDIOSCROBBLER_ENABLE = "jajuk.network.audioscrobbler"; 
{% endhighlight %}

- don't forget to set a default value in ``org.jajuk.util.Conf`` :
{% highlight java %}
properties.put(CONF_AUDIOSCROBBLER_ENABLE, FALSE);
{% endhighlight %}

- Use ``setProperty()`` method to set it in the program and ``getBoolean()``, ``getProperty()``, ``getInt()``... methods to retrieve it. Options are automatically saved to the ``conf.properties`` file at shutdown and loaded at startup.

### How are managed window startup sizes and positions ?
- Default size is set using this algorithm:
<pre>
begin
 width = screen width
 if width &gt; 1400  
   width = 1200  //deal with dual heads
 else
   width = screen width - 120
 height = screen height
 if height &gt; 1200  
  height = 1000  //deal with dual heads
 else
  height = screen height - 120
end
</pre>

- Then size is set at each startup using:
<pre>
begin
 if we find a forced position in conf.properties (jajuk.frame.forced_position entry)
  use this position/size (used to allow XGL users to force a position)
 else
  if window manager buggy
    Apply (60,60,screen width - 120, screen height - 120)
  else 
    if stored position (jajuk.window_position) contains "max" (maximalize)
      if window manager supports expand
      	expand (the window manager then deal with task bars)
      else
   	Apply (60,60,screen width - 120, screen height - 120)
    else
     int x = configurated x
     int y = configurated y
     int width = configurated width
     int height = configurated height
     if x &lt; 0 or x &gt; screen width
      x = 60
     if y &lt; 0 or y &gt; screen height
      y = 60
     if width &lt;= 0 or width &gt; screen width
      width = window width - 120
     if height &lt;= 0 or height &gt; screen height 
      height = screen height - 120
     Apply (x,y,width,height)
end
</pre>

### How to manage mouse events and right clicks ?
- Do not override directly ``MouseAdapter`` to manage mouse clicks but use ``JajukMouseAdapter`` class instead (see its detailed javadoc for reasons, handling right click on every OS is a bit complicated)
- Note that what makes all this a little complicated is the fact that most items can throw at the same time popup on right click and realize an action when the left click is recognized.

### How to use the font manager ?
- Please always use the ``FontManager`` class to deal with fonts for code factorization and performance
- If you don't find a required font in ``JajukFont`` enum, please create a new one (set its properties in the ``registerFonts()`` method)
- Fonts are accessed using  :
{% highlight java %}
FontManager.getInstance().getFont(&lt;a JajukFont&gt;)
{% endhighlight %}

### How to format dates ?
- Use ``UtilString.getLocaleDateFormatter()`` and ``UtilString.getAdditionDateFormatter()`` date formatters. The first method return the default date formatter for the current user and is intended for human display purpose. The second is used to store dates to be stored, it is the format used to store the date when tracks have been discovered (YYYYMMDD format)

### How to get good random value ?
- Use only this method to get random value (use the Mersenne twister algorithm):
{% highlight java %}
UtilSystem.getRandom()
{% endhighlight %}

## Traps

### Date format not thread safe
- Keep in mind that several threads cannot use the same ``DateFormat`` object (can throws ``OutOfBoundsException``), this applies to locale and addition formatters provided by jajuk (see how to format dates)

### canWrite() method
- Do not use the ``java.io.File.canWrite()`` method. Under Windows, it may return always false. Prefer to catch ``IOException``.

### SteppedComboBox fonts
- Do not use custom font for stepped comboboxes : the stepping doesn't work anymore for unknown reason

### Reading events properties
- If an event contains an non-string property to read, use ``get(&lt;property&gt;)`` to retrieve it. When using ``getProperty()`` method, the ``Property`` class returns ``null``.

### Trailing zeros
Do not use trailing ``0`` in integers like in :
{% highlight java %}
throw new JajukException(005);
{% endhighlight %}

but instead :
{% highlight java %}
throw new JajukException(5);
{% endhighlight %}

because ``005`` != ``5`` (octal)

### Char issue
Avoid using chars in strings building because a char + int + string =&gt; (int) + string. Example:
{% highlight java %}
String s = '('+33+") foo)"
{% endhighlight %}

### How to avoid memory leaks ?
- Use jconsole and/or visualvm to track class with high generations value (generations value is the number of concurrent generations alive). Use snapshots to compare generations values.
- Avoid using static inner classes : once loaded, they are never unloaded and are kept on non-heap space.
- Avoid using too much singletons pattern and static attributes
- Always clear collections after use if these collections are classes attributes.