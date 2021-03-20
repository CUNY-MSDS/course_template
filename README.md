Template for MSDS Courses
================

## Recommendations for a successful online course

The design of successful online courses requires special considerations
as compared to traditional classroom based instruction. Joosten and
Cusatis (2019) studied the characteristics of successful online courses
and identified eight indicators for successful course (see the National
Research Center for [Distance Education and Technological
Advancements](https://uwm.edu/deta/) figure below). To address these
characteristics at CUNY SPS for the Master’s in Data Science (MSDS)
program, we have outlined the following specific components MSDS courses
should have:

-   Clearly define learning objectives both for the overall course as
    well as each learning module.

-   Organize the course with all required assignments, with due dates,
    available at the beginning of the semester. This will allow students
    to schedule their time and know when large assignements are due.

-   An introductory video that introduces yourself, explains the course
    organization, and clearly articulates student expectations.

-   Use a *variety of assessments* throughout the semester that give
    students an opportunity to apply the knowledge and skills outlined
    in the learning objectives.

    -   *Formative assessment(s)* given at the beginning of the semester
        can help you and students understand where they are vis-à-vis
        prior knowledge. These should not be graded and any course
        points should be given on did or did not do basis.

    -   Most, if not all, courses should have a culminating project
        where students apply the skills and knowledge obtained in the
        course.

-   Weekly meetings of approximately one hour.

    -   Although we cannot strictly require students to attend a
        synchronous meeting, we can expect (require) students to watch
        the meetings. Recordings should be made available as soon as
        possible.

    -   The meetings should have some direct instruction. For example,
        explaining key concepts or walking through an analysis are good
        use of this time.

    -   Weekly meetings are a good time to share your own experiences
        regarding the current topic. Providing examples beyond the
        course materials (e.g. textbook) exposes students to the issues
        of applying the theoretical concepts to “real world” problems.

-   Value student engagement/participation. Admittedly the evaluation of
    student engagement and participation is difficult, especially in an
    asynchronous environment. One approach is the use of one minute
    papaers (Angelo & Cross, 1993; see also [Bali,
    2015](https://topr.online.ucf.edu/use-minute-paper-to-evaluate-student-participation/)
    for an applied use). The one minute paper asks students to answer
    the two questions at the completion of a class: 1. What was the most
    important thing you learned during this class? and 2. What important
    question remains unanswered for you? The one minute paper not only
    provides an opportunity to check student understanding, but any
    misconceptions can be addressed (retaught) either in a follow-up
    written communication or during the next meeting.

-   Create a climate of open student-to-instructor and
    student-to-student communication. There are a number of
    technological options available including Blackboard discussion
    boards and/or Slack (the free version is typically sufficient for
    MSDS courses).

![DETA DETA Online Course Quallity
Indicators](images/DETA_Online_Course_Quallity_Indicators.jpg)

**Resources**

These are some resources that may be helpful for course design and
teaching:

-   [The SUNY Online Course Quality Review Rubric
    OSCQR](https://oscqr.suny.edu)
-   [Github Teachers Toolbox](https://education.github.com/toolbox)
-   [Happy Git and GitHub for the useR](https://happygitwithr.com)
-   [Delivering High-Quality Instruction Online in Response to
    COVID-19](Resources/Faculty-Playbook_Final-1.pdf)

**References**

Angelo, T.A. & Cross, K.P. (1993). *Classroom Assessment Techniques, 2nd
ed.* San Francisco: Jossey-Bass.

Joosten, T., Cusatis, R., & Harness, L. (2019). [A cross-institutional
study of instructional characteristics and student outcomes: Are quality
indicators of online courses able to predict student
success?](https://olj.onlinelearningconsortium.org/index.php/olj/article/view/1432)
*Online Learning Journal, 23*(4).

Hermans, F. (2019). [Explicit Direct Instruction in Programming
Education](https://rstudio.com/resources/rstudioconf-2019/explicit-direct-instruction-in-programming-education/).
Talk given at 2019 RStudio::conf.

## Course Website

The course website is built created using the
[Blogdown](https://bookdown.org/yihui/blogdown) which extends the
[Hugo](https://gohugo.io) framework for generating static websites with
the use of RMarkdown files. Specifically, Blogdown will first convert
`Rmd` files to `md` files before being converted to HTML by Hugo. By
default, this repository will use the
[Techdoc](https://github.com/thingsym/hugo-theme-techdoc) theme.
Documentation on configuring the website is available here:
<https://themes.gohugo.io/theme/hugo-theme-techdoc/>

``` r
install.packages(c('blogdown', 'tidyverse', 'devtools', 'ggweekly', 'rlang', 
                   'stringr', 'configr', 'readxl', 'lubridate', 'XML')


blogdown::hugo_version()
blogdown::install_hugo()
blogdown::update_hugo()
```

``` r
blogdown::new_site(dir = 'website',
                   theme = "thingsym/hugo-theme-techdoc",
                   format = 'toml', to_yaml = FALSE)
```

``` r
wd <- setwd('website'); blogdown::serve_site('website'); setwd(wd)
```

``` r
blogdown::stop_server()
```

#### Steps to modify the template for your course:

-   `Schedule.xml` - This Excel file has two tabs that need be modified.
    The `Schedule` tab lists the date ranges for each unit/module in the
    course. The `Meetups` tab lists the dates and times for each meetup.
    There are `Topic` and `Resources` columns to provide additional
    information for students. Note that any Markdown used in the columns
    will be converted. This is particularly useful for including links
    to slides or recordings.
-   `website/config.toml` - Modify this file with values corresponding
    to your course. This includes the following variables:
    -   `title` - The course title.
    -   `github_repository` - The Github URL for where the site is
        hosted.
    -   `github_doc_repository` - This is the same as
        `github_repository` with the addition of `/website`
        subdirectory.
    -   Under params, `title` - The course title.
    -   Under the menu section, the `url` for the Slack (or whichever
        communication system you use) should be set.
    -   Other menu items can be added or removed in this section (these
        appear accross the top of each page).
-   `website/content/course-overview/_index.md` - Edit course syllabus.
-   `website/content/course-overview/instructor.md`
-   `website/content/course-overview/schedule.Rmd`
-   `website/content/course-overview/meetups.Rmd`
-   `website/content/course-overview/textbooks.md`
-   `website/content/course-overview/software.md`
-   `website/content/course-overview/materials.Rmd`
-   Edit files in the `website/content/assignments/` folder. Each
    markdown file should correspond to a particular assignment in the
    course. The exact structure is entirely up to you, but by way of
    example a page for each common type of assignment is provided,
    namely homework (i.e. textbook assignments), labs, project, and
    exam(s). Pages can be deleted, renamed, or newly created depending
    on your structure.
-   Edit files in the `website/content/chapters/` folder. The purpose of
    these files is to provide information (e.g. course notes, links,
    videos, etc.) for each unit of study. If your units are organized
    around chapters of a textbook, this structure may work for you. If
    you design your own learning modules, the folder can be renamed
    (e.g. to `modules`) and files as appropriate to your course
    organization.
-   The markdown files in the `website/content/blog/` folder correspond
    to announcements, or news items. These will be listed on the course
    homepage or from the “Announcements” link on the top navigation bar.

#### Navigation Bar

There are two ways to include links on the top navigation bar. 1.
Specify links in the `config.toml`. Look for the `[menu]` section of the
configuration file for details. 2. Include `menu: "main"` in the YAML of
any markdown file you wish to have linked in the navigation bar. The
Meetup page is included in the navigation bar by default.

#### Building and Deploying the Site

The `blogdown::build_site('webiste')` function will build the website
into the `docs` subdirectory. This is the default location for Github
pages. Be sure to verify this on the settings page for the repository
under the “GitHub Pages” heading.

``` r
blogdown::build_site()
```

Additionally, you can configure a custom URL if you wish on the Github
settings page. Once the website is built, push the `docs` folder to your
Github repository.

## Learning Management System (LMS)

Coming soon…

## TODO

-   Create icon for each site
-   Update og-image.png
