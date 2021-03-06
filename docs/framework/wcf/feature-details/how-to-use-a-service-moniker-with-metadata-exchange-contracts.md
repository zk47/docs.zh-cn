---
title: "如何：将服务标记与元数据交换协定一起使用"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c41a07e5-cb9d-45d6-9ea4-34511e227faf
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 31720b0639f9be68a2124b4ff844a2837787ef81
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-use-a-service-moniker-with-metadata-exchange-contracts"></a>如何：将服务标记与元数据交换协定一起使用
在开发了一些新的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务后，您也许会决定希望能够从脚本或 Visual Basic 6.0 应用程序中调用这些服务。 为此，您可以先生成一个 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端程序集，然后使用 COM 注册该程序集，再将该程序集安装在 GAC 中，然后从您的 Visual Basic 代码中引用 COM 类型。 在您分发应用程序时，您必须同时分发 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端程序集。 然后，用户必须使用 COM 注册 WCF 客户端程序集，并且将该程序集放置在 GAC 中。 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] COM 互操作使您在不依赖 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端程序集的情况下，也能够完成相同的服务调用。 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 标记使您能够从任何与 COM 兼容的语言（Visual Basic、VBScript、Visual Basic for Applications (VBA) 等）中调用任何 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务，方法是通过指定服务标记用于提取有关该服务的类型信息的元数据交换 (Mex) 终结点 URI。 本主题描述如何使用指定 Mex 终结点的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 标记调用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 入门示例。  
  
> [!NOTE]
>  实际上，从不实例化由 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端程序集定义的类型。 该程序集只用于元数据。  
  
### <a name="using-the-service-moniker-with-a-mex-address"></a>使用带有 Mex 地址的服务标记  
  
1.  生成入门示例并使用 Internet Explorer 浏览至其 URL (http://localhost/ServiceModelSamples/Service.svc) 以确保服务正在运行。  
  
2.  生成 Visual Basic 脚本或包含以下代码的 Visual Basic 应用程序：  
  
    ```  
    monString = "service:mexaddress=http://localhost/ServiceModelSamples/Service.svc/MEX"  
    monString = monString + ", address=http://localhost/ServiceModelSamples/Service.svc"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set calc = GetObject(monString)  
    MsgBox calc.Add(3, 4)  
    ```  
  
3.  运行 Visual Basic 应用程序或脚本。  
  
    > [!NOTE]
    >  您所调用的服务必须公开标记的 Mex 终结点，以便能够从服务中读取元数据。 有关详细信息，请参阅[如何： 使用配置文件服务的发布元数据](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)。  
  
    > [!NOTE]
    >  如果标记格式不正确，或如果服务不可用，则对 `GetObject` 的调用将返回一个错误，指示“语法无效”。  如果您收到此错误，请确保所使用的标记正确无误且服务可用。  
  
## <a name="see-also"></a>另请参阅  
 [如何： 使用 Windows Communication Foundation 服务标记，而无需注册](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 [如何： 使用服务标记用于 WSDL 协定](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)
