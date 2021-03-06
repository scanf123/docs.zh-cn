---
title: 如何：在运行时为 Windows 窗体创建事件处理程序
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, event handling
- event handlers [Windows Forms], creating
- run time [Windows Forms], creating event handlers at
- examples [Windows Forms], event handling
- Button control [Windows Forms], event handlers
ms.assetid: 2e7c9e1a-61fe-444d-8113-3c5bacf1c8cb
ms.openlocfilehash: 38453c751e6cc63827f3f1e9d20ad2ebdfc841d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-event-handlers-at-run-time-for-windows-forms"></a>如何：在运行时为 Windows 窗体创建事件处理程序
除了使用 Windows 窗体设计器创建事件外，还可以在运行时创建事件处理程序。 该操作允许在运行时根据代码中的条件连接相应的事件处理程序，而不是在程序刚启动时连接事件处理程序。  
  
### <a name="to-create-an-event-handler-at-run-time"></a>在运行时创建事件处理程序  
  
1.  在代码编辑器中打开要向其添加事件处理程序的窗体。  
  
2.  对于要处理的事件，将带有其方法签名的方法添加到窗体上。  
  
     例如，如果已处理<xref:System.Windows.Forms.Control.Click>事件<xref:System.Windows.Forms.Button>控件，你将创建以下之类的方法：  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As Object, ByVal e As EventArgs)  
       ' Add event handler code here.  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
    // Add event handler code here.  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,   
          System::EventArgs ^ e)  
       {  
          // Add event handler code here.  
       }  
    ```  
  
3.  根据应用程序添加相应的事件处理程序代码。  
  
4.  确定要为其创建事件处理程序的窗体或控件。  
  
5.  在窗体类的方法中添加代码，以指定用于处理事件的事件处理程序。 例如，下面的代码指定事件处理程序`button1_Click`句柄<xref:System.Windows.Forms.Control.Click>事件<xref:System.Windows.Forms.Button>控件：  
  
    ```vb  
    AddHandler Button1.Click, AddressOf Button1_Click  
    ```  
  
    ```csharp  
    button1.Click += new EventHandler(button1_Click);  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     <xref:System.ComponentModel.EventHandlerList.AddHandler%2A>上面的 Visual Basic 代码中演示的方法建立按钮单击事件处理程序。  
  
## <a name="see-also"></a>请参阅  
 [在 Windows 窗体中创建事件处理程序](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
 [事件处理程序概述](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)  
 [Visual Basic 中继承的事件处理程序疑难解答](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
