---
title: <service>
ms.date: 03/30/2017
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
ms.openlocfilehash: dcc32f5aa055942408a3f01d37b5aa27ac0f51ee
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173772"
---
# \<service>

<span data-ttu-id="8805f-101">`service` 요소에는 WCF(Windows Communication Foundation) 서비스 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8805f-101">The `service` element contains the settings for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="8805f-102">이 요소에는 서비스를 공개하는 엔드포인트도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8805f-102">It also contains endpoints that expose the service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<service>**  
  
## <a name="syntax"></a><span data-ttu-id="8805f-103">구문</span><span class="sxs-lookup"><span data-stu-id="8805f-103">Syntax</span></span>  
  
```xml  
<service behaviorConfiguration="String"
         name="String">
</service>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8805f-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8805f-104">Attributes and Elements</span></span>  

 <span data-ttu-id="8805f-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8805f-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8805f-106">특성</span><span class="sxs-lookup"><span data-stu-id="8805f-106">Attributes</span></span>  
  
|<span data-ttu-id="8805f-107">attribute</span><span class="sxs-lookup"><span data-stu-id="8805f-107">Attribute</span></span>|<span data-ttu-id="8805f-108">설명</span><span class="sxs-lookup"><span data-stu-id="8805f-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8805f-109">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="8805f-109">behaviorConfiguration</span></span>|<span data-ttu-id="8805f-110">서비스 인스턴스화에 사용할 동작의 동작 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8805f-110">A string that contains the behavior name of the behavior to be used to instantiate the service.</span></span> <span data-ttu-id="8805f-111">동작 이름은 서비스가 정의된 지점의 범위에 속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8805f-111">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="8805f-112">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8805f-112">The default value is an empty string.</span></span>|  
|<span data-ttu-id="8805f-113">name</span><span class="sxs-lookup"><span data-stu-id="8805f-113">name</span></span>|<span data-ttu-id="8805f-114">인스턴스화할 서비스 형식을 지정하는 필수 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="8805f-114">Required String attribute that specifies the type of the service to be instantiated.</span></span> <span data-ttu-id="8805f-115">이 설정은 유효한 형식을 사용해야 하며,</span><span class="sxs-lookup"><span data-stu-id="8805f-115">This setting must equate to a valid type.</span></span> <span data-ttu-id="8805f-116">`Namespace.Class.` 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8805f-116">The format should be `Namespace.Class.`</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8805f-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8805f-117">Child Elements</span></span>  
  
|<span data-ttu-id="8805f-118">요소</span><span class="sxs-lookup"><span data-stu-id="8805f-118">Element</span></span>|<span data-ttu-id="8805f-119">설명</span><span class="sxs-lookup"><span data-stu-id="8805f-119">Description</span></span>|  
|-------------|-----------------|  
|[\<endpoint>](endpoint-element.md)|<span data-ttu-id="8805f-120">이 서비스를 공개하는 `endpoint` 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8805f-120">A collection of `endpoint` elements that expose this service.</span></span>|  
|[\<host>](host.md)|<span data-ttu-id="8805f-121">이 서비스 인스턴스의 호스트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8805f-121">Specifies the host of this service instance.</span></span> <span data-ttu-id="8805f-122">이 요소는 <xref:System.ServiceModel.Configuration.HostElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8805f-122">This element is of type <xref:System.ServiceModel.Configuration.HostElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8805f-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8805f-123">Parent Elements</span></span>  
  
|<span data-ttu-id="8805f-124">요소</span><span class="sxs-lookup"><span data-stu-id="8805f-124">Element</span></span>|<span data-ttu-id="8805f-125">설명</span><span class="sxs-lookup"><span data-stu-id="8805f-125">Description</span></span>|  
|-------------|-----------------|  
|[\<services>](services.md)|<span data-ttu-id="8805f-126">모든 WCF 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8805f-126">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8805f-127">설명</span><span class="sxs-lookup"><span data-stu-id="8805f-127">Remarks</span></span>  

 <span data-ttu-id="8805f-128">서비스는 구성 파일의 `services` 섹션에 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="8805f-128">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="8805f-129">어셈블리에는 여러 개의 서비스가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8805f-129">An assembly can contain any number of services.</span></span> <span data-ttu-id="8805f-130">서비스별로 해당 `service` 구성 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8805f-130">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="8805f-131">이 단원 및 내용에서는 특정 서비스의 서비스 계약, 동작 및 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8805f-131">This section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="8805f-132">`behaviorConfiguration` 요소도 선택적 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="8805f-132">The `behaviorConfiguration` element is also optional.</span></span> <span data-ttu-id="8805f-133">서비스가 사용하는 동작을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="8805f-133">It identifies the behavior the service uses.</span></span> <span data-ttu-id="8805f-134">이 특성에 지정된 동작은 동일한 구성 파일의 범위에 있는 동작에 연결되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8805f-134">The behavior specified in this attribute must link to a behavior in scope in the same configuration file.</span></span>  
  
 <span data-ttu-id="8805f-135">각 서비스는 하나 이상의 엔드포인트를 노출하는데, 여기에는 자체 주소 및 바인딩이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8805f-135">Each service exposes one or more endpoints, which has its own address and binding.</span></span> <span data-ttu-id="8805f-136">구성 파일 내에서 사용되는 모든 바인딩은 파일 범위 내에서 정의되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8805f-136">All bindings used within the configuration file must be defined in the scope of the file.</span></span> <span data-ttu-id="8805f-137">바인딩은 `name` 및 `bindingConfiguration` 특성 조합을 통해 엔드포인트에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="8805f-137">Binding are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="8805f-138">`name` 특성은 바인딩이 정의된 섹션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8805f-138">The `name` attribute describes the section the binding is defined in.</span></span> <span data-ttu-id="8805f-139">`bindingConfiguration` 특성은 바인딩 섹션 내에서 사용되는 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8805f-139">The `bindingConfiguration` attribute defines which configuration within the binding section is used.</span></span> <span data-ttu-id="8805f-140">바인딩 섹션에서는 여러 개의 구성을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8805f-140">A binding section can define several configurations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8805f-141">예제</span><span class="sxs-lookup"><span data-stu-id="8805f-141">Example</span></span>  

 <span data-ttu-id="8805f-142">서비스 구성의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="8805f-142">This is an example of a service configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8805f-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8805f-143">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceElement>
- [<span data-ttu-id="8805f-144">서비스 구성</span><span class="sxs-lookup"><span data-stu-id="8805f-144">Configuring Services</span></span>](../../../wcf/configuring-services.md)
