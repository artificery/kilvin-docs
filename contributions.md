# Contribution Guide

- [Bug Reports](#bug-reports)
- [Which Branch?](#which-branch)
- [Compiled Assets](#compiled-assets)
- [Security Vulnerabilities](#security-vulnerabilities)
- [Coding Style](#coding-style)
    - [PHPDoc](#phpdoc)

<a name="bug-reports"></a>
## Bug Reports

To encourage active collaboration, Kilvin CMS strongly encourages pull requests, not just bug reports. "Bug reports" may also be sent in the form of a pull request containing a failing test.

However, if you file a bug report, your issue should contain a title and a clear description of the issue. You should also include as much relevant information as possible and a code sample that demonstrates the issue. The goal of a bug report is to make it easy for yourself - and others - to replicate the bug and develop a fix.

Remember, bug reports are created in the hope that others with the same problem will be able to collaborate with you on solving it. Do not expect that the bug report will automatically see any activity or that others will jump to fix it. Creating a bug report serves to help yourself and others start on the path of fixing the problem.

The Kilvin CMS source code is managed on GitHub, and there are repositories for specific projects:

<div class="content-list" markdown="1">
- [Kilvin CMS](https://github.com/artificery/kilvin)
- [Kilvin CMS Package](https://github.com/artificery/kilvin-cms)
- [Kilvin CMS Documentation](https://github.com/artificery/kilvin-docs)
</div>

<a name="which-branch"></a>
## Which Branch?

**All** bug fixes should be sent to the latest stable branch or to the [current LTS branch](/docs/{{version}}/releases#support-policy). Bug fixes should **never** be sent to the `master` branch unless they fix features that exist only in the upcoming release.

**Minor** features that are **fully backwards compatible** with the current Kilvin CMS release may be sent to the latest stable branch.

**Major** new features should always be sent to the `master` branch, which contains the upcoming Kilvin CMS release.

If you are unsure if your feature qualifies as a major or minor, please ask Paul Burdick at <a href="mailto:paul@reedmaniac.com">paul@reedmaniac.com</a>.

<a name="compiled-assets"></a>
## Compiled Assets

If you are submitting a change that will affect a compiled file, such as most of the files in `resources/sass` or `resources/js` of the `artificery/kilvin-cms` repository, do not commit the compiled files. Due to their large size, they cannot realistically be reviewed by a maintainer. This could be exploited as a way to inject malicious code into Kilvin CMS. In order to defensively prevent this, all compiled files will be generated and committed by the maintainers.

<a name="security-vulnerabilities"></a>
## Security Vulnerabilities

If you discover a security vulnerability within Kilvin CMS, please send an email to Paul Burdick at <a href="mailto:paul@reedmaniac.com">paul@reedmaniac.com</a>. All security vulnerabilities will be promptly addressed.

<a name="coding-style"></a>
## Coding Style

Kilvin CMS follows the [PSR-2](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-2-coding-style-guide.md) coding standard and the [PSR-4](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-4-autoloader.md) autoloading standard.

<a name="phpdoc"></a>
### PHPDoc

Below is an example of a valid Kilvin CMS documentation block. Note that the `@param` attribute is followed by two spaces, the argument type, two more spaces, and finally the variable name:

    /**
     * Register a binding with the container.
     *
     * @param  string|array  $abstract
     * @param  \Closure|string|null  $concrete
     * @param  bool  $shared
     * @return void
     * @throws \Exception
     */
    public function newFunction($abstract, $concrete = null, $shared = false)
    {
        //
    }
