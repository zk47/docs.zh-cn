---
title: contextSwitchDeadlock MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deadlocks [.NET Framework]
- pumping messages
- STA message pumping
- single-threaded COM components
- MDAs (managed debugging assistants), context switching deadlocks
- managed debugging assistants (MDAs), context switching deadlocks
- ContextSwitchDeadlock MDA
- message pumping
- context switching deadlocks
ms.assetid: 26dfaa15-9ddb-4b0a-b6da-999bba664fa6
caps.latest.revision: "22"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e67c5c47dbe95d7c2b804f0ae87200db489d0306
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="contextswitchdeadlock-mda"></a>contextSwitchDeadlock MDA
如果在尝试进行 COM 上下文转换期间检测到一个死锁，将激活 `contextSwitchDeadlock` 托管调试助手 (MDA)。  
  
## <a name="symptoms"></a>症状  
 最常见的症状是：从托管代码对非托管 COM 组件的调用未返回任何结果。  另一个症状是内存使用量不断增加。  
  
## <a name="cause"></a>原因  
 原因很可能是单线程单元 (STA) 线程不发送消息。 STA 线程要么等待而不发送消息，要么执行一个长时间的操作而不允许发送消息队列。  
  
 内存使用不断增加的原因是：终结器线程尝试对非托管 COM 组件调用 `Release` 而该组件未返回任何结果。  这会阻止终结器回收其他对象。  
  
 默认情况下，Visual Basic 控制台应用程序的主线程的线程模型为 STA。 如果 STA 线程通过公共语言运行时或第三方控件直接或间接使用 COM 互操作性，MDA 将被激活。  若要避免在 Visual Basic 控制台应用程序中激活此 MDA，请将 <xref:System.MTAThreadAttribute> 特性应用于 Main 方法或修改应用程序让其发送消息。  
  
 当满足以下所有条件时，可能会错误地激活此 MDA：  
  
-   应用程序通过库从 STA 线程直接或间接地创建 COM 组件。  
  
-   应用程序在调试器中已停止，而用户继续运行该应用程序或执行单步操作。  
  
-   未启用非托管调试。  
  
 若要确定是否错误地激活了 MDA，请禁用所有断点，重新启动应用程序，然后让它可以不间断地运行。 如果没有激活 MDA，则最初的激活很可能是错误的。 在此情况下，请禁用 MDA，以避免干扰调试会话。  
  
> [!NOTE]
>  此 MDA 处于 [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] 和更高版本的默认集合中。 当在 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 中启用宿主进程时，将无法禁用处于默认集合中的 MDA。 默认情况下，托管进程处于启用状态，因此必须将其显式禁用。 有关如何禁用 MDA 的信息，请参阅[使用托管调试助手诊断错误](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)中的“启用和禁用 MDA”。  
  
## <a name="resolution"></a>解决方法  
 遵循有关 STA 消息发送的 COM 规则。  
  
## <a name="effect-on-the-runtime"></a>对运行时的影响  
 此 MDA 对 CLR 无任何影响。 它只报告有关 COM 上下文的数据。  
  
## <a name="output"></a>输出  
 一条描述当前上下文和目标上下文的消息。  
  
## <a name="configuration"></a>配置  
  
```xml  
<mdaConfig>  
  <assistants>  
    <contextSwitchDeadlock />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [使用托管调试助手诊断错误](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [互操作封送处理](../../../docs/framework/interop/interop-marshaling.md)
