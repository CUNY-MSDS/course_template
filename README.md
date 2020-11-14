Template for MSDS Course
================

## Course Website

The course website is built created using the
[Blogdown](https://bookdown.org/yihui/blogdown) which extends the
[Hugo](https://gohugo.io) framework for generating static websites with
the use of RMarkdown files. Specifically, Blogdown will first convert
`Rmd` files to `md` files before being converted to HTML by Hugo. By
default, this repository will use the
[Geekdoc](https://github.com/thegeeklab/hugo-geekdoc) theme.
Documentation on configuring the website is available here:
<https://geekdocs.de>

``` r
install.packages('blogdown') 

blogdown::hugo_version()
blogdown::install_hugo()
blogdown::update_hugo()

blogdown::new_site(theme = "thegeeklab/hugo-geekdoc")
```

``` r
blogdown::serve_site()
```

## Learning Management System (LMS) Creation (i.e. Blackboard)
