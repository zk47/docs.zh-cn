---
title: "AJAX 集成和 JSON 支持"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: AJAX integration and JSON support [WCF]
ms.assetid: 3851a8fc-d861-4ac1-873c-96af0343d3a7
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 98efc62a133b86ab71e34671bc6385a5a94897ea
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ajax-integration-and-json-support"></a>AJAX 集成和 JSON 支持
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 支持 ASP.NET 异步 JavaScript 和 XML (AJAX)，并且 JavaScript 对象表示法 (JSON) 数据格式允许 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务向 AJAX 客户端公开操作。 AJAX 客户端是运行 JavaScript 代码并使用 HTTP 请求访问这些 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务的网页。 本节中的主题提供有关此支持以及如何实现此支持的信息。  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]ASP.NET AJAX 和的集成与 ASP.NET 2.0，请参阅[ASP.NET AJAX 概述](http://go.microsoft.com/fwlink/?LinkId=96725)。  
  
## <a name="in-this-section"></a>本节内容  
 [为 ASP.NET AJAX 创建 WCF 服务](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)  
 描述如何通过使用配置或服务主机工厂（自定义为生成自动配置 AJAX 终结点的服务主机）添加相应的 AJAX 终结点以将 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务公开到 AJAX 客户端。  
  
 [创建不使用 ASP.NET 的 WCF AJAX 服务](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md)  
 描述如何在不使用 ASP.NET 的情况下创建 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务。  
  
 [对 JSON 和其他数据传输格式的支持](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)  
 描述对通常用于与 ASP.NET AJAX 服务进行通信的 JSON 格式（替代 XML）的支持。  
  
 [如何： 将启用了 AJAX 的 ASP.NET Web 服务迁移到 WCF](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)  
 描述如何将支持 AJAX 的 ASP.NET Web 服务迁移到 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web 服务。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>  
 [WCF Web HTTP 编程模型](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
