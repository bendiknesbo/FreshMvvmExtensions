# FreshMvvm Extensions
[FreshMvvm](https://github.com/rid00z/FreshMvvm) makes developing Xamarin.Forms-apps easier, but creating a new Page and PageModel can be tiresome, when all the references has to be set up correctly, and in the correct folders.  
Thus I created this Visual Studio Extension that creates a blank FreshBasePageModel and FreshBaseContentPage (with d:DataContext for Design-time binding) with the naming-convention that FreshMvvm uses.

# How to install
Install from [Visual Studio Marketplace](https://marketplace.visualstudio.com/vsgallery/a3bdb812-8470-40b5-94e3-7c0cc6fe2aaa).  
Or: download and install the .vsix directly. Find the newest release on the [releases page](https://github.com/XplittR/FreshMvvmExtensions/releases/)

# How to use
* Right-click the PCL-project-root -> "Add" -> "New Item..."
* Select "Forms Blank FreshMvvm Page and PageModel"
* Enter the name of the Page/Page model you want to create. ("Quote" becomes "QuotePageModel" and "QuotePage")
* Click Add

And thats it!

# Examples
Example output QuotePage.xaml:  

```xml
<?xml version="1.0" encoding="utf-8" ?>
<freshMvvm:FreshBaseContentPage
    xmlns="http://xamarin.com/schemas/2014/forms"
    xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
    xmlns:freshMvvm="clr-namespace:FreshMvvm;assembly=FreshMvvm"
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
    xmlns:pageModels="clr-namespace:MyProject.PageModels;assembly=MyProject"
    mc:Ignorable="d" d:DataContext="{d:DesignInstance pageModels:QuotePageModel}"
    x:Class="MyProject.Pages.QuotePage">
</freshMvvm:FreshBaseContentPage>
```

Example output QuotePage.xaml.cs:  

```csharp
using FreshMvvm;

namespace MyProject.Pages {
    public partial class QuotePage : FreshBaseContentPage {
        public QuotePage() {
            InitializeComponent();
        }
    }
}
```

Example output QuotePageModel.cs:  

```csharp
using FreshMvvm;

namespace MyProject.PageModels {
    public class QuotePageModel : FreshBasePageModel {

    }
}
```

## Issues?
If you encounter any issues, have any feature requests or pull requests, please do not hesitate to submit them!  
I have only tested with Microsoft Visual Studio Enterprise 2017.

## Thanks
- Thanks to Microsoft for creating [Xamarin.Forms](https://www.xamarin.com/).
- Thanks to [Michael Ridland](https://github.com/rid00z) for creating [FreshMvvm for Xamarin.Forms](https://github.com/rid00z/FreshMvvm).
- Thanks to [Icons8](http://icons8.com) for providing free icon.