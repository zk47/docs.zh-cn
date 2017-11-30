---
title: "ICLRMetaHostPolicy::GetRequestedRuntime 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHostPolicy.GetRequestedRuntime
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHostPolicy::GetRequestedRuntime
helpviewer_keywords:
- GetRequestedRuntime method [.NET Framework hosting]
- ICLRMetaHostPolicy::GetRequestedRuntime method [.NET Framework hosting]
ms.assetid: 59ec1832-9cc1-4b5c-983d-03407e51de56
topic_type: apiref
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 57e5efc604568aea0a6edef5cc57f83fb99eb561
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrmetahostpolicygetrequestedruntime-method"></a><span data-ttu-id="6826e-102">ICLRMetaHostPolicy::GetRequestedRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="6826e-102">ICLRMetaHostPolicy::GetRequestedRuntime Method</span></span>
<span data-ttu-id="6826e-103">提供基于宿主策略、托管程序集、版本字符串和配置流的公共语言运行时 (CLR) 的首选版本的接口。</span><span class="sxs-lookup"><span data-stu-id="6826e-103">Provides an interface to a preferred version of the common language runtime (CLR) based on a hosting policy, managed assembly, version string, and configuration stream.</span></span> <span data-ttu-id="6826e-104">此方法不实际上不会加载或激活 CLR，而只是返回[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)表示策略结果的接口。</span><span class="sxs-lookup"><span data-stu-id="6826e-104">This method does not actually load or activate the CLR, but simply returns the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that represents the policy result.</span></span> <span data-ttu-id="6826e-105">此方法取代[GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)， [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)， [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)， [CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)，和[GetCORRequiredVersion](../../../../docs/framework/unmanaged-api/hosting/getcorrequiredversion-function.md)方法。</span><span class="sxs-lookup"><span data-stu-id="6826e-105">This method supersedes the [GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md), [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md), [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md), [CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md), and [GetCORRequiredVersion](../../../../docs/framework/unmanaged-api/hosting/getcorrequiredversion-function.md) methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6826e-106">语法</span><span class="sxs-lookup"><span data-stu-id="6826e-106">Syntax</span></span>  
  
```  
HRESULT GetRequestedRuntime(  
    [in]  METAHOST_POLICY_FLAGS dwPolicyFlags,  
    [in]  LPCWSTR pwzBinary,  
    [in]  IStream *pCfgStream,  
    [in, out, size_is(*pcchVersion)] LPWSTR pwzVersion,  
    [in, out]  DWORD *pcchVersion,  
    [out, size_is(*pcchImageVersion)] LPWSTR pwzImageVersion,  
    [in, out]  DWORD *pcchImageVersion,  
    [out] DWORD *pdwConfigFlags,  
    [in]  REFIID  riid  
    [out, iid_is(riid), retval] LPVOID *ppRuntime);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6826e-107">参数</span><span class="sxs-lookup"><span data-stu-id="6826e-107">Parameters</span></span>  
  
|<span data-ttu-id="6826e-108">名称</span><span class="sxs-lookup"><span data-stu-id="6826e-108">Name</span></span>|<span data-ttu-id="6826e-109">描述</span><span class="sxs-lookup"><span data-stu-id="6826e-109">Description</span></span>|  
|----------|-----------------|  
|`dwPolicyFlags`|<span data-ttu-id="6826e-110">[in] 必需。</span><span class="sxs-lookup"><span data-stu-id="6826e-110">[in] Required.</span></span> <span data-ttu-id="6826e-111">指定的成员[METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md)枚举，表示某个绑定策略，以及任何数量的修饰符。</span><span class="sxs-lookup"><span data-stu-id="6826e-111">Specifies a member of the [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) enumeration, representing a binding policy, and any number of modifiers.</span></span> <span data-ttu-id="6826e-112">当前可用的策略只有[METAHOST_POLICY_HIGHCOMPAT](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md)。</span><span class="sxs-lookup"><span data-stu-id="6826e-112">The only policy that is currently available is [METAHOST_POLICY_HIGHCOMPAT](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md).</span></span><br /><br /> <span data-ttu-id="6826e-113">修饰符包括[METAHOST_POLICY_EMULATE_EXE_LAUNCH](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md)， [METAHOST_POLICY_APPLY_UPGRADE_POLICY](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md)， [METAHOST_POLICY_SHOW_ERROR_DIALOG](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md)， [METAHOST_POLICY_USE_PROCESS_IMAGE_PATH](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md)，和[METAHOST_POLICY_ENSURE_SKU_SUPPORTED](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md)。</span><span class="sxs-lookup"><span data-stu-id="6826e-113">Modifiers include [METAHOST_POLICY_EMULATE_EXE_LAUNCH](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md), [METAHOST_POLICY_APPLY_UPGRADE_POLICY](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md), [METAHOST_POLICY_SHOW_ERROR_DIALOG](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md), [METAHOST_POLICY_USE_PROCESS_IMAGE_PATH](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md), and [METAHOST_POLICY_ENSURE_SKU_SUPPORTED](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md).</span></span>|  
|`pwzBinary`|<span data-ttu-id="6826e-114">[in] 可选。</span><span class="sxs-lookup"><span data-stu-id="6826e-114">[in] Optional.</span></span> <span data-ttu-id="6826e-115">指定程序集文件路径。</span><span class="sxs-lookup"><span data-stu-id="6826e-115">Specifies the assembly file path.</span></span>|  
|`pCfgStream`|<span data-ttu-id="6826e-116">[in] 可选。</span><span class="sxs-lookup"><span data-stu-id="6826e-116">[in] Optional.</span></span> <span data-ttu-id="6826e-117">指定配置文件作为 <xref:System.Runtime.InteropServices.ComTypes.IStream?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="6826e-117">Specifies the configuration file as a <xref:System.Runtime.InteropServices.ComTypes.IStream?displayProperty=nameWithType>.</span></span>|  
|`pwzVersion`|<span data-ttu-id="6826e-118">[in, out] 可选。</span><span class="sxs-lookup"><span data-stu-id="6826e-118">[in, out] Optional.</span></span> <span data-ttu-id="6826e-119">指定或返回要加载的首选 CLR 版本。</span><span class="sxs-lookup"><span data-stu-id="6826e-119">Specifies or returns the preferred CLR version to be loaded.</span></span>|  
|`pcchVersion`|<span data-ttu-id="6826e-120">[in, out] 必需。</span><span class="sxs-lookup"><span data-stu-id="6826e-120">[in, out] Required.</span></span> <span data-ttu-id="6826e-121">输入时指定 `pwzVersion` 的预期的大小，以避免缓冲区溢出。</span><span class="sxs-lookup"><span data-stu-id="6826e-121">Specifies the expected size of `pwzVersion` as input, to avoid buffer overruns.</span></span> <span data-ttu-id="6826e-122">如果 `pwzVersion` 为 null，则当 `GetRequestedRuntime` 返回时，`pcchVersion` 包含 `pwzVersion` 的预期的大小以允许预分配；否则为 `pcchVersion` 包含写入 `pwzVersion` 的字符数量。</span><span class="sxs-lookup"><span data-stu-id="6826e-122">If `pwzVersion` is null, `pcchVersion` contains the expected size of `pwzVersion` when `GetRequestedRuntime` returns, to allow pre-allocation; otherwise, `pcchVersion` contains the number of characters written to `pwzVersion`.</span></span>|  
|`pwzImageVersion`|<span data-ttu-id="6826e-123">[out] 可选。</span><span class="sxs-lookup"><span data-stu-id="6826e-123">[out] Optional.</span></span> <span data-ttu-id="6826e-124">当`GetRequestedRuntime`返回时，包含 CLR 版本对应于[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)返回的接口。</span><span class="sxs-lookup"><span data-stu-id="6826e-124">When `GetRequestedRuntime` returns, contains the CLR version corresponding to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that is returned.</span></span>|  
|`pcchImageVersion`|<span data-ttu-id="6826e-125">[in, out] 可选。</span><span class="sxs-lookup"><span data-stu-id="6826e-125">[in, out] Optional.</span></span> <span data-ttu-id="6826e-126">输入时指定 `pwzImageVersion` 的预期的大小以避免缓冲区溢出。</span><span class="sxs-lookup"><span data-stu-id="6826e-126">Specifies the size of `pwzImageVersion` as input to avoid buffer overruns.</span></span> <span data-ttu-id="6826e-127">如果 `pwzImageVersion` 为 null，则当 `GetRequestedRuntime` 返回时，`pcchImageVersion` 包含 `pwzImageVersion` 的所需大小，以允许预分配。</span><span class="sxs-lookup"><span data-stu-id="6826e-127">If `pwzImageVersion` is null, `pcchImageVersion` contains the required size of `pwzImageVersion` when `GetRequestedRuntime` returns, to allow pre-allocation.</span></span>|  
|`pdwConfigFlags`|<span data-ttu-id="6826e-128">[out] 可选。</span><span class="sxs-lookup"><span data-stu-id="6826e-128">[out] Optional.</span></span> <span data-ttu-id="6826e-129">如果`GetRequestedRuntime`绑定过程中，使用配置文件，当它返回，`pdwConfigFlags`包含[METAHOST_CONFIG_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-config-flags-enumeration.md)值，该值指示是否[\<启动 >](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)元素具有`useLegacyV2RuntimeActivationPolicy`属性集以及属性的值。</span><span class="sxs-lookup"><span data-stu-id="6826e-129">If `GetRequestedRuntime` uses a configuration file during the binding process, when it returns, `pdwConfigFlags` contains a [METAHOST_CONFIG_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-config-flags-enumeration.md) value that indicates whether the [\<startup>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) element has the `useLegacyV2RuntimeActivationPolicy` attribute set, and the value of the attribute.</span></span> <span data-ttu-id="6826e-130">应用[METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK](../../../../docs/framework/unmanaged-api/hosting/metahost-config-flags-enumeration.md)屏蔽到`pdwConfigFlags`若要获取的值与相关`useLegacyV2RuntimeActivationPolicy`。</span><span class="sxs-lookup"><span data-stu-id="6826e-130">Apply the [METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK](../../../../docs/framework/unmanaged-api/hosting/metahost-config-flags-enumeration.md) mask to `pdwConfigFlags` to get the values relevant to `useLegacyV2RuntimeActivationPolicy`.</span></span>|  
|`riid`|<span data-ttu-id="6826e-131">[in]指定请求的接口标识符 IID_ICLRRuntimeInfo [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="6826e-131">[in] Specifies the interface identifier IID_ICLRRuntimeInfo for the requested [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>|  
|`ppRuntime`|<span data-ttu-id="6826e-132">[out]当`GetRequestedRuntime`返回时，包含指向对应[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="6826e-132">[out] When `GetRequestedRuntime` returns, contains a pointer to the corresponding [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6826e-133">备注</span><span class="sxs-lookup"><span data-stu-id="6826e-133">Remarks</span></span>  
 <span data-ttu-id="6826e-134">如果此方法成功，当且仅当一个或多个以下元素存在于 `<configuration><runtime>` 部分内的配置流中时，该方法具有将其他标志与返回运行时接口的当前默认启动标志结合的副作用：</span><span class="sxs-lookup"><span data-stu-id="6826e-134">When this method succeeds, it has the side effect of combining additional flags with the current default startup flags of the returned runtime interface, if and only if one or more of the following elements exist in the configuration stream within the `<configuration><runtime>` section:</span></span>  
  
-   <span data-ttu-id="6826e-135">`<gcServer enabled="true"/>` 导致 `STARTUP_SERVER_GC` 将被设置。</span><span class="sxs-lookup"><span data-stu-id="6826e-135">`<gcServer enabled="true"/>` causes `STARTUP_SERVER_GC` to be set.</span></span>  
  
-   <span data-ttu-id="6826e-136">`<etwEnable enabled="true"/>` 导致 `STARTUP_ETW` 将被设置。</span><span class="sxs-lookup"><span data-stu-id="6826e-136">`<etwEnable enabled="true"/>` causes `STARTUP_ETW` to be set.</span></span>  
  
-   <span data-ttu-id="6826e-137">`<appDomainResourceMonitoring enabled="true"/>` 导致 `STARTUP_ARM` 将被设置。</span><span class="sxs-lookup"><span data-stu-id="6826e-137">`<appDomainResourceMonitoring enabled="true"/>` causes `STARTUP_ARM` to be set.</span></span>  
  
 <span data-ttu-id="6826e-138">产生的默认 `STARTUP_FLAGS` 值是从前述列表设置的值与默认启动标志的按位“或”组合。</span><span class="sxs-lookup"><span data-stu-id="6826e-138">The resulting default `STARTUP_FLAGS` value is the bitwise OR combination of the values that are set from the preceding list with the default startup flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6826e-139">返回值</span><span class="sxs-lookup"><span data-stu-id="6826e-139">Return Value</span></span>  
 <span data-ttu-id="6826e-140">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="6826e-140">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="6826e-141">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6826e-141">HRESULT</span></span>|<span data-ttu-id="6826e-142">描述</span><span class="sxs-lookup"><span data-stu-id="6826e-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6826e-143">S_OK</span><span class="sxs-lookup"><span data-stu-id="6826e-143">S_OK</span></span>|<span data-ttu-id="6826e-144">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="6826e-144">The method completed successfully.</span></span>|  
|<span data-ttu-id="6826e-145">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="6826e-145">E_POINTER</span></span>|<span data-ttu-id="6826e-146">`pwzVersion` 不为 null 且 `pcchVersion` 为 null。</span><span class="sxs-lookup"><span data-stu-id="6826e-146">`pwzVersion` is not null and `pcchVersion` is null.</span></span><br /><br /> <span data-ttu-id="6826e-147">- 或 -</span><span class="sxs-lookup"><span data-stu-id="6826e-147">-or-</span></span><br /><br /> <span data-ttu-id="6826e-148">`pwzImageVersion` 不为 null 且 `pcchImageVersion` 为 null。</span><span class="sxs-lookup"><span data-stu-id="6826e-148">`pwzImageVersion` is not null and `pcchImageVersion` is null.</span></span>|  
|<span data-ttu-id="6826e-149">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="6826e-149">E_INVALIDARG</span></span>|<span data-ttu-id="6826e-150">`dwPolicyFlags` 未指定 `METAHOST_POLICY_HIGHCOMPAT`。</span><span class="sxs-lookup"><span data-stu-id="6826e-150">`dwPolicyFlags` does not specify `METAHOST_POLICY_HIGHCOMPAT`.</span></span>|  
|<span data-ttu-id="6826e-151">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="6826e-151">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="6826e-152">分配给 `pwzVerison` 的内存不足。</span><span class="sxs-lookup"><span data-stu-id="6826e-152">The memory allocated to `pwzVerison` is inadequate.</span></span><br /><br /> <span data-ttu-id="6826e-153">- 或 -</span><span class="sxs-lookup"><span data-stu-id="6826e-153">-or-</span></span><br /><br /> <span data-ttu-id="6826e-154">分配给 `pwzImageVerison` 的内存不足。</span><span class="sxs-lookup"><span data-stu-id="6826e-154">The memory allocated to `pwzImageVerison` is inadequate.</span></span>|  
|<span data-ttu-id="6826e-155">CLR_E_SHIM_RUNTIMELOAD</span><span class="sxs-lookup"><span data-stu-id="6826e-155">CLR_E_SHIM_RUNTIMELOAD</span></span>|<span data-ttu-id="6826e-156">`dwPolicyFlags` 包括 METAHOST_POLICY_APPLY_UPGRADE_POLICY，并且 `pwzVersion` 和 `pcchVersion` 均为 null。</span><span class="sxs-lookup"><span data-stu-id="6826e-156">`dwPolicyFlags` includes METAHOST_POLICY_APPLY_UPGRADE_POLICY, and both `pwzVersion` and `pcchVersion` are null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6826e-157">要求</span><span class="sxs-lookup"><span data-stu-id="6826e-157">Requirements</span></span>  
 <span data-ttu-id="6826e-158">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6826e-158">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6826e-159">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="6826e-159">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6826e-160">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6826e-160">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6826e-161">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6826e-161">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6826e-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6826e-162">See Also</span></span>  
 [<span data-ttu-id="6826e-163">ICLRMetaHostPolicy 接口</span><span class="sxs-lookup"><span data-stu-id="6826e-163">ICLRMetaHostPolicy Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md)  
 [<span data-ttu-id="6826e-164">CLR 承载接口添加在.NET Framework 4 和 4.5</span><span class="sxs-lookup"><span data-stu-id="6826e-164">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 [<span data-ttu-id="6826e-165">承载接口</span><span class="sxs-lookup"><span data-stu-id="6826e-165">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="6826e-166">承载</span><span class="sxs-lookup"><span data-stu-id="6826e-166">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)