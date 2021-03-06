---
title: ICorProfilerInfo2::GetStaticFieldInfo 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetStaticFieldInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo method [.NET Framework profiling]
- GetStaticFieldInfo method [.NET Framework profiling]
ms.assetid: fc663e76-e23f-49a8-bdd5-52cdf1a3b2b3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f2ab0d482366b037f92a55f00dd33df8a312e84b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfo2getstaticfieldinfo-method"></a>ICorProfilerInfo2::GetStaticFieldInfo 方法
获取一个值，该值指示的将应用到指定的字段的静态类型。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetStaticFieldInfo (  
    [in] ClassID               classId,  
    [in] mdFieldDef            fieldToken,  
    [out] COR_PRF_STATIC_TYPE  *pFieldInfo);  
```  
  
#### <a name="parameters"></a>参数  
 `classId`  
 [in]在其中定义的静态字段的类 ID。  
  
 `fieldToken`  
 [in]静态字段的元数据标记。  
  
 `pFieldInfo`  
 [out]指向的值的指针[COR_PRF_STATIC_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md)枚举，指示是否指定的字段为静态，和如果因此，静态的种类，它将应用于字段。  
  
## <a name="remarks"></a>备注  
 此信息可以用于确定哪一个函数调用以获取静态字段的地址。  
  
 探查器代码仍应检查以确保它确实拥有一个地址的静态字段的元数据。 静态文本 （即，常量） 仅在元数据中存在，但没有一个地址。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
