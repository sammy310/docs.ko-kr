---
title: <mexHttpsBinding>
ms.date: 03/30/2017
ms.assetid: f2ed3774-78b9-4a15-b79b-655f1ad68b86
ms.openlocfilehash: 30d1aa27ce29b6aa4091c3e7be05746ad462102a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931263"
---
# <a name="mexhttpsbinding"></a><span data-ttu-id="48bfc-101">\<mexHttpsBinding></span><span class="sxs-lookup"><span data-stu-id="48bfc-101">\<mexHttpsBinding></span></span>
<span data-ttu-id="48bfc-102">HTTPS를 통한 WS-MEX(WS-MetadataExchange) 메시지 교환에 사용되는 바인딩의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="48bfc-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTPS.</span></span>  
  
 <span data-ttu-id="48bfc-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="48bfc-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="48bfc-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="48bfc-104">\<bindings></span></span>  
<span data-ttu-id="48bfc-105">\<mexHttpsBinding></span><span class="sxs-lookup"><span data-stu-id="48bfc-105">\<mexHttpsBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48bfc-106">구문</span><span class="sxs-lookup"><span data-stu-id="48bfc-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="48bfc-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="48bfc-107">Attributes and Elements</span></span>  
 <span data-ttu-id="48bfc-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="48bfc-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="48bfc-109">특성</span><span class="sxs-lookup"><span data-stu-id="48bfc-109">Attributes</span></span>  
  
|<span data-ttu-id="48bfc-110">특성</span><span class="sxs-lookup"><span data-stu-id="48bfc-110">Attribute</span></span>|<span data-ttu-id="48bfc-111">설명</span><span class="sxs-lookup"><span data-stu-id="48bfc-111">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="48bfc-112">닫기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="48bfc-112">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="48bfc-113">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48bfc-113">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="48bfc-114">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="48bfc-114">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="48bfc-115">바인딩의 구성 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="48bfc-115">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="48bfc-116">이 값은 바인딩의 ID로 사용되므로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48bfc-116">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="48bfc-117">각 바인딩에는 서비스의 메타데이터에서 함께 바인딩을 고유하게 식별하는 `name` 및 `namespace` 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48bfc-117">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="48bfc-118">또한 이 이름은 동일한 형식의 바인딩 간에 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="48bfc-118">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="48bfc-119">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="48bfc-119">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="48bfc-120">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 [WCF 서비스에 대 한](../../../wcf/samples/simplified-configuration-for-wcf-services.md) [간소화 된 구성](../../../wcf/simplified-configuration.md) 및 단순화 된 구성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="48bfc-120">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="48bfc-121">열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="48bfc-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="48bfc-122">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48bfc-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="48bfc-123">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="48bfc-123">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="48bfc-124">받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="48bfc-124">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="48bfc-125">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48bfc-125">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="48bfc-126">기본값은 00:10:00입니다.</span><span class="sxs-lookup"><span data-stu-id="48bfc-126">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="48bfc-127">보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="48bfc-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="48bfc-128">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48bfc-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="48bfc-129">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="48bfc-129">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="48bfc-130">자식 요소</span><span class="sxs-lookup"><span data-stu-id="48bfc-130">Child Elements</span></span>  
 <span data-ttu-id="48bfc-131">없음</span><span class="sxs-lookup"><span data-stu-id="48bfc-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="48bfc-132">부모 요소</span><span class="sxs-lookup"><span data-stu-id="48bfc-132">Parent Elements</span></span>  
  
|<span data-ttu-id="48bfc-133">요소</span><span class="sxs-lookup"><span data-stu-id="48bfc-133">Element</span></span>|<span data-ttu-id="48bfc-134">설명</span><span class="sxs-lookup"><span data-stu-id="48bfc-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="48bfc-135">\<bindings></span><span class="sxs-lookup"><span data-stu-id="48bfc-135">\<bindings></span></span>](bindings.md)|<span data-ttu-id="48bfc-136">이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="48bfc-136">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48bfc-137">설명</span><span class="sxs-lookup"><span data-stu-id="48bfc-137">Remarks</span></span>  
 <span data-ttu-id="48bfc-138">이 바인딩은 기본적으로 인증서를 사용하여 전송 수준에서 보안을 지원할 수 있는 `WSHttpBinding` 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="48bfc-138">This binding is essentially a `WSHttpBinding` binding that supports transport-level security using certificates.</span></span> <span data-ttu-id="48bfc-139">이러한 메타 데이터 끝점을 [구성 하 고 사용 하는 방법에 대 한 자세한 내용은 방법: 사용자 지정 WS 메타 데이터 교환 바인딩](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)구성, [방법: MEX가 아닌 바인딩을](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)통해 메타 데이터를 검색 하 고 샘플 [사용자 지정 보안 메타 데이터 끝점](../../../wcf/samples/custom-secure-metadata-endpoint.md)을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="48bfc-139">For more information about configuring and using such a metadata endpoint, see [How to: Configure a Custom WS-Metadata Exchange Binding](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [How to: Retrieve Metadata Over a non-MEX Binding](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), and the sample [Custom Secure Metadata Endpoint](../../../wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48bfc-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="48bfc-140">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpsBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpsBindingElement>
- [<span data-ttu-id="48bfc-141">방법: 구성 파일을 사용 하 여 서비스에 대 한 메타 데이터 게시</span><span class="sxs-lookup"><span data-stu-id="48bfc-141">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="48bfc-142">사용자 지정 바인딩을 통해 메타데이터 게시 및 검색</span><span class="sxs-lookup"><span data-stu-id="48bfc-142">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="48bfc-143">방법: 사용자 지정 WS-Metadata Exchange 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="48bfc-143">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)
- [<span data-ttu-id="48bfc-144">방법: MEX가 아닌 바인딩을 통해 메타 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="48bfc-144">How to: Retrieve Metadata Over a non-MEX Binding</span></span>](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)
- [<span data-ttu-id="48bfc-145">사용자 지정 보안 메타 데이터 엔드포인트</span><span class="sxs-lookup"><span data-stu-id="48bfc-145">Custom Secure Metadata Endpoint</span></span>](../../../wcf/samples/custom-secure-metadata-endpoint.md)
- [<span data-ttu-id="48bfc-146">메타데이터</span><span class="sxs-lookup"><span data-stu-id="48bfc-146">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="48bfc-147">바인딩</span><span class="sxs-lookup"><span data-stu-id="48bfc-147">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="48bfc-148">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="48bfc-148">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="48bfc-149">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="48bfc-149">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="48bfc-150">\<binding></span><span class="sxs-lookup"><span data-stu-id="48bfc-150">\<binding></span></span>](../../../misc/binding.md)
