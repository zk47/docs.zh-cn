---
title: "服务性能计数器"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d2bc29ace454c6c41d3ad6ec11f98a9e6fb3e7d0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="service-performance-counters"></a>服务性能计数器
服务性能计数器将服务行为作为整体来进行衡量，可用于诊断服务整体性能。 如果使用性能监视器 (Perfmon.exe) 查看，可以在 `ServiceModelService 4.0.0.0` 性能对象下找到服务性能计数器。 使用以下模式命名计数器实例：  
  
```  
ServiceName@ServiceBaseAddress  
```  
  
> [!CAUTION]
>  性能计数器实例的名称长度存在限制。 当 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 计数器实例名称超出最大长度时，[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 会用一个哈希值替换实例名称的一部分。  
  
## <a name="see-also"></a>另请参阅  
 [性能计数器](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
