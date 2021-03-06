---
-api-id: T:Windows.UI.Xaml.Media.SolidColorBrush
-api-type: winrt class
---

<!-- Class syntax.
public class SolidColorBrush : Windows.UI.Xaml.Media.Brush, Windows.UI.Xaml.Media.ISolidColorBrush
-->

# Windows.UI.Xaml.Media.SolidColorBrush

## -description
Paints an area with a solid color. The solid color is defined by a [Color](../windows.ui/color.md) value.

## -xaml-syntax
```xaml
<SolidColorBrush .../>
-or-
<SolidColorBrush>colorString</SolidColorBrush>
```

```xaml
<SolidColorBrush Color="predefinedColorName"/>
- or -
<SolidColorBrush Color="#rgb"/>
- or -
<SolidColorBrush Color="#argb"/>
- or -
<SolidColorBrush Color="#rrggbb"/>
- or -
<SolidColorBrush Color="#aarrggbb"/>
- or -
<SolidColorBrush Color="sc#scR,scG,scB"/>
- or -
<SolidColorBrush Color="sc#scA,scR,scG,scB"/>
```


## -remarks
A [SolidColorBrush](solidcolorbrush.md) is the most common type of [Brush](brush.md) that is used for many possible UI properties that use a [Brush](brush.md) to fill some or all of an object's visual area in app UI. Examples of some of the most commonly-used properties that use a [Brush](brush.md) value include: [Control.Background](../windows.ui.xaml.controls/control_background.md), [Control.Foreground](../windows.ui.xaml.controls/control_foreground.md), [Shape.Fill](../windows.ui.xaml.shapes/shape_fill.md), [Control.BorderBrush](../windows.ui.xaml.controls/control_borderbrush.md), [Panel.Background](../windows.ui.xaml.controls/panel_background.md), [TextBlock.Foreground](../windows.ui.xaml.controls/textblock_foreground.md).

For these properties, a **null** value is often acceptable, and has the result that nothing is rendered there. If the element appears in the same coordinate space as other elements, the **null** value for a property such as **Background** causes that element to not register for purposes of hit-testing, and determining where an input event should be sourced from. Any pointer events, gestures or so on that occur on that point in the UI coordinate space are only detectable when there's a value other than **null** for the [Brush](brush.md) property that influences rendering for that point.

A [SolidColorBrush](solidcolorbrush.md) can be created that uses the [Transparent](../windows.ui/colors_transparent.md) value, and although this doesn't visually apply any changes to UI (it's transparent), that point is detectable for hit-testing purposes. So this is different than a [Brush](brush.md) property with a **null** value. A [Transparent](../windows.ui/colors_transparent.md) brush can be useful for techniques such as creating overlay regions over UI elements where you want to intercept the hit testing with an element like a [Rectangle](../windows.ui.xaml.shapes/rectangle.md), [Border](../windows.ui.xaml.controls/border.md) or panel. You might do this if the elements underneath aren't able to do their own hit-testing, but you still want to detect input events. For more info on hit testing, see "Hit testing" section of [Mouse interactions](http://msdn.microsoft.com/library/c8a158ef-70a9-4ba2-a270-7d08125700ac).

Properties using brushes can be animated as part of transitions or decorative animations. You don't typically animate an entire [SolidColorBrush](solidcolorbrush.md) object, you'd have to use a discrete **Object** animation and that's neither efficient nor aesthetic. Instead, you use property targeting to animate just the [Color](solidcolorbrush_color.md) value, using one of the dedicated animation types that can animate a [Color](../windows.ui/color.md) value. This usually involves having `.(SolidColorBrush.Color)` be a part of the [Storyboard.TargetProperty](../windows.ui.xaml.media.animation/storyboard_targetproperty.md) value. For more info on property targeting and how to animate properties that use [SolidColorBrush](solidcolorbrush.md) or other [Brush](brush.md) values, see [Storyboarded animations](http://msdn.microsoft.com/library/0cbceea0-2b0e-44a1-a09a-f7a939632f3a).

A [SolidColorBrush](solidcolorbrush.md) is a shareable object, as are the other derived types of [Brush](brush.md) such as [LinearGradientBrush](lineargradientbrush.md) and [ImageBrush](imagebrush.md). Because it's shareable a [SolidColorBrush](solidcolorbrush.md) is sometimes defined in XAML as a resource in a XAML [ResourceDictionary](../windows.ui.xaml/resourcedictionary.md). The advantage of using shareable resources from XAML is that you're only creating the value once and applying it to multiple properties.

Applying a [UIElement.Opacity](../windows.ui.xaml/uielement_opacity.md) value can change the color appearance of a [SolidColorBrush](solidcolorbrush.md) property applied to an object. The [UIElement.Opacity](../windows.ui.xaml/uielement_opacity.md) value can be cumulative depending on the layout of objects that overlap. The colors appear as expected only when the net **Opacity** value is 1. There's also a [Brush.Opacity](brush_opacity.md) property that can affect the apparent color similarly. [Brush.Opacity](brush_opacity.md) is usually left at its default value of 1, unless it's being deliberately animated for a fade-in or fade-out effect.

### Brushes as XAML resources

Each of the [Brush](brush.md) types that can be declared in XAML ([SolidColorBrush](solidcolorbrush.md), [LinearGradientBrush](lineargradientbrush.md), [ImageBrush](imagebrush.md)) is intended to be defined as a resource, so that you can reuse that brush as a resource throughout your app. The XAML syntax shown for [Brush](brush.md) types is appropriate for defining the brush as a resource. When you declare a brush as a resource, you also need an [x:Key attribute](http://msdn.microsoft.com/library/141fc5af-80ee-4401-8a1b-17cb22c2277a) that you'll later use to refer to that resource from other UI definitions. For more info on XAML resources and how to use [x:Key attribute](http://msdn.microsoft.com/library/141fc5af-80ee-4401-8a1b-17cb22c2277a), see [ResourceDictionary and XAML resource references](http://msdn.microsoft.com/library/e3cbfa3d-6af5-44e1-b9f9-c3d3ea8a25ce).

The advantage of declaring brushes as resources is that it reduces the number of runtime objects that are needed to construct a UI: the brush is now shared as a common resource that's providing values for multiple parts of the object graph.

If you look at the existing control template definitions for Windows Runtime XAML controls, you'll see that the templates use brush resources extensively. Many of these resources are system resources, and they use the [{ThemeResource} markup extension](http://msdn.microsoft.com/library/8a1c79d2-9566-44aa-b8e1-cc7adad1bcc5) for the resource reference rather than [{StaticResource} markup extension](http://msdn.microsoft.com/library/d50349b5-4588-4ebd-9458-75f629ccc395). For more info on how to use system resource brushes in your own control template XAML, see [XAML theme resources](http://msdn.microsoft.com/library/41b87dbf-e7a2-44e9-beba-af6eebabb81b).

## -examples
The most common way to use [SolidColorBrush](solidcolorbrush.md) is to define a XAML element as a resource in a [ResourceDictionary](../windows.ui.xaml/resourcedictionary.md), and then reference that resource later from other parts of UI definitions, styles or templates using either [{StaticResource} markup extension](http://msdn.microsoft.com/library/d50349b5-4588-4ebd-9458-75f629ccc395) or [{ThemeResource} markup extension](http://msdn.microsoft.com/library/8a1c79d2-9566-44aa-b8e1-cc7adad1bcc5) s.

```xaml
<ResourceDictionary>
...
    <SolidColorBrush x:Key="BlockBackgroundBrush" Color="#FF557EB9"/>
...
</ResourceDictionary>
```

```xaml
<Border Background="{StaticResource BlockBackgroundBrush}" 
    Width="80" Height="80"/>

```

There are several different ways to define a [SolidColorBrush](solidcolorbrush.md) as an inline UI value rather than as a resource:


+ Select a predefined color by name, and rely on the XAML "shortcut" that this color will create a [SolidColorBrush](solidcolorbrush.md) when it's parsed. For example, you can set the [Fill](../windows.ui.xaml.shapes/shape_fill.md) of a [Rectangle](../windows.ui.xaml.shapes/rectangle.md) to "Red" like this:




[!code-xml[SolidColorBrushIntroExampleWholePage](../windows.ui.xaml.media/code/brushes_snip/csharp/solidcolorbrush_intro.xaml#SnippetSolidColorBrushIntroExampleWholePage)]

[!code-xml[SolidColorBrushIntroExampleWholePage](../windows.ui.xaml.media/code/brushes_snip/csharp/solidcolorbrush_intro.xaml#SnippetSolidColorBrushIntroExampleWholePage)]
+ Create a color within a 32-bit color palette by specifying the amounts of red, green, and blue to combine into a single solid color.




[!code-xml[SolidColorBrushIntroExampleWholePage](../windows.ui.xaml.media/code/brushes_snip/csharp/solidcolorbrush_intro.xaml#SnippetSolidColorBrushIntroExampleWholePage)]

[!code-xml[SolidColorBrushIntroExampleWholePage](../windows.ui.xaml.media/code/brushes_snip/csharp/solidcolorbrush_intro.xaml#SnippetSolidColorBrushIntroExampleWholePage)]

```csharp
SolidColorBrush greenBrush = new SolidColorBrush(Colors.Green);
```

```cpp
auto greenBrush = ref new SolidColorBrush(Colors::Green);
```

Another way to define a new [SolidColorBrush](solidcolorbrush.md) object is to use the [FromArgb](../windows.ui/color_fromargb.md) static utility method. This is useful if there is no named [Colors](../windows.ui/colors.md) value for the color you want.

```csharp
SolidColorBrush myBrush = new SolidColorBrush(Color.FromArgb(255, 20, 20, 90));

```

```cpp
auto myBrush = ref new SolidColorBrush(ColorHelper::FromArgb(255, 90, 200, 90));

```



## -see-also
[Color](../windows.ui/color.md), [Colors](../windows.ui/colors.md), [Brush](brush.md), [Color.FromArgb](../windows.ui/color_fromargb.md), [Use brushes](http://msdn.microsoft.com/library/02141f86-355e-4046-86ea-2a89d615b7db), [ResourceDictionary and XAML resource references](http://msdn.microsoft.com/library/e3cbfa3d-6af5-44e1-b9f9-c3d3ea8a25ce)
Color.FromArgb(255, 20, 20, 90));

```

```cpp
auto myBrush = ref new SolidColorBrush(ColorHelper::FromArgb(255, 90, 200, 90));

```



## -see-also
[Color](../windows.ui/color.md), [Colors](../windows.ui/colors.md), [Brush](brush.md), [Color.FromArgb](../windows.ui/color_fromargb.md), [Use brushes](http://msdn.microsoft.com/library/02141f86-355e-4046-86ea-2a89d615b7db), [ResourceDictionary and XAML resource references](http://msdn.microsoft.com/library/e3cbfa3d-6af5-44e1-b9f9-c3d3ea8a25ce)