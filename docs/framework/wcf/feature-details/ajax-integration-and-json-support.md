---
title: AJAX 통합 및 JSON 지원
ms.date: 03/30/2017
helpviewer_keywords:
- AJAX integration and JSON support [WCF]
ms.assetid: 3851a8fc-d861-4ac1-873c-96af0343d3a7
ms.openlocfilehash: 3054c3c6faa8dfe621c706d8df031c23d497da0c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84576514"
---
# <a name="ajax-integration-and-json-support"></a><span data-ttu-id="49417-102">AJAX 통합 및 JSON 지원</span><span class="sxs-lookup"><span data-stu-id="49417-102">AJAX Integration and JSON Support</span></span>
<span data-ttu-id="49417-103">Wcf (ASP.NET) Windows Communication Foundation에서 AJAX (비동기 JavaScript and XML) 및 JavaScript Object Notation (JSON) 데이터 형식을 지원 하므로 WCF 서비스에서 AJAX 클라이언트에 작업을 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49417-103">The Windows Communication Foundation (WCF) support for ASP.NET Asynchronous JavaScript and XML (AJAX) and the JavaScript Object Notation (JSON) data format allow WCF services to expose operations to AJAX clients.</span></span> <span data-ttu-id="49417-104">AJAX 클라이언트는 JavaScript 코드를 실행 하 고 HTTP 요청을 사용 하 여 이러한 WCF 서비스에 액세스 하는 웹 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="49417-104">AJAX clients are Web pages running JavaScript code and accessing these WCF services using HTTP requests.</span></span> <span data-ttu-id="49417-105">이 단원의 항목에서는 이러한 지원에 대한 정보와 이러한 지원을 구현하는 방법에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="49417-105">The topics in this section provide information about this support and about how to implement it.</span></span>  
  
 <span data-ttu-id="49417-106">ASP.NET AJAX에 대 한 자세한 내용과 ASP.NET 2.0과의 통합에 대 한 자세한 내용은 [ASP.NET Ajax 개요](https://docs.microsoft.com/previous-versions/aspnet/bb398874(v=vs.100))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49417-106">For more information about ASP.NET AJAX and its integration with ASP.NET 2.0, see [ASP.NET AJAX Overview](https://docs.microsoft.com/previous-versions/aspnet/bb398874(v=vs.100)).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="49417-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="49417-107">In This Section</span></span>  
 [<span data-ttu-id="49417-108">ASP.NET AJAX용 WCF 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="49417-108">Creating WCF Services for ASP.NET AJAX</span></span>](creating-wcf-services-for-aspnet-ajax.md)  
 <span data-ttu-id="49417-109">구성 또는 AJAX 끝점을 자동으로 구성 하는 서비스 호스트 팩터리를 사용 하 여 사용자 지정 된 서비스 호스트 팩터리를 사용 하 여 적절 한 AJAX 끝점을 추가 하 여 WCF 서비스를 AJAX 클라이언트에 노출 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="49417-109">Describes how a WCF service can be exposed to AJAX clients by adding the appropriate AJAX endpoint either through configuration or by using a service host factory customized to generate a service host that configures the AJAX endpoint automatically.</span></span>  
  
 [<span data-ttu-id="49417-110">ASP.NET을 사용하지 않고 WCF AJAX 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="49417-110">Creating WCF AJAX Services without ASP.NET</span></span>](creating-wcf-ajax-services-without-aspnet.md)  
 <span data-ttu-id="49417-111">ASP.NET를 사용 하지 않고 WCF 서비스를 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="49417-111">Describes how to create a WCF service without using ASP.NET.</span></span>  
  
 [<span data-ttu-id="49417-112">JSON 및 기타 데이터 전송 형식에 대한 지원</span><span class="sxs-lookup"><span data-stu-id="49417-112">Support for JSON and Other Data Transfer Formats</span></span>](support-for-json-and-other-data-transfer-formats.md)  
 <span data-ttu-id="49417-113">ASP.NET AJAX 서비스와의 메시징에 XML 대신 일반적으로 사용되는 JSON 형식의 지원에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="49417-113">Describes the support of the JSON format typically used (instead of XML) for messaging with ASP.NET AJAX services.</span></span>  
  
 [<span data-ttu-id="49417-114">방법: AJAX 사용 ASP.NET 웹 서비스를 WCF로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="49417-114">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)  
 <span data-ttu-id="49417-115">AJAX 사용 ASP.NET 웹 서비스를 WCF 웹 서비스로 마이그레이션하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="49417-115">Describes how to migrate an AJAX-enabled ASP.NET Web service to a WCF Web service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49417-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="49417-116">See also</span></span>

- <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>
- [<span data-ttu-id="49417-117">WCF 웹 HTTP 프로그래밍 모델</span><span class="sxs-lookup"><span data-stu-id="49417-117">WCF Web HTTP Programming Model</span></span>](wcf-web-http-programming-model.md)
