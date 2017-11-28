---
title: "ICorDebugEval2::NewParameterizedArray 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval2.NewParameterizedArray
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval2::NewParameterizedArray
helpviewer_keywords:
- ICorDebugEval2::NewParameterizedArray method [.NET Framework debugging]
- NewParameterizedArray method [.NET Framework debugging]
ms.assetid: 45efb8ba-c4de-4109-945f-e734d376b43c
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cf7f8fb0d3418f863f2cd1531dc32b7e64c2b8a5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugeval2newparameterizedarray-method"></a><span data-ttu-id="6c066-102">ICorDebugEval2::NewParameterizedArray 方法</span><span class="sxs-lookup"><span data-stu-id="6c066-102">ICorDebugEval2::NewParameterizedArray Method</span></span>
<span data-ttu-id="6c066-103">分配的指定的元素类型和维度的一个新数组。</span><span class="sxs-lookup"><span data-stu-id="6c066-103">Allocates a new array of the specified element type and dimensions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c066-104">语法</span><span class="sxs-lookup"><span data-stu-id="6c066-104">Syntax</span></span>  
  
```  
HRESULT NewParameterizedArray(  
    [in] ICorDebugType          *pElementType,  
    [in] ULONG32                rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6c066-105">参数</span><span class="sxs-lookup"><span data-stu-id="6c066-105">Parameters</span></span>  
 `pElementType`  
 <span data-ttu-id="6c066-106">[in]指向一个 ICorDebugType 对象，表示存储在数组中元素的类型的指针。</span><span class="sxs-lookup"><span data-stu-id="6c066-106">[in] A pointer to an ICorDebugType object that represents the type of element stored in the array.</span></span>  
  
 `rank`  
 <span data-ttu-id="6c066-107">[in]数组的维度数。</span><span class="sxs-lookup"><span data-stu-id="6c066-107">[in] The number of dimensions of the array.</span></span> <span data-ttu-id="6c066-108">在.NET Framework 2.0 版中，此值必须为 1。</span><span class="sxs-lookup"><span data-stu-id="6c066-108">In the .NET Framework version 2.0, this value must be 1.</span></span>  
  
 `dims`  
 <span data-ttu-id="6c066-109">[in]以字节为单位，每个维度的数组大小。</span><span class="sxs-lookup"><span data-stu-id="6c066-109">[in] The size, in bytes, of each dimension of the array.</span></span>  
  
 `lowBounds`  
 <span data-ttu-id="6c066-110">[in] 可选。</span><span class="sxs-lookup"><span data-stu-id="6c066-110">[in] Optional.</span></span> <span data-ttu-id="6c066-111">数组的每个维度的下限。</span><span class="sxs-lookup"><span data-stu-id="6c066-111">The lower bound of each dimension of the array.</span></span> <span data-ttu-id="6c066-112">如果省略此值，每个维度假设下限为零。</span><span class="sxs-lookup"><span data-stu-id="6c066-112">If this value is omitted, a lower bound of zero is assumed for each dimension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c066-113">备注</span><span class="sxs-lookup"><span data-stu-id="6c066-113">Remarks</span></span>  
 <span data-ttu-id="6c066-114">数组的元素可能是泛型类型的实例。</span><span class="sxs-lookup"><span data-stu-id="6c066-114">The elements of the array may be instances of a generic type.</span></span> <span data-ttu-id="6c066-115">始终在线程当前运行的应用程序域中创建数组。</span><span class="sxs-lookup"><span data-stu-id="6c066-115">The array is always created in the application domain in which the thread is currently running.</span></span> <span data-ttu-id="6c066-116">在.NET Framework 2.0 中，值`rank`必须为 1。</span><span class="sxs-lookup"><span data-stu-id="6c066-116">In the .NET Framework 2.0, the value of `rank` must be 1.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c066-117">要求</span><span class="sxs-lookup"><span data-stu-id="6c066-117">Requirements</span></span>  
 <span data-ttu-id="6c066-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6c066-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c066-119">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6c066-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6c066-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c066-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c066-121">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c066-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>