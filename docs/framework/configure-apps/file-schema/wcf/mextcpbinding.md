---
title: <mexTcpBinding>
ms.date: 03/30/2017
ms.assetid: 01baba8d-d784-4255-9ea2-7afff1482bf0
ms.openlocfilehash: 0d12f886eaee6283ee686209dfc129e397a8e1fe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204699"
---
# \<mexTcpBinding>

<span data-ttu-id="4e5b6-101">TCP를 통한 WS-MEX(WS-MetadataExchange) 메시지 교환에 사용되는 바인딩의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e5b6-101">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over TCP.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexTcpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="4e5b6-102">구문</span><span class="sxs-lookup"><span data-stu-id="4e5b6-102">Syntax</span></span>  
  
```xml  
<mexTcpBinding>
  <binding closeTimeout="TimeSpan"
           name="string"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
  </binding>
</mexTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4e5b6-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4e5b6-103">Attributes and Elements</span></span>  

 <span data-ttu-id="4e5b6-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4e5b6-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4e5b6-105">특성</span><span class="sxs-lookup"><span data-stu-id="4e5b6-105">Attributes</span></span>  
  
|<span data-ttu-id="4e5b6-106">attribute</span><span class="sxs-lookup"><span data-stu-id="4e5b6-106">Attribute</span></span>|<span data-ttu-id="4e5b6-107">설명</span><span class="sxs-lookup"><span data-stu-id="4e5b6-107">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="4e5b6-108">닫기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4e5b6-108">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="4e5b6-109">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e5b6-109">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="4e5b6-110">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="4e5b6-110">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="4e5b6-111">바인딩의 구성 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4e5b6-111">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="4e5b6-112">이 값은 바인딩의 ID로 사용되므로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e5b6-112">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="4e5b6-113">.NET Framework 4부터 바인딩과 동작은 이름을 가질 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4e5b6-113">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="4e5b6-114">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 [WCF 서비스에 대 한](../../../wcf/samples/simplified-configuration-for-wcf-services.md) [간소화 된 구성](../../../wcf/simplified-configuration.md) 및 단순화 된 구성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e5b6-114">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="4e5b6-115">열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4e5b6-115">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="4e5b6-116">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e5b6-116">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="4e5b6-117">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="4e5b6-117">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="4e5b6-118">받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4e5b6-118">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="4e5b6-119">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e5b6-119">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="4e5b6-120">기본값은 00:10:00입니다.</span><span class="sxs-lookup"><span data-stu-id="4e5b6-120">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="4e5b6-121">보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4e5b6-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="4e5b6-122">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e5b6-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="4e5b6-123">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="4e5b6-123">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4e5b6-124">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4e5b6-124">Child Elements</span></span>  

 <span data-ttu-id="4e5b6-125">없음</span><span class="sxs-lookup"><span data-stu-id="4e5b6-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4e5b6-126">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4e5b6-126">Parent Elements</span></span>  
  
|<span data-ttu-id="4e5b6-127">요소</span><span class="sxs-lookup"><span data-stu-id="4e5b6-127">Element</span></span>|<span data-ttu-id="4e5b6-128">설명</span><span class="sxs-lookup"><span data-stu-id="4e5b6-128">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="4e5b6-129">이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="4e5b6-129">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4e5b6-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e5b6-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.MexTcpBindingElement>
- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexTcpBinding%2A>
- [<span data-ttu-id="4e5b6-131">방법: 구성 파일을 사용하여 서비스에 대한 메타데이터 게시</span><span class="sxs-lookup"><span data-stu-id="4e5b6-131">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="4e5b6-132">사용자 지정 바인딩을 통해 메타데이터 게시 및 검색</span><span class="sxs-lookup"><span data-stu-id="4e5b6-132">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="4e5b6-133">메타데이터</span><span class="sxs-lookup"><span data-stu-id="4e5b6-133">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="4e5b6-134">바인딩하</span><span class="sxs-lookup"><span data-stu-id="4e5b6-134">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="4e5b6-135">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="4e5b6-135">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="4e5b6-136">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="4e5b6-136">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
