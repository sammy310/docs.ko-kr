---
title: <mexHttpsBinding>
ms.date: 03/30/2017
ms.assetid: f2ed3774-78b9-4a15-b79b-655f1ad68b86
ms.openlocfilehash: 924d68dd828622b74c5e424a695f80874391b453
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430344"
---
# <a name="mexhttpsbinding"></a><span data-ttu-id="1b476-101">\<mexHttpsBinding></span><span class="sxs-lookup"><span data-stu-id="1b476-101">\<mexHttpsBinding></span></span>
<span data-ttu-id="1b476-102">HTTPS를 통한 WS-MEX(WS-MetadataExchange) 메시지 교환에 사용되는 바인딩의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1b476-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTPS.</span></span>  
  
<span data-ttu-id="1b476-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1b476-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1b476-104">&nbsp;&nbsp;[ **\<system.serviceModel>** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="1b476-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="1b476-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<bindings>** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="1b476-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="1b476-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<mexHttpsBinding>**</span><span class="sxs-lookup"><span data-stu-id="1b476-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexHttpsBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b476-107">구문</span><span class="sxs-lookup"><span data-stu-id="1b476-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1b476-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1b476-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1b476-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1b476-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1b476-110">특성</span><span class="sxs-lookup"><span data-stu-id="1b476-110">Attributes</span></span>  
  
|<span data-ttu-id="1b476-111">특성</span><span class="sxs-lookup"><span data-stu-id="1b476-111">Attribute</span></span>|<span data-ttu-id="1b476-112">설명</span><span class="sxs-lookup"><span data-stu-id="1b476-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="1b476-113">닫기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1b476-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="1b476-114">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b476-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="1b476-115">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="1b476-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="1b476-116">바인딩의 구성 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1b476-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="1b476-117">이 값은 바인딩의 ID로 사용되므로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b476-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="1b476-118">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span><span class="sxs-lookup"><span data-stu-id="1b476-118">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="1b476-119">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="1b476-119">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="1b476-120">열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1b476-120">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="1b476-121">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b476-121">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="1b476-122">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="1b476-122">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="1b476-123">받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1b476-123">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="1b476-124">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b476-124">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="1b476-125">The default is 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="1b476-125">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="1b476-126">보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1b476-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="1b476-127">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b476-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="1b476-128">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="1b476-128">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1b476-129">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1b476-129">Child Elements</span></span>  
 <span data-ttu-id="1b476-130">없음.</span><span class="sxs-lookup"><span data-stu-id="1b476-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1b476-131">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1b476-131">Parent Elements</span></span>  
  
|<span data-ttu-id="1b476-132">요소</span><span class="sxs-lookup"><span data-stu-id="1b476-132">Element</span></span>|<span data-ttu-id="1b476-133">설명</span><span class="sxs-lookup"><span data-stu-id="1b476-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1b476-134">\<bindings></span><span class="sxs-lookup"><span data-stu-id="1b476-134">\<bindings></span></span>](bindings.md)|<span data-ttu-id="1b476-135">이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="1b476-135">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b476-136">주의</span><span class="sxs-lookup"><span data-stu-id="1b476-136">Remarks</span></span>  
 <span data-ttu-id="1b476-137">이 바인딩은 기본적으로 인증서를 사용하여 전송 수준에서 보안을 지원할 수 있는 `WSHttpBinding` 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="1b476-137">This binding is essentially a `WSHttpBinding` binding that supports transport-level security using certificates.</span></span> <span data-ttu-id="1b476-138">For more information about configuring and using such a metadata endpoint, see [How to: Configure a Custom WS-Metadata Exchange Binding](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [How to: Retrieve Metadata Over a non-MEX Binding](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), and the sample [Custom Secure Metadata Endpoint](../../../wcf/samples/custom-secure-metadata-endpoint.md).</span><span class="sxs-lookup"><span data-stu-id="1b476-138">For more information about configuring and using such a metadata endpoint, see [How to: Configure a Custom WS-Metadata Exchange Binding](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [How to: Retrieve Metadata Over a non-MEX Binding](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), and the sample [Custom Secure Metadata Endpoint](../../../wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b476-139">참조</span><span class="sxs-lookup"><span data-stu-id="1b476-139">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpsBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpsBindingElement>
- [<span data-ttu-id="1b476-140">방법: 구성 파일을 사용하여 서비스의 메타데이터 게시</span><span class="sxs-lookup"><span data-stu-id="1b476-140">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="1b476-141">사용자 지정 바인딩을 통해 메타데이터 게시 및 검색</span><span class="sxs-lookup"><span data-stu-id="1b476-141">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="1b476-142">방법: 사용자 지정 WS-Metadata Exchange 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="1b476-142">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)
- [<span data-ttu-id="1b476-143">방법: MEX가 아닌 바인딩을 통해 메타데이터 검색</span><span class="sxs-lookup"><span data-stu-id="1b476-143">How to: Retrieve Metadata Over a non-MEX Binding</span></span>](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)
- [<span data-ttu-id="1b476-144">사용자 지정 보안 메타 데이터 엔드포인트</span><span class="sxs-lookup"><span data-stu-id="1b476-144">Custom Secure Metadata Endpoint</span></span>](../../../wcf/samples/custom-secure-metadata-endpoint.md)
- [<span data-ttu-id="1b476-145">메타데이터</span><span class="sxs-lookup"><span data-stu-id="1b476-145">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="1b476-146">바인딩</span><span class="sxs-lookup"><span data-stu-id="1b476-146">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="1b476-147">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="1b476-147">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="1b476-148">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="1b476-148">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="1b476-149">\<binding></span><span class="sxs-lookup"><span data-stu-id="1b476-149">\<binding></span></span>](bindings.md)
