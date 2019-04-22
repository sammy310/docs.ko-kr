---
title: AJAX 통합 및 JSON 지원
ms.date: 03/30/2017
helpviewer_keywords:
- AJAX integration and JSON support [WCF]
ms.assetid: 3851a8fc-d861-4ac1-873c-96af0343d3a7
ms.openlocfilehash: a3d9c29f3223624653f2d568bb351d90334a4318
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59137113"
---
# <a name="ajax-integration-and-json-support"></a><span data-ttu-id="bc146-102">AJAX 통합 및 JSON 지원</span><span class="sxs-lookup"><span data-stu-id="bc146-102">AJAX Integration and JSON Support</span></span>
<span data-ttu-id="bc146-103">ASP.NET Asynchronous JavaScript and XML (AJAX)에 대 한 Windows Communication Foundation (WCF) 지원 및 개체 JSON (JavaScript Notation) 데이터 형식에는 WCF 서비스에서 AJAX 클라이언트에 작업을 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc146-103">The Windows Communication Foundation (WCF) support for ASP.NET Asynchronous JavaScript and XML (AJAX) and the JavaScript Object Notation (JSON) data format allow WCF services to expose operations to AJAX clients.</span></span> <span data-ttu-id="bc146-104">AJAX 클라이언트는 웹 페이지 JavaScript 코드를 실행 하 고 HTTP 요청을 사용 하 여 이러한 WCF 서비스에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc146-104">AJAX clients are Web pages running JavaScript code and accessing these WCF services using HTTP requests.</span></span> <span data-ttu-id="bc146-105">이 단원의 항목에서는 이러한 지원에 대한 정보와 이러한 지원을 구현하는 방법에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bc146-105">The topics in this section provide information about this support and about how to implement it.</span></span>  
  
 <span data-ttu-id="bc146-106">ASP.NET AJAX에 대 한 자세한 내용과 ASP.NET 2.0와의 통합을 참조 하세요 [ASP.NET AJAX Overview](https://go.microsoft.com/fwlink/?LinkId=96725)합니다.</span><span class="sxs-lookup"><span data-stu-id="bc146-106">For more information about ASP.NET AJAX and its integration with ASP.NET 2.0, see [ASP.NET AJAX Overview](https://go.microsoft.com/fwlink/?LinkId=96725).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bc146-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="bc146-107">In This Section</span></span>  
 [<span data-ttu-id="bc146-108">ASP.NET AJAX용 WCF 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="bc146-108">Creating WCF Services for ASP.NET AJAX</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)  
 <span data-ttu-id="bc146-109">어떻게 하는 WCF 서비스를 노출할 수 있습니다 AJAX 클라이언트 구성을 통해 중 적합 한 AJAX 끝점을 추가 하거나 자동으로 AJAX 끝점을 구성 하는 서비스 호스트를 생성 하도록 사용자 지정 서비스 호스트 팩터리를 사용 하 여 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc146-109">Describes how an WCF service can be exposed to AJAX clients by adding the appropriate AJAX endpoint either through configuration or by using a service host factory customized to generate a service host that configures the AJAX endpoint automatically.</span></span>  
  
 [<span data-ttu-id="bc146-110">ASP.NET을 사용하지 않고 WCF AJAX 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="bc146-110">Creating WCF AJAX Services without ASP.NET</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md)  
 <span data-ttu-id="bc146-111">ASP.NET을 사용 하지 않고 WCF 서비스를 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc146-111">Describes how to create an WCF service without using ASP.NET.</span></span>  
  
 [<span data-ttu-id="bc146-112">JSON 및 기타 데이터 전송 형식에 대한 지원</span><span class="sxs-lookup"><span data-stu-id="bc146-112">Support for JSON and Other Data Transfer Formats</span></span>](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)  
 <span data-ttu-id="bc146-113">ASP.NET AJAX 서비스와의 메시징에 XML 대신 일반적으로 사용되는 JSON 형식의 지원에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bc146-113">Describes the support of the JSON format typically used (instead of XML) for messaging with ASP.NET AJAX services.</span></span>  
  
 [<span data-ttu-id="bc146-114">방법: AJAX 사용 ASP.NET 웹 서비스를 WCF로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="bc146-114">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)  
 <span data-ttu-id="bc146-115">WCF 웹 서비스에 AJAX 사용 ASP.NET 웹 서비스를 마이그레이션하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc146-115">Describes how to migrate an AJAX-enabled ASP.NET Web service to a WCF Web service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc146-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="bc146-116">See also</span></span>

- <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>
- [<span data-ttu-id="bc146-117">WCF 웹 HTTP 프로그래밍 모델</span><span class="sxs-lookup"><span data-stu-id="bc146-117">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
