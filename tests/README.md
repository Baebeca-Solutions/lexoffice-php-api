This folder contains scripts for automated tests before new versions will be published.

To start a test execute ./test.php
All testscripts located in the subfolder "tests" will be executed and tested.

Test definition:
```php
// initiate test with test_start()
test_start('description of the test');

// do funny stuff and test your code
// log some output in your test
test('log some messages');

// compare exepcted output with output and decide if your test was successful
if ($something_is_true) {
    test_finished(true);
} else {
    test_finished(false);
}
```

Sample output
```
C:\Users\slutz\Downloads\php-7.1.1-nts-Win32-VC14-x64\php.exe C:\Users\slutz\Documents\GitHub\lexoffice-php-api\tests\test.php
20.11.2019 17:15:31 [] - include test: ./tests/001_webhooks.php
20.11.2019 17:15:31 [] - include test: ./tests/002_invoices.php
20.11.2019 17:15:31 [5dd574b3ef6ce] - start new test - 5dd574b3ef6ce
20.11.2019 17:15:31 [5dd574b3ef6ce] - description: create draft invoice
20.11.2019 17:15:33 [5dd574b3ef6ce] - draft invoice created - id: bcce6f19-e600-4641-b178-7691fa105635
20.11.2019 17:15:33 [5dd574b3ef6ce] ===> Testresult OK

20.11.2019 17:15:33 [] - include test: ./tests/010_error_handling.php
20.11.2019 17:15:33 [5dd574b50129b] - start new test - 5dd574b50129b
20.11.2019 17:15:33 [5dd574b50129b] - description: create draft invoice and download pdf (not possible)
20.11.2019 17:15:33 [5dd574b50129b] - draft invoice created - id: 66a0060d-b58c-4836-9cbe-5dfb1d8c59fa
20.11.2019 17:15:33 [5dd574b50129b] - try download pdf
20.11.2019 17:15:33 [5dd574b50129b] - lexoffice-php-api: error in api request - check details via $e->get_error()
20.11.2019 17:15:33 [5dd574b50129b] ===> Testresult OK


Process finished with exit code 0
``` 