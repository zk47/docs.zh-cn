---
title: "ICeeGen::ComputePointer 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.ComputePointer
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::ComputePointer
helpviewer_keywords:
- ICeeGen::ComputePointer method [.NET Framework metadata]
- ComputePointer method [.NET Framework metadata]
ms.assetid: b6b95c04-0f2c-4fcc-a8bc-3b1dcbdba731
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c1f5f1c0ea5672812fca387b34238ada2a109938
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="iceegencomputepointer-method"></a>ICeeGen::ComputePointer 方法
确定指定的代码部分的缓冲区。  
  
 此方法已过时，不应使用。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,   
    [out] UCHAR        **lpBuffer  
);  
```  
  
#### <a name="parameters"></a>参数  
 `section`  
 [in]为其返回缓冲区的代码部分。  
  
 `RVA`  
 [in]若要获取的指针的方法相对虚拟地址。  
  
 `lpBuffer`  
 [out]指向返回的缓冲区的指针。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [ICeeGen 接口](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
