---
title: "活动树检查"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 100d00e4-8c1d-4233-8fbb-dd443a01155d
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 91f706b527551bd66bfa18dc926f9453ea9b30fe
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="activity-tree-inspection"></a>活动树检查
活动树检查由工作流应用程序作者用于检查由应用程序承载的工作流。 使用 <xref:System.Activities.WorkflowInspectionServices>，可以在工作流中搜索特定子活动、单个活动并可以枚举其属性，还可以在特定时间缓存活动的运行时元数据。 此主题概述 <xref:System.Activities.WorkflowInspectionServices> 以及如何将其用于检查活动树。  
  
## <a name="using-workflowinspectionservices"></a>使用 WorkflowInspectionServices  
 <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> 方法用于枚举指定活动树中的所有活动。 <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> 返回一个可枚举对象，该对象涉及树中包括子活动在内的所有活动、委托处理程序、变量默认值和参数表达式。 在下面的示例中，使用 <xref:System.Activities.Statements.Sequence>、<xref:System.Activities.Statements.While>、<xref:System.Activities.Statements.ForEach%601>、<xref:System.Activities.Statements.WriteLine> 和表达式创建一个工作流定义。 在创建工作流定义后，将调用此定义，然后再调用 `InspectActivity` 方法。  
  
 [!code-csharp[CFX_WorkflowApplicationExample#45](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#45)]  
  
 为了枚举活动，在根活动上调用了 <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A>，并在返回的每个活动上重新递归调用。 在下面的示例中，将活动树中每个活动和表达式的 <xref:System.Activities.Activity.DisplayName%2A> 写入控制台。  
  
 [!code-csharp[CFX_WorkflowApplicationExample#46](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#46)]  
  
 此示例代码提供以下输出。  
  
 **列表项 1**  
**列表项 2**   
**List Item 3**   
**列表项 4**   
**列表项 5**   
**添加到集合的项。**   
**序列**   
 **文本 < 列表\<字符串 >>**  
 **While**  
 **AddToCollection\<字符串 >**  
 **VariableValue < ICollection\<字符串 >>**  
 **LambdaValue\<字符串 >**  
 **LocationReferenceValue < 列表\<字符串 >>**  
 **LambdaValue\<布尔 >**  
 **LocationReferenceValue < 列表\<字符串 >>**  
 **ForEach\<字符串 >**  
 **VariableValue < IEnumerable\<字符串 >>**  
 WriteLine  
 **DelegateArgumentValue\<字符串 >**  
 **序列**  
 WriteLine  
 **文本\<字符串 >**检索特定活动而不是枚举的所有活动，<xref:System.Activities.WorkflowInspectionServices.Resolve%2A>使用。 如果以前没有调用过 <xref:System.Activities.WorkflowInspectionServices.Resolve%2A>，则 <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> 和 `WorkflowInspectionServices.CacheMetadata` 均会执行元数据缓存。 如果已调用过 <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A>，则 <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> 基于现有元数据。 因此，如果自上次调用 <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A> 以来对树进行了更改，则 <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> 可能会产生意外的结果。 如果在调用之后到工作流进行更改<xref:System.Activities.WorkflowInspectionServices.GetActivities%2A>，可以通过调用重新缓存元数据<xref:System.Activities.Validation.ActivityValidationServices><xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>方法。 缓存元数据在下一节中讨论。  
  
### <a name="caching-metadata"></a>缓存元数据  
 缓存某个活动的元数据将生成并验证活动的参数、变量、子活动和活动委托的描述。 默认情况下，元数据在准备执行某个活动时由运行时缓存。 例如，如果工作流宿主作者希望在此之前缓存某个活动或活动树的元数据，以便提前使用所有开销，则可使用 <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A> 在需要时缓存元数据。
