# csc_picker_plus 
![version](https://img.shields.io/badge/version-0.2.6-blue.svg)  ![version](https://img.shields.io/badge/NullSefety-True-brightgreen) 

A flutter package to display a country, states, and cities. In addition it gives the possibility to select a list of countries, States and Cities depends on Selected, also you can search country, state, and city all around the world.

<div style="text-align:center">
<table>
<tr>
<td><img src="https://github.com/altafc22/csc_picker/blob/master/screenshot/horizontal_layout.gif?raw=true" alt="Horizontal Layout" width="240"/></td>
<td><img src="https://github.com/altafc22/csc_picker/blob/master/screenshot/vertical_layout.gif?raw=true"  alt="Vertical Layout" width="240"/></td>

</tr>
</table>
</div>

## How to Use

To use this Package, add `csc_picker_plus` as a [dependency in your pubspec.yaml](https://flutter.io/platform-plugins/).

```dart
CSCPickerPlus(
  countryStateLanguage: CountryStateLanguage.arabic,
  // countryStateLanguage: CountryStateLanguage.englishOrNative,
  onCountryChanged: (value) {
    setState(() {
      countryValue = value;
    });
  },
  onStateChanged: (value) {
    setState(() {
      stateValue = value ?? '';
    });
  },
  onCityChanged: (value) {
    setState(() {
      cityValue = value ?? '';
    });
  },
),
```
you will get feedback in onChanged functions
<br>
<br>

### Parameters
<table>
  <thead>
    <tr>
      <th><b>Parameters</b></th>
      <th><b>Type</b></th>
      <th><b>Description</b></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><b>countryStateLanguage</b></td>
      <td>CountryStateLanguage</td>
      <td>This property controls the language of the country and state list. You can choose between Arabic or English (English or the country's native language if English is not available).</td>
    </tr>
    <tr>
      <td><b>cityLanguage</b></td>
      <td>CityLanguage</td>
      <td>This property controls the language of the city list.</td>
    </tr>
    <tr>
      <td><b>flagState</b></td>
      <td>CountryFlag</td>
      <td>Enable (get flag with country name) / Disable (Disable flag) / ShowInDropdownOnly (display flag in dropdown only).</td>
    </tr>
    <tr>
      <td><b>layout</b></td>
      <td>Layout</td>
      <td>Toggle dropdown layout (Horizontal / Vertical).</td>
    </tr>
    <tr>
      <td><b>showStates</b></td>
      <td>Boolean</td>
      <td>Enable/disable States dropdown (true / false).</td>
    </tr>
    <tr>
      <td><b>showCities</b></td>
      <td>Boolean</td>
      <td>Enable/disable Cities dropdown (true / false).</td>
    </tr>
    <tr>
      <td><b>dropdownDecoration</b></td>
      <td>BoxDecoration</td>
      <td>Dropdown box decoration to style your dropdown selector [OPTIONAL PARAMETER] (USE with disabledDropdownDecoration).</td>
    </tr>
    <tr>
      <td><b>disabledDropdownDecoration</b></td>
      <td>BoxDecoration</td>
      <td>Disabled Dropdown box decoration to style your dropdown selector [OPTIONAL PARAMETER] (USE with disabled dropdownDecoration).</td>
    </tr>
    <tr>
      <td><b>selectedItemStyle</b></td>
      <td>TextStyle</td>
      <td>To change selected item style.</td>
    </tr>
    <tr>
      <td><b>dropdownHeadingStyle</b></td>
      <td>TextStyle</td>
      <td>To change DropdownDialog Heading style.</td>
    </tr>
    <tr>
      <td><b>dropdownItemStyle</b></td>
      <td>TextStyle</td>
      <td>To change DropdownDialog Item style.</td>
    </tr>
    <tr>
      <td><b>dropdownDialogRadius</b></td>
      <td>double</td>
      <td>To change DropdownDialogBox radius.</td>
    </tr>
    <tr>
      <td><b>searchBarRadius</b></td>
      <td>double</td>
      <td>To change search bar radius.</td>
    </tr>
    <tr>
      <td><b>defaultCountry</b></td>
      <td>CscCountry</td>
      <td>To select default country.</td>
    </tr>
    <tr>
      <td><b>disableCountry</b></td>
      <td>Boolean</td>
      <td>Disable country dropdown (Note: use it with default country).</td>
    </tr>
    <tr>
      <td><b>countryFilter</b></td>
      <td>List of CscCountry</td>
      <td>Show only countries in dropdown that you want.</td>
    </tr>
    <tr>
      <td><b>countrySearchPlaceholder</b></td>
      <td>String</td>
      <td>Placeholder for country search field.</td>
    </tr>
    <tr>
      <td><b>stateSearchPlaceholder</b></td>
      <td>String</td>
      <td>Placeholder for state search field.</td>
    </tr>
    <tr>
      <td><b>citySearchPlaceholder</b></td>
      <td>String</td>
      <td>Placeholder for city search field.</td>
    </tr>
    <tr>
      <td><b>countryDropdownLabel</b></td>
      <td>String</td>
      <td>Label/Title for country dropdown.</td>
    </tr>
    <tr>
      <td><b>stateDropdownLabel</b></td>
      <td>String</td>
      <td>Label/Title for state dropdown.</td>
    </tr>
    <tr>
      <td><b>cityDropdownLabel</b></td>
      <td>String</td>
      <td>Label/Title for city dropdown.</td>
    </tr>
  </tbody>
</table>

### Example

```dart
import 'package:csc_picker_plus/csc_picker_plus.dart';
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'CSC Picker Plus Demo',
      theme: ThemeData(
        colorScheme: ColorScheme.fromSeed(seedColor: Colors.deepPurple),
        useMaterial3: true,
        visualDensity: VisualDensity.adaptivePlatformDensity,
      ),
      home: const MyHomePage(title: 'CSC Picker Plus'),
    );
  }
}

class MyHomePage extends StatefulWidget {
  const MyHomePage({super.key, required this.title});

  final String title;

  @override
  State<MyHomePage> createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  /// Variables to store country state city data in onChanged method.
  String countryValue = "";
  String stateValue = "";
  String cityValue = "";
  String address = "";

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text(widget.title)),
      body: Center(
        child: Container(
          padding: const EdgeInsets.symmetric(horizontal: 20),
          height: 600,
          child: Column(
            children: [
              /// Adding CSC Picker Plus Widget in app
              CSCPickerPlus(
                /// Enable disable state dropdown [OPTIONAL PARAMETER]
                showStates: true,

                /// Enable disable city drop down [OPTIONAL PARAMETER]
                showCities: true,

                /// Enable (get flag with country name) / Disable (Disable flag) / ShowInDropdownOnly (display flag in dropdown only) [OPTIONAL PARAMETER]
                flagState: CountryFlag.ENABLE,

                /// Control the language of the country and state list [OPTIONAL PARAMETER]
                countryStateLanguage: CountryStateLanguage.englishOrNative,

                /// Control the language of the country and state list [OPTIONAL PARAMETER]
                cityLanguage: CityLanguage.native,

                /// Dropdown box decoration to style your dropdown selector [OPTIONAL PARAMETER] (USE with disabledDropdownDecoration)
                dropdownDecoration: BoxDecoration(
                  borderRadius: const BorderRadius.all(Radius.circular(10)),
                  color: Colors.white,
                  border: Border.all(color: Colors.grey.shade300, width: 1),
                ),

                /// Disabled Dropdown box decoration to style your dropdown selector [OPTIONAL PARAMETER]  (USE with disabled dropdownDecoration)
                disabledDropdownDecoration: BoxDecoration(
                  borderRadius: const BorderRadius.all(Radius.circular(10)),
                  color: Colors.grey.shade200,
                  border: Border.all(color: Colors.grey.shade300, width: 1),
                ),

                /// placeholders for dropdown search field [OPTIONAL PARAMETERS]
                // countrySearchPlaceholder: "Country",
                // stateSearchPlaceholder: "State",
                // citySearchPlaceholder: "City",

                /// labels for dropdown [OPTIONAL PARAMETERS]
                countryDropdownLabel: "Country",
                stateDropdownLabel: "State",
                cityDropdownLabel: "City",

                /// Default Country [OPTIONAL PARAMETER]
                // defaultCountry: CscCountry.Yemen,

                /// Country Filter [OPTIONAL PARAMETER]
                // countryFilter: const [
                //   CscCountry.Yemen,
                //   CscCountry.Saudi_Arabia,
                //   CscCountry.United_States,
                // ],

                /// Disable country dropdown (Note: use it with default country)
                // disableCountry: true,

                /// selected item style [OPTIONAL PARAMETER]
                selectedItemStyle: const TextStyle(
                  color: Colors.black,
                  fontSize: 14,
                ),

                /// DropdownDialog Heading style [OPTIONAL PARAMETER]
                dropdownHeadingStyle: const TextStyle(
                  color: Colors.black,
                  fontSize: 17,
                  fontWeight: FontWeight.bold,
                ),

                /// DropdownDialog Item style [OPTIONAL PARAMETER]
                dropdownItemStyle: const TextStyle(
                  color: Colors.black,
                  fontSize: 14,
                ),

                /// Dialog box radius [OPTIONAL PARAMETER]
                dropdownDialogRadius: 10.0,

                /// Search bar radius [OPTIONAL PARAMETER]
                searchBarRadius: 10.0,

                /// triggers once country selected in dropdown
                onCountryChanged: (value) {
                  setState(() {
                    /// store value in country variable
                    countryValue = value;
                  });
                },

                /// triggers once state selected in dropdown
                onStateChanged: (value) {
                  if (value != null) {
                    setState(() {
                      ///store value in state variable
                      stateValue = value;
                    });
                  }
                },

                /// triggers once city selected in dropdown
                onCityChanged: (value) {
                  if (value != null) {
                    setState(() {
                      ///store value in city variable
                      cityValue = value;
                    });
                  }
                },
              ),

              /// print newly selected country state and city in Text Widget
              TextButton(
                onPressed: () {
                  setState(() {
                    address = "$cityValue, $stateValue, $countryValue";
                  });
                },
                child: const Text("Print Data"),
              ),
              Text(address),
            ],
          ),
        ),
      ),
    );
  }
}
```

### Contributor

**Hezbr Al-humaidi**  
Email: [eng.hezbr@gmail.com](mailto:eng.hezbr@gmail.com)


### Special Thanks to
- Altaf Razzaque, csc_picker [country_state_city_picker](https://github.com/ltafc22/csc_picker)