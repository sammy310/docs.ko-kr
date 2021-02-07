---
description: 다음에 대해 자세히 알아보세요. <mexHttpsBinding>
title: <mexHttpsBinding>
ms.date: 03/30/2017
ms.assetid: f2ed3774-78b9-4a15-b79b-655f1ad68b86
ms.openlocfilehash: 1e6eb66e1379cb8f351e34d4fd406dd3cc1f9a4e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99684336"
---
# \<mexHttpsBinding>

<span data-ttu-id="6a7f7-102">HTTPS를 통한 WS-MEX(WS-MetadataExchange) 메시지 교환에 사용되는 바인딩의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTPS.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexHttpsBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="6a7f7-103">구문</span><span class="sxs-lookup"><span data-stu-id="6a7f7-103">Syntax</span></span>  
  
```xml  
<mexHttpsBinding>
  <binding closeTimeout="TimeSpan"
            name="string"
            openTimeout="TimeSpan"
            receiveTimeout="TimeSpan"
            sendTimeout="TimeSpan">
  </binding>
</mexHttpsBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6a7f7-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6a7f7-104">Attributes and Elements</span></span>  

 <span data-ttu-id="6a7f7-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6a7f7-106">특성</span><span class="sxs-lookup"><span data-stu-id="6a7f7-106">Attributes</span></span>  
  
|<span data-ttu-id="6a7f7-107">attribute</span><span class="sxs-lookup"><span data-stu-id="6a7f7-107">Attribute</span></span>|<span data-ttu-id="6a7f7-108">설명</span><span class="sxs-lookup"><span data-stu-id="6a7f7-108">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="6a7f7-109">닫기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-109">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="6a7f7-110">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-110">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="6a7f7-111">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-111">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="6a7f7-112">바인딩의 구성 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-112">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="6a7f7-113">이 값은 바인딩의 ID로 사용되므로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-113">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="6a7f7-114">.NET Framework 4부터 바인딩과 동작은 이름을 가질 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-114">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="6a7f7-115">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 [WCF 서비스에 대 한](../../../wcf/samples/simplified-configuration-for-wcf-services.md) [간소화 된 구성](../../../wcf/simplified-configuration.md) 및 단순화 된 구성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-115">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="6a7f7-116">열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-116">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="6a7f7-117">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-117">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="6a7f7-118">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-118">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="6a7f7-119">받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-119">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="6a7f7-120">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-120">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="6a7f7-121">기본값은 00:10:00입니다.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-121">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="6a7f7-122">보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="6a7f7-123">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="6a7f7-124">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-124">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6a7f7-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6a7f7-125">Child Elements</span></span>  

 <span data-ttu-id="6a7f7-126">없음</span><span class="sxs-lookup"><span data-stu-id="6a7f7-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6a7f7-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6a7f7-127">Parent Elements</span></span>  
  
|<span data-ttu-id="6a7f7-128">요소</span><span class="sxs-lookup"><span data-stu-id="6a7f7-128">Element</span></span>|<span data-ttu-id="6a7f7-129">설명</span><span class="sxs-lookup"><span data-stu-id="6a7f7-129">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="6a7f7-130">이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-130">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a7f7-131">설명</span><span class="sxs-lookup"><span data-stu-id="6a7f7-131">Remarks</span></span>  

 <span data-ttu-id="6a7f7-132">이 바인딩은 기본적으로 인증서를 사용하여 전송 수준에서 보안을 지원할 수 있는 `WSHttpBinding` 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-132">This binding is essentially a `WSHttpBinding` binding that supports transport-level security using certificates.</span></span> <span data-ttu-id="6a7f7-133">구성 및 메타 데이터 엔드포인트을 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [방법:는 사용자 지정 Ws-metadata Exchange 바인딩 구성](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)를 [방법: 검색 메타 데이터를 통해가 아닌-MEX 바인딩을](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), 및 샘플 [사용자 지정 보안 메타 데이터 엔드포인트](../../../wcf/samples/custom-secure-metadata-endpoint.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-133">For more information about configuring and using such a metadata endpoint, see [How to: Configure a Custom WS-Metadata Exchange Binding](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [How to: Retrieve Metadata Over a non-MEX Binding](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), and the sample [Custom Secure Metadata Endpoint](../../../wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a7f7-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6a7f7-134">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpsBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpsBindingElement>
- [<span data-ttu-id="6a7f7-135">방법: 구성 파일을 사용하여 서비스에 대한 메타데이터 게시</span><span class="sxs-lookup"><span data-stu-id="6a7f7-135">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="6a7f7-136">사용자 지정 바인딩을 통해 메타데이터 게시 및 검색</span><span class="sxs-lookup"><span data-stu-id="6a7f7-136">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="6a7f7-137">방법: 사용자 지정 WS-Metadata Exchange 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="6a7f7-137">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)
- [<span data-ttu-id="6a7f7-138">방법: MEX가 아닌 바인딩을 통해 메타데이터 검색</span><span class="sxs-lookup"><span data-stu-id="6a7f7-138">How to: Retrieve Metadata Over a non-MEX Binding</span></span>](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)
- [<span data-ttu-id="6a7f7-139">Custom Secure Metadata Endpoint</span><span class="sxs-lookup"><span data-stu-id="6a7f7-139">Custom Secure Metadata Endpoint</span></span>](../../../wcf/samples/custom-secure-metadata-endpoint.md)
- [<span data-ttu-id="6a7f7-140">메타데이터</span><span class="sxs-lookup"><span data-stu-id="6a7f7-140">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="6a7f7-141">바인딩</span><span class="sxs-lookup"><span data-stu-id="6a7f7-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="6a7f7-142">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="6a7f7-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="6a7f7-143">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="6a7f7-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
