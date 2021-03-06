== Changelog ==


= v3.27.0 - 2019-01-22 =
------------------------

###### Updates

+ Added the ability to add existing questions to a quiz in the course builder. This allows cloning of existing questions as well as attaching "orphaned" questions currently attached to no quizzes.
+ Added the ability to detach questions from quizzes. Coupled with adding existing questions, questions can now be easily moved between quizzes.
+ Added permalink capabilities to the builder to allow linking to specific items within the builder (a lesson, quiz, etc...).
+ Quizzes with 0 possible points will no longer show a Pass/Fail chart with a 0% (failing) grade on quiz results screens.
+ Replaced option `lifterlms_lock_down` which cannot be set via any setting with a filter to reduce database calls. This will have no effect on anyone unless you manually set this option to "no" via a database query. Having done this would allow the admin bar to be shown to students.

##### Bug Fixes

+ Fixed an issue causing the default "Redeem Voucher" and "My Orders" student dashboard endpoint slugs from not having the correct default values. Thanks [@tnorthcutt](https://github.com/tnorthcutt)!
+ Fixed an issue causing quotation marks in quiz question answers to show escaping slashes on results screens.
+ Fixed a bug preventing viewing quiz results for quizzes with questions that have been deleted.
+ Fixed a bug causing a PHP Notice to be output when registering a new user with a valid voucher.

##### Templates Changed

+ [quiz/results-attempt.php](https://github.com/gocodebox/lifterlms/blob/master/templates/quiz/results-attempt.php)


= v3.26.4 - 2019-01-16 =
------------------------

+ Update to [LifterLMS Blocks 1.3.2](https://make.lifterlms.com/2019/01/15/lifterlms-blocks-version-1-3-1/), fixing an issue preventing template actions from being removed from migrated courses & lessons.


= v3.26.3 - 2019-01-15 =
------------------------

##### Updates

+ Improved pagination methods on Student Dashboard Endpoints
+ "My Notifications" dashboard tab now consistently paginated like other dashboard endpoints
+ Update to [LifterLMS Blocks 1.3.1](https://make.lifterlms.com/2019/01/15/lifterlms-blocks-version-1-3-1/).

##### Bug Fixes

+ Fixed an issue preventing course difficulty and course length from being edited when using various page builders.
+ Fixed issues causing errors on quiz reporting screens for quiz attempts made by deleted users.

##### Deprecated Functions

+ `LLMS_Student_Dashboard::output_notifications_content()` replaced with `lifterlms_template_student_dashboard_my_notifications()`

##### Templates Changed

+ [myaccount/my-notifications.php](https://github.com/gocodebox/lifterlms/blob/master/templates/myaccount/my-notifications.php)
+ [admin/reporting/tabs/quizzes/attempt.php](https://github.com/gocodebox/lifterlms/blob/master/templates/admin/reporting/tabs/quizzes/attempt.php)


= v3.26.2 - 2019-01-09 =
------------------------

+ Fast follow to fix incorrect version number pushed to the readme files for 3.26.1 which prevents upgrading to 3.26.1


= v3.26.1 - 2019-01-09 =
------------------------

##### Updates

+ Tested to WordPress 5.0.3
+ Student CSV reports will now bypass cached data during report generation.
+ Add course and membership catalog visibility settings into the block editor.
+ Includes LifterLMS Blocks 1.3.0.

##### Bug Fixes

+ Fixed issue preventing the course instructors metabox from displaying when using the classic editor plugin.
+ Fixed an issue causing membership background enrollment from processing when the course background processor is disabled via filters.
+ Fixed an issue causing errors when reviewing orders on the admin panel which were placed via a payment gateway which is no longer active.
+ Fixed an issue preventing course difficulty and course length from being edited when using the classic editor plugin.
+ Fixed a very convoluted conflict between LifterLMS, WooCommerce, and Elementor explained at https://github.com/gocodebox/lifterlms/issues/730.


= v3.26.0 - 2018-12-27 =
------------------------

+ Adds conditional support for page builders: Beaver Builder, Divi Builder, and Elementor.
+ Fixed issue causing LifterLMS core sales pages from outputting automatic content (like pricing tables) on migrated posts.
+ Student unenrollment calls always bypass cache during enrollment precheck.
+ Membership post type "name" label is now plural (as it is supposed to be).


= v3.25.4 - 2018-12-17 =
------------------------

+ Adds a filter (`llms_blocks_is_post_migrated`) to allow determining if a course or lesson has been migrated to the WP 5.0 block editor.
+ Added a filter (`llms_dashboard_courses_wp_query_args`) to the WP_Query used to display courses on the student dashboard.
+ Fixed issue on course builder causing prerequisites to not be saved when the first lesson in a course was selected as the prereq.
+ Fixed issue on course builder causing lesson settings to be inaccessible without first saving the lesson to the database.


= v3.25.3 - 2018-12-14 =
------------------------

+ Fixed compatibility issue with the Classic Editor plugin when it was added after a post was migrated to the new editor structure.


= v3.25.2 - 2018-12-13 =
------------------------

+ Added new filters to the `LLMS_Product` model.
+ Fix issue with student dashboard login redirect causing a white screen on initial login.


= v3.25.1 - 2018-12-12 =
------------------------

##### Updates

+ Editor blocks now display a lock icon when hovering/selecting a block which corresponds to the enrollment visibility settings of the block.
+ Removal of core actions is now handled by a general migrator function instead of by individual blocks.

##### Bug fixes

+ Fixed issue preventing strings from the lifterlms-blocks package from being translateable.
+ Fix issue causing block visibility options to not be properly set when enrollment visibility is first enabled for a block.
+ Fixed compatibility issue with Yoast SEO Premium redirect manager settings, thanks [@moorscode](https://github.com/moorscode)!
+ Fixed typo preventing tag size options (or filters) of course information block from functioning properly. Thanks [@tnorthcutt](https://github.com/tnorthcutt)!

##### Templates Changed

+ [templates/course/meta-wrapper-start.php](https://github.com/gocodebox/lifterlms/blob/master/templates/course/meta-wrapper-start.php)