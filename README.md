# Units-Conversion-App-using-Koltin
This project is a part of my journey in learning Kotlin language It's an app that convert weight, distance and temperature units" 

#The code is below : 

import java.util.Scanner
import kotlin.Double as Double

fun main() {
    println("What's Your name?")
    val name:String = readln()
    println("Hello $name")
    println("this is an app that convert weight,distance and temperature units")
    print("Please choose what you wanna to convert : ")
    val choice:String = readln()
    converter(choice)
}

fun converter(chc: String){
    val scan = Scanner(System.`in`)
    var distance: Double
    var temperature: Double
    var weight: Double
    val unit1: String
    val unit2: String
    when(chc){
        "weight" -> {
            print("Enter the value you want to convert : ")
            weight = scan.nextDouble()
            println("Choose the current unit of the value Entered: ")
            println("1-Lb")
            println("2-Kg")
            unit1 = readln()
            when(unit1){
                "lb" -> {
                    println("Conversion")
                    print("$weight lb = ")
                    weight /= 2.205
                    //this method below display the value on a #.## format
                    val newValue = String.format("%.2f", weight)
                    println(newValue + "kg")
                }
                "kg" -> {
                    println("Conversion")
                    print("$weight kg = ")
                    weight *= 2.205
                    val newValue = String.format("%.2f", weight)
                    println(newValue + "lb")
                }

            }
        }
        "distance" ->{
            println("Enter the value that you want to convert : ")
            distance = scan.nextDouble()
            println("Choose the unit of the value entered")
            println("1-Km")
            println("2-Miles")
            println("3-Meters")
            println("4-Yard")
            unit1 = readln()

            when(unit1){
                "Km"-> {
                    println("Choose a unit to convert your value to : ")
                    println("1-Miles")
                    println("2-Meters")
                    println("3-Yard")
                    unit2 = readln()
                    println("Conversion")
                    when(unit2){
                        "Miles" ->{
                            print("$distance Km = ")
                            distance /= 1.609
                            val newValue = String.format("%.2f", distance)
                            println(newValue + "Miles")
                        }
                        "Meters" ->{
                            print("$distance Km = ")
                            distance *= 1000
                            val newValue = String.format("%.2f", distance)
                            println(newValue + "m")
                        }
                        "Yard" ->{
                            print("$distance Km = ")
                            distance *= 1094
                            val newValue = String.format("%.2f", distance)
                            println(newValue + "yd")
                        }
                    }
                }
                "Miles" -> {
                    println("Choose a unit to convert your value to ")
                    println("1-Km")
                    println("2-Meters")
                    println("3-Yard")
                    unit2 = readln()
                    println("Conversion")
                    when(unit2){
                        "Km" ->{
                            print("$distance mi = ")
                            distance *= 1.609
                            val newValue = String.format("%.2f", distance)
                            println(newValue + "Km")
                        }
                        "Meters" ->{
                            print("$distance mi = ")
                            distance *= 1609
                            val newValue = String.format("%.2f", distance)
                            println(newValue + "m")
                        }
                        "Yard" ->{
                            print("$distance mi = ")
                            distance *= 1760
                            val newValue = String.format("%.2f", distance)
                            println(newValue + "yd")
                        }
                    }
                }
                "Meters" ->{
                    println("Conversion")
                    println("Choose a unit to convert your value to")
                    println("1-Km")
                    println("2-Miles")
                    println("3-Yard")
                    unit2 = readln()
                    when(unit2){
                        "Km" ->{
                            print("$distance m = ")
                            distance /= 1000
                            val newValue = String.format("%.2f", distance)
                            println(newValue + "Km")
                        }
                        "Miles" ->{
                            print("^$distance m = ")
                            distance /= 1609
                            val newValue = String.format("%.2f", distance)
                            println(newValue + "mi")
                        }
                        "Yard" ->{
                            print("$distance m = ")
                            distance *= 1.094
                            val newValue = String.format("%.2f", distance)
                            println(newValue + "yd")
                        }
                    }
                }
                "Yard" ->{
                    println("Choose a unit to convert your value to")
                    println("1-Km")
                    println("2-Miles")
                    println("3-Meters")
                    unit2 = readln()
                    println("Conversion")
                    when(unit2){
                        "Km" -> {
                            print("$distance yd = ")
                            distance /= 1094
                            val newValue = String.format("%.2f", distance)
                            println(newValue + "Km")
                        }
                        "Miles" ->{
                            print("$distance yd = ")
                            distance /= 1760
                            val newValue = String.format("%.2f", distance)
                            println(newValue + "mi")
                        }
                        "Meters" ->{
                            print("$distance yd = ")
                            distance /= 1.094
                            val newValue = String.format("%.2f", distance)
                            println(newValue + "m")
                        }
                    }
                }
            }
        }
        "temperature" -> {
            print("Enter the value that you want to convert : ")
            temperature = scan.nextDouble()
            println("What is the Unit of the value entred : ")
            println("1-Celsius")
            println("2-Kelvin")
            println("3-Fahrenheit")
            unit1 = readln()
            when(unit1){
                "Celsius" ->{
                    println("Choose a unit to convert your value to")
                    println("1-Kelvin")
                    println("2-Fahrenheit")
                    unit2 = readln()
                    when(unit2){
                        "Kelvin" ->{
                            println("Conversion")
                            print("$temperature °C = ")
                            temperature += 273.15
                            val newValue = String.format("%.2f ",temperature)
                            println(newValue + "K")
                        }
                        "Fahrenheit" ->{
                            println("Conversion")
                            print("$temperature °C = ")
                            temperature = (temperature * 9/5 ) + 32
                            val newValue = String.format("%.2f ",temperature)
                            println("$newValue°F")
                        }
                    }
                }
                "Kelvin" -> {
                    println("Choose a unit to convert your value to")
                    println("1-Celsius")
                    println("2-Fahrenheit")
                    unit2 = readln()
                    when(unit2){
                        "Celsius" ->{
                            println("Conversion")
                            print("$temperature K = ")
                            temperature -= 273.15
                            val newValue = String.format("%.2f ",temperature)
                            println("$newValue°C")
                        }
                        "Fahrenheit" ->{
                            println("Conversion")
                            print("$temperature K = ")
                            temperature = (temperature - 273.15) * 9/5 + 32
                            val newValue = String.format("%.2f ",temperature)
                            println("$newValue°F")
                        }
                    }
                }
                "Fahrenheit" ->{
                    println("Choose a unit to convert your value to")
                    println("1-Celsius")
                    println("2-Kelvin")
                    unit2 = readln()
                    when(unit2){
                        "Celsius" ->{
                            println("Conversion")
                            print("$temperature °F = ")
                            temperature = (temperature - 32) * 5/9
                            val newValue = String.format("%.2f ",temperature)
                            println("$newValue°C")
                        }
                        "Kelvin" ->{
                            println("Conversion")
                            print("$temperature °F = ")
                            temperature = (temperature - 32) * 5/9 + 273.15
                            val newValue = String.format("%.2f ",temperature)
                            println(newValue + "K")
                        }
                    }
                }
            }
        }
        else -> println("Error")
    }
}
