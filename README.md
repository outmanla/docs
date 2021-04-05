## <?php
/** 
 * @var string $db     Database
 * @var string $host   Host
 * @var int    $port   Port
 * @var array  $admin  Admin login data
 * @var array  $insert Insert login data
 * @var array  $select Select login data
 * @var array  $update Update login data
 * @var array  $delete Delete login data
 * @var array  $schema Schema login data
 * @var string $dbname Database name
 * @var string $prefix Table prefix
 * @var string $subdir Subdirectory path
 * @var string $tld    Top level domain
 */
return <<<EOT
<?php
/**
 * Orange Management
 *
 * PHP Version 7.2
 *
 * @package    Install
 * @copyright  Dennis Eichhorn
 * @license    OMS License 1.0
 * @version    1.0.0
 * @link       http://website.orange-management.de
 */
return [
    'db'       => [
        'core' => [
            'masters' => [
                'admin'  => [
                    'db'       => '$db', /* db type */
                    'host'     => '$host', /* db host address */
                    'port'     => '$port', /* db host port */
                    'login'    => '{$admin['login']}', /* db login name */
                    'password' => '{$admin['password']}', /* db login password */
                    'database' => '$dbname', /* db name */
                    'prefix'   => '$prefix', /* db table prefix */
                    'weight'   => 1000, /* db table prefix */
                ],
                'insert'  => [
                    'db'       => '$db', /* db type */
                    'host'     => '$host', /* db host address */
                    'port'     => '$port', /* db host port */
                    'login'    => '{$insert['login']}', /* db login name */
                    'password' => '{$insert['password']}', /* db login password */
                    'database' => '$dbname', /* db name */
                    'prefix'   => '$prefix', /* db table prefix */
                    'weight'   => 1000, /* db table prefix */
                ],
                'select'  => [
                    'db'       => '$db', /* db type */
                    'host'     => '$host', /* db host address */
                    'port'     => '$port', /* db host port */
                    'login'    => '{$select['login']}', /* db login name */
                    'password' => '{$select['password']}', /* db login password */
                    'database' => '$dbname', /* db name */
                    'prefix'   => '$prefix', /* db table prefix */
                    'weight'   => 1000, /* db table prefix */
                ],
                'update'  => [
                    'db'       => '$db', /* db type */
                    'host'     => '$host', /* db host address */
                    'port'     => '$port', /* db host port */
                    'login'    => '{$update['login']}', /* db login name */
                    'password' => '{$update['password']}', /* db login password */
                    'database' => '$dbname', /* db name */
                    'prefix'   => '$prefix', /* db table prefix */
                    'weight'   => 1000, /* db table prefix */
                ],
                'delete'  => [
                    'db'       => '$db', /* db type */
                    'host'     => '$host', /* db host address */
                    'port'     => '$port', /* db host port */
                    'login'    => '{$delete['login']}', /* db login name */
                    'password' => '{$delete['password']}', /* db login password */
                    'database' => '$dbname', /* db name */
                    'prefix'   => '$prefix', /* db table prefix */
                    'weight'   => 1000, /* db table prefix */
                ],
                'schema'  => [
                    'db'       => '$db', /* db type */
                    'host'     => '$host', /* db host address */
                    'port'     => '$port', /* db host port */
                    'login'    => '{$schema['login']}', /* db login name */
                    'password' => '{$schema['password']}', /* db login password */
                    'database' => '$dbname', /* db name */
                    'prefix'   => '$prefix', /* db table prefix */
                    'weight'   => 1000, /* db table prefix */
                ],
            ],
        ],
    ],
    'log'      => [
        'file' => [
            'path' => __DIR__ . '/Logs',
        ],
    ],
    'page'     => [
        'root'  => '$subdir',
        'https' => false,
    ],
    'socket'   => [
        'master' => [
            'host'  => '$tld',
            'limit' => 300,
            'port'  => 4310,
        ],
    ],
    'language' => [
        'en',
    ],
    'apis'     => [
    ]
];

EOT;
 cz.mtrakal.remoteview;

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
