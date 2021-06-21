# ReportPortal agent for PHP Codeception framework

Specific class to integrate Codeception-based test framework with Report Portal (http://reportportal.io/).

### Install:
1) Using composer
    1) Update your project's composer.json file with next data:
        ```json
        "require": {
            "osi-open-source/reporting-portal-agent-codeception": "*"
        },
        ```
        Execute command:
        ```shell script
        composer update
        ```
    2) Or execute command:
        ```shell script
        composer require osi-open-source/reporting-portal-agent-codeception
        ```
2) Update codeception.yml file of your test framework according to codeception.yml file in this repository.
     ```yaml
     extensions:
        enabled:
            - ...
            - ReportingPortalAgent:
                UUID: 07104d6b-45a0-442f-b7ed-a79fa5321123
                host: https://report-portal.example.com
                projectName: your_name_personal
                timeZone: .000+00:00
                launchName: testLaunchName!!!
                tags: tag1value,tag2value
                launchDescription: test launch description !!!
     ```
The description and tags string can be templated from the environment variables using the `{<VAR_NAME>}` syntax. For example if before a test run the env var `SUITE` is set to for example `my service` then the description "Launch {SUITE}" will be templated into "Launch my service".

Tags string must be coma separated string without spaces.

3) Run codeception tests as usual:
    ```shell script
    vendor/bin/codecept run
    ```
