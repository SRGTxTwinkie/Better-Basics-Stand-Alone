# DOCUMENTATION

#### There are three modules so far. They have some basic stuff in them that's already in C# prolly', I just couldn't find them.


Better Basics has three modules.
* String Parse
  * Contains a few helpful things for streamlined string parsing
  * Will loop until an int has been found
* Range
  * Litterally has two functions in it, one has a start stop step, the other starts at 1 and goes till you tell it to stop
* Arrays
  * Since Arrays are non mutable, this module has an array adder.
  * Arrays also has a method to check if a value is contained in an array.
  
____________________________________________________________________________________________________________________________________


# String Parse:

    public static int IntVarParse(string string_in) { 
       
            int final_int;
            bool is_int = int.TryParse(string_in, out final_int);

            if(is_int)
            {
                return final_int;
            }
            else
            {
                return 0;
            }
            
        }

When passed a string, it will either return the parsed int, or 0 if parsing fails.

Call this to Parse a string from a passed int32
Will __not__ prompt the user for input inside function.

### Example
string equals_one = "1"; 
Console.WriteLine(StringParse.Int(equals_one).GetType())

Expected Output {
 System.Int32
}

### Practical

    while (StringParse.IntVarParse(current_string) != -1)
            {
                Console.Write("Input: ");
                current_string = Console.ReadLine();

                if (StringParse.IntVarParse(current_string) == -1)
                {
                    stringHandleMenu(data);
                }
                else
                {
                    data.Add(current_string);
                }
            }
            

___________________________________
    public static int Int()
        {
            string string_in;
            int final_int;
            bool is_int;

            string_in = Console.ReadLine();

            is_int = int.TryParse(string_in, out final_int);

            while (!is_int)
            {
                string_in = Console.ReadLine();
                is_int = int.TryParse(string_in, out final_int);
            }

            return final_int;
        }
        
When called, will parse and read an int from the console.
Will prompt the user for input inside function.

### Example
Console.Write("Whatever you type will be converted to a number: ");
int example_to_int = StringParse.Int(example);

### Practical
    Console.Write("How many books are you gonna need: ");
    book_num = StringParse.Int();
            
___________________________________

    public static int Int(string output)
        {
            Console.Write("{0}: ", output);
            string string_in = Console.ReadLine();
            int final_int;
            bool is_int;

            is_int = int.TryParse(string_in, out final_int);

            while (!is_int)
            {
                string_in = Console.ReadLine();
                is_int = int.TryParse(string_in, out final_int);
            }

            return final_int;
        }
        
Works the same as previous, adds the ability to pass a string for a prompt.
Will prompt the user for input inside function.

### Example
int example_to_int = StringParse.Int();

### Practical
    Console.WriteLine("Enter the digit you want to find. Will return all instances of value and place in array.");
    arr_value = StringParse.Int("Value");

## The double variations work the same as integer. Exactly the same.

____________________________________________________________________________________________________________________________________



