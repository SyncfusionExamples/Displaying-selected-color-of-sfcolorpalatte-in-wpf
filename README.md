# Display Selected Color from Syncfusion SfColorPalette in WPF

This sample shows how to display the currently selected color from the Syncfusion SfColorPalette control in a WPF application. It binds the SfColorPalette.SelectedColor property to a Rectangle.Fill using a simple IValueConverter so users get an instant visual preview of the chosen color.

## Features
- Syncfusion SfColorPalette integration for quick color picking
- Live color preview using a Rectangle bound to SelectedColor
- Lightweight IValueConverter to convert Color to SolidColorBrush
- Clean WPF MVVM-friendly binding approach (no code-behind logic required for preview)

## What the Sample Demonstrates
- Binding from the Syncfusion color picker to another UI element
- Converting the Color selected in the palette to a SolidColorBrush for UI painting

Key pieces:
- Converter class: ColorHexToStringConverter in [MainWindow.xaml.cs](ColorPalatte_SelectedColor/MainWindow.xaml.cs)
- Binding in XAML: Rectangle.Fill bound to SelectedColor with converter in [MainWindow.xaml](ColorPalatte_SelectedColor/MainWindow.xaml)

## Getting Started
1. Open the solution:
   - File > Open > Project/Solution, then select [ColorPalatte_SelectedColor/ColorPalatte_SelectedColor.sln](ColorPalatte_SelectedColor/ColorPalatte_SelectedColor.sln)
2. Restore NuGet packages:
   - In Visual Studio: Right-click the solution > Restore NuGet Packages
   - Ensure the packages in [packages.config](ColorPalatte_SelectedColor/packages.config) are restored (Syncfusion.Licensing, Syncfusion.SfColorPalette.WPF, Syncfusion.SfShared.WPF, Syncfusion.SfRadialMenu.WPF)
3. Build and run:
   - Set startup project to ColorPalatte_SelectedColor
   - Press F5 to run

## How It Works
- The SfColorPalette control (named "SfColorPalette" in [MainWindow.xaml](ColorPalatte_SelectedColor/MainWindow.xaml)) exposes a SelectedColor property of type System.Windows.Media.Color.
- The Rectangle.Fill expects a SolidColorBrush, so the sample includes an IValueConverter (ColorHexToStringConverter) in [MainWindow.xaml.cs](ColorPalatte_SelectedColor/MainWindow.xaml.cs) that wraps the Color into a SolidColorBrush.
- The binding applies this converter so the Rectangle shows the selected color live as the user interacts with the palette.

## Usage Tips
- To use the selected color elsewhere in your app, bind to SfColorPalette.SelectedColor and apply a similar converter or handle it in your view model.
- If you need two-way scenarios (e.g., setting the initial selected color), set the bound source to a Color property and update it programmatically.
- Keep the converter stateless and reusable by placing it in application resources (see Window.Resources in [MainWindow.xaml](ColorPalatte_SelectedColor/MainWindow.xaml)).

## About the Sample
This is a concise reference for previewing colors selected with Syncfusion SfColorPalette. Extend it by binding SelectedColor into your application theme, storing chosen colors in settings, or using the selected color to style other controls dynamically.
