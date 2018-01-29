---
layout: post
title: Understanding Toml 
tags: toml yaml python learning
---

<div class="img_center">
![Toml Logo]({{ site.baseurl }}/images/toml-logo.png "Toml Logo in Greyscale")
</div>

In the past I have used .ini files for Python config, while an older format it is easy to understand and has std-lib support with [configparser](https://docs.python.org/3/library/configparser.html "Python 3.6 Documentation - ConfigParser"). Since starting with Jekyll I have gotten used to working with ymal files, since my pdf reading project needs a config file I started to use ymal. But while looking for yaml on python docs I ran across several threads about yaml vs toml.  

Reading through them changed my mind about using yaml.
Reasons important to me to choose Toml:

-   Default config format for Rust-Cargo
-   Default config format for Pipenv
-   Similar structure to .ini
-   Clear way to next tables
-   More strongly typed than yaml 
-   Younger than yaml or JSON

### Resources

[Reddit - Yaml vs Toml](https://www.reddit.com/r/devops/comments/6f82nu/yaml_vs_toml/)

[Toml Style Guide](https://github.com/toml-lang/toml#user-content-example "Toml Repository - Content Examples")

[Hugo - Toml vs JSON vs Yaml ](https://gohugohq.com/howto/toml-json-yaml-comparison/ "Hugo Documentation - Toml vs JSON vs Yaml")
