# Control Naming Convention

### Control Naming Convention

| #  | Description                                                  | Object/Element               | Naming Example                         | UI Examples            | Actions                                 |
|----|--------------------------------------------------------------|------------------------------|----------------------------------------|------------------------|-----------------------------------------|
| 1  | Class/object for a page contains page’s name + "Page"         | Page                         | `LoginPage`, `ComponentDetailsPage`    |                        | `clickHeader`                          |
| 2  | Header control contains header + name                        | Header                       | `headerComponentDetails`               | #1                     |                                         |
| 3  | Label control contains label + name                          | Label                        | `labelExpirationDate`                  | #2                     |                                         |
| 4  | Radio button contains `inputRadioButton + name`, `labelRadioButton + name` | Radio Button (label + input) | `inputRadioButtonSomeName`, `labelRadioButtonSomeName` | #3 | `selectRadioBtnSomename`               |
| 5  | Checkbox contains `inputCheckbox + name`, `labelCheckbox + name` | Checkbox (label + input)     | `inputCheckBoxSomeName`, `labelCheckBoxSomeName` | | `setCheckBoxSomeName(true | false)`    |
| 6  | Text field (input, edit box, text area) contains input + name | Text Fields/Inputs           | `inputName`                            |                        | `setInputSomeName`                     |
| 7  | Asterisk’s names contain label + Name + Required              | Asterisk                     | `labelDateRequired`                    | #5                     |                                         |
| 8  | Switcher contains `input + name`, `label + name`             | Switcher (label + input)      | `inputSwitcherName`, `labelSwitcherName` | #6                    | `setSwitcherSomeName`                  |
| 9  | Combo box contains comboBox + name                           | ComboBox                     | `comboBoxSomeName`                     |                        | `selectSomeOption`, `selectAccessoryLotId()` |
| 10 | Drop down contains dropDown + name                           | Dropdown                     | `dropDownSomeName`                     |                        | `selectSomeOption`, `selectEquipment()` |
| 11 | List in combo box/drop down contains listItem + name         | ListItem (ComboBox/DropDown)  | `listItemComboBoxOptionName`, `listItemDropDownOptionName` | #8 |                                         |

### FIG.2: Table Naming Convention

| #  | Description                                             | Object/Element               | Naming Example                         | UI Example             | Actions                                 |
|----|---------------------------------------------------------|------------------------------|----------------------------------------|------------------------|-----------------------------------------|
| 12 | Table name contains table + 'Name'                      | Table                        | `tableSomeTableName`                        | #1                     | `clickHeaderTableSomeTableName`             |
| 13 | Table column contains column + ‘Name’ + table name      | Column                       | `columnPatientIdTableSomeTableName`         | #2                     | `clickColumnPatientIdTableSomeTableName`, `getColumnValuesByColumnName(columnName: type)` |
| 14 | Table row contains row + table name                     | Row                          | `rowTableSomeTableName`                     | #3                     | `click`, `getRowValuesByUnitNo(unitNo: string)`, `getRowValuesFromSourceTableByUnitNo(unitNo: string)`, `getRowValuesByRowIndex(1)` |
| 15 | Table column header contains header + column + table name | HeaderColumn                 | `headerPatientTableLedger`             |                        | `click`                                |
| 16 | Table cell contains cell + column + table name          | Cell                         | `cellUnitNoTableComponents`            | #4                     | `click`, `getCellValueByColumnNameForUnitNo(columnName: type, unitNo: string)` |
| 17 | Icon contains icon + name                               | Icon                         | `iconInfo`, `iconTrash`                | #6                     | `click`, `hover`                       |

### Other Naming Conventions

| #  | Description                                             | Object/Element               | Naming Example                         | UI Example             | Actions                                 |
|----|---------------------------------------------------------|------------------------------|----------------------------------------|------------------------|-----------------------------------------|
| 18 | Name of button contains button + name                   | Button                       | `buttonX`, `buttonSave`                |                        | `click`                                |
| 19 | Date picker contains `datePickers + datePickers name`, `datePickers + field name` | DatePicker                   | `datePickerStartDate`, `datePickerDate` |                        | `set (date to field)`, `select (from date picker)` |
| 20 | Name of tab contains tab + name                         | Tab                          | `tabTests`                             |                        | `goToTab`                              |
| 21 | Name of link contains link + name                       | Link                         | `linkUnitNumber`                       |                        | `click`                                |
| 22 | Name of menu items contains menu + name                 | Menu                         | `menuInventories`                      |                        |                                         |

### Methods Naming Conventions

| №  | Description                                             | Object/Element               | Naming Example                         |
|----|---------------------------------------------------------|------------------------------|----------------------------------------|
| 23 | Name of action methods contains action + control name (actions: click, select, clear, set..) | Methods (Positive State only) | `clickButtonPrint()`, `setCheckboxComponent(state: boolean)`, `clearInputAmount()`, `selectTestBattery()` |
| 24 | Name of verify methods contains verify + control name + state (state: checked, exists, isCorrect…) | Verify Methods                | `isNoteDisplayed()`, `isRowWithTextDisplayed(text: string)`, `isCheckboxStatusChecked()`, `isInputStatusCorrect(expectedStatus:string)`, `isTetsBatterySelected()` |

**Note**:  
- Actions contain ONLY Positive state (not "Uncheck").  
- Verify methods also use ONLY Positive state (not "verifyNotExist").  
- Exists - for control existence (true/false), On - true/false (for switcher), Enabled - true/false, Checked - true/false, Selected - true/false, Correct - for displaying of correct data.  
- "Correct" is usually used for inputs where the SAME element can contain DIFFERENT values.  
- "Displayed" verifies the presence of a web element with given parameters on a page.
