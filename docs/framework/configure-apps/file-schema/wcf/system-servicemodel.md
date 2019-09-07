---
title: <system.serviceModel>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.ServiceModel
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel
helpviewer_keywords:
- <system.serviceModel> element
- system.serviceModel element
ms.assetid: 78519531-ad7a-40d3-b3e7-42f1103d8854
ms.openlocfilehash: 2125ce00b0e23f2e93ff251549f9c1276892b16b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399450"
---
# <a name="systemservicemodel"></a><span data-ttu-id="2daea-102">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2daea-102">\<system.serviceModel></span></span>
<span data-ttu-id="2daea-103">이 구성 섹션에는 WCF (Windows Communication Foundation) ServiceModel 구성 요소가 모두 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-103">This configuration section contains all the Windows Communication Foundation (WCF) ServiceModel configuration elements.</span></span>  

<span data-ttu-id="2daea-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2daea-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2daea-105">&nbsp;&nbsp; **\<System.servicemodel >**</span><span class="sxs-lookup"><span data-stu-id="2daea-105">&nbsp;&nbsp;**\<system.serviceModel>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2daea-106">구문</span><span class="sxs-lookup"><span data-stu-id="2daea-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <behaviors>
  </behaviors>
  <bindings>
  </bindings>
  <client>
  </client>
  <comContracts>
  </comContracts>
  <commonBehaviors>
  </commonBehaviors>
  <diagnostics>
  </diagnostics>
  <extensions>
  </extensions>
  <protocolMapping>
  </protocolMapping>
  <routing>
  </routing>
  <serviceHostingEnvironment>
  </serviceHostingEnvironment>
  <services>
  </services>
  <standardEndpoints>
  </standardEndpoints>
  <tracking>
  </tracking>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2daea-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2daea-107">Attributes and Elements</span></span>  
 <span data-ttu-id="2daea-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2daea-109">특성</span><span class="sxs-lookup"><span data-stu-id="2daea-109">Attributes</span></span>  
 <span data-ttu-id="2daea-110">없음</span><span class="sxs-lookup"><span data-stu-id="2daea-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2daea-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2daea-111">Child Elements</span></span>  
  
|<span data-ttu-id="2daea-112">요소</span><span class="sxs-lookup"><span data-stu-id="2daea-112">Element</span></span>|<span data-ttu-id="2daea-113">설명</span><span class="sxs-lookup"><span data-stu-id="2daea-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2daea-114">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="2daea-114">\<behaviors></span></span>](behaviors.md)|<span data-ttu-id="2daea-115">이 섹션은 두 자식 컬렉션 `endpointBehaviors` 및 `serviceBehaviors`를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-115">This section defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="2daea-116">각 컬렉션은 엔드포인트 및 서비스가 사용하는 동작 요소를 각각 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-116">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="2daea-117">각 동작 요소는 고유한 `name` 특성으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-117">Each behavior element is identified by its unique `name` attribute.</span></span>|  
|[<span data-ttu-id="2daea-118">\<bindings></span><span class="sxs-lookup"><span data-stu-id="2daea-118">\<bindings></span></span>](bindings.md)|<span data-ttu-id="2daea-119">이 섹션에는 표준 및 사용자 지정 바인딩 컬렉션이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-119">This section holds a collection of standard and custom bindings.</span></span> <span data-ttu-id="2daea-120">각 항목은 고유한 `name`으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-120">Each entry is identified by its unique `name`.</span></span> <span data-ttu-id="2daea-121">서비스에서는 `name`을 통해 바인딩을 연결하여 바인딩을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-121">Services use bindings by linking them using the `name`.</span></span>|  
|[<span data-ttu-id="2daea-122">\<client></span><span class="sxs-lookup"><span data-stu-id="2daea-122">\<client></span></span>](client.md)|<span data-ttu-id="2daea-123">이 섹션에는 클라이언트가 서비스에 연결하는 데 사용하는 엔드포인트의 목록이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-123">This section contains a list of endpoints a client uses to connect to a service.</span></span>|  
|[<span data-ttu-id="2daea-124">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="2daea-124">\<comContracts></span></span>](comcontracts.md)|<span data-ttu-id="2daea-125">이 섹션은 WCF 및 COM interop에 사용하도록 설정된 COM 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-125">This section defines COM contracts enabled for WCF and COM interop.</span></span>|  
|[<span data-ttu-id="2daea-126">\<commonBehaviors></span><span class="sxs-lookup"><span data-stu-id="2daea-126">\<commonBehaviors></span></span>](commonbehaviors.md)|<span data-ttu-id="2daea-127">이 섹션은 machine.config 파일에서만 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-127">This section can only be defined in the machine.config file.</span></span> <span data-ttu-id="2daea-128">이 섹션은 두 자식 컬렉션 `endpointBehaviors` 및 `serviceBehaviors`를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-128">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="2daea-129">각 컬렉션은 컴퓨터의 모든 WCF 끝점과 서비스에서 사용 하는 동작 요소를 각각 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-129">Each collection defines behavior elements consumed by all WCF endpoints and services on the machine respectively.</span></span>  <span data-ttu-id="2daea-130">동작이 및 `<commonBehaviors>` `<behaviors>` 섹션 모두에서 정의 되는 경우 동작 > 섹션의 \<동작이 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-130">If a behavior is defined in both `<commonBehaviors>` and `<behaviors>` sections, the behavior in the \<behaviors> section is given preference.</span></span>|  
|[<span data-ttu-id="2daea-131">\<diagnostics></span><span class="sxs-lookup"><span data-stu-id="2daea-131">\<diagnostics></span></span>](diagnostics.md)|<span data-ttu-id="2daea-132">이 섹션에는 WCF의 진단 기능에 대한 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-132">This section contains settings for the diagnostics features of WCF.</span></span> <span data-ttu-id="2daea-133">사용자는 추적, 성능 카운터 및 WMI 공급자를 사용하거나 사용하지 않도록 설정하고 사용자 지정 메시지 필터를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-133">The user can enable/disable tracing, performance counters, and the WMI provider, and can add custom message filters.</span></span>|  
|[<span data-ttu-id="2daea-134">\<extensions></span><span class="sxs-lookup"><span data-stu-id="2daea-134">\<extensions></span></span>](extensions-section.md)|<span data-ttu-id="2daea-135">이 섹션에는 사용자 정의 바인딩, 동작 및 확장의 기타 측면을 만들 수 있도록 하는 확장명 컬렉션이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-135">This section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>|  
|[<span data-ttu-id="2daea-136">\<protocolMapping></span><span class="sxs-lookup"><span data-stu-id="2daea-136">\<protocolMapping></span></span>](protocolmapping.md)|<span data-ttu-id="2daea-137">이 섹션에서는 전송 프로토콜 체계 (예: http, net.tcp, net.pipe 등)와 WCF 바인딩 간의 기본 프로토콜 매핑 집합을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-137">This section defines a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span>|  
|[<span data-ttu-id="2daea-138">\<routing></span><span class="sxs-lookup"><span data-stu-id="2daea-138">\<routing></span></span>](routing.md)|<span data-ttu-id="2daea-139">이 섹션에서는 들어오는 메시지를 평가할 때 사용할 WCF (Windows Communication Foundation 형식)<xref:System.ServiceModel.Dispatcher.MessageFilter> 와 메시지를 보낼 대상 끝점을 정의 하는 라우팅 테이블을 결정 하는 라우팅 필터 집합을 정의 합니다. 필터 일치.</span><span class="sxs-lookup"><span data-stu-id="2daea-139">This section defines a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
|[<span data-ttu-id="2daea-140">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="2daea-140">\<serviceHostingEnvironment></span></span>](servicehostingenvironment.md)|<span data-ttu-id="2daea-141">이 섹션은 특정 전송을 위해 서비스 호스팅 환경에서 인스턴스화하는 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-141">This section defines what type the service hosting environment instantiates for a particular transport.</span></span> <span data-ttu-id="2daea-142">이 섹션이 비어 있으면 기본 형식이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-142">If this section is empty, the default type is used.</span></span>|  
|[<span data-ttu-id="2daea-143">\<services></span><span class="sxs-lookup"><span data-stu-id="2daea-143">\<services></span></span>](services.md)|<span data-ttu-id="2daea-144">이 섹션에는 서비스의 컬렉션이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-144">The section contains a collection of services.</span></span> <span data-ttu-id="2daea-145">이 요소에는 어셈블리에 정의된 서비스별로 서비스의 설정을 지정하는 `service` 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-145">For each service defined in the assembly, this element contains a `service` element specifying settings for the service.</span></span>|  
|[<span data-ttu-id="2daea-146">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="2daea-146">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="2daea-147">이 섹션은 다시 사용할 수 있는 미리 구성된 엔드포인트인 표준 엔드포인트의 컬렉션을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-147">This section defines a collection of standard endpoints, which are reusable preconfigured endpoints.</span></span> <span data-ttu-id="2daea-148">표준 엔드포인트에는 고정 값으로 설정된 하나 이상의 주소, 바인딩 및 계약 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-148">A standard endpoint will have one or more of the address, binding and contract attributes set to a fixed value.</span></span> <span data-ttu-id="2daea-149">예를 들어 검색 엔드포인트에서는 계약이 고정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-149">For example, in the discovery endpoint the contract is fixed.</span></span> <span data-ttu-id="2daea-150">표준 엔드포인트를 사용자 지정 바인딩 정의와 유사한 새 속성과 함께 사용하여 서비스 엔드포인트를 확장할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-150">You can also use standard endpoints to extend service endpoint with new properties similar to defining custom bindings.</span></span>|
|[<span data-ttu-id="2daea-151">\<tracking></span><span class="sxs-lookup"><span data-stu-id="2daea-151">\<tracking></span></span>](tracking-of-wcf.md)|<span data-ttu-id="2daea-152">이 섹션에서는 워크플로 서비스에 대 한 추적 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-152">This section defines tracking settings for a workflow service.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="2daea-153">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2daea-153">Parent Elements</span></span>  
  
|<span data-ttu-id="2daea-154">요소</span><span class="sxs-lookup"><span data-stu-id="2daea-154">Element</span></span>|<span data-ttu-id="2daea-155">설명</span><span class="sxs-lookup"><span data-stu-id="2daea-155">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2daea-156">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2daea-156">\<configuration></span></span>|<span data-ttu-id="2daea-157">.NET 구성 파일에 있는 모든 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-157">The root element for all configuration elements in a .NET configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2daea-158">설명</span><span class="sxs-lookup"><span data-stu-id="2daea-158">Remarks</span></span>  
 <span data-ttu-id="2daea-159">WCF는 다른 제품의 구성 섹션에 요소를 추가 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-159">WCF does not add elements to the configuration sections of other products.</span></span>  
  
 <span data-ttu-id="2daea-160">WCF 서비스는 구성 파일의 `services` 섹션에 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-160">WCF services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="2daea-161">어셈블리에는 여러 개의 서비스가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-161">An assembly can contain any number of services.</span></span> <span data-ttu-id="2daea-162">서비스별로 해당 `service` 구성 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-162">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="2daea-163">해당 단원 및 내용에서는 특정 서비스의 서비스 계약, 동작 및 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-163">The section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="2daea-164">서비스의 `name` 특성만 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-164">Only a service's `name` attribute is required.</span></span>  <span data-ttu-id="2daea-165">기본적으로 서비스 이름은 서비스를 구현하는 데 사용되는 기본 CLR 형식을 설명하지만 <xref:System.ServiceModel.ServiceContractAttribute>에서 ConfigurationName 속성을 변경하여 CLR 형식 요구 사항을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-165">By default, a service's name describes the underlying CLR type used to implement a service; however, you may change the ConfigurationName property on a <xref:System.ServiceModel.ServiceContractAttribute> to override the CLR type requirement.</span></span>  
  
 <span data-ttu-id="2daea-166">`behaviorConfiguration` 특성은 선택 사항이며</span><span class="sxs-lookup"><span data-stu-id="2daea-166">The `behaviorConfiguration` attribute is optional.</span></span> <span data-ttu-id="2daea-167">이 특성은 서비스에 사용되는 서비스 동작을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-167">It identifies the service behavior used by a service.</span></span> <span data-ttu-id="2daea-168">이 특성에 지정된 동작은 동일한 파일이나 부모 파일과 같은 동일한 구성 파일의 범위에 정의된 서비스 동작에 연결되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-168">The behavior specified by this attribute must link to a service behavior defined in the scope of the same configuration file (i.e. the same file or a parent file).</span></span>  
  
 <span data-ttu-id="2daea-169">각 서비스는 `endpoint` 요소에 정의된 하나 이상의 엔드포인트를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-169">Each service exposes one or more endpoints defined in an `endpoint` element.</span></span> <span data-ttu-id="2daea-170">각 엔드포인트에는 고유한 주소와 바인딩이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-170">Each endpoint has its own address and binding.</span></span> <span data-ttu-id="2daea-171">구성 파일 내에서 사용되는 모든 바인딩은 파일 범위 내에서 정의되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-171">All bindings used within the configuration file must be defined in the scope of the file.</span></span>  
  
 <span data-ttu-id="2daea-172">바인딩은 `name` 및 `bindingConfiguration` 특성을 조합하여 엔드포인트에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-172">Bindings are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="2daea-173">`binding` 특성은 바인딩이 정의된 섹션을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-173">The `binding` attribute defines in which section the binding is defined.</span></span> <span data-ttu-id="2daea-174">`bindingConfiguration` 특성은 바인딩 섹션에서 사용되는 구성된 바인딩을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-174">The `bindingConfiguration` attribute defines which configured binding within the binding section is used.</span></span> <span data-ttu-id="2daea-175">바인딩 섹션에서는 여러 개의 구성된 바인딩을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-175">A binding section can define several configured bindings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2daea-176">예제</span><span class="sxs-lookup"><span data-stu-id="2daea-176">Example</span></span>  
 <span data-ttu-id="2daea-177">다음은 WCF 구성 파일의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="2daea-177">This is an example of a WCF configuration file.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <behaviors>
      <!-- List of Behaviors -->
    </behaviors>
    <client>
      <!-- List of Endpoints -->
    </client>
    <diagnostics wmiProviderEnabled="false"
                 performanceCountersEnabled="false"
                 tracingEnabled="false">
    </diagnostics>
    <serviceHostingEnvironment>
      <!-- List of entries -->
    </serviceHostingEnvironment>
    <comContracts>
      <!-- List of COM+ Contracts -->
    </comContracts>
    <services>
      <!-- List of Services -->
    </services>
    <bindings>
      <!-- List of Bindings -->
    </bindings>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="2daea-178">참고자료</span><span class="sxs-lookup"><span data-stu-id="2daea-178">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceModelSectionGroup>
