#This is old now and not maintained and probably doesnt work perfectly anymore#

Hijri (Islamic) Calendar
========

HijriCalendar is a fragment made from the Caldroid fragment by thomasdao. Made Originally for my app [Muslim Zone] (https://play.google.com/store/apps/details?id=com.sahaab.android.muslimzone.donation).

It has the same functions as Caldroid and more. You can get Islamic Dates for a certain date and many other functions.

<img src="https://raw.githubusercontent.com/sahaab/HijriCalendar-master/master/HijriCalendarScreenShots/Screenshot_2014-11-10-22-02-30.png" width="270">
<img src="https://raw.githubusercontent.com/sahaab/HijriCalendar-master/master/HijriCalendarScreenShots/Screenshot_2014-11-10-22-02-39.png" width="270">

Sources
=======
Caldroid : https://github.com/roomorama/Caldroid <br>
Umm Al Qura Islamic Calendar : https://gist.github.com/fatfingers/6492017

Instructions
=======
This is mainly built for eclipse, on eclipse. To use on eclipse, 
1 - download the Project and import it into eclipse
2 - To use in your project, reference the child library project as a library, by going to your apps properties - > Android - > and the add as library
3 - Then simply in you activity file, add this code 
```
    final CaldroidFragment caldroidFragment = new CaldroidFragment();
    Bundle args = new Bundle();
    Calendar cal = Calendar.getInstance();
    args.putInt(CaldroidFragment.MONTH, cal.get(Calendar.MONTH) + 1);
    args.putInt(CaldroidFragment.YEAR, cal.get(Calendar.YEAR));
    caldroidFragment.setArguments(args);

        
    FragmentTransaction t = getSupportFragmentManager().beginTransaction();
    t.replace(R.id.calendar1, caldroidFragment);
    t.commit();
```

and in your activity layout add
```
	<LinearLayout
		android:id="@+id/calendar1"
		android:layout_width="match_parent"
		android:layout_height="wrap_content"
		android:layout_below="@+id/HijriDateCalendar"
		android:orientation="vertical" >
	</LinearLayout> 
```		

**For More Detailed Instructions** - Please Look at the sample app, or the README_CALDROID.md file	

**To Get HijriDate** - You have 4 options to get the Hijri  Dates
```
	public static String getSimpleDate(Calendar cal, String valuechange) returns Full Date (e.g 17 Muharram 1436)
	
	public static String getSimpleDateDay(Calendar cal, String valuechange) returns Date
	
	public static String getSimpleDateMonth(Calendar cal, String valuechange) returns Month
	
	public static String getSimpleDateYear(Calendar cal, String valuechange) returns Year
```
	
Accepted Strings for ```valuechange``` are
```
any integer
```

To use, simply use code 
e.g for current date
```
HijriCalendarDate.getSimpleDate(Calendar.getInstance(),"0")
```
License
=======
See LICENSE.md

