---
title: 如何：使 UIElement 呈现为透明或半透明
ms.date: 03/30/2017
helpviewer_keywords:
- UIElements [WPF], transparency
- opacity [WPF], of UIElements
- transparency of UIElements [WPF]
- UIElements [WPF], opacity
ms.assetid: a49fc8d6-7b32-4f28-9122-39b632a19b4b
ms.openlocfilehash: 7bf79848edb84a5bd93d1196fbe0b3196d159ff3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-make-a-uielement-transparent-or-semi-transparent"></a>如何：使 UIElement 呈现为透明或半透明
此示例演示如何使<xref:System.Windows.UIElement>透明或不完全透明。 若要使元素透明或不完全透明，你将设置其<xref:System.Windows.UIElement.Opacity%2A>属性。 值为`0.0`使元素完全透明，而值`1.0`使元素完全不透明。 值为`0.5`使元素 50%不透明，依次类推。 元素的<xref:System.Windows.UIElement.Opacity%2A>设置为`1.0`默认情况下。  
  
## <a name="example"></a>示例  
 下面的示例设置<xref:System.Windows.UIElement.Opacity%2A>到按钮的`0.25`，使它和其内容 （在这种情况下，该按钮的文本） 25%不透明。  
  
 [!code-xaml[brushsamples_snip#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#2)]  
  
 [!code-csharp[brushsamples_procedural_snip#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#2)]  
  
 如果元素的内容有其自己<xref:System.Windows.UIElement.Opacity%2A>设置，这些值乘以包含元素<xref:System.Windows.UIElement.Opacity%2A>。  
  
 下面的示例设置按钮的<xref:System.Windows.UIElement.Opacity%2A>到`0.25`，和<xref:System.Windows.UIElement.Opacity%2A>的<xref:System.Windows.Controls.Image>控件中的按钮为与包含`0.5`。 因此，图像将显示 12.5%不透明： 0.25 * 0.5 = 0.125。  
  
 [!code-xaml[brushsamples_snip#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#3)]  
  
 [!code-csharp[brushsamples_procedural_snip#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#3)]  
  
 若要控制元素的不透明度的另一个方法是设置的不透明度<xref:System.Windows.Media.Brush>绘制元素。 这种方法，您可以有选择性地修改元素，某些部分的不透明度，并通过使用元素的提供性能优势<xref:System.Windows.UIElement.Opacity%2A>属性。 下面的示例设置<xref:System.Windows.Media.Brush.Opacity%2A>的<xref:System.Windows.Media.SolidColorBrush>用于绘制按钮的<xref:System.Windows.Controls.Control.Background%2A>设置为`0.25`。 因此，画笔的背景为 25%不透明的但其内容 （该按钮的文本） 仍保留 100%不透明。  
  
 [!code-xaml[brushsamples_snip#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#4)]  
  
 [!code-csharp[brushsamples_procedural_snip#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#4)]  
  
 您也可以控制单个画笔颜色的不透明度。 有关颜色和画笔的详细信息，请参阅[使用纯色和渐变概述绘制](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)。 有关展示如何进行动画处理的元素的不透明度的示例，请参阅[动画元素或画笔的不透明度](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-the-opacity-of-an-element-or-brush.md)。
