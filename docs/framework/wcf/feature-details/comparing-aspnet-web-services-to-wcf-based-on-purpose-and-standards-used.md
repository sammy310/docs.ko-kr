---
description: '자세한 내용: 용도 및 사용 되는 표준에 따라 ASP.NET 웹 서비스를 WCF와 비교'
title: 용도와 사용되는 표준을 기반으로 ASP.NET 웹 서비스와 WCF 비교
ms.date: 03/30/2017
ms.assetid: d3890278-fa9b-4902-91ea-8da73b7143cc
ms.openlocfilehash: debc20f3ab3e8e9f83641eaa7d3b52dabe82055c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99743449"
---
# <a name="comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used"></a><span data-ttu-id="ed070-103">용도와 사용되는 표준을 기반으로 ASP.NET 웹 서비스와 WCF 비교</span><span class="sxs-lookup"><span data-stu-id="ed070-103">Comparing ASP.NET Web Services to WCF Based on Purpose and Standards Used</span></span>

<span data-ttu-id="ed070-104">ASP.NET Web 서비스는 HTTP에서 SOAP(Simple Object Access Protocol)를 사용하여 메시지를 보내고 받는 애플리케이션을 빌드하기 위해 개발되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ed070-104">ASP.NET Web services was developed for building applications that send and receive messages by using the Simple Object Access Protocol (SOAP) over HTTP.</span></span> <span data-ttu-id="ed070-105">메시지 구조는 XML 스키마를 사용하여 정의할 수 있으며 메시지를 .NET Framework 개체로 또는 그 반대로 쉽게 serialize하기 위한 도구가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed070-105">The structure of the messages can be defined using an XML Schema, and a tool is provided to facilitate serializing the messages to and from .NET Framework objects.</span></span> <span data-ttu-id="ed070-106">이 기술은 자동으로 메타데이터를 생성하여 WSDL(웹 서비스 기술 언어)로 웹 서비스를 설명할 수 있으며 WSDL에서 웹 서비스용 클라이언트를 생성하기 위한 두 번째 도구가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed070-106">The technology can automatically generate metadata to describe Web services in the Web Services Description Language (WSDL), and a second tool is provided for generating clients for Web services from the WSDL.</span></span>  
  
 <span data-ttu-id="ed070-107">WCF는 .NET Framework 응용 프로그램이 다른 소프트웨어 엔터티와 메시지를 교환할 수 있도록 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ed070-107">WCF is for enabling .NET Framework applications to exchange messages with other software entities.</span></span> <span data-ttu-id="ed070-108">기본적으로 SOAP가 사용되지만 메시지는 임의의 형식일 수 있으며 모든 전송 프로토콜을 사용하여 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed070-108">SOAP is used by default, but the messages can be in any format, and conveyed by using any transport protocol.</span></span> <span data-ttu-id="ed070-109">메시지 구조는 XML 스키마를 사용하여 정의할 수 있으며 메시지를 .NET Framework 개체로 또는 그 반대로 쉽게 serialize하기 위한 다양한 옵션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed070-109">The structure of the messages can be defined using an XML Schema, and there are various options for serializing the messages to and from .NET Framework objects.</span></span> <span data-ttu-id="ed070-110">WCF는 WSDL에서 기술을 사용 하 여 빌드한 응용 프로그램을 설명 하는 메타 데이터를 자동으로 생성할 수 있으며, WSDL에서 이러한 응용 프로그램용 클라이언트를 생성 하기 위한 도구도 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed070-110">WCF can automatically generate metadata to describe applications built using the technology in WSDL, and it also provides a tool for generating clients for those applications from the WSDL.</span></span>  
  
 <span data-ttu-id="ed070-111">ASP.NET 웹 서비스에서 지 원하는 표준은 [ASP.NET를 사용 하 여 만든 XML Web services의 이점](/previous-versions/dotnet/netframework-4.0/0859ebft(v=vs.100))에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed070-111">The standards supported by ASP.NET Web services are documented in [Benefits of XML Web Services Created Using ASP.NET](/previous-versions/dotnet/netframework-4.0/0859ebft(v=vs.100)).</span></span> <span data-ttu-id="ed070-112">WCF에서 지원 되는 더 광범위 한 표준 목록은 [System-Provided 상호 운용성 바인딩에서 지 원하는 웹 서비스 프로토콜](web-services-protocols-supported-by-system-provided-interoperability-bindings.md)에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed070-112">The more extensive list of standards supported by WCF are listed at [Web Services Protocols Supported by System-Provided Interoperability Bindings](web-services-protocols-supported-by-system-provided-interoperability-bindings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed070-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ed070-113">See also</span></span>

- [<span data-ttu-id="ed070-114">개발을 기반으로 ASP.NET 웹 서비스와 WCF 비교</span><span class="sxs-lookup"><span data-stu-id="ed070-114">Comparing ASP.NET Web Services to WCF Based on Development</span></span>](comparing-aspnet-web-services-to-wcf-based-on-development.md)
