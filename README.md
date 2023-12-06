# Repo2
Debig or Refactor # 2
Code from Co-Opt - Fetching & Parsoing JSON Data
Group Trolley Boys - Darian, Reid & Louis

Improvements:
Function MyApp was upated from:
fun MyApp(products: Products?) {
        Surface(
            modifier = Modifier.fillMaxSize(),
            color = MaterialTheme.colorScheme.background
        ) {
            // Pass the myData parameter to DisplayJsonData
            DisplayJsonData(products)
        }
    }
to:
    fun MyApp(products: Products?) {
        Surface(
            modifier = Modifier.fillMaxSize(),
            color = MaterialTheme.colorScheme.background
        ) {
            // Show loading state while data is being fetched
            if (products == null) {
                CircularProgressIndicator(modifier = Modifier.fillMaxSize().padding(16.dp))
            } else {
                DisplayJsonData(products)
            }
        }
    }

    
The code checks if the products object is null. If it is null, it displays a CircularProgressIndicator, indicating that data is being loaded. 
Otherwise, if the products object is not null, it displays the DisplayJsonData composable function with the fetched products.

CircularProgressIndicator(modifier = Modifier.fillMaxSize().padding(16.dp)): This is displayed while the data is being fetched. 
The CircularProgressIndicator is a composable that shows a circular progress indicator, and Modifier.fillMaxSize().padding(16.dp) ensures that it is centered within the Surface.

Finally: DisplayJsonData(products): Is responsible for displaying the data fetched from the JSON file.
