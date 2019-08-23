---
title: <mexTcpBinding>
ms.date: 03/30/2017
ms.assetid: 01baba8d-d784-4255-9ea2-7afff1482bf0
ms.openlocfilehash: 491597da508487c3988b284c84411123d434fe72
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932526"
---
# <a name="mextcpbinding"></a><span data-ttu-id="d7e30-101">\<mexTcpBinding></span><span class="sxs-lookup"><span data-stu-id="d7e30-101">\<mexTcpBinding></span></span>
<span data-ttu-id="d7e30-102">TCP를 통한 WS-MEX(WS-MetadataExchange) 메시지 교환에 사용되는 바인딩의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e30-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over TCP.</span></span>  
  
 <span data-ttu-id="d7e30-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d7e30-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="d7e30-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="d7e30-104">\<bindings></span></span>  
<span data-ttu-id="d7e30-105">\<mexTcpBinding></span><span class="sxs-lookup"><span data-stu-id="d7e30-105">\<mexTcpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7e30-106">구문</span><span class="sxs-lookup"><span data-stu-id="d7e30-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d7e30-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d7e30-107">Attributes and Elements</span></span>  
 <span data-ttu-id="d7e30-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e30-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d7e30-109">특성</span><span class="sxs-lookup"><span data-stu-id="d7e30-109">Attributes</span></span>  
  
|<span data-ttu-id="d7e30-110">특성</span><span class="sxs-lookup"><span data-stu-id="d7e30-110">Attribute</span></span>|<span data-ttu-id="d7e30-111">설명</span><span class="sxs-lookup"><span data-stu-id="d7e30-111">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="d7e30-112">닫기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d7e30-112">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="d7e30-113">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e30-113">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d7e30-114">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="d7e30-114">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="d7e30-115">바인딩의 구성 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d7e30-115">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="d7e30-116">이 값은 바인딩의 ID로 사용되므로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e30-116">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="d7e30-117">각 바인딩에는 서비스의 메타데이터에서 함께 바인딩을 고유하게 식별하는 `name` 및 `namespace` 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e30-117">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="d7e30-118">또한 이 이름은 동일한 형식의 바인딩 간에 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e30-118">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="d7e30-119">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e30-119">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="d7e30-120">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 [WCF 서비스에 대 한](../../../wcf/samples/simplified-configuration-for-wcf-services.md) [간소화 된 구성](../../../wcf/simplified-configuration.md) 및 단순화 된 구성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d7e30-120">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="d7e30-121">열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d7e30-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="d7e30-122">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e30-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d7e30-123">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="d7e30-123">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="d7e30-124">받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d7e30-124">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="d7e30-125">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e30-125">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d7e30-126">기본값은 00:10:00입니다.</span><span class="sxs-lookup"><span data-stu-id="d7e30-126">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="d7e30-127">보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d7e30-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="d7e30-128">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e30-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d7e30-129">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="d7e30-129">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d7e30-130">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d7e30-130">Child Elements</span></span>  
 <span data-ttu-id="d7e30-131">없음</span><span class="sxs-lookup"><span data-stu-id="d7e30-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d7e30-132">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d7e30-132">Parent Elements</span></span>  
  
|<span data-ttu-id="d7e30-133">요소</span><span class="sxs-lookup"><span data-stu-id="d7e30-133">Element</span></span>|<span data-ttu-id="d7e30-134">설명</span><span class="sxs-lookup"><span data-stu-id="d7e30-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d7e30-135">\<bindings></span><span class="sxs-lookup"><span data-stu-id="d7e30-135">\<bindings></span></span>](bindings.md)|<span data-ttu-id="d7e30-136">이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e30-136">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d7e30-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="d7e30-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.MexTcpBindingElement>
- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexTcpBinding%2A>
- [<span data-ttu-id="d7e30-138">방법: 구성 파일을 사용 하 여 서비스에 대 한 메타 데이터 게시</span><span class="sxs-lookup"><span data-stu-id="d7e30-138">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="d7e30-139">사용자 지정 바인딩을 통해 메타데이터 게시 및 검색</span><span class="sxs-lookup"><span data-stu-id="d7e30-139">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="d7e30-140">메타데이터</span><span class="sxs-lookup"><span data-stu-id="d7e30-140">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="d7e30-141">바인딩</span><span class="sxs-lookup"><span data-stu-id="d7e30-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d7e30-142">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="d7e30-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="d7e30-143">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="d7e30-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="d7e30-144">\<binding></span><span class="sxs-lookup"><span data-stu-id="d7e30-144">\<binding></span></span>](../../../misc/binding.md)
