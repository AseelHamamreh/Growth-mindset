# Read: 28 - RecyclerView

* RecyclerView helps us to display a large set of data. we just supply the data and choose how each item looks, and the RecyclerView library dynamically creates the elements when they're needed.
* RecyclerView doesn't distroy the app view, the new large items will have a scroll.

### Creating dynamic lists with RecyclerView:

1. choose how the list is going to look like.
2. Design how each element in the list is going to look and behave. Based on this design, extend the ViewHolder class. Your version of ViewHolder provides all the functionality for your list items. Your view holder is a wrapper around a View, and that view is managed by RecyclerView.
3. Define the Adapter that associates your data with the ViewHolder views.
4. Plan your layout.
5. Implementing your adapter and view holder: create two classes; ```Adapter``` and ```ViewHolder```. These two classes work together to define how your data is displayed.
* The ```ViewHolder``` is a wrapper around a View that contains the layout for an individual item in the list.
* The ```Adapter``` creates ```ViewHolder``` objects as needed, and also sets the data for those views. The process of associating views to their data is called binding.

* When you define your adapter, you need to override three key methods:
1. ``` onCreateViewHolder()```: RecyclerView calls this method whenever it needs to create a new ViewHolder. The method creates and initializes the ViewHolder and its associated View, but does not fill in the view's contents—the ViewHolder has not yet been bound to specific data.
2. ```onBindViewHolder()```: RecyclerView calls this method to associate a ViewHolder with data. The method fetches the appropriate data and uses the data to fill in the view holder's layout. For example, if the RecyclerView displays a list of names, the method might find the appropriate name in the list and fill in the view holder's TextView widget.
4. ```getItemCount()```: RecyclerView calls this method to get the size of the data set. For example, in an address book app, this might be the total number of addresses. RecyclerView uses this to determine when there are no more items that can be displayed.