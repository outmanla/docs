FotoRatan
=========

FotoRatan(图藤) is an open source software package for creating and supporting image hosting. It's written in Python and running on [Google App Engine](http://code.google.com/appengine), which is a free and robust cloud hosting infrastructure.

[FotoRatan.appspot.com](http://fotoratan.appspot.com/), also a demo of FotoRatan. It shows Some Friends' high-quality original work. To ask for testing account please mail to linuximo@gmail.com

FotoRatan is based on GAE image hosting program [diabloimage](http://code.google.com/p/diabloimage)

Features
--------
* Easy to use
* Host on Google App Engine
* Optimized for modern browsers
* Optimized font end for tablet or mobile devices
* HTML5

Installation
------------
It's recommended to get the latest codebase of FotoRatan with git:

        git clone git://github.com/Quasimo/FotoRatan.git
Then you can rename FotoRatan to whatever you want to match your own App Engine AppID. And follow the steps:

1.  Change app.yaml application to match your own AppID.
2.  Add this folder to Google App Engine Launcher as an existing application, and click Deploy. 
3.  End.

If you have any questions or feature requests, feel free to discuss it in official development node at [GeeKaa](http://geekaa3.appspot.com):
http://geekaa3.appspot.com/go/fotoratan

Usage
-----
1.  Put app's url in browser and key 'Enter' in your keyboard.
2.  Click "Upload!" button in the app then sign in via your app engine developer account.(*If your are using iPhone / iPod Touch you may not see the button*)
3.	Select a image in your computer and then click the upload button in this form.
4.	Can't you see online now?
5.	Click the "Sign out" link in footer to sign out.

Need Some Help!
---------------
* Larger Than 1Mb Upload Per File.
	*now just 1Mb, it's small.*
* Multiple Uploader
	*You can try http://YOUR-APP-URL/admin/upload2/ but it dosen't works.*
* Multiple User
	*Now you can invite other developers to collaborate on your application is [appengine](https://appengine.google.com/) dashboard > Administration > Permissions , then the developers are be able to upload images in your app, but User A can delete images that upload by User B now, I wish there some permissions to save one user's images that never deleted by others.*
* Site Configurator
	*To generate site infomations like title and descriptions, to create pages, to switch themes.*
* Theme
	*in static/themes*

Quota and Performance
---------------------
See [Google App Engine - Billing and Budgeting Resources](http://code.google.com/intl/en/appengine/docs/billing.html#Setting_a_Daily_Budget)

License
-------
FotoRatan under [GNU Lesser General Public License](http://www.gnu.org/licenses/lgpl.html)

Special Thanks
--------------
* [Benmao](http://github.com/benmao) *He created diabloimage that FotoRatan is base on.*
* [Livid](http://github.com/livid) *I love his works and this README is copies somethings from [Project Babel 2](http://github.com/livid/v2ex/blob/master/README.md)*
* [ZRUB](http://www.zurb.com) *[Absolutly, I love ZURB](http://geekaa3.appspot.com/t/201), I use the CSS3 buttons from them in FotoRatan.*
* [Fennel](http://chagallsilk.blogbus.com/) *Always support my works.*
* [Hgta](http://geekaa3.appspot.com/member/hgta) *Comrade in arms in these years.*package cz.mtrakal.remoteview;

import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }
}
 Docs <!-- omit in toc -->

This repository contains the documentation website code and Markdown source files for [docs.github.com](https://docs.github.com).

GitHub's Docs team works on pre-production content in a private repo that regularly syncs with this public repo.

In this article:

- [Contributing](#contributing)
- [READMEs](#readmes)
- [License](#license)

## Contributing

### Start contributing right now:

We accept a lot of [different contributions](CONTRIBUTING.md/#types-of-contributions-memo), including some that don't require you to write a single line of code.

#### Click **make a contribution** from docs

As you're using GitHub Docs, you may find something in an article that you'd like to add to, update, or change. Click on **make a contribution** to navigate directly to that article in the codebase, so that you can begin making your contribution.

<img src="./assets/images/contribution_cta.png" width="400">

#### Open an issue

If you've found a problem, you can open an issue using a [template](https://github.com/github/docs/issues/new/choose).

#### Solve an issue

If you have a solution to one of the open issues, you will need to fork the repository and submit a pull request using the [template](https://github.com/github/docs/blob/main/CONTRIBUTING.md#pull-request-template) that is visible automatically in the pull request body. For more details about this process, please check out [Getting Started with Contributing](/CONTRIBUTING.md).

#### Join us in discussions

We use GitHub Discussions to talk about all sorts of topics related to documentation and this site. For example: if you'd like help troubleshooting a PR, have a great new idea, or want to share something amazing you've learned in our docs, join us in [discussions](https://github.com/github/docs/discussions).

#### And that's it!

That's how you can get started easily as a member of the GitHub Documentation community. :sparkles:

If you want to know more, or you're making a more complex contribution, check out [Getting Started with Contributing](/CONTRIBUTING.md).

There are a few more things to know when you're getting started with this repo:

1. If you're having trouble with your GitHub account, contact [Support](https://support.github.com/contact).
2. We do not accept pull requests for translated content - see [CONTRIBUTING.md](/CONTRIBUTING.md) for more information.

## READMEs

In addition to the README you're reading right now, this repo includes other READMEs that describe the purpose of each subdirectory in more detail:

- [content/README.md](content/README.md)
- [content/graphql/README.md](content/graphql/README.md)
- [content/rest/README.md](content/rest/README.md)
- [contributing/README.md](contributing/README.md)
- [data/README.md](data/README.md)
- [data/reusables/README.md](data/reusables/README.md)
- [data/variables/README.md](data/variables/README.md)
- [includes/liquid-tags/README.md](includes/liquid-tags/README.md)
- [includes/README.md](includes/README.md)
- [javascripts/README.md](javascripts/README.md)
- [layouts/README.md](layouts/README.md)
- [lib/liquid-tags/README.md](lib/liquid-tags/README.md)
- [middleware/README.md](middleware/README.md)
- [script/README.md](script/README.md)
- [stylesheets/README.md](stylesheets/README.md)
- [tests/README.md](tests/README.md)

## License

The GitHub product documentation in the assets, content, and data folders are licensed under a [CC-BY license](LICENSE).

All other code in this repository is licensed under a [MIT license](LICENSE-CODE).

When using the GitHub logos, be sure to follow the [GitHub logo guidelines](https://github.com/logos).
