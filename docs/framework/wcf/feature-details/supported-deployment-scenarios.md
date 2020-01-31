---
title: 지원 되는 배포 시나리오
ms.date: 03/30/2017
ms.assetid: 3399f208-3504-4c70-a22e-a7c02a8b94a6
ms.openlocfilehash: 5be9ab3d300da2095a45846d334512382b4067f6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743458"
---
# <a name="supported-deployment-scenarios"></a><span data-ttu-id="2fe3d-102">지원 되는 배포 시나리오</span><span class="sxs-lookup"><span data-stu-id="2fe3d-102">Supported deployment scenarios</span></span>

<span data-ttu-id="2fe3d-103">부분적으로 신뢰할 수 있는 응용 프로그램에서 사용할 수 있도록 지원 되는 WCF (Windows Communication Foundation) 기능의 하위 집합은 WCF 사용에 대 한 일부 시나리오의 요구 사항을 충족 하도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2fe3d-103">The subset of Windows Communication Foundation (WCF) features supported for use in partially trusted applications is designed to meet the requirements of some, but not all, scenarios for using WCF.</span></span> <span data-ttu-id="2fe3d-104">서버에서 WCF는 보안상의 이유로 ASP.NET 2.0 보통 신뢰 권한 집합에서 타사 응용 프로그램을 실행 하는 인터넷 범위의 공유 호스팅 공급자 요구 사항을 충족 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fe3d-104">On the server, WCF meets the requirements of Internet-scale shared hosting providers who run third-party applications in the ASP.NET 2.0 Medium Trust permission set for security reasons.</span></span> <span data-ttu-id="2fe3d-105">클라이언트에서 WCF 부분 신뢰 지원은 [ClickOnce 배포](/visualstudio/deployment/clickonce-security-and-deployment) 또는 WPF의 XAML 브라우저 응용 프로그램 기술과 같은 배포 기술의 요구 사항을 충족 하도록 설계 되어 신뢰할 수 없는 사이트에서 데스크톱 응용 프로그램을 원활 하 고 안전 하 게 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fe3d-105">On the client, WCF partial trust support is designed to meet the requirements of deployment technologies such as [ClickOnce Deployment](/visualstudio/deployment/clickonce-security-and-deployment) or WPF's XAML Browser Application technology, which allow seamless and secure deployment of desktop applications from untrusted sites.</span></span>

## <a name="minimum-permission-requirements"></a><span data-ttu-id="2fe3d-106">최소 권한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2fe3d-106">Minimum permission requirements</span></span>

<span data-ttu-id="2fe3d-107">WCF는 다음 표준 명명 된 권한 집합 중 하나에서 실행 되는 응용 프로그램의 기능 하위 집합을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fe3d-107">WCF supports a subset of features in applications running under either of the following standard named permission sets:</span></span>

- <span data-ttu-id="2fe3d-108">보통 신뢰 권한</span><span class="sxs-lookup"><span data-stu-id="2fe3d-108">Medium Trust permissions</span></span>

- <span data-ttu-id="2fe3d-109">인터넷 영역 권한</span><span class="sxs-lookup"><span data-stu-id="2fe3d-109">Internet Zone permissions</span></span>

<span data-ttu-id="2fe3d-110">좀 더 제한적인 권한을 가진 부분적으로 신뢰할 수 있는 응용 프로그램에서 WCF를 사용 하려는 경우 런타임에 보안 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fe3d-110">Attempting to use WCF in partially trusted applications with more restrictive permissions may result in security exceptions at runtime.</span></span>

<span data-ttu-id="2fe3d-111">이러한 권한 집합에서 지원되는 기능에 대한 자세한 내용은 [Partial Trust Feature Compatibility](partial-trust-feature-compatibility.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2fe3d-111">For more information about the features supported in these permission sets, see [Partial Trust Feature Compatibility](partial-trust-feature-compatibility.md).</span></span>

## <a name="partial-trust-on-the-server"></a><span data-ttu-id="2fe3d-112">서버의 부분 신뢰</span><span class="sxs-lookup"><span data-stu-id="2fe3d-112">Partial trust on the server</span></span>

<span data-ttu-id="2fe3d-113">ASP.NET 웹 응용 프로그램 호스팅 서비스의 많은 상업적 공급자는 서버에서 실행 중인 응용 프로그램이 ASP.NET 2.0 Medium Trust 권한 집합에서 실행 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fe3d-113">Many commercial providers of ASP.NET Web application hosting services mandate that applications running on their servers run in the ASP.NET 2.0 Medium Trust permission set.</span></span> <span data-ttu-id="2fe3d-114"><xref:System.ServiceModel.BasicHttpBinding>, <xref:System.ServiceModel.WebHttpBinding>또는 전송 수준 보안을 사용 하는 <xref:System.ServiceModel.WSHttpBinding>를 사용 하는 경우 WCF 서비스를 이러한 환경에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fe3d-114">WCF services can run in these environments provided they use the <xref:System.ServiceModel.BasicHttpBinding>, the <xref:System.ServiceModel.WebHttpBinding>, or the <xref:System.ServiceModel.WSHttpBinding> with transport-level security.</span></span>

<span data-ttu-id="2fe3d-115">보통 신뢰 호스팅 환경에서 실행 되는 WCF 서비스는 클라이언트 요청에 대 한 응답으로 다른 서버에 메시지를 전송 하 여 중간 계층 서비스 역할을 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fe3d-115">WCF services running in Medium Trust hosting environments can also act as middle-tier services by sending messages to other servers in response to client requests.</span></span> <span data-ttu-id="2fe3d-116">서버에서 중간 계층 시나리오는 호스팅 환경이 애플리케이션에 적합한 <xref:System.Net.WebPermission> 을 부여해서 원하는 서버로 아웃바운드 요청을 한 경우 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fe3d-116">Middle-tier scenarios on the server are supported if the hosting environment has granted the application the appropriate <xref:System.Net.WebPermission> to make outbound requests to the desired server.</span></span>

<span data-ttu-id="2fe3d-117">WCF는 지원 되는 SOAP 바인딩 중 하나를 사용 하는 SOAP 메시징 외에도 부분적으로 신뢰할 수 있는 응용 프로그램에서 웹 스타일 서비스를 빌드하기 위한 <xref:System.ServiceModel.WebHttpBinding> 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fe3d-117">In addition to SOAP messaging using one of the supported SOAP bindings, WCF supports the <xref:System.ServiceModel.WebHttpBinding> for building Web-style services in partially trusted applications.</span></span> <span data-ttu-id="2fe3d-118">Wcf의 wcf [웹 HTTP 프로그래밍 모델](wcf-web-http-programming-model.md), [Wcf 배포](wcf-syndication.md)및 [AJAX 통합 및 JSON 지원](ajax-integration-and-json-support.md) 기능은 모두 부분 신뢰에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fe3d-118">The [WCF Web HTTP Programming Model](wcf-web-http-programming-model.md), [WCF Syndication](wcf-syndication.md), and [AJAX Integration and JSON Support](ajax-integration-and-json-support.md) features of WCF are all supported in partial trust.</span></span>

<span data-ttu-id="2fe3d-119">워크플로 서비스는 완전 신뢰 권한이 필요하며, 부분 신뢰 애플리케이션에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2fe3d-119">Workflow Services require Full Trust permissions and cannot be used in partially trusted applications.</span></span>

<span data-ttu-id="2fe3d-120">자세한 내용은 [How to: Use Medium Trust in ASP.NET 2.0](https://docs.microsoft.com/previous-versions/msp-n-p/ff648344(v=pandp.10))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2fe3d-120">For more information, see [How to: Use Medium Trust in ASP.NET 2.0](https://docs.microsoft.com/previous-versions/msp-n-p/ff648344(v=pandp.10)).</span></span>

## <a name="partial-trust-on-the-client"></a><span data-ttu-id="2fe3d-121">클라이언트의 부분 신뢰</span><span class="sxs-lookup"><span data-stu-id="2fe3d-121">Partial trust on the client</span></span>

<span data-ttu-id="2fe3d-122">신뢰할 수 없는 인터넷 사이트에서 코드를 다운로드하고 실행할 때 특정 보안 조치를 취해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fe3d-122">Certain security precautions must be taken when downloading and running code from untrusted Internet sites.</span></span> <span data-ttu-id="2fe3d-123">[ClickOnce 배포](/visualstudio/deployment/clickonce-security-and-deployment) 와 WPF의 XBAP (XAML 브라우저 응용 프로그램) 기술은 모두 부분 신뢰를 사용 하 여 제한 된 권한 (인터넷 영역)을 신뢰할 수 없는 코드에 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fe3d-123">Both [ClickOnce Deployment](/visualstudio/deployment/clickonce-security-and-deployment) and WPF's XAML Browser Application (XBAP) technology make use of partial trust to grant limited permissions (Internet Zone) to untrusted code.</span></span>

<span data-ttu-id="2fe3d-124">WCF는 [ClickOnce 배포](/visualstudio/deployment/clickonce-security-and-deployment) 또는 XBAP에서 배포한 부분 신뢰 응용 프로그램 내에서 원격 서버와 통신 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fe3d-124">WCF can be used to communicate with remote servers from within partially trusted applications deployed by either [ClickOnce Deployment](/visualstudio/deployment/clickonce-security-and-deployment) or XBAP.</span></span> <span data-ttu-id="2fe3d-125">인터넷 영역 권한 집합에는 원래 호스트에 대 한 <xref:System.Net.WebPermission> 포함 되어 있으며, 이러한 응용 프로그램은 [부분 신뢰 기능 호환성](partial-trust-feature-compatibility.md)에 설명 된 지원 되는 WCF 바인딩 중 하나를 사용 하 여 원본 서버와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fe3d-125">The Internet Zone permission set includes <xref:System.Net.WebPermission> for the originating host, which allows these applications to communicate with their origin server using any of the supported WCF bindings described in [Partial Trust Feature Compatibility](partial-trust-feature-compatibility.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2fe3d-126">참조</span><span class="sxs-lookup"><span data-stu-id="2fe3d-126">See also</span></span>

- [<span data-ttu-id="2fe3d-127">코드 액세스 보안</span><span class="sxs-lookup"><span data-stu-id="2fe3d-127">Code Access Security</span></span>](../../misc/code-access-security.md)
- [<span data-ttu-id="2fe3d-128">Windows Presentation Foundation 브라우저에서 호스팅되는 응용 프로그램 개요</span><span class="sxs-lookup"><span data-stu-id="2fe3d-128">Windows Presentation Foundation Browser-Hosted Applications Overview</span></span>](../../wpf/app-development/wpf-xaml-browser-applications-overview.md)
- [<span data-ttu-id="2fe3d-129">부분 신뢰</span><span class="sxs-lookup"><span data-stu-id="2fe3d-129">Partial Trust</span></span>](partial-trust.md)
- <span data-ttu-id="2fe3d-130">[ASP.NET 신뢰 수준 및 정책 파일](https://docs.microsoft.com/previous-versions/wyts434y(v=vs.140))</span><span class="sxs-lookup"><span data-stu-id="2fe3d-130">[ASP.NET Trust Levels and Policy Files](https://docs.microsoft.com/previous-versions/wyts434y(v=vs.140))</span></span>
