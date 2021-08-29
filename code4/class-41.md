# Lab: 41 - Intent Filters

### Add an Intent Filter
In order to properly define which intents your activity can handle, each intent filter you add should be as specific as possible in terms of the type of action and data the activity accepts.

The system may send a given Intent to an activity if that activity has an intent filter fulfills the following criteria of the Intent object:
##### Action
A string naming the action to perform. Usually one of the platform-defined values such as ACTION_SEND or ACTION_VIEW.
Specify this in your intent filter with the <action> element. The value you specify in this element must be the full string name for the action, instead of the API constant.

##### Data
A description of the data associated with the intent.
Specify this in your intent filter with the <data> element. Using one or more attributes in this element, you can specify just the MIME type, just a URI prefix, just a URI scheme, or a combination of these and others that indicate the data type accepted.

##### Category
Provides an additional way to characterize the activity handling the intent, usually related to the user gesture or location from which it's started. There are several different categories supported by the system, but most are rarely used. However, all implicit intents are defined with CATEGORY_DEFAULT by default.
Specify this in your intent filter with the <category> element.

In your intent filter, you can declare which criteria your activity accepts by declaring each of them with corresponding XML elements nested in the <intent-filter> element.

Each incoming intent specifies only one action and one data type, but it's OK to declare multiple instances of the <action>, <category>, and <data> elements in each <intent-filter>.

If any two pairs of action and data are mutually exclusive in their behaviors, you should create separate intent filters to specify which actions are acceptable when paired with which data types.

### Handle the Intent in Your Activity

In order to decide what action to take in your activity, you can read the Intent that was used to start it.

As your activity starts, call getIntent() to retrieve the Intent that started the activity. You can do so at any time during the lifecycle of the activity, but you should generally do so during early callbacks such as onCreate() or onStart().

example:

```
override fun onCreate(savedInstanceState: Bundle?) {
    super.onCreate(savedInstanceState)

    setContentView(R.layout.main)

    val data: Uri? = intent?.data

    // Figure out what to do based on the intent type
    if (intent?.type?.startsWith("image/") == true) {
        // Handle intents with image data ...
    } else if (intent?.type == "text/plain") {
        // Handle intents with text ...
    }
}
```

### Return a Result

If you want to return a result to the activity that invoked yours, simply call setResult() to specify the result code and result Intent. When your operation is done and the user should return to the original activity, call finish() to close (and destroy) your activity. For example:
```
// Create intent to deliver some kind of result data
Intent("com.example.RESULT_ACTION", Uri.parse("content://result_uri")).also { result ->
    setResult(Activity.RESULT_OK, result)
}
finish()
```

You must always specify a result code with the result. Generally, it's either RESULT_OK or RESULT_CANCELED. You can then provide additional data with an Intent, as necessary.

If you simply need to return an integer that indicates one of several result options, you can set the result code to any value higher than 0. If you use the result code to deliver an integer and you have no need to include the Intent, you can call setResult() and pass only a result code. For example:

```
setResult(RESULT_COLOR_RED)
finish()
```

In this case, there might be only a handful of possible results, so the result code is a locally defined integer (greater than 0). This works well when you're returning a result to an activity in your own app, because the activity that receives the result can reference the public constant to determine the value of the result code.

