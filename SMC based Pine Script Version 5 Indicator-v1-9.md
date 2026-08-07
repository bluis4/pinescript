SMC based Pine Script Version 5 Indicator



### Zone Drawing

The script should be able to draw 2 zones with label for each zone “ZN 1” and “ZN 2”.

Zone specification are listed below :

1. “ZN 1” a.k.a Zone 1, is based on equilibrium logic derived from original LuxAlgo’s SMC script. \[Done]
2. “ZN 2” a.k.a Zone 2, is based on fibo 0.61 and 0.78. Those 2 fibo will formed the “ZN 2” zone. \[Done]
3. Both zones should follow the latest Swing High and Low based on LuxAlgo’s original script. \[Done]
4. Add price label beside both zones border. \[Done]
5. Dynamic zone colour :

   1. If the break is bearish break (the solid line and label is Red), the zone colour should be Red. \[Done]
   2. If the break is bullish break (the solid line and label is Green), the zone colour should be Green. \[Done]
6. Increase price label size twice the current size. \[Done]
7. Add label before the ZN inside the zone box. Buy or Sell. The condition are below :

   1. If the solid break line is green, which mean it’s a bullish break, the zone boxes will turn to Green. So the Buy label will be print. Example : Buy ZN 1.  \[Done]
   2. If the solid break line is red, which mean it’s a bearish break, the zone boxes will turn to Red. So the Sell label will be print. Example : Sell ZN 1. \[Done]
   3. The label should be printed on both zones. \[Done]
8. Add additional tag in front of price label :

   1. \[UPB] for upper boundary. \[Done]
   2. \[LWB] for lower boundary. \[Done]
   3. The tag label should change based on zone condition either it’s a bearish or bullish zone. \[Done]
9. Zone 2 should be drawn vertically align starting with the candle where the swing low dash line started for Buy/Bullish/Green zone box, and swing high dash line started for Sell/Bearish/Red zone box. \[Done]
10. Zone 1 adjustment : make it to match Zone 2 starting point. \[Done]
11. Adjust Zone calculation logic so it match exactly the swing low/high so the box drawn correctly. \[Done]
12. Adjust zone label to precisely center in the middle of the box even if the box expand to the right. \[Done]





\---------------------------------------



### Swing High and Swing Low

The script should be able to find swing high and low and draw dash line based on LuxAlgo’s script logic of Strong High and Weak Low.

The specifications are listed below :

1. Able to find the “Swing High” and “Swing Low” based on LuxAlgo’s script. On the original LuxAlgo’s script it is called Strong / Weak High and Strong / Weak Low and marked by solid line accompanied by label. \[Done]
2. The line for “Swing High” and “Swing Low” on SMC-Imperator (our indicator) should be dash line instead of solid line and no need for label. The dash line should be 1px thick. \[Done]
3. The dash line color for “Swing High” should be “Red”, while “Swing Low” should be “Green / Light Blue”. \[Done]
4. Change the swing low dash line color to Green (currently it’s blue). \[Done]





\---------------------------------------



### Break of Structure (BoS) and Change of Character (CHoCH)

The script should be able to determined BoS and CHoCH based on LuxAlgo’s script logic with specification below :

1. The BoS and CHoCH should use confluence filter from LuxAlgo’s original script. \[Done]
2. The BoS and CHoCH should ignore “Internal Structure” as describe on the parameter setting of LuxAlgo’s script “Show Internal Structure”. This parameter is unchecked / disabled manually by myself to ensure the structure is clean and less clutter. \[Done]
3. The CHoCH and BoS label from LuxAlgo’s original script, should be change to just “Break” on our indicator SMC-Imperator. \[Done]
4. The break should be drawn with 1px solid line. \[Done]
5. The break color should be “Red” for bearish break, and “Light Blue” for bullish break. \[Done]
6. The break should be trigger when candle break either “Swing High” or “Swing Low” dash line and closed with full body. \[Done]
7. Change bullish break line and label color to “Green” (currently it’s blue). \[Done]
8. Update BoS and CHoCH logic to match exactly the original LuxAlgo’s script. \[Done]





\---------------------------------------



### Dashboard

The script should be able to show dashboard with information and format below :

1. Have option in the setting parameter to show where the dashboard should be displayed (Top Left or Top Right). \[Done]
2. Dashboard information table : (refer to the table below). \[Done]
3. Adjust all placeholder text (hardcode text with no logic) to show as “Nulled” with gray color. \[Done]
4. Adjust ZN 1 and ZN 2 validity with rules below :

   1. When a Zone status changed from Fresh to Used, the zone validity should be changed from Valid to Invalid. \[Done]
   2. When a Zone status still printed as Fresh, the zone validity should be also printed as Valid. \[Done]
   3. If a Zone status is Invalid, the validity status should be also printed as Invalid. \[Done]
5. Adjust ZN 1 and ZN 2 zone Formed with rules below :

   1. When Zone status is Fresh, the Zone Formed status should be “OK”. \[Done]
   2. When Zone status is Used, the Zone Formed status should stay “OK”. \[Done]
   3. When Zone status is Invalid, the Zone Formed status should be “Invalid” too. \[Done]
6. Adjust Waiting Entry for ZN 1 and ZN 2 with rules below :

   1. If zone freshness status still "Fresh", the waiting entry status should be "OK". \[Done]
   2. If zone freshness status already "Used", the waiting entry status should be "NO". \[Done]
   3. If zone freshness status is "Invalid", the waiting entry status should be "Invalid". \[Done]
7. Add New row above action row containing 2 columns. The left column label is "SESSION", while the right column should contain either : Asia, Europe, New York, Asia -> Europe, Europe -> New York. \[Done]
8. Adjust action row for buy/sell when the freshness of both zones either buy/sell zone is Used, the Buy/Sell action should change to Wait (also add clock icon in front of the Wait label). \[Todo]
9. Proceed with the trend filter (EMA, RSI, Stoch) as what we discussed before. \[Todo]





\---------------------------------------



### Freshness

The script should be able to determine zone freshness (fresh, used, or invalid). The specifications are listed below :

1. A zone status is “Fresh” when :

   1. No candle closed inside the zone. \[Done]
   2. No candle Overlap \[UPB] upper boundary of sell zone (This is for when the zone box is red or bearish setup or the break line is bearish break / red break line. \[Done]





\---------------------------------------



### Parameters

This is the part of the indicator parameter setting. This parameter setting will be split in to sub section for each feature. Below is the detail :

1. Trend Filter \[Todo]

   1. Exponential Moving Average (EMA)
   2. Relative Strength Index (RSI)
   3. Stochastic Oscillator (Stoch)
2. Zones \[Todo]

   1. Zone ZN 1
   2. Zone ZN 2
3. Dashboard \[Todo]
4. Entry Strategy \[Todo]
5. Take Profit - Stoploss - Breakeven \[Todo]
6. Coming soon \[Hold]
7. Hide Swing High/Low sub section (no need for user to tweak it) [Todo]
8. Disable Zones color setting from Zones sub section [Todo]
9. Remove break of structure sub section (no need for user to tweak it) [Todo]



\---------------------------------------



### Miscellaneous

1. Categorize the code features/function header to be more structured and clean.

   1. Input (Setting Parameter). \[Done]
   2. Data Structure. \[Done]
   3. Core Logic. \[Done]
   4. Zone Drawing. \[Done]
   5. Freshness. \[Done]
   6. Dashboard. \[Done]
2. Each feature, if have any sub-features should have their own header too. \[Done]
3. Add short description as comment so it’s easier to understand what the feature/function do. \[Done]





\---------------------------------------



Legend :

\[Done] = The checklist has been done and nothing to fix

\[Todo] = The checklist need to be implemented

\[Hold] = Do nothing to the checklist



Dashboard table structure (from Dashboard section number 2). \[Done]

Zone A1	Buy / Long	Sell / Short

Trend EMA	Allow \[Check Icon]	Allow \[Check Icon]

Swing Bias	Bullish / Bearish \[Check / X Icon]	Bullish / Bearish \[Check / X Icon]

\--- Zone 1 ---	Buy / Long	Sell / Short

ZN 1 Formed	Ok \[Check Icon]	Ok \[Check Icon]

Waiting Entry for ZN 1	Waiting \[Check Icon]	Done/No \[X Icon]

ZN 1 Validity	Valid/Invalid	Valid/Invalid

ZN 1 Freshness	Fresh/Used/Invalid	Fresh/Used/Invalid

\--- Zone 2 ---	Buy / Long	Sell / Short

ZN 2 Formed	Ok \[Check Icon]	Ok \[Check Icon]

Waiting Entry for ZN 2	Waiting \[Check Icon]	Done/No \[X Icon]

ZN 2 Validity	Valid/Invalid	Valid/Invalid

ZN 2 Freshness	Fresh/Used/Invalid	Fresh/Used/Invalid

ACTION	STATUS	CONDITION

\[Arrow / No Icon] BUY / SELL / WAIT	READY ENTRY / WAITING	RETEST ZONE 1 \& 2 / WAITING

