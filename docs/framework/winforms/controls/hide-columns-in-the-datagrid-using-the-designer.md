---
title: 如何：使用设计器隐藏 Windows 窗体 DataGridView 控件中的列
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], hiding
- DataGridView control [Windows Forms], column hiding
- data [Windows Forms], displaying
ms.assetid: a81c38e6-2527-426a-bcb1-be691403be04
ms.openlocfilehash: c7362b503f16dd184be3bd04ba21a4d1eb55a390
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-hide-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>如何：使用设计器隐藏 Windows 窗体 DataGridView 控件中的列
有时，你会想仅显示在 Windows 窗体 <xref:System.Windows.Forms.DataGridView> 控件中可用的某些列。 例如，你可能想要显示雇员薪金列具有管理凭据，但却对其他用户隐藏的用户。 或者，你可能想要将控件绑定到包含许多列，其中仅有一些你想要显示的数据源。 在这种情况下，你通常会移除你不感兴趣显示，而不是隐藏它们的列。 有关详细信息，请参阅[如何： 添加和删除 Windows 窗体 DataGridView 控件使用设计器中的列](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)。  
  
 下面的过程需要**Windows 应用程序**具有一个窗体包含项目<xref:System.Windows.Forms.DataGridView>控件。 有关设置此类项目的信息，请参阅[如何： 创建 Windows 应用程序项目](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)和[如何： 向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-hide-a-column-using-the-designer"></a>若要隐藏某一列使用设计器  
  
1.  单击智能标记标志符号 (![智能标记标志符号](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) 右上角<xref:System.Windows.Forms.DataGridView>控制，，然后选择**编辑列**。  
  
2.  选择从列**选定的列**列表。  
  
3.  在**列属性**网格中，设置<xref:System.Windows.Forms.DataGridViewColumn.Visible%2A>属性`false`。  
  
    > [!NOTE]
    >  你还可以隐藏某一列，将其添加通过清除时**可见**中的复选框**添加列**对话框。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>  
 [如何：使用设计器在 Windows 窗体 DataGridView 控件中添加和删除列](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 [如何： 创建 Windows 应用程序项目](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [如何：向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
