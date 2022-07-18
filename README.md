# KenyanCounties
A Simple Android Library for Kenyan Counties

### Step 1. Add the JitPack repository to your build file 
Add it in your root build.gradle at the end of repositories:
```Kotlin
allprojects {
    repositories {
        ...
        maven { url 'https://jitpack.io' }
    }
}
```

### Step 2. Add the dependency
```Kotlin
dependencies {
    implementation 'com.github.JoelKanyi:KenyanCounties:1.0.0'
}
```

### Usage
#### Attaching Counties to Spinner
```kotlin
        val arrayAdapter: ArrayAdapter<String> =
            ArrayAdapter<String>(this, android.R.layout.simple_spinner_item, Kenya.counties())
        arrayAdapter.setDropDownViewResource(android.R.layout.simple_spinner_dropdown_item)
        binding.spinner.adapter = arrayAdapter
```
  
#### Getting a County Name by it Code  
```kotlin
        binding.textViewCountyName.text = Kenya.getCountyName("001")
```

#### Getting a County Code from its Name        
```kotlin
        binding.textViewCountyCode.text = Kenya.getCountyCode("Nairobi")
```

#### Getting CountName and CountyCode and displaying them in a RecyclerView
```kotlin
        adapter.submitList(Kenya.countiesWithCodes())
        binding.countiesAndCodesRecyclerview.adapter = adapter
```
