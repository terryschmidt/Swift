// Terry Schmidt.  CSC471.  Spring 2015.  Assignment 2.

// 1. Create a new Playground. Include all the code of this assignment in a single Playground.

// 2a - Function rank performs a binary search of a key in a sorted integer array.  If the key appears in the array, the rank function returns the index of key in the array. If the key does not appear in the array, the rank function returns -1.
public func rank(key: Int, a: [Int]) -> Int {
    var lo = 0
    var hi = a.capacity - 1
        while(lo <= hi) {
            var mid = lo + (hi - lo) / 2
            if key < a[mid] {
                hi = mid - 1
            }
            else if key > a[mid] {
                lo = mid + 1
            } else {
                return mid
            }
        }
    return -1
}

// 2b - Create a sorted integer array to test the rank function. Make several calls to the rank function. Verify that the results are correct.
var sortedArray = [11, 23, 34, 46, 68, 72, 83, 94, 101, 102]
// these are values that are present in sortedArray.  Should return the position of that value in the array.
println(rank(83, sortedArray))
println(rank(102, sortedArray))
println(rank(23, sortedArray))
println(rank(68, sortedArray))
println(rank(94, sortedArray))
println(rank(11, sortedArray))
// these are not values present in sortedArray.  Should return -1.
println(rank(200, sortedArray))
println(rank(547, sortedArray))




// 3a - Add methods to the version 4 of the Fraction class to compute the subtraction, multiplication, and division of two fractions in a similar way to the add: method (see http://en.wikipedia.org/wiki/Rational_number for the formulae to compute the subtraction, multiplication, and division of two fractions). Each method should take another fraction object as the parameter and return the result as a new Fraction object.
class Fraction {
    var numerator: Int = 0
    var denominator: Int = 1
    
    func add(f: Fraction) -> Fraction {
        var result: Fraction = Fraction()
        result.numerator = numerator * f.denominator + denominator * f.numerator
        result.denominator = denominator * f.denominator
        result.reduce()
        return result
    }
    
    func subtract(f: Fraction) -> Fraction {
        var result: Fraction = Fraction()
        result.numerator = numerator * f.denominator - denominator * f.numerator
        result.denominator = denominator * f.denominator
        result.reduce()
        return result
    }
    
    func multiply(f: Fraction) -> Fraction {
        var result: Fraction = Fraction()
        result.numerator = numerator * f.numerator
        result.denominator = denominator * f.denominator
        result.reduce()
        return result
    }
    
    func divide(f: Fraction) -> Fraction {
        var result: Fraction = Fraction()
        result.numerator = numerator * f.denominator
        result.denominator = denominator * f.numerator
        result.reduce()
        return result
    }
    
    func reduce() {
        let sign = numerator >= 0 ? 1:-1
        var u = numerator * sign
        var v = denominator
        var r: Int
        while v != 0 {
            r = u % v
            u = v
            v = r
        }
        numerator /= u * sign
        denominator /= u
    }
    
    init(numerator: Int, denominator: Int) {
        self.numerator = numerator
        self.denominator = denominator
    }
    
    init(_ numerator: Int, over denominator: Int) {
        self.numerator = numerator
        self.denominator = denominator
    }
    
    init() { }
    
    func setTo(numerator: Int, denominator: Int) {
        self.numerator = numerator
        self.denominator = denominator
    }
    
    func setTo(numerator: Int, over denominator: Int) {
        self.numerator = numerator
        self.denominator = denominator
    }
    
    func setTo(numerator: Int, _ denominator: Int) {
        self.numerator = numerator
        self.denominator = denominator
    }
    
    func print() {
        println("\(numerator)/\(denominator)")
    }
    
    func toDouble() -> Double {
        return Double(numerator) / Double(denominator)
    }
    
    func add(a: Fraction, b: Fraction) -> Fraction {
        return a.add(b)
    }
}

// global functions outside of Fraction class.  Overloading.
func add(a: Fraction, b: Fraction) -> Fraction {
    return a.add(b)
}

func +(a: Fraction, b: Fraction) -> Fraction {
    return a.add(b)
}

func += (inout left: Fraction, right: Fraction) {
    left = left + right
}

func subtract(a: Fraction, b: Fraction) -> Fraction {
    return a.subtract(b)
}

func multiply(a: Fraction, b: Fraction) -> Fraction {
    return a.multiply(b)
}

func divide(a: Fraction, b: Fraction) -> Fraction {
    return a.divide(b)
}

var f1 = Fraction(1, over: 2)
var f2 = Fraction(1, over: 4)
f1.add(f2)  //This has to return 3/4, not 6/8.  It does, thanks to the reduce() method called inside of add().

// 3b - Write test code to test each of the new methods of the class with different input values. Verify that your results are correct.
var f3 = Fraction(1, over: 2)
var f4 = Fraction(1, over: 5)
f3.subtract(f4)

var f5 = Fraction(3, over: 5)
var f6 = Fraction(1, over: 3)
f5.subtract(f6)

var f7 = Fraction(1, over: 2)
var f8 = Fraction(1, over: 2)
f7.multiply(f8)

var f9 = Fraction(7, over: 16)
var f10 = Fraction(3, over: 7)
f9.multiply(f10)

var f11 = Fraction(1, over: 3)
var f12 = Fraction(1, over: 5)
f11.divide(f12)

var f13 = Fraction(8, over: 15)
var f14 = Fraction(4, over: 9)
f13.divide(f14)
