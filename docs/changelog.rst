Changelog
=========

0.4
---

* New plugin: Added nose2.plugins.layers to support Zope testing style
  fixture layers.

* New tool: Added nose2.tools.such, a spec-like DSL for writing tests
  with layers.

0.3
---

* New plugin: Added nose2.plugins.mp to support distributing test runs
  across multiple processes.

* New plugin: Added nose2.plugins.testclasses to support loading tests
  from ordinary classes that are not subclasses of unittest.TestCase.

* The default script target was changed from ``nose2.main`` to ``nose2.discover``.
  The former may still be used for running a single module of teststs,
  unittest-style. The latter ignores the ``module`` argument. Thanks to
  @dtcaciuc for the bug report (#32).

* ``nose2.main.PluggableTestProgram`` now accepts an ``extraHooks`` keyword
  argument, which allows attaching arbitrary objects to the hooks system.

* Bug: Fixed bug that caused Skip reason to always be set to ``None``.

0.2
---

* New plugin: Added nose2.plugins.junitxml to support jUnit XML output.

* New plugin: Added nose2.plugins.attrib to support test filtering by
  attributes.

* New hook: Added afterTestRun hook, moved result report output calls
  to that hook. This prevents plugin ordering issues with the
  stopTestRun hook (which still exists, and fires before
  afterTestRun).

* Bug: Fixed bug in loading of tests by name that caused ImportErrors
  to be silently ignored.

* Bug: Fixed missing __unittest flag in several modules. Thanks to
  Wouter Overmeire for the patch.

* Bug: Fixed module fixture calls for function, generator and param tests.

* Bug: Fixed passing of command-line argument values to list
  options. Before this fix, lists of lists would be appended to the
  option target. Now, the option target list is extended with the new
  values. Thanks to memedough for the bug report.

0.1
---

Initial release.
