#Cucumber-TestNg

##If you ever dreamt about running cucumber test with testng look into this project :).

#Configuration:
You need to put configuration file in your project like:

<b>src/test/resources/cucumber.properties</b> with content:

<pre><code>
# java package with steps classes in your project
cucumber.steps.package=com.yourpackage
</code></pre>

To check you didn't forget to implement TestNG @Test add such additional test:

<pre><code>
public class StateTest {

    @Test(priority = -1)
    public void testState() {
        // setup

        // act
        String result = CucumberTestsStateUtil.checkTests();

        // verify
        Assert.assertNull(result, result);
    }
}
</code></pre>

#Changelog:
<p>
<b>0.1.0<b>
</p>
<ul>
<li>
[+] Feature. Retry run failed test support added.
Need to be added java property at runtime -Dretry.tests=3 to rerun this test max 3 times more if it failed
at first run. 0 by default.
</li>
</ul>