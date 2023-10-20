# dvsa-1
Vehicle enforcement checks at roadside and operators' premises

dvsa
The dataset could not be built, this was a straightforward data cleansing exercise. The error message ValueError: Unable to parse string "-" at position 260 identifies that this is a parsing issue, all columns observations are treated as numeric so this is likely to be an invalid value. It also identifies the index of the row, which if viewed in the source document shows a dash in the column "Offence prohibition". Remember that pandas starts counting indexes at 0 and the header doesn't count so you'd see it in row 262 in Excel. If these were simply made blank the observation status columns would work. (Transform)

The naming of the observation status columns in the csv file are not directly related to the column by name, only by proximity. This issue has been identified before (transform)
Instead of renaming the columns in the CSV to be briefer but equally descriptive, you relabelled them in the CSV-W. (transform)
For both the observation and observation status column comparision, a good pair would be "mech-checks", "mech-checks-obs-status". You renamed them, but not in the correct way (transform)
Your observation status columns would all have the same name on PMD, though they are correctly linked to their respective observations (describe)
The source website had a comprehensive description of the dataset, which was not included in the metadata. (describe)
No summary was provided. (describe)
No themes were provided. (describe)
The geography column was omitted causing MECE issues, as the dataset is about the number of prohibitions issued within the GB or without. (component id)
Summary of measures/units checked (note: labels are poorly abbreviated as described above) (describe, component id, component separation)
mechanical checks: correct measure extended, correct unit extended but poor label (integer is a data_type not a unit, the label should be "number")
mechanical prohibitions issued: correct measure extended, correct unit extended but poor label (integer is a data_type not a unit, the label should be "number")
mechanical prohibition rate: incorrect measure extended (this is a percentage which is portion, what was extended from was a scale), incorrect unit extended (this is a percentage which is PER, not NUM) and also the label is down as float which should be "Percent".
traffic checks: correct measure extended, correct unit extended but poor label (integer is a data_type not a unit, the label should be "number")
Drivers' hours prohibitions issued: correct measure extended, correct unit extended but poor label (integer is a data_type not a unit, the label should be "number")
Drivers' hours prohibition rate: incorrect measure extended (this is a percentage which is portion, what was extended from was a scale), incorrect unit extended (this is a percentage which is PER, not NUM) and also the label is down as float which should be "Percent".
Offence prohibition: correct measure extended, correct unit extended but poor label (integer is a data_type not a unit, the label should be "number")
Offence prohibition rate: incorrect measure extended (this is a percentage which is portion, what was extended from was a scale), incorrect unit extended (this is a percentage which is PER, not NUM) and also the label is down as float which should be "Percent".
Weight checks: correct measure extended, correct unit extended but poor label (integer is a data_type not a unit, the label should be "number")
Overload prohibitions issued: correct measure extended, correct unit extended but poor label (integer is a data_type not a unit, the label should be "number")
Overload prohibition rate: incorrect measure extended (this is a percentage which is portion, what was extended from was a scale), incorrect unit extended (this is a percentage which is PER, not NUM) and also the label is down as float which should be "Percent".
Fixed penalties: correct measure extended, correct unit extended but poor label (integer is a data_type not a unit, the label should be "number")
Fixed penalties amount: correct measure extended, incorrect unit extended (this is a currency which is GBP, not NUM) and also the label is down as "Currency" which should be "Pounds Sterling".
All the measures' descriptions finish with "during the quarter" which is implied by the refPeriod, this should be omitted from the description. (describe)
