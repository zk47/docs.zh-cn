---
title: "ICorDebugStepper::IsActive 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.IsActive
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::IsActive method [.NET Framework debugging]
ms.assetid: 8b35e7a9-b40e-40a9-8d8e-b82e823fc575
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 25e4b59c59ee4340c14da22143f49c645e1dcc7b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugstepperisactive-method"></a><span data-ttu-id="e79a8-102">ICorDebugStepper::IsActive 方法</span><span class="sxs-lookup"><span data-stu-id="e79a8-102">ICorDebugStepper::IsActive Method</span></span>
<span data-ttu-id="e79a8-103">获取一个值，该值指示是否此 ICorDebugStepper 当前正在执行一个步骤。</span><span class="sxs-lookup"><span data-stu-id="e79a8-103">Gets a value that indicates whether this ICorDebugStepper is currently executing a step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e79a8-104">语法</span><span class="sxs-lookup"><span data-stu-id="e79a8-104">Syntax</span></span>  
  
```  
HRESULT IsActive (  
    [out] BOOL   *pbActive  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e79a8-105">参数</span><span class="sxs-lookup"><span data-stu-id="e79a8-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="e79a8-106">[out]返回`true`如果分档器当前正在执行一个步骤; 否则，返回`false`。</span><span class="sxs-lookup"><span data-stu-id="e79a8-106">[out] Returns `true` if the stepper is currently executing a step; otherwise, returns `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e79a8-107">备注</span><span class="sxs-lookup"><span data-stu-id="e79a8-107">Remarks</span></span>  
 <span data-ttu-id="e79a8-108">任何步骤操作保持活动状态，直至调试器收到[icordebugmanagedcallback:: Stepcomplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)调用，这可以自动将分档器停用。</span><span class="sxs-lookup"><span data-stu-id="e79a8-108">Any step action remains active until the debugger receives a [ICorDebugManagedCallback::StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md) call, which automatically deactivates the stepper.</span></span> <span data-ttu-id="e79a8-109">分档器可能还停用过早地通过调用[icordebugstepper:: Deactivate](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md)在回调之前条件为止。</span><span class="sxs-lookup"><span data-stu-id="e79a8-109">A stepper may also be deactivated prematurely by calling [ICorDebugStepper::Deactivate](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md) before the callback condition is reached.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e79a8-110">要求</span><span class="sxs-lookup"><span data-stu-id="e79a8-110">Requirements</span></span>  
 <span data-ttu-id="e79a8-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e79a8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e79a8-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e79a8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e79a8-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e79a8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e79a8-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e79a8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>