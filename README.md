# ReportPortal agent for PHP Codeception framework

Specific class to integrate Codeception-based test framework with Report Portal (http://reportportal.io/).

### Install:
1) Using composer
    1) Update your project's composer.json file with next data:
        ```json
        "require": {
            "osi-open-source/reporting-portal-agent-codeception": "^0.2"
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
                launchDescription: test launch description !!!
     ```
3) Run codeception tests as usual:
    ```shell script
    vendor/bin/codecept run
    ```
