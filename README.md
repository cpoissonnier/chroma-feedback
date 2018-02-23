Chroma Feedback
===============

> Turn your Razer keyboard, mouse or headphone into a extreme feedback device.

[![Build Status](https://img.shields.io/travis/redaxmedia/chroma-feedback.svg)](https://travis-ci.org/redaxmedia/chroma-feedback)
[![Build Status](https://img.shields.io/appveyor/ci/redaxmedia/chroma-feedback.svg)](https://ci.appveyor.com/project/redaxmedia/chroma-feedback)
[![Build Status](https://img.shields.io/circleci/project/github/redaxmedia/chroma-feedback.svg)](https://circleci.com/gh/redaxmedia/chroma-feedback)
[![PyPI](https://img.shields.io/pypi/v/chroma-feedback.svg)](https://pypi.org/project/chroma-feedback)
[![License](https://img.shields.io/pypi/l/chroma-feedback.svg)](https://pypi.org/project/chroma-feedback)


Preview
-------

![Terminal Session](https://cdn.rawgit.com/redaxmedia/media/master/chroma-feedback/terminal-session.svg)


Installation
------------

Install the required OpenRazer driver:

* [Ubuntu / Linux Mint](https://openrazer.github.io/#ubuntu)
* [Debian](https://openrazer.github.io/#debian)
* [Arch Linux](https://openrazer.github.io/#arch)
* [Fedora](https://openrazer.github.io/#fedora)
* [openSUSE](https://openrazer.github.io/#opensuse)
* [Gentoo](https://openrazer.github.io/#gentoo)

Install Chroma Feedback using PyPI:

```
pip install chroma-feedback
```

Install Chroma Feedback using GitHub:

```
git clone https://github.com/redaxmedia/chroma-feedback.git
cd chroma-feedback
./setup.py install
```


Usage
-----

```
chroma-feedback [options]

-V, --version
-P, --provider <provider>
-H, --host <host>
-S, --slug <slug>
-T, --token <token>
-I, --background-interval <background-interval>
-B, --background-run
-D, --dry-run
-h, --help
```


Examples
--------

**AppVeyor**

Monitor a single project by slug:

```
chroma-feedback --provider=appveyor --slug=redaxmedia/chroma-feedback
```

Monitor multiple projects by authentication:

```
chroma-feedback --provider=appveyor --token={TOKEN}
```

**Circle**

Monitor a single project by slug:

```
chroma-feedback --provider=circle --slug=github/redaxmedia/chroma-feedback
```

Monitor multiple projects by authentication:

```
chroma-feedback --provider=circle --token={TOKEN}
```

**Jenkins**

Monitor a single project by slug:

```
chroma-feedback --provider=jenkins --host={HOST} --slug={SLUG}
```

Monitor multiple projects by slug:

```
chroma-feedback --provider=jenkins --host={HOST} --slug={SLUG} --slug={SLUG}
```

**Travis**

Monitor a single project by slug:

```
chroma-feedback --provider=travis --slug=redaxmedia/chrome-feedback
```

Monitor multiple projects by user:

```
chroma-feedback --provider=travis --slug=redaxmedia
```


Errors
------

| Message          | Type        | Description                                     |
|------------------|-------------|-------------------------------------------------|
| Driver not found | ImportError | Module `openrazer.client` could not be imported |
| Daemon not found | Exception   | The `DeviceManager` throwed a `DaemonNotFound`  |
| Device not found | General     | There is no supported device connected          |
| Data not found   | General     | There is no data available for your request     |


Indicators
----------

| Status  | Color  | Effect  |
|---------|--------|---------|
| Process | Yellow | Static  |
| Passed  | Green  | Static  |
| Errored | White  | Pulsate |
| Failed  | Red    | Pulsate |
