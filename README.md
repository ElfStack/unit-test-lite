# Unit
 ElfStack\Unit is a easy-to-use unit test class, not providing much function but light and easy.

## Quick overview
 Let's see a code example:
```
use ElfStack\Unit;

$unit = new Unit();

$unit->start('Unit test group name(can be null)');

$str = 'Hello World!';
$unit->describe('First way to use', 'Here comes more info')->expect($str)->toBe('Hello World');

$unit->describe('Simple compare', 'You can also use not to be')->expect($str)->notToBe(null);

$unit->assertEqual('You can also use this way to run a test', $str, 'Hello World!', 'More info comes here now');

$unit->assertUnequal('Unequal method', $str, null);

$unit->assert('You can use user defined functions too.', function () use ($str) {
	echo 'Output in function will shows too.';
	return $str == true;
}, 'Any function call be recognized by `is_callable` can be called.<br>The function\'s output and return value are displayed as `Expected` and `Got`.');

$unit->printResult();


$unit->start();
$var = 1 + 1;
$unit->assertEqual('You can use `start` method to start another group of unit test.', $var, 2,
						 'You can print result in one page too.<br>You can use `result` method to get result without output it.');
echo $unit->result();
```

 And you will got(show as 67%):

![Unit Test Report](https://github.com/Tamce/outter-img/raw/master/UnitTestReport.png)

## Usage
```
composer require elfstack/unit-test-light
```
