# hackerrank-php
List of solved Hackerrank challenges in PHP language

# Practice > Algorithms > Warmup
- [Solve me first](https://www.hackerrank.com/challenges/solve-me-first/problem "Solve me first")
```php
function solveMeFirst($a,$b){
	return $a + $b;
}
```
- [Simple Array Sum](https://www.hackerrank.com/challenges/simple-array-sum/problem "Simple Array Sum")
```php
function simpleArraySum($ar) {
    $sum = 0;
    foreach($ar as $value){
        $sum+=$value;
    }
    return $sum;
}
```
- [Compare the Triplets](https://www.hackerrank.com/challenges/compare-the-triplets/problem "Compare the Triplets")
```php
function compareTriplets($a, $b) {
    $length = count($a);
    $aliceScore = 0;
    $bobScore = 0;
    for($i=0; $i<$length; $i++){
        if($a[$i] == $b[$i]){
            continue;
        }
        if($a[$i] > $b[$i]){
            $aliceScore++;
            continue;
        }
        $bobScore++;
    }
    return [$aliceScore, $bobScore];
}
```
- [A Very Big Sum](https://www.hackerrank.com/challenges/a-very-big-sum/problem "A Very Big Sum")
```php
function aVeryBigSum($ar) {
    $sum = 0;
    foreach($ar as $value){
        $sum+=$value;
    }
    return $sum;
}
```
- [Diagonal Difference](https://www.hackerrank.com/challenges/diagonal-difference/problem "Diagonal Difference")
```php
function diagonalDifference($arr) {
    $length = count($arr);
    $primaryDiagonal = 0;
    $secondaryDiagonal = 0;
    $lastIndex = $length - 1;
    for($i = 0; $i<$length; $i++){
        $primaryDiagonal+=$arr[$i][$i];
        $secondaryDiagonal+=$arr[$i][$lastIndex--];
    }
    return abs($primaryDiagonal - $secondaryDiagonal);
}
```
- [Plus Minus](https://www.hackerrank.com/challenges/plus-minus/problem "Plus Minus")
```php
function plusMinus($arr) {
    $POSITIVES = 0;
    $NEGATIVES = 1;
    $ZEROES = 2;

    $length = count($arr);
    // declare the temp numbers to index positions
    $numbers = [0, 0, 0];

    // determine the plusMinus of the numbers
    foreach($arr as $val){
        if($val === 0){
            $numbers[$ZEROES] = $numbers[$ZEROES] + 1;
            continue;
        }
        if($val > 0){
            $numbers[$POSITIVES] = $numbers[$POSITIVES] + 1;
            continue;
        }
        $numbers[$NEGATIVES] = $numbers[$NEGATIVES] + 1;
    }

    $plusMinusArr = array_map(function ($number) use ($length) {
        return number_format($number/$length, 6);
    }, $numbers);

    foreach($plusMinusArr as $plusMinus){
        echo $plusMinus;
        echo "\n";
    }
}
```
- [Staircase](https://www.hackerrank.com/challenges/staircase/problem "Staircase")
```php
function staircase($n) {
    $totalSteps = $n;
    $staircase = [];
    // start from the right steps
    for($n; $n>0; $n--){
        $stairs = [];
        // proceed from left stair until the reach the final stair steps
        // then gradually increase the starting stair
        for($i=1; $i<=$n; $i++){
            // if it reached the final step print the stairs "#" else the its spaces
            if($i == $n){
                // calculate the total stairs to print
                $totalPrintOfStairs = ($totalSteps - $n) + 1;
                for($totalPrintOfStairs; $totalPrintOfStairs>0; $totalPrintOfStairs--){
                 array_push($stairs, "#");
                }
                array_push($staircase, $stairs);
                break;
            }
            array_push($stairs, " ");
        }
    }

    // print the staircases
    foreach($staircase as $stairs){
        foreach($stairs as $stair){
            echo $stair;
        }
        echo "\n";
    }
}
```
- [Mini-Max Sum](https://www.hackerrank.com/challenges/mini-max-sum/problem "Mini-Max Sum")
```php
function miniMaxSum($arr) {
    $maxSumTempArr = $arr;
    $minSumTempArr = $arr;

    // sort into ascending order and get the first four values
    sort($minSumTempArr);
    $minSumArr = array_splice($minSumTempArr, 0 ,4);

    // sort into descending order and get the first four values
    rsort($maxSumTempArr);
    $maxSumArr = array_splice($maxSumTempArr, 0, 4);    

    echo array_sum($minSumArr) . ' ' . array_sum($maxSumArr);
}
```



