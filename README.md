# React Native Modern Datepicker 📆

A customizable calendar, time & month picker for React Native (including Persian Jalaali calendar & locale). For more information, please visit [website](https://hosseinshabani.github.io/react-native-modern-datepicker)

<a href="https://hosseinshabani.github.io/react-native-modern-datepicker">
	<img src="http://tehranreact.ir/public/react-native-modern-datepicker.jpg" alt="hero image" />
</a>


---
__Getting started :)__


Welcome to react-native-modern-datepicker!

1- The package is both Android and iOS compatible.

2- This package uses React hooks. Make sure you're running react-native >= 0.59.0 version.

3- By default, this package inherits font-family from your project ('System'). You can use your own custom font, See options prop.

4- You might see performance issues in development mode. However, you won't see such thing in production build.

---

## Install


    // Some comments
    yarn add react-native-modern-datepicker
    //or if you prefer npm
    npm install react-native-modern-datepicker --save


### Basic usage

``` js
import React, { useState } from 'react';
import DatePicker from 'react-native-modern-datepicker';

const BasicUsage = () => {
  const [selectedDate, setSelectedDate] = useState('');

  return (
    <DatePicker
      onSelectedChange={date => setSelectedDate(date)}
    />
  );
};
```

### RTL/LTR

``` js
import React from 'react';
import DatePicker, { getFormatedDate } from 'react-native-modern-datepicker';

const JalaaliExample = () => {
  return (
    <DatePicker
      isGregorian={false}
      options={{
        defaultFont: 'Shabnam-Light',
        headerFont: 'Shabnam-Medium',
      }}
      selected={getFormatedDate(new Date(), 'jYYYY/jMM/jDD')}
    />
  );
};
```

### Customizable

``` js
import React from 'react';
import DatePicker from 'react-native-modern-datepicker';

const FullUsageExample = () => {
  return (
    <DatePicker
      options={{
        backgroundColor: '#090C08',
        textHeaderColor: '#FFA25B',
        textDefaultColor: '#F6E7C1',
        selectedTextColor: '#fff',
        mainColor: '#F4722B',
        textSecondaryColor: '#D6C7A1',
        borderColor: 'rgba(122, 146, 165, 0.1)',
      }}
      current="2020-07-13"
      selected="2020-07-23"
      mode="calendar"
      minuteInterval={30}
      style={{ borderRadius: 10 }}
    />
  );
};
```
### Minimum and Maximum

```js
import React from 'react';
import DatePicker from 'react-native-modern-datepicker';

const MinMaxExample = () => {
  return (
    <DatePicker
      current="2020-07-13"
      minimumDate="2020-02-17"
      maximumDate="2020-07-25"
    />
  );
};
```

### Time picker

```js
import React, { useState } from 'react';
import DatePicker from 'react-native-modern-datepicker';

const TimePickerExample = () => {
  const [time, setTime] = useState('');

  return (
    <DatePicker
      mode="time"
      minuteInterval={3}
      onTimeChange={selectedTime => setTime(selectedTime)}
    />
  );
};
```

### Month year picker

``` js
import React, { useState } from 'react';
import DatePicker from 'react-native-modern-datepicker';

const MonthYearExample = () => {
  const [date, setDate] = useState('');

  return (
        <DatePicker
              mode="monthYear"
              selectorStartingYear={2023}
              current={'2023/01/05'}
              disabledMonths={[
                { month: 1, year: 2023 },
                { month: 3, year: 2023 },
                { month: 6, year: 2024 },
              ]}
              options={{
                backgroundColor: '#171e30',
                textHeaderColor: '#fff',
                textDefaultColor: '#F6E7C1',
                selectedTextColor: '#fff',
                mainColor: PRIMARY,
                textSecondaryColor: PRIMARY,
              }}
              onMonthYearChange={selectedDate => {console.log(selectedDate)}
            />
  );
};
```

### Localization

```js
import { setCustomNames } from 'react-native-modern-datepicker';

// you can use the utility  to set custom days and months
  setCustomNames({
    dayNames: [
      'Dimanche',
      'Lundi',
      'Mardi',
      'Mercredi',
      'Jeudi',
      'Vendredi',
      'Samedi',
    ],
    dayNamesShort: ['Di', 'Lu', 'Ma', 'Me', 'Je', 'Ve', 'Sa'],
    monthNames: [
      'Janvier',
      'Février',
      'Mars',
      'Avril',
      'Mai',
      'Juin',
      'Juillet',
      'Aout',
      'Septembre',
      'Octobre',
      'Novembre',
      'Décembre',
    ],
  });
```

##### For more examples and more details about used props please check
### [https://hosseinshabani.github.io/react-native-modern-datepicker/](https://hosseinshabani.github.io/react-native-modern-datepicker/)
