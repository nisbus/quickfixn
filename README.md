System Setup
------------
This project requires MSBuild, NUnit, and xsltproc.

You can get xsltproc via cygwin, or by installing libxslt (which requires
libxml2 and zlib).


Code Generation
---------------
To generate the code from Data Dictionaries, you need Ruby/JRuby (http://jruby.org/download) and the Nokogiri gem:

    gem install nokogiri
    ruby generator/generate.rb


Build
-----
To build the project, run:

    build.bat

You can also override the default target, configuration, and .NET framework version by giving command line arguments:

    build.bat Rebuild Release v3.5


The build.bat script expects MSBuild.exe to be on your PATH.  If you run it
from a Visual Studio cmd shell, this should not be a problem.  However, if you
run it from some other shell (e.g. cygwin), you may need to append something
like:

    C:\WINDOWS\Microsoft.NET\Framework\v3.5

to your PATH environment variable.


Unit Tests
----------
To run the NUnit tests, run:

    unit_test.bat

An HTML report of the test results will then be available here:

    UnitTests\bin\Release\UnitTests.html


Acceptance Tests
----------------
To run the full suite of acceptance tests:

    acceptance_test.bat

An HTML report of the test results will then be available here:

    AcceptanceTests\AcceptanceTests.html

To run one particular acceptance test, e.g. fix42\14e_IncorrectEnumValue.def:

    cd AcceptanceTests
    runat.bat release 5001 definitions\server\fix42\14e_IncorrectEnumValue.def

The test results will then be available in AcceptanceTests\TestResults.xml and
debug information will be available in the AcceptanceTests\log directory.



