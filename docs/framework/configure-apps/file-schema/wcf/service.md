---
title: <service>
ms.date: 03/30/2017
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
ms.openlocfilehash: 69f3c70514fc2bcab1b4ef6a45036de98d1af7b7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936520"
---
# <a name="service"></a><span data-ttu-id="febcf-101">\<service></span><span class="sxs-lookup"><span data-stu-id="febcf-101">\<service></span></span>
<span data-ttu-id="febcf-102">`service` 요소에는 WCF(Windows Communication Foundation) 서비스 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="febcf-102">The `service` element contains the settings for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="febcf-103">이 요소에는 서비스를 공개하는 엔드포인트도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="febcf-103">It also contains endpoints that expose the service.</span></span>  
  
 <span data-ttu-id="febcf-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="febcf-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="febcf-105">\<services></span><span class="sxs-lookup"><span data-stu-id="febcf-105">\<services></span></span>  
<span data-ttu-id="febcf-106">\<service></span><span class="sxs-lookup"><span data-stu-id="febcf-106">\<service></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="febcf-107">구문</span><span class="sxs-lookup"><span data-stu-id="febcf-107">Syntax</span></span>  
  
```xml  
<service behaviorConfiguration="String"
         name="String">
</service>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="febcf-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="febcf-108">Attributes and Elements</span></span>  
 <span data-ttu-id="febcf-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="febcf-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="febcf-110">특성</span><span class="sxs-lookup"><span data-stu-id="febcf-110">Attributes</span></span>  
  
|<span data-ttu-id="febcf-111">특성</span><span class="sxs-lookup"><span data-stu-id="febcf-111">Attribute</span></span>|<span data-ttu-id="febcf-112">Description</span><span class="sxs-lookup"><span data-stu-id="febcf-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="febcf-113">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="febcf-113">behaviorConfiguration</span></span>|<span data-ttu-id="febcf-114">서비스 인스턴스화에 사용할 동작의 동작 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="febcf-114">A string that contains the behavior name of the behavior to be used to instantiate the service.</span></span> <span data-ttu-id="febcf-115">동작 이름은 서비스가 정의된 지점의 범위에 속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="febcf-115">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="febcf-116">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="febcf-116">The default value is an empty string.</span></span>|  
|<span data-ttu-id="febcf-117">name</span><span class="sxs-lookup"><span data-stu-id="febcf-117">name</span></span>|<span data-ttu-id="febcf-118">인스턴스화할 서비스 형식을 지정하는 필수 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="febcf-118">Required String attribute that specifies the type of the service to be instantiated.</span></span> <span data-ttu-id="febcf-119">이 설정은 유효한 형식을 사용해야 하며,</span><span class="sxs-lookup"><span data-stu-id="febcf-119">This setting must equate to a valid type.</span></span> <span data-ttu-id="febcf-120">Namespace.Class`Namespace.Class.` 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="febcf-120">The format should be `Namespace.Class.`</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="febcf-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="febcf-121">Child Elements</span></span>  
  
|<span data-ttu-id="febcf-122">요소</span><span class="sxs-lookup"><span data-stu-id="febcf-122">Element</span></span>|<span data-ttu-id="febcf-123">Description</span><span class="sxs-lookup"><span data-stu-id="febcf-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="febcf-124">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="febcf-124">\<endpoint></span></span>](endpoint-element.md)|<span data-ttu-id="febcf-125">이 서비스를 공개하는 `endpoint` 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="febcf-125">A collection of `endpoint` elements that expose this service.</span></span>|  
|[<span data-ttu-id="febcf-126">\<host></span><span class="sxs-lookup"><span data-stu-id="febcf-126">\<host></span></span>](host.md)|<span data-ttu-id="febcf-127">이 서비스 인스턴스의 호스트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="febcf-127">Specifies the host of this service instance.</span></span> <span data-ttu-id="febcf-128">이 요소는 <xref:System.ServiceModel.Configuration.HostElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="febcf-128">This element is of type <xref:System.ServiceModel.Configuration.HostElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="febcf-129">부모 요소</span><span class="sxs-lookup"><span data-stu-id="febcf-129">Parent Elements</span></span>  
  
|<span data-ttu-id="febcf-130">요소</span><span class="sxs-lookup"><span data-stu-id="febcf-130">Element</span></span>|<span data-ttu-id="febcf-131">Description</span><span class="sxs-lookup"><span data-stu-id="febcf-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="febcf-132">\<services></span><span class="sxs-lookup"><span data-stu-id="febcf-132">\<services></span></span>](services.md)|<span data-ttu-id="febcf-133">모든 WCF 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="febcf-133">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="febcf-134">설명</span><span class="sxs-lookup"><span data-stu-id="febcf-134">Remarks</span></span>  
 <span data-ttu-id="febcf-135">서비스는 구성 파일의 `services` 섹션에 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="febcf-135">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="febcf-136">어셈블리에는 여러 개의 서비스가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="febcf-136">An assembly can contain any number of services.</span></span> <span data-ttu-id="febcf-137">서비스별로 해당 `service` 구성 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="febcf-137">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="febcf-138">이 단원 및 내용에서는 특정 서비스의 서비스 계약, 동작 및 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="febcf-138">This section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="febcf-139">`behaviorConfiguration` 요소도 선택적 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="febcf-139">The `behaviorConfiguration` element is also optional.</span></span> <span data-ttu-id="febcf-140">서비스가 사용하는 동작을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="febcf-140">It identifies the behavior the service uses.</span></span> <span data-ttu-id="febcf-141">이 특성에 지정된 동작은 동일한 구성 파일의 범위에 있는 동작에 연결되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="febcf-141">The behavior specified in this attribute must link to a behavior in scope in the same configuration file.</span></span>  
  
 <span data-ttu-id="febcf-142">각 서비스는 하나 이상의 엔드포인트를 노출하는데, 여기에는 자체 주소 및 바인딩이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="febcf-142">Each service exposes one or more endpoints, which has its own address and binding.</span></span> <span data-ttu-id="febcf-143">구성 파일 내에서 사용되는 모든 바인딩은 파일 범위 내에서 정의되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="febcf-143">All bindings used within the configuration file must be defined in the scope of the file.</span></span> <span data-ttu-id="febcf-144">바인딩은 `name` 및 `bindingConfiguration` 특성 조합을 통해 엔드포인트에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="febcf-144">Binding are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="febcf-145">`name` 특성은 바인딩이 정의된 섹션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="febcf-145">The `name` attribute describes the section the binding is defined in.</span></span> <span data-ttu-id="febcf-146">`bindingConfiguration` 특성은 바인딩 섹션 내에서 사용되는 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="febcf-146">The `bindingConfiguration` attribute defines which configuration within the binding section is used.</span></span> <span data-ttu-id="febcf-147">바인딩 섹션에서는 여러 개의 구성을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="febcf-147">A binding section can define several configurations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="febcf-148">예제</span><span class="sxs-lookup"><span data-stu-id="febcf-148">Example</span></span>  
 <span data-ttu-id="febcf-149">서비스 구성의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="febcf-149">This is an example of a service configuration.</span></span>  
  
```xml  
<service behaviorConfiguration="testChannelBehavior"
         name="HelloWorld">
  <endpoint address="/HelloWorld2/"
            name="test"
            bindingNamespace="http://www.cohowinery.com/"
            binding="basicHttpBinding"
            contract="IHelloWorld" />
</service>
```  
  
## <a name="see-also"></a><span data-ttu-id="febcf-150">참고자료</span><span class="sxs-lookup"><span data-stu-id="febcf-150">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceElement>
- [<span data-ttu-id="febcf-151">서비스 구성</span><span class="sxs-lookup"><span data-stu-id="febcf-151">Configuring Services</span></span>](../../../wcf/configuring-services.md)
