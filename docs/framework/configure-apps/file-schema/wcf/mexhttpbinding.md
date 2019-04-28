---
title: <mexHttpBinding>
ms.date: 03/30/2017
ms.assetid: e50b2e1f-9668-41a5-8077-dee7abff9f0f
ms.openlocfilehash: 1aa9512c3d0d52f8cc3c7bd7b82bcfd37c418ce7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61773453"
---
# <a name="mexhttpbinding"></a><span data-ttu-id="8d540-101">\<mexHttpBinding></span><span class="sxs-lookup"><span data-stu-id="8d540-101">\<mexHttpBinding></span></span>
<span data-ttu-id="8d540-102">HTTP를 통한 WS-MEX(WS-MetadataExchange) 메시지 교환에 사용되는 바인딩의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d540-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTP.</span></span>  
  
 <span data-ttu-id="8d540-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8d540-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="8d540-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="8d540-104">\<bindings></span></span>  
<span data-ttu-id="8d540-105">\<mexHttpBinding></span><span class="sxs-lookup"><span data-stu-id="8d540-105">\<mexHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d540-106">구문</span><span class="sxs-lookup"><span data-stu-id="8d540-106">Syntax</span></span>  
  
```xml  
<mexHttpBinding>
  <binding closeTimeout="TimeSpan"
           name="string"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
  </binding>
</mexHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8d540-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8d540-107">Attributes and Elements</span></span>  
 <span data-ttu-id="8d540-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8d540-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8d540-109">특성</span><span class="sxs-lookup"><span data-stu-id="8d540-109">Attributes</span></span>  
  
|<span data-ttu-id="8d540-110">특성</span><span class="sxs-lookup"><span data-stu-id="8d540-110">Attribute</span></span>|<span data-ttu-id="8d540-111">설명</span><span class="sxs-lookup"><span data-stu-id="8d540-111">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="8d540-112">닫기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8d540-112">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="8d540-113">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d540-113">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="8d540-114">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="8d540-114">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="8d540-115">바인딩의 구성 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8d540-115">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="8d540-116">이 값은 바인딩의 ID로 사용되므로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d540-116">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="8d540-117">각 바인딩에는 서비스의 메타데이터에서 함께 바인딩을 고유하게 식별하는 `name` 및 `namespace` 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d540-117">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="8d540-118">또한 이 이름은 동일한 형식의 바인딩 간에 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="8d540-118">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="8d540-119">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d540-119">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="8d540-120">기본 구성 및 이름 없는 바인딩 및 동작에 대 한 자세한 내용은 참조 하세요. [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) 하 고 [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8d540-120">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="8d540-121">열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8d540-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="8d540-122">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d540-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="8d540-123">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="8d540-123">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="8d540-124">받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8d540-124">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="8d540-125">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d540-125">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="8d540-126">기본값은 00:10:00입니다.</span><span class="sxs-lookup"><span data-stu-id="8d540-126">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="8d540-127">보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8d540-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="8d540-128">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d540-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="8d540-129">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="8d540-129">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8d540-130">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8d540-130">Child Elements</span></span>  
 <span data-ttu-id="8d540-131">없음</span><span class="sxs-lookup"><span data-stu-id="8d540-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8d540-132">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8d540-132">Parent Elements</span></span>  
  
|<span data-ttu-id="8d540-133">요소</span><span class="sxs-lookup"><span data-stu-id="8d540-133">Element</span></span>|<span data-ttu-id="8d540-134">설명</span><span class="sxs-lookup"><span data-stu-id="8d540-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8d540-135">\<bindings></span><span class="sxs-lookup"><span data-stu-id="8d540-135">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="8d540-136">이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="8d540-136">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d540-137">설명</span><span class="sxs-lookup"><span data-stu-id="8d540-137">Remarks</span></span>  
 <span data-ttu-id="8d540-138">기본적으로 이 바인딩은 보안이 설정되지 않은 `WSHttpBinding` 바인딩이며</span><span class="sxs-lookup"><span data-stu-id="8d540-138">This binding is essentially a `WSHttpBinding` binding with security disabled.</span></span> <span data-ttu-id="8d540-139">대부분의 메타데이터 요청을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="8d540-139">It supports most metadata requests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d540-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="8d540-140">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpBindingElement>
- [<span data-ttu-id="8d540-141">방법: 구성 파일을 사용 하는 서비스의 메타 데이터 게시</span><span class="sxs-lookup"><span data-stu-id="8d540-141">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="8d540-142">사용자 지정 바인딩을 통해 메타데이터 게시 및 검색</span><span class="sxs-lookup"><span data-stu-id="8d540-142">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="8d540-143">메타데이터</span><span class="sxs-lookup"><span data-stu-id="8d540-143">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)
- [<span data-ttu-id="8d540-144">바인딩</span><span class="sxs-lookup"><span data-stu-id="8d540-144">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="8d540-145">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="8d540-145">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="8d540-146">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="8d540-146">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="8d540-147">\<binding></span><span class="sxs-lookup"><span data-stu-id="8d540-147">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
