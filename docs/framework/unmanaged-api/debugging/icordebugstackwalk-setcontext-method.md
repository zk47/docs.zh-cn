---
title: "ICorDebugStackWalk::SetContext 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStackWalk.SetContext Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStackWalk::SetContext
helpviewer_keywords:
- SetContext method [.NET Framework debugging]
- ICorDebugStackWalk::SetContext method [.NET Framework debugging]
ms.assetid: bac0b156-31a3-4e7f-be4d-ab21789c81f1
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 374092c500d4263a172219c38cbc1b2f0ce293a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugstackwalksetcontext-method"></a><span data-ttu-id="74c2e-102">ICorDebugStackWalk::SetContext 方法</span><span class="sxs-lookup"><span data-stu-id="74c2e-102">ICorDebugStackWalk::SetContext Method</span></span>
<span data-ttu-id="74c2e-103">集[ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)到有效的上下文线程对象的当前上下文。</span><span class="sxs-lookup"><span data-stu-id="74c2e-103">Sets the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object’s current context to a valid context for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74c2e-104">语法</span><span class="sxs-lookup"><span data-stu-id="74c2e-104">Syntax</span></span>  
  
```  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="74c2e-105">参数</span><span class="sxs-lookup"><span data-stu-id="74c2e-105">Parameters</span></span>  
 `flag`  
 <span data-ttu-id="74c2e-106">[in]A [CorDebugSetContextFlag](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md)指示上下文是来自堆栈上，活动帧，还是通过展开堆栈获取上下文的标志。</span><span class="sxs-lookup"><span data-stu-id="74c2e-106">[in] A [CorDebugSetContextFlag](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md) flag that indicates whether the context is from the active frame on the stack, or a context obtained by unwinding the stack.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="74c2e-107">[in]分配的大小的`CONTEXT`缓冲区。</span><span class="sxs-lookup"><span data-stu-id="74c2e-107">[in] The allocated size of the `CONTEXT` buffer.</span></span>  
  
 `context`  
 <span data-ttu-id="74c2e-108">[in]`CONTEXT`缓冲区。</span><span class="sxs-lookup"><span data-stu-id="74c2e-108">[in] The `CONTEXT` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74c2e-109">返回值</span><span class="sxs-lookup"><span data-stu-id="74c2e-109">Return Value</span></span>  
 <span data-ttu-id="74c2e-110">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="74c2e-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="74c2e-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="74c2e-111">HRESULT</span></span>|<span data-ttu-id="74c2e-112">描述</span><span class="sxs-lookup"><span data-stu-id="74c2e-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="74c2e-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="74c2e-113">S_OK</span></span>|<span data-ttu-id="74c2e-114">`ICorDebugStackWalk`成功设置对象的上下文。</span><span class="sxs-lookup"><span data-stu-id="74c2e-114">The `ICorDebugStackWalk` object's context was successfully set.</span></span>|  
|<span data-ttu-id="74c2e-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="74c2e-115">E_FAIL</span></span>|<span data-ttu-id="74c2e-116">`ICorDebugStackWalk`未设置对象的上下文。</span><span class="sxs-lookup"><span data-stu-id="74c2e-116">The `ICorDebugStackWalk` object's context was not set.</span></span>|  
|<span data-ttu-id="74c2e-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="74c2e-117">E_INVALIDARG</span></span>|<span data-ttu-id="74c2e-118">上下文为 null。</span><span class="sxs-lookup"><span data-stu-id="74c2e-118">The context is null.</span></span>|  
|<span data-ttu-id="74c2e-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="74c2e-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="74c2e-120">太小的上下文缓冲区。</span><span class="sxs-lookup"><span data-stu-id="74c2e-120">The context buffer is too small.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="74c2e-121">异常</span><span class="sxs-lookup"><span data-stu-id="74c2e-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74c2e-122">备注</span><span class="sxs-lookup"><span data-stu-id="74c2e-122">Remarks</span></span>  
 <span data-ttu-id="74c2e-123">此方法不会更改线程的当前上下文。</span><span class="sxs-lookup"><span data-stu-id="74c2e-123">This method does not alter the current context of the thread.</span></span>  
  
 <span data-ttu-id="74c2e-124">从堆栈查看器，将当前上下文设置为无效的上下文可能会导致不可预知的结果。</span><span class="sxs-lookup"><span data-stu-id="74c2e-124">Setting the current context to an invalid context may cause unpredictable results from the stack walker.</span></span>  
  
 <span data-ttu-id="74c2e-125">你可以通过立即调用检索此上下文的确切的按位复制[icordebugstackwalk:: Getcontext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="74c2e-125">You can retrieve an exact bitwise copy of this context by immediately calling the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74c2e-126">要求</span><span class="sxs-lookup"><span data-stu-id="74c2e-126">Requirements</span></span>  
 <span data-ttu-id="74c2e-127">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="74c2e-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74c2e-128">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="74c2e-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="74c2e-129">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74c2e-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74c2e-130">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74c2e-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74c2e-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74c2e-131">See Also</span></span>  
 [<span data-ttu-id="74c2e-132">调试接口</span><span class="sxs-lookup"><span data-stu-id="74c2e-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="74c2e-133">调试</span><span class="sxs-lookup"><span data-stu-id="74c2e-133">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)