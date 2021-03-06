---
title: LoadFromHistory 函数 （WPF 非托管 API 参考）
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: 19674b45af84e1e6a6ca169f7b6654c6e3847416
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a>LoadFromHistory 函数 （WPF 非托管 API 参考）
此 API 支持的 Windows Presentation Foundation (WPF) 基础结构，不宜在代码中直接使用。  
  
 Windows Presentation Foundation (WPF) 基础结构用于 windows 管理。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,   
        IBindCtx* pBindCtx  
)  
```  
  
#### <a name="parameters"></a>参数  
 pHistoryStream  
 指向历史记录信息的流的指针。  
  
 pBindCtx  
 指向绑定上下文的指针。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[.NET Framework 系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **DLL:**  
  
 在.NET Framework 3.0 和 3.5: PresentationHostDLL.dll  
  
 在.NET Framework 4 及更高版本： PresentationHost_v0400.dll  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [WPF 非托管 API 参考](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
