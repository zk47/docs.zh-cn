---
title: ServiceThrottlingBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 59f85a148d6707876a4df512d5cfbd07ca0e54b7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="servicethrottlingbehavior"></a>ServiceThrottlingBehavior
ServiceThrottlingBehavior  
  
## <a name="syntax"></a>语法  
  
```  
class ServiceThrottlingBehavior : Behavior  
{  
  sint32 MaxConcurrentCalls;  
  sint32 MaxConcurrentInstances;  
  sint32 MaxConcurrentSessions;  
};  
```  
  
## <a name="methods"></a>方法  
 ServiceThrottlingBehavior 类未定义任何方法。  
  
## <a name="properties"></a>属性  
 ServiceThrottlingBehavior 类有以下属性：  
  
### <a name="maxconcurrentcalls"></a>MaxConcurrentCalls  
 数据类型：sint32  
  
 访问类型：只读  
  
 ServiceHost 中所有调度程序对象正在积极处理的消息的最大数量。  
  
### <a name="maxconcurrentinstances"></a>MaxConcurrentInstances  
 数据类型：sint32  
  
 访问类型：只读  
  
 一次可执行的服务对象的最大数量。  
  
### <a name="maxconcurrentsessions"></a>MaxConcurrentSessions  
 数据类型：sint32  
  
 访问类型：只读  
  
 主机一次可接受的最大会话数。  
  
## <a name="requirements"></a>要求  
  
|MOF|已在 Servicemodel.mof 中声明。|  
|---------|-----------------------------------|  
|命名空间|已在 root\ServiceModel 中定义|  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
