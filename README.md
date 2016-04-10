Math PHP
=====================

A math library for PHP in pure PHP. A work in progress.

Features
--------
 * Probability
     * Combinatorics
 * Statistics
     * Averages
     * Descriptive

Usage
-----

### Probability - Combinatorics
```php
use Math\Probability\Combinatorics;

// Factorial and permutations
$factorial    = Combinatorics::factorial(5);
$permutations = Combinatorics::permutations(5);

// Permutations n choose r
$n = 10;
$r = 4;
$permutations = Combinatorics::permutationsChooseR( $n, $r );

// Combinations
$combinations = Combinatorics::combinations( $n, $r );
$combinations = Combinatorics::combinationsWithRepetition( $n, $r );

// Multinomial Theorem
$n      = 10;
$groups = [ 5, 2, 3 ];
$divisions = Combinatorics::multinomialTheorem( $n, $groups );
```

### Statistics - Averages
```php
use Math\Statistics\Average;

$numbers = [ 13, 18, 13, 14, 13, 16, 14, 21, 13 ];

// Mean, median, mode
$mean   = Average::mean($numbers);
$median = Average::median($numbers);
$mode   = Average::mode($numbers); // Returns an array -- may be multimodal

// Averages report
// Returns array with keys: mean, median and mode
$averages = Average::getAverages($numbers);
```

### Statistics - Descriptive
```php
use Math\Statistics\Descriptive

$numbers = [ 13, 18, 13, 14, 13, 16, 14, 21, 13 ];

// Range and midrange
$range    = Descriptive::range($numbers);
$midrange = Descriptive::midrange($numbers);

// Variance (population and sample)
$σ² = Descriptive::populationVariance($numbers);
$S² = Descriptive::sampleVariance($numbers);

// Standard deviation
$σ = Descriptive::standardDeviation($numbers); // Has optional parameter to set population or sample variance

// MAD - mean/median absolute deviations
$mean_mad   = Descriptive::meanAbsoluteDeviation($numbers);
$median_mad = Descriptive::medianAbsoluteDeviation($numbers);

// Descriptive stats report
// Returns array with keys: mean, median, mode, range, midrange, variance, standard deviation
$stats = Descriptive::getStats($numbers); // Has optional parameter to set population or sample variance
```

Unit Tests
----------

```bash
$ cd tests
$ phpunit
```