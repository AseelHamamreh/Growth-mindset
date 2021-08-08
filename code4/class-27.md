# Read: 27 - Intents, Activities, and SharedPreferences

## Android Tasks and the Back Stack

#### activities vs tasks:

1, When Activity A starts Activity B, Activity A is stopped, but the system retains its state (such as scroll position and text entered into forms). If the user presses the Back button while in Activity B, Activity A resumes with its state restored.
2. When the user leaves a task by pressing the Home button, the current activity is stopped and its task goes into the background. The system retains the state of every activity in the task. If the user later resumes the task by selecting the launcher icon that began the task, the task comes to the foreground and resumes the activity at the top of the stack.
3. If the user presses the Back button, the current activity is popped from the stack and destroyed. The previous activity in the stack is resumed. When an activity is destroyed, the system does not retain the activity's state.
4. Activities can be instantiated multiple times, even from other tasks.

#### Managing Tasks:

The way Android manages tasks and the back stack, as described above—by placing all activities started in succession in the same task and in a "last in, first out" stack—works great for most apps and you shouldn't have to worry about how your activities are associated with tasks or how they exist in the back stack. 

#### Defining launch modes:

Launch modes allow you to define how a new instance of an activity is associated with the current task. You can define different launch modes in two ways:

1. Using the manifest file.
2. Using Intent flags.

****

## Android SharedPreferences

#### Save key-value data

If you have a relatively small collection of key-values that you'd like to save, you should use the SharedPreferences APIs. A SharedPreferences object points to a file containing key-value pairs and provides simple methods to read and write them. Each SharedPreferences file is managed by the framework and can be private or shared.

##### Get a handle to shared preferences:

You can create a new shared preference file or access an existing one by calling one of these methods:

* getSharedPreferences() — Use this if you need multiple shared preference files identified by name, which you specify with the first parameter. You can call this from any Context in your app.
* getPreferences() — Use this from an Activity if you need to use only one shared preference file for the activity. Because this retrieves a default shared preference file that belongs to the activity, you don't need to supply a name.

##### Write to shared preferences:

To write to a shared preferences file, create a SharedPreferences.Editor by calling edit() on your SharedPreferences.
Pass the keys and values you want to write with methods such as putInt() and putString(). Then call apply() or commit() to save the changes.

##### Read from shared preferences:

To retrieve values from a shared preferences file, call methods such as getInt() and getString(), providing the key for the value you want, and optionally a default value to return if the key isn't present. For example:




