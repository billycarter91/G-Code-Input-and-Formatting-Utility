# G-Code Input and Formatting Utility  
Just copy the gCodeInputAndFormatting.h into your project.  
Functions:  

------------------------------------------------------------------  
## Round off insignificant digits from 1-6 decimal places:  
//returns a double rounded to the number of places implied  
  
* double roundSixDecimal(double){}  
* double roundFiveDecimal(double){}  
* double roundFourDecimal(double){}  
* double roundThreeDecimal(double){}  
* double roundTwoDecimal(double){}  
* double roundOneDecimal(double){}  
  
------------------------------------------------------------------  
## Format decimal appearance for printing.:  
//decimal precision for string output in gcode file. Call from main like "formatGCodeDecimals<5>(xCoordinate)" or "formatGCodeDecimals<2>(IPM)"  
//forces decimal appearance. Accepts 1-6 only, limiting up to 6 significant digits but will remove any and all trailing zeros  
//also removes leading zeros (e.g. .2 instead of 0.2) and trailing zeros (e.g. 1. instead of 1.0)  
//for no decimal e.g. for RPM, you would want to restrict user input or convert to an int before printing the value so this function isn't used in that case  
  
* string formatGCodeDecimals<>(double val)  
  
------------------------------------------------------------------  
## Handles keyboard entry for user inputs restricting user input as required. Returns the validated input.:  
// on numeric userInput...() calls, pass true as an argument to allow 'mm' suffix - see "gCodeInputAndFormatting.h"  
  
//Allows the user to input only positive numbers, decimal or fraction, with optional mm suffix  
* double userInputPos(bool allowMM = false)  
  
//Allows the user to input only positive numbers, decimal or fraction, and Zero, with optional mm suffix  
* double userInputPosZero(bool allowMM = false)  
  
//Allows the user to input only negative numbers, decimal or fraction, with optional mm suffix  
* double userInputNeg(bool allowMM = false)  
  
//Allows the user to input positive or negative numbers, decimal or fraction, and Zero, with optional mm suffix  
* double userInputPosNeg(bool allowMM = false)  
  
//Additional userInput...() function - Allow the user to input only l L r or R for left and right  
* char userInputLR()  
