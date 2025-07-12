## Features

- Unlimited Habits
- Calendar view
- ~Calendar Subscription~
- Maintain third-party calendar subscription (If you subscribe your calendar via Paid Ticktick (maybe even with trials version), after opting-out you can still use it)
- Widgets
- Reminders
- Themes
- ⚠️ Some features might not work if it is restricted on server side

## How I made it

- Use dnSpy
- Update these:

Approach 1:

```
// in ticktick_WPF.Models.UserModel
proEndDate=>DateTime.MaxValue;
pro=>true;
```

Approach 2:

```c#
// in ticktick_WPF.Resource.LocalSettings

public bool IsPro
{
  get
  {
    return this.SettingsModel.IsPro;
  }
  set
  {
    this.SettingsModel.IsPro = true; //force it to true
    this.OnPropertyChanged("IsPro");
  }
}

// ticktick_WPF.Dal.UserDao
//public static bool IsPro()
//{
//  return true; // force to true
//}
```
