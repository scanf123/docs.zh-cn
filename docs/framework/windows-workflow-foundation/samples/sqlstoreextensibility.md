---
title: SQLStoreExtensibility
ms.date: 03/30/2017
ms.assetid: 5da1b5a3-f144-41ba-b9c4-02818b28b15d
ms.openlocfilehash: 37c83a9c1062fe074e41ec5db211fd513355c045
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="sqlstoreextensibility"></a>SQLStoreExtensibility
此示例演示了 SQL 工作流实例存储中的已提升属性的使用和配置。 SQL 工作流实例存储是基于 SQL 的实例存储实现。 利用此存储，实例可保存其状态，并将其状态加载到 SQL Server 或 SQL Server Express 数据库中以及从 SQL Server 或 SQL Server Express 数据库中加载其状态。 用户可使用存储扩展性功能来定义存储在示例存储中的属性。 这些属性显示在已提升属性视图中，用户可利用该视图查询这些属性。  
  
 此示例由一个实现计数服务的工作流构成。 在调用该服务的启动方法之后，该服务将从 0 计数到 29。 计数器将每 2 秒递增一次。 在每次计数之后，工作流将持久化。 当前的计数器值将作为一个已提升属性存储在实例存储中。  
  
 计数工作流由工作流服务主机进行自承载。 该程序的 `Main` 方法将执行以下操作：  
  
-   创建一个工作流服务主机实例，它承载计数工作流并定义计数工作流可到达的终结点。  
  
-   定义一个 SQL 工作流实例存储行为，该行为用于配置 SQL 工作流实例存储。 指示存储将 `CountStatus` 视为已提升属性。  
  
-   创建一个调用计数工作流的启动方法的客户端。  
  
 在程序启动之后，计数器自动开始计数。 请注意，加载该实例并配置 SQL 工作流实例存储可能需要花费几秒钟的时间。  
  
 若要将计数器值提升为自定义属性，则必须执行以下步骤：  
  
1.  类 `CounterStatus` 定义类型 <xref:System.Activities.Persistence.PersistenceParticipant> 的实例扩展，活动使用该实例扩展来提供状态变量。 将 `Count` 定义为只写值。 当工作流实例到达某个持久性点时，该实例扩展会将 `Count` 属性保存到持久性数据集合中。  
  
2.  在创建实例存储时，将通过 `CountStatus` 方法定义一个新属性，即 `store.Promote()`。  
  
3.  工作流的 `SaveCounter` 活动将当前计数器值分配给 `Count` 状态字段。  
  
### <a name="to-use-this-sample"></a>使用此示例  
  
1.  创建实例存储区数据库。  
  
    1.  打开一个 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 命令提示符。  
  
    2.  导航到示例目录 (\WF\Basic\Persistence\SqlStoreExtensibility\CS) 并在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 命令提示符下运行 CreateInstanceStore.cmd。  
  
        > [!WARNING]
        >  CreateInstanceStore.cmd 脚本尝试在 SQL Server 2008 Express 的默认实例上创建数据库。 如果要在不同的实例上安装数据库，请修改脚本。  
  
2.  打开 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 并加载 SqlStoreExtensibility.sln 解决方案，然后通过按 CTRL+SHIFT+B 生成它。  
  
    > [!WARNING]
    >  如果在 SQL Server 的非默认实例上安装了数据库，请在生成解决方案之前更新代码中的连接字符串。  
  
3.  通过导航到项目的 bin 目录 (\WF\Basic\Persistence\SqlStoreExtensibility\bin\Debug) 中使用管理员特权运行该示例[!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]，右击 SqlStoreExtensibility.exe 并选择**以运行管理员**。  
  
### <a name="to-verify-the-sample-is-working-correctly"></a>验证此示例是否正常工作  
  
1.  使用 SQL Server Management Studio 查看实例表的内容通过选择**数据库**， **InstanceStore**，，然后**System.ServiceModel.Activities.DurableInstancing.InstanceTable**在对象资源管理器，右键单击**System.ServiceModel.Activities.DurableInstancing.InstanceTable**和选择**选择前 1000年行**。 有关 SQL Server Management Studio 的详细信息，请参阅[SQL Server Management Studio 简介](http://go.microsoft.com/fwlink/?LinkId=165645)  
  
2.  观察列出的工作流实例。  
  
3.  在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 命令提示符下，运行位于示例目录 (\WF\Basic\Persistence\SqlStoreExtensibility) 中的 QueryInstanceStore.cmd 脚本。  
  
4.  观察下显示的计数器值**CountStatus**。  
  
5.  运行脚本几次以查看**CountStats**值的更改。  
  
6.  按 Enter 以终止工作流应用程序。  
  
### <a name="to-uninstall-the-sample"></a>卸载此示例  
  
1.  通过运行位于示例目录 (\WF\Basic\Persistence\SqlStoreExtensibility) 中的 RemoveInstanceStore.cmd 脚本来移除实例存储区数据库。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\SQLStoreExtensibility`  
  
## <a name="see-also"></a>请参阅  
 [工作流暂留](../../../../docs/framework/windows-workflow-foundation/workflow-persistence.md)  
 [工作流服务](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [AppFabric 承载和持久性示例](http://go.microsoft.com/fwlink/?LinkId=193961)
