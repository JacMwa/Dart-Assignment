# Dart-Assignment
// main function: The entry point of every Dart program.
void main() {
  print('--- 1. Define Variables ---');
  // Define an integer variable
  int age = 30;
  print('Integer (age): $age');

  // Define a double variable
  double price = 19.99;
  print('Double (price): $price');

  // Define a String variable
  String greeting = 'Hello, Dart!';
  print('String (greeting): $greeting');

  // Define a boolean variable
  bool isActive = true;
  print('Boolean (isActive): $isActive');

  // Define a List of integers
  List<int> numbers = [10, 20, 30, 40, 50];
  print('List of integers (numbers): $numbers');

  print('\n--- 2. Type Conversion ---');
  // Example usage of String to int/double conversion functions
  stringToIntAndDouble('123');
  stringToIntAndDouble('98.76');
  stringToIntAndDouble('abc'); // This will show null for conversion

  // Example usage of int to String/double conversion functions
  intToStringAndDouble(12345);

  print('\n--- 3. Conversion Function ---');
  convertAndDisplay('789');
  convertAndDisplay('12.34');
  convertAndDisplay('hello'); // This will show conversion failure

  print('\n--- 4. Control Flow ---');
  // If-Else examples
  print('--- If-Else ---');
  checkNumberSign(5);
  checkNumberSign(-3);
  checkNumberSign(0);

  checkVotingEligibility(20);
  checkVotingEligibility(16);

  // Switch Case example
  print('\n--- Switch Case (Day of Week) ---');
  printDayOfWeek(1); // Monday
  printDayOfWeek(5); // Friday
  printDayOfWeek(7); // Sunday
  printDayOfWeek(9); // Invalid day

  // Loops examples
  print('\n--- Loops ---');
  print('For loop (1 to 10):');
  forLoopExample();

  print('\nWhile loop (10 to 1):');
  whileLoopExample();

  print('\nDo-While loop (1 to 5):');
  doWhileLoopExample();

  print('\n--- 5. Combine Data & Control Flow ---');
  List<int> mixedNumbers = [7, 15, 98, 5, 101, 23, 150, 2];
  print('Iterating and analyzing list: $mixedNumbers');
  iterateAndCategorizeList(mixedNumbers);
}

/// Converts a String to int and double, then prints the results.
void stringToIntAndDouble(String s) {
  int? intValue = int.tryParse(s);
  double? doubleValue = double.tryParse(s);

  print('Converting "$s":');
  print('  To int: ${intValue ?? 'Conversion failed'}');
  print('  To double: ${doubleValue ?? 'Conversion failed'}');
}

/// Converts an int to String and double, then prints the results.
void intToStringAndDouble(int i) {
  String stringValue = i.toString();
  double doubleValue = i.toDouble();

  print('Converting integer $i:');
  print('  To String: "$stringValue"');
  print('  To double: $doubleValue');
}

/// Converts an input string to int and double, and displays them.
void convertAndDisplay(String number) {
  print('Processing input: "$number"');
  int? intConverted = int.tryParse(number);
  double? doubleConverted = double.tryParse(number);

  if (intConverted != null) {
    print('  Converted to int: $intConverted');
  } else {
    print('  Could not convert to int.');
  }

  if (doubleConverted != null) {
    print('  Converted to double: $doubleConverted');
  } else {
    print('  Could not convert to double.');
  }
}

/// Checks if a number is positive, negative, or zero.
void checkNumberSign(int number) {
  if (number > 0) {
    print('$number is positive.');
  } else if (number < 0) {
    print('$number is negative.');
  } else {
    print('$number is zero.');
  }
}

/// Verifies voting eligibility based on age (18+).
void checkVotingEligibility(int age) {
  if (age >= 18) {
    print('Age $age: Eligible to vote.');
  } else {
    print('Age $age: Not eligible to vote yet.');
  }
}

/// Prints the day of the week based on an integer (1-7).
void printDayOfWeek(int dayNumber) {
  String day;
  switch (dayNumber) {
    case 1:
      day = 'Monday';
      break;
    case 2:
      day = 'Tuesday';
      break;
    case 3:
      day = 'Wednesday';
      break;
    case 4:
      day = 'Thursday';
      break;
    case 5:
      day = 'Friday';
      break;
    case 6:
      day = 'Saturday';
      break;
    case 7:
      day = 'Sunday';
      break;
    default:
      day = 'Invalid Day Number';
  }
  print('Day $dayNumber is $day.');
}

/// Prints numbers from 1 to 10 using a for loop.
void forLoopExample() {
  for (int i = 1; i <= 10; i++) {
    print(i);
  }
}

/// Prints numbers from 10 to 1 using a while loop.
void whileLoopExample() {
  int i = 10;
  while (i >= 1) {
    print(i);
    i--;
  }
}

/// Prints numbers from 1 to 5 using a do-while loop.
void doWhileLoopExample() {
  int i = 1;
  do {
    print(i);
    i++;
  } while (i <= 5);
}

/// Iterates a list of integers, checks if even/odd, and categorizes them.
void iterateAndCategorizeList(List<int> numbers) {
  for (int number in numbers) {
    // Check if even or odd
    if (number % 2 == 0) {
      print('$number is even.');
    } else {
      print('$number is odd.');
    }

    // Categorize using switch
    switch (number) {
      case >= 1 && <= 10: // Dart 3.0 feature: Relational patterns
        print('  $number is a small number.');
        break;
      case >= 11 && <= 100:
        print('  $number is a medium number.');
        break;
      case > 100:
        print('  $number is a large number.');
        break;
      default:
        print('  $number falls outside defined categories.');
    }
  }
}
