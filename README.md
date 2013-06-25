Android Color Picker with Transparent Setting

It is basically a clone of [Android Color Picker](http://code.google.com/p/android-color-picker/), with a seekbar fo transparent setting.


Below text is copied from the original project.

------------------------------------------------------------------------------

This is an Android Library Project where you can include it into your main project.

How to use the dialog
---------------------

Create a color picker dialog by calling the following constructor, and then show it.

AmbilWarnaDialog(Context context, int color, OnAmbilWarnaListener listener)

as follows:

// initialColor is the initially-selected color to be shown in the rectangle on the left of the arrow.
// for example, 0xff000000 is black, 0xff0000ff is blue. Please be aware of the initial 0xff which is the alpha.
AmbilWarnaDialog dialog = new AmbilWarnaDialog(this, initialColor, new OnAmbilWarnaListener() {
        @Override
        public void onOk(AmbilWarnaDialog dialog, int color) {
                // color is the color selected by the user.
        }
                
        @Override
        public void onCancel(AmbilWarnaDialog dialog) {
                // cancel was selected by the user
        }
});

dialog.show();

You need to link against Android 3.0 or higher since there is an XML attribute layerType in use. This doesn't mean you can use this only for applications requiring Android 3.0 to operate. It works even in Android 1.6. You just need to select Android 3.0 (API level 11) on the project settings.

How to use it as a Preference
-----------------------------

Very simple. It works like a DialogPreference that stores an Integer to the shared preferences file.

Just add the following to the preferences xml file.

        <yuku.ambilwarna.widget.AmbilWarnaPreference
                android:key="your_preference_key"
                android:defaultValue="0xff6699cc" 
                android:title="Pick a color" />
