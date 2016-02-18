# Supported Delphi versions #

  * Delphi 2010
  * Delphi XE
  * Delphi XE2
  * Delphi XE3
  * Delphi XE4
  * Delphi XE5
  * Delphi XE6
  * Delphi XE7



# Why does it not run on Delphi 2009 or any older version ? #

VerySimpleXml makes use of Generics, so any older versions aren't supported. It does not run on Delphi 2009 because it uses some list functions found only in Delphi version 2010 and higher (e.g. TObjectList.First and TObjectList.Last).

# How to rewrite it to support older versions #

Feel free to replace the Generic TObjectList with a standard TObjectList, use casts for the list objects and replace the TList.Last and TList.First list routines with `TList.Items[0]` and `TList.Items[TList.ItemsCount - 1]`. It is not that difficult - just try it.

# Why do you not rewrite it to support older versions if it's that easy? #

I don't think using old Delphi versions makes sense at all - you miss all the great code features which simplifies your code and makes it more readable, less buggy  - and think of the great IDE functions you're missing as well.