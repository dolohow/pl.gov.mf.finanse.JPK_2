Flatpak for "Klient JPK 2.0"
===========================

This repository consists source of flatpak package for polish JPK_VAT
program called "Klient JPK 2.0" created by
[Ministerstwo Finansów](http://www.finanse.mf.gov.pl/web/wp/pp/jpk/aplikacje-do-pobrania)


[Flatpak](http://flatpak.org/) is application sandbox.  Since this
program is proprietary I do not want to give him full access to my
system.


## Installation


### Full local build

Make sure you have installed those packages:
  * git
  * flatpak
  * flatpak-builder

Add flathub repository:
```shell
$ flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
```

Install SDK and runtime:
```shell
$ flatpak install flathub org.gnome.Sdk//3.26
$ flatpak install flathub org.gnome.Platform//3.26
```

Clone this repo or download the zip:
```shell
$ git clone https://github.com/dolohow/pl.gov.mf.finanse.JPK_2.git
```

Enter cloned directory:
```shell
$ cd pl.gov.mf.finanse.JPK_2
```

Build local repo:
```shell
$ flatpak-builder --repo=local JPK pl.gov.mf.finanse.JPK_2.json
```

Add repo:
```shell
$ flatpak --user remote-add --no-gpg-verify --if-not-exists dolohow local
```

Install the package:
```shell
$ flatpak --user install dolohow pl.gov.mf.finanse.JPK_2
```


### Binary Bundle
You can download bundle from [here](https://github.com/dolohow/pl.gov.mf.finanse.JPK_2/releases)

You can install them by just clicking or use this command:
```shell
$ flatpak build-import-bundle local dictionary.flatpak
```

Where `local` is your repo created by command:
```shell
$ flatpak build-import-bundle ~/my-apps dictionary.flatpak
```
