# luVia.bee

---------------------------------------------------------------------------------------------------------------------------------------------
This a work in progress to create a matrix style piece of ASCII art for Android and/or Linux (with a fast refresh rate)
---------------------------------------------------------------------------------------------------------------------------------------------



 FINAL GOAL: On top of the Matrix part, I would like to include the folowing features:

  
  - A lot of settings to enable the user to fine tune the default settings (settings as a popup window)
  - Display pictures (very short display to create a subminal effect (would require access of user's Pictures directory.
  - Get text from text files / PDF / movies subtitles. Maybe some data scrapped from the Net ...
  - Why not including a piece of software such as GPT4ALL with some agency?



NOTE: my knowledge of programing is very limited. I know a bit of Bash, and I started to use Kotlin very recently.
But I managed to achieve some results, and I am sure that I can only improve. I am using Copilot without copy paste:
I do not understand Kotlin very well, so I limit myself to boiler plate (in a nutshell, I use Kotlin "Bash style")

What matter is an aesthetic result!

Here is the Main.kt


// ---------------------------------------------------------------------------------------------------------------------------


import kotlin.random.Random

data class MyclasS(var ShoW: String, var BottoM: Int, var SpeeD: Int, var SpeedevenT: Int, var BooM: Int, var TopshoW: String, var Event2: Int)

data class MydisplayclasS(var FinalshoW: String, var BottomshoW: String, var SpeedshoW: String)

// ** Global variables

val A: String = "a"
val B: String = "b"
val C: String = "c"


val AA: String = "aa"
val BB: String = "bb"
val BA: String = "ba"
val AB: String = "ab"
val AAA: String = "aaa"
val AAB: String = "aab"
val ABB: String = "abb"
val BBB: String = "bbb"



val BBA: String = "bba"
val BAA: String = "baa"


var X: String = "O"
var Y: String = "."
var Z: String = ""

val LengtH: Int = 50
val CoL: Int = 20
var SleeptimE: Long = 1000L

var SpeeD: Int = 0
var SpeedevenT: Int = 0
var BooM: Int = 0
var TopshoW: String = "whatever"
var Event2: Int = 0
var BottoM: Int = 0
var ShoW: String = B.repeat(LengtH)

var HolE: Int = 0

var LoW: Int = 1
var HigH: Int = 101
var AorB: Int = 0

// ** Create ThelisT with instances of MyclasS
var ThelisT = mutableListOf<MyclasS>().apply {
    repeat(CoL) {
        add(MyclasS(ShoW, BottoM, SpeeD, SpeedevenT, BooM, TopshoW, Event2))
    }
}
// Create a mutable list to store MydisplayclasS instances

var ThedisplaylisT = mutableListOf<MydisplayclasS>().apply {
    repeat(CoL) {
        add(MydisplayclasS(FinalshoW = "ttt", BottomshoW = "hhh", SpeedshoW = "ppp"))
    }
}

// VAR TO GET PROPORTION OF A AND bSS

fun ProportionnABcontroL(A: Int): Int {
    return 100 - A
}




// _____________________________________________________________


// ** PRINT ALL THE INSTANCE OF MY CLASS ->> USAGE PrintalL()
fun PrintalL() {
    for (item in ThelisT) {
        println("MyclasS(ShoW=${item.ShoW}, BottoM=${item.BottoM}, SpeeD=${item.SpeeD}, SpeedevenT=${item.SpeedevenT}, BooM=${item.BooM}, TopshoW=${item.TopshoW}, Event2=${item.Event2})")
    }
}

// ___________________________________________________________________


// ** PRINT ALL THE INSTANCE OF MY CLASS ->> USAGE PrintalL()
fun PrintallstrinG() {
    for (item in ThedisplaylisT) {
        println("MydisplayclasS(FinalshoW=${item.FinalshoW}, BottomshoW=${item.BottomshoW}, SpeedshoW=${item.SpeedshoW})")
    }
}

// ________________________________________________________________________________________________________




// ** generate random numbers:
fun GeneraterandomnumbeR(LoW: Int, HigH: Int): Int {
    return Random.nextInt(LoW, HigH)
}

// ** GENERATE RANDOM NUMBER AS A PERCENTAGE OF A PERCENTAGE OF LengtH (Smaller figure)
// USAGE IS var randomValue = MyRandomLengthOfLengtH(LengtH, ChosenperC, RangE)
fun MyRandomLengthOfLengtH(LengtH: Int, ChosenperC: Int, RangE: Int): Int {
    // First calculation
    var result = LengtH * ChosenperC / 100

    // Calculate the lower and upper bounds for the random value
    var lowerBound = result - (result * RangE / 100)
    var upperBound = result + (result * RangE / 100)

    // Ensure lowerBound is not negative (optional)
    var validLowerBound = if (lowerBound < 0) 0 else lowerBound

    // Generate a random value between validLowerBound and upperBound
    return Random.nextInt(validLowerBound, upperBound + 1)
}

// ** ADD A STRING AT THE BEGINING  &&  REMOVE LAST CHAR
fun ADDLETTER(ShoW: String, replacement: String): String {
    var removeXletters: Int = replacement.length
    var modifiedShoW = replacement + ShoW // Add replacement to the beginning of ShoW
    modifiedShoW = modifiedShoW.dropLast(removeXletters) // Remove the specified number of characters from the end
    return modifiedShoW // Return the modified ShoW
}

fun ModifySpeedWithModulO(list: MutableList<MyclasS>) { // odd is slow; even is fast
    for (i in list.indices) {
        if (i % 2 == 0) {
            list[i].SpeeD = 1
        } else {
            list[i].SpeeD = 2
        }
    }
}



// START OF MAIN ___________________________________________________________________________________________

fun main() {


    // create Hole for the entired program:


    ModifySpeedWithModulO(ThelisT)

    // Update BooM for each item in ThelisT
    for (item in ThelisT) {
        var ChosenperC = 25
        var RangE = 10
        item.BooM = MyRandomLengthOfLengtH(LengtH, ChosenperC, RangE)
    }


    // Update BottoM for each item in ThelisT

    for (item in ThelisT) {
       var ChosenperC = 20
       var RangE = 10
       item.BottoM = MyRandomLengthOfLengtH(LengtH, ChosenperC, RangE)
     }

    var ChosenperC = 25
    var RangE = 10
    HolE = MyRandomLengthOfLengtH(LengtH, ChosenperC, RangE)
    //println(HolE) !!!! does not work



// _________________________________________________


    // ** WHILE LOOP STARTING.
    var counter = 0

    while (counter < 50)  //  START OF WHILE LOOP
    {

// __________________________________________________

        for (item in ThelisT) { // START OF FOR LOOP 1


            var FirststrinG: String = item.ShoW.substring(0, 3)
            var AorB = GeneraterandomnumbeR(LoW, HigH)

            if (AorB > 50) // letter A has been chosen
            { // beginning of the if statement for A

                if (FirststrinG == AAA) // first if statement
                { // beginning of outer if block
                    if (item.SpeeD == 1) { // beginning of first inner if block
                        item.ShoW = ADDLETTER(item.ShoW, B)
                    } // end of first inner if block

                    if (item.SpeeD == 2) { // beginning of second inner if block
                        item.ShoW = ADDLETTER(item.ShoW, AB)
                    } // end of second inner if block
                } // end of outer if block

                else if (FirststrinG == AAB) // beginning of 2nd if statement
                { // beginning of outer if block
                    if (item.SpeeD == 1) { // beginning of first inner if block
                        item.ShoW = ADDLETTER(item.ShoW, A)
                    } // end of first inner if block

                    if (item.SpeeD == 2) { // beginning of second inner if block
                        item.ShoW = ADDLETTER(item.ShoW, BA)
                    } // end of second inner if block
                } // end of outer if block

                else // beginning of 3rd if statement
                { // beginning of outer if block
                    if (item.SpeeD == 1) { // beginning of first inner if block
                        item.ShoW = ADDLETTER(item.ShoW, A)
                    } // end of first inner if block

                    if (item.SpeeD == 2) { // beginning of second inner if block
                        item.ShoW = ADDLETTER(item.ShoW, AA)
                    } // end of second inner if block
                } // end of outer if block
            } // end of : "letter A has been chosen"

            if (AorB <= 50) // letter B has been chosen
            { // beginning of letter B if statement

                if (FirststrinG == AAB) // scenario 1 if AorB has been chosen
                { // beginning of outer if block
                    if (item.SpeeD == 1) { // beginning of first inner if block
                        item.ShoW = ADDLETTER(item.ShoW, A)
                    } // end of first inner if block

                    if (item.SpeeD == 2) { // beginning of second inner if block
                        item.ShoW = ADDLETTER(item.ShoW, BA)
                    } // end of second inner if block
                } // end of outer if block

                else if (FirststrinG == ABB) { // beginning of outer if block
                    if (item.SpeeD == 1) { // beginning of first inner if block
                        item.ShoW = ADDLETTER(item.ShoW, A)
                    } // end of first inner if block

                    if (item.SpeeD == 2) { // beginning of second inner if block
                        item.ShoW = ADDLETTER(item.ShoW, AA)
                    } // end of second inner if block
                } // end of outer if block

                else { // beginning of outer if block
                    if (item.SpeeD == 1) { // beginning of first inner if block
                        item.ShoW = ADDLETTER(item.ShoW, B)
                    } // end of first inner if block

                    if (item.SpeeD == 2) { // beginning of second inner if block
                        item.ShoW = ADDLETTER(item.ShoW, BB)
                    } // end of second inner if block
                } // end of outer if block
            } // end of : "letter B has been chosen"d


        } // END OF FOR LOOP 1


        println(AorB)
// ______________________________

        for (item in ThelisT) { // for loop 1B BEGINS

            var newString = item.ShoW.substring(1, item.BooM + 1)
            item.TopshoW = newString
            //println("New String: $newString")

        } // for loop 1B ENDS

// _______________________________________________________________




        for (item in ThelisT) { // FOR LOOP 2 STARTS



            var lastindexofAAA: Int = item.TopshoW.lastIndexOf(AAA)


            if (item.BooM == lastindexofAAA || item.BooM == lastindexofAAA - 1) { // start of if statement block

                // Find the index of the last occurrence of AAA in item.ShoW
                //lastindexofAAA = item.ShoW.lastIndexOf(AAA)


                // Replace the last occurrence of AAA with CCC
                item.ShoW = item.ShoW.substring(0, lastindexofAAA) + BBB + item.ShoW.substring(lastindexofAAA + AAA.length)



                var numberList = mutableListOf<Int>() // make sure to create a mutable for while loop
                //println(numberList)

                while (numberList.size < 3) { // begining of while loopof while loop for unique choice)

                    var randomNumber = Random.nextInt(HolE)
                    if (randomNumber !in numberList) {
                        numberList.add(randomNumber)
                    }
                }// end of while loop for unique choice

                var IndexfalL = HolE + item.BooM
                var updatedNumberList = numberList.map { it + IndexfalL }
                //println(updatedNumberList)


                // create a filler
                val FilleR: String = B.repeat(87)
                item.ShoW += FilleR



                // Insert A at each index in updatedNumberList within item.ShoW
                updatedNumberList.forEach { index ->
                    item.ShoW = item.ShoW.substring(0, index) + A + item.ShoW.substring(index + A.length)
                }


                item.ShoW = item.ShoW.removeSuffix(FilleR)


            } // end of if statement block

        } // FOR LOOP 2 ENDS




// ----------------   for loop 2B--------------------------------------------------------------------------



        for (item in ThelisT) {
            var X2 = LengtH - item.BottoM
            var MiddlE = item.ShoW.substring(item.BooM + 5, X2 - 2)
            println("MiddlE: $MiddlE")  // Optional: Print MiddlE to verify the value

            if (MiddlE.contains(A)) {
                MiddlE = MiddlE.replace(AAA, ABB)

            }
            item.ShoW = item.ShoW.substring(0, item.BooM + 5) + MiddlE + item.ShoW.substring(X2 - 2)

        }







// ______________________  end of for loop 2B__________________________________________________________________________


        for (item in ThelisT)

        {  //BEGINNING OF FOR LOOP 3


            var TetriS: Int = LengtH - item.BottoM

            var TetristrinG = item.ShoW.substring(0, TetriS)  // STRING FROM BEGINING OF SHOW TILL START OF bOTTOM
            var TetrislasT = TetristrinG.takeLast(2) // takes the 2 chars just before reaching Bottom


            if (TetrislasT == AA)

            { // begining of if block

                item.BottoM = (item.BottoM + 2)
                // RE UPDATE BY ADDING 2 TO BottoM

            } // end of block

            else if (TetrislasT == BA)

            { // start else block

                item.BottoM = (item.BottoM + 1)
                //item.ShoW = (TetristrinG + BottomdisplaY)

            } // end of else block


        } // END OF FOR LOOP3



        // ________   FOR LOOP 4 : controls the heigth of Bottom string   ___________


        for (item in ThelisT) {  // beginning of for loop
            if (item.BottoM > 15) {
                item.BottoM -= 5  // Subtract 5 from item.BottoM
            }
        } // end of for LOOP 4 ______________________________________________________




        // ______________  end of for loop 4________________________________






//   LOOP 5 copy item ShoW to FinalshoW (START OF LOOP5) ______________________

        for ((index, item) in ThelisT.withIndex()) {
            ThedisplaylisT[index].FinalshoW = item.ShoW
        }
//  END OF LOOP 5 _________________________________________________________


// loop 6 : create a string for BottomshoW

        for ((index, item) in ThelisT.withIndex()) {
            var BottomshoW = A.repeat(item.BottoM)
            ThedisplaylisT[index].BottomshoW = BottomshoW
              // Print the updated BottomshoW to verify
        }



// FOR LOOP TO SUBSTITUTE THE END OF FINALSHOW WITH bottomshoW

        for (item in ThedisplaylisT) { // start
            var endIndex = item.FinalshoW.length - item.BottomshoW.length
            if (endIndex >= 0) {
                item.FinalshoW = item.FinalshoW.substring(0, endIndex) + item.BottomshoW
            } else {
                item.FinalshoW = item.BottomshoW
            }
            println("Updated FinalshoW: ${item.FinalshoW}")
        }


/////___     for loop to diminish the length of the bottom  of final show________________________________________

        for (item in ThedisplaylisT) {  // begining of for loop K

            if (item.BottomshoW.length > 15) {

                item.FinalshoW = item.FinalshoW.dropLast(5)


            }


        } // end of for loop K


        // UPDATE SHOW WITH fINALSHOw

        // update ShoW with FinalShoW


        for ((index, item) in ThelisT.withIndex()) {
            item.ShoW = ThedisplaylisT[index].FinalshoW
        }





        // ** DISPLAY PART

        PrintalL() // Call PrintalL to print all instances of MyclasS
        PrintallstrinG()

        //substitution
        //ThedisplaylisT

        var maxLength = ThedisplaylisT.maxOf { it.FinalshoW.length } // CREATE A LIST OF CHARS ....
        var newShowArray = Array(maxLength) { CharArray(ThedisplaylisT.size) }

        for (i in ThedisplaylisT.indices)
        {
            for (j in 0 until maxLength)
            {
                if (j < ThedisplaylisT[i].FinalshoW.length)
                {
                    newShowArray[j][i] = ThedisplaylisT[i].FinalshoW[j]
                }
            }
        }






        for (row in newShowArray)  // ** FURTHER ITERATIONS TO ACT ON STRING
        {
            for (char in row)
            {
                var charString = char.toString()
                charString = charString.replace(A, X)
                charString = charString.replace(B, Y)
                print("$charString  ") // For instance, print with a space
            }
            println()
        }

        // println(HolE) )))))))))))))))))))


        counter++
        Thread.sleep(SleeptimE)  // Sleep for 1000 milliseconds (1 second)

    } // END OF WHILE LOOP



} // END OF MAIN












