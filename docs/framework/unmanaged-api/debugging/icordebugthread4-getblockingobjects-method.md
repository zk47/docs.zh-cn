---
title: "ICorDebugThread4::GetBlockingObjects 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread4.GetBlockingObjects Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread4::GetBlockingObjects
helpviewer_keywords:
- GetBlockingObjects method [.NET Framework debugging]
- ICorDebugThread4::GetBlockingObjects method [.NET Framework debugging]
ms.assetid: a7e6c54e-7be9-4e52-bbb4-95f52458e8e4
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6783d7f9af67acdff147cc46ea4f856f9b10bf3a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugthread4getblockingobjects-method"></a>ICorDebugThread4::GetBlockingObjects 方法
提供的有序的枚举[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)结构，并提供线程阻塞信息。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
```  
  
#### <a name="parameters"></a>参数  
 `ppBlockingObjectEnum`  
 [out]指向的有序枚举[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)结构。  
  
## <a name="remarks"></a>备注  
 返回的枚举中的第一个元素对应于第一个阻塞线程的结构。 第二个元素对应于时阻止在第一天，并因此在运行异步过程调用 (APC) 时遇到的阻碍性项。  
  
 枚举的有效期仅为当前的同步状态的持续时间。  
  
 调试对象处于正在同步状态时，必须调用此方法。  
  
 如果`ppBlockingObjectEnum`不是有效的指针，结果不可确定。  
  
 如果一个线程被阻止，并且无法确定该错误，该方法返回一个 HRESULT，指示故障;否则，它将返回，则为 S_OK。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [ICorDebugThread4 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
