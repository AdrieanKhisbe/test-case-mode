test-case-mode
==============

Unit test front-end for Emacs

[![Build Status](https://travis-ci.org/nschum/test-case-mode.png?branch=master)](https://travis-ci.org/nschum/test-case-mode)

`test-case-mode` is a minor mode for running unit tests.  It is extensible and
currently comes with back-ends for JUnit, CxxTest, CppUnit, gtest, Python and
Ruby.

The back-ends probably need some more path options to work correctly.
Please let me know, as I'm not an expert on all of them.

To install `test-case-mode`, use [Melpa](http://melpa.org/#/test-case-mode)

To enable it automatically when opening test files:

    (add-hook 'find-file-hook 'enable-test-case-mode-if-test)

If you want to run all visited tests after a compilation, add:

    (add-hook 'compilation-finish-functions
              'test-case-compilation-finish-run-all)

If failures have occurred, they are highlighted in the buffer and/or its
fringes (if fringe-helper.el is installed).

fringe-helper is available at:
http://nschum.de/src/emacs/fringe-helper/

Limitations:
C++ tests can be compiled in a multitude of ways.  test-case-mode currently
only supports running them if each test class comes in its own file.
