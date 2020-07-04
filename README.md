# DOCUMENTATION

#### There are three modules so far. They have some basic stuff in them that's already in C# prolly', I just couldn't find them.


Better Basics has three modules.
* String Parse
  * Contains a few helpful things for streamlined string parsing
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

