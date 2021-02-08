---
description: '자세한 정보: COM 응용 프로그램과 통합 개요'
title: COM 애플리케이션과 통합 개요
ms.date: 03/30/2017
helpviewer_keywords:
- COM [WCF], integration overview
ms.assetid: 02c5697f-6e2e-47d6-b715-f3a28aebfbd5
ms.openlocfilehash: a179fd73c8065fff1e16d3f86202d717df155b81
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802816"
---
# <a name="integrating-with-com-applications-overview"></a><span data-ttu-id="4099f-103">COM 애플리케이션과 통합 개요</span><span class="sxs-lookup"><span data-stu-id="4099f-103">Integrating with COM Applications Overview</span></span>

<span data-ttu-id="4099f-104">WCF (Windows Communication Foundation)는 관리 코드 개발자에 게 연결 된 응용 프로그램을 만들기 위한 풍부한 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-104">Windows Communication Foundation (WCF) provides the managed code developer with a rich environment for creating connected applications.</span></span> <span data-ttu-id="4099f-105">그러나 관리 되지 않는 COM 기반 코드에 상당한 투자가 필요 하지만 마이그레이션하지 않으려는 경우 WCF 서비스 모니커를 사용 하 여 WCF 웹 서비스를 기존 코드에 직접 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-105">However, if you have a substantial investment in unmanaged COM-based code and do not want to migrate, you can still integrate WCF Web services directly into your existing code by using the WCF service moniker.</span></span> <span data-ttu-id="4099f-106">서비스 모니커는 Office VBA, Visual Basic 6.0 또는 Visual C++ 6.0과 같은 다양한 범위의 COM 기반 개발 환경에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-106">The service moniker can be used from a wide range of COM-based development environments, such as Office VBA, Visual Basic 6.0, or Visual C++ 6.0.</span></span>

> [!NOTE]
> <span data-ttu-id="4099f-107">서비스 모니커는 모든 통신에 대해 WCF 통신 채널을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-107">The service moniker uses a WCF communication channel for all communication.</span></span> <span data-ttu-id="4099f-108">이 채널의 보안 및 ID 메커니즘은 표준 COM 및 DCOM 프록시에 사용되는 메커니즘과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-108">The security and identity mechanisms for that channel differ from those used in standard COM and DCOM proxies.</span></span> <span data-ttu-id="4099f-109">또한 서비스 모니커가 WCF 통신 채널을 사용 하기 때문에 모든 호출에 대해 기본 제한 시간은 1 분입니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-109">In addition, because the service moniker uses a WCF communication channel the default timeout period is one minute for all calls.</span></span>

<span data-ttu-id="4099f-110">서비스 모니커는 함수와 함께 사용 되어 `GetObject` 관리 되지 않는 개발자에 게 WCF 웹 서비스를 호출 하기 위한 강력한 형식의 COM 관련 접근 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-110">The service moniker is used with the `GetObject` function to provide the unmanaged developer with a strongly-typed, COM-specific approach for calling WCF Web services.</span></span> <span data-ttu-id="4099f-111">이렇게 하려면 WCF 웹 서비스 계약의 로컬 및 COM에 표시 되는 정의와 사용할 바인딩을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-111">This requires a local, COM-visible definition of the WCF Web service contract and the binding that is to be used.</span></span> <span data-ttu-id="4099f-112">다른 WCF 클라이언트와 마찬가지로,이 채널 생성은 첫 번째 메서드 호출에서 COM 프로그래머에 게 투명 하 게 발생 하지만 서비스 모니커는 서비스에 형식화 된 채널을 생성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-112">Like other WCF clients, the service moniker must construct a typed channel to the service, though this channel construction occurs transparently to the COM programmer on the first method call.</span></span>

<span data-ttu-id="4099f-113">다른 WCF 클라이언트와 일반적으로 모니커를 사용 하는 경우 응용 프로그램은 서비스와 통신 하는 주소, 바인딩 및 계약을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-113">In common with other WCF clients, when using the moniker, applications specify the address, binding and contract to communicate with a service.</span></span> <span data-ttu-id="4099f-114">계약은 다음 방법 중 하나로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-114">The contract can be specified in one of the following ways:</span></span>

- <span data-ttu-id="4099f-115">형식화된 계약 – 계약이 클라이언트 컴퓨터에 COM 노출 형식으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-115">Typed contract – the contract is registered as a COM visible type on the client machine.</span></span>

- <span data-ttu-id="4099f-116">WSDL 계약 – 계약이 WSDL 문서 형식으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-116">WSDL contract – the contract is supplied in the form of a WSDL document.</span></span>

- <span data-ttu-id="4099f-117">MEX 계약 – 계약이 MEX(메타데이터 교환) 엔드포인트에서 런타임에 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-117">MEX contract – the contract is retrieved at runtime from a Metadata Exchange (MEX) endpoint.</span></span>

## <a name="parameters-supported-by-the-service-moniker"></a><span data-ttu-id="4099f-118">서비스 모니커에서 지원하는 매개 변수</span><span class="sxs-lookup"><span data-stu-id="4099f-118">Parameters Supported by the Service Moniker</span></span>

<span data-ttu-id="4099f-119">다음 표에서는 서비스 모니커에서 지원하는 매개 변수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-119">The following table shows the parameters that are supported by the service moniker.</span></span>

|<span data-ttu-id="4099f-120">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4099f-120">Parameter</span></span>|<span data-ttu-id="4099f-121">설명</span><span class="sxs-lookup"><span data-stu-id="4099f-121">Description</span></span>|
|---------------|-----------------|
|`address`|<span data-ttu-id="4099f-122">서비스의 URL 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-122">URL location of the service.</span></span>|
|`binding`|<span data-ttu-id="4099f-123">애플리케이션 구성의 바인딩 섹션 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-123">Binding section name from the application configuration.</span></span>|
|`bindingConfiguration`|<span data-ttu-id="4099f-124">명명된 바인딩 섹션 내의 명명된 바인딩 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-124">Named binding instance from within the named binding section.</span></span>|
|`contract`|<span data-ttu-id="4099f-125">MEX에서 서비스 계약이나 계약 이름을 나타내는 IID(인터페이스 식별자)입니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-125">Interface identifier (IID) that represents the service contract or the contract name (from MEX).</span></span>|
|`wsdl`|<span data-ttu-id="4099f-126">계약 정의에 대한 대체 형식을 제공하는 WSDL 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-126">WSDL document that provides an alternative form of contract definition.</span></span>|
|`spnIdentity`|<span data-ttu-id="4099f-127">서비스와의 통신에 사용되는 SPN(서비스 사용자 이름) ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-127">Server principal name (SPN) identity to be used to communicate with the service.</span></span>|
|`upnIdentity`|<span data-ttu-id="4099f-128">서비스와의 통신에 사용되는 UPN(User Principal Name) ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-128">User principal name (UPN) identity to be used to communicate with the service.</span></span>|
|`dnsIdentity`|<span data-ttu-id="4099f-129">서비스와의 통신에 사용되는 DNS ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-129">DNS identity to be used to communicate with the service.</span></span>|
|`mexAddress`|<span data-ttu-id="4099f-130">서비스의 MEX(메타데이터 교환) 엔드포인트에 대한 URL 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-130">URL location of the Metadata Exchange (MEX) endpoint of the service.</span></span>|
|`mexBinding`|<span data-ttu-id="4099f-131">MEX 엔드포인트와 연결하기 위한 애플리케이션 구성의 바인딩 섹션 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-131">Binding section name from the application configuration to connect with the MEX endpoint.</span></span>|
|`mexBindingConfiguration`|<span data-ttu-id="4099f-132">MEX 엔드포인트와 연결하기 위한 명명된 바인딩 섹션 내의 명명된 바인딩 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-132">Named binding instance from within the named binding section to connect with the MEX endpoint.</span></span>|
|`bindingNamespace`|<span data-ttu-id="4099f-133">검색된 MEX의 바인딩 섹션 이름에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-133">Namespace of the binding section name from the retrieved MEX.</span></span>|
|`contractNamespace`|<span data-ttu-id="4099f-134">검색된 MEX의 계약에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-134">Namespace of the contract from the retrieved MEX.</span></span>|
|`mexSpnIdentity`|<span data-ttu-id="4099f-135">MEX 엔드포인트와의 통신에 사용되는 SPN(서버 사용자 이름) ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-135">Server principal name (SPN) identity to be used to communicate with the MEX endpoint.</span></span>|
|`mexUpnIdentity`|<span data-ttu-id="4099f-136">MEX 엔드포인트와의 통신에 사용되는 UPN(User Principal Name) ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-136">User principal name (UPN) identity to be used to communicate with the MEX endpoint.</span></span>|
|`mexDnsIdentity`|<span data-ttu-id="4099f-137">MEX 엔드포인트와의 통신에 사용되는 DNS ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-137">DNS identity to be used to communicate with the MEX endpoint.</span></span>|
|`serializer`|<span data-ttu-id="4099f-138">"xml" 또는 "datacontract" serializer 사용을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-138">Specify the use of either the "xml" or "datacontract" serializer.</span></span>|

> [!NOTE]
> <span data-ttu-id="4099f-139">전체 COM 기반 클라이언트와 함께 사용 하는 경우에도 서비스 모니커는 WCF와 지원 .NET Framework 2.0를 클라이언트 컴퓨터에 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-139">Even when used with entirely COM-based clients, the service moniker requires WCF and the supporting .NET Framework 2.0 to be installed on the client computer.</span></span> <span data-ttu-id="4099f-140">또한 서비스 모니커를 사용하는 클라이언트 애플리케이션에서 올바른 버전의 .NET Framework 런타임을 로드해야 하는 점도 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-140">It is also critical that client applications that use the service moniker load the appropriate version of the .NET Framework runtime.</span></span> <span data-ttu-id="4099f-141">Office 애플리케이션에서 모니커를 사용할 때 올바른 프레임워크 버전이 로드되도록 하기 위해 구성 파일이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-141">When using the moniker within Office applications, a configuration file may be required to ensure that the correct framework version is loaded.</span></span> <span data-ttu-id="4099f-142">예를 들어 Excel을 사용하는 경우, 다음 텍스트가 Excel.exe 파일과 동일한 디렉터리의 Excel.exe.config라는 파일에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4099f-142">For example, with Excel, the following text should be placed in a file called Excel.exe.config in the same directory as the Excel.exe file:</span></span>
>
> `<?xml version="1.0" encoding="utf-8"?>`
>
> <span data-ttu-id="4099f-143">`<configuration xmlns=` `http://schemas.microsoft.com/.NetConfiguration/v2.0` `>`</span><span class="sxs-lookup"><span data-stu-id="4099f-143">`<configuration xmlns=` `http://schemas.microsoft.com/.NetConfiguration/v2.0` `>`</span></span>
>
> `<startup>`
>
> `<requiredRuntime version="v2.0.50727" />`
>
> `</startup>`
>
> `</configuration>`

## <a name="see-also"></a><span data-ttu-id="4099f-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4099f-144">See also</span></span>

- [<span data-ttu-id="4099f-145">방법: 서비스 모니커 등록 및 구성</span><span class="sxs-lookup"><span data-stu-id="4099f-145">How to: Register and Configure a Service Moniker</span></span>](how-to-register-and-configure-a-service-moniker.md)
