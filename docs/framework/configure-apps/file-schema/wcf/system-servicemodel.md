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
ms.openlocfilehash: c176f7f470cc65bb135e5f92935102e09c7e8485
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59209829"
---
# <a name="systemservicemodel"></a><span data-ttu-id="2d63c-102">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2d63c-102">\<system.serviceModel></span></span>
<span data-ttu-id="2d63c-103">이 구성 섹션에는 모든 Windows Communication Foundation (WCF) ServiceModel 구성 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-103">This configuration section contains all the Windows Communication Foundation (WCF) ServiceModel configuration elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d63c-104">구문</span><span class="sxs-lookup"><span data-stu-id="2d63c-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2d63c-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2d63c-105">Attributes and Elements</span></span>  
 <span data-ttu-id="2d63c-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2d63c-107">특성</span><span class="sxs-lookup"><span data-stu-id="2d63c-107">Attributes</span></span>  
 <span data-ttu-id="2d63c-108">없음</span><span class="sxs-lookup"><span data-stu-id="2d63c-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2d63c-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2d63c-109">Child Elements</span></span>  
  
|<span data-ttu-id="2d63c-110">요소</span><span class="sxs-lookup"><span data-stu-id="2d63c-110">Element</span></span>|<span data-ttu-id="2d63c-111">설명</span><span class="sxs-lookup"><span data-stu-id="2d63c-111">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2d63c-112">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="2d63c-112">\<behaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)|<span data-ttu-id="2d63c-113">이 섹션은 두 자식 컬렉션 `endpointBehaviors` 및 `serviceBehaviors`를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-113">This section defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="2d63c-114">각 컬렉션은 엔드포인트 및 서비스가 사용하는 동작 요소를 각각 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-114">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="2d63c-115">각 동작 요소는 고유한 `name` 특성으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-115">Each behavior element is identified by its unique `name` attribute.</span></span>|  
|[<span data-ttu-id="2d63c-116">\<bindings></span><span class="sxs-lookup"><span data-stu-id="2d63c-116">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="2d63c-117">이 섹션에는 표준 및 사용자 지정 바인딩 컬렉션이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-117">This section holds a collection of standard and custom bindings.</span></span> <span data-ttu-id="2d63c-118">각 항목은 고유한 `name`으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-118">Each entry is identified by its unique `name`.</span></span> <span data-ttu-id="2d63c-119">서비스에서는 `name`을 통해 바인딩을 연결하여 바인딩을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-119">Services use bindings by linking them using the `name`.</span></span>|  
|[<span data-ttu-id="2d63c-120">\<client></span><span class="sxs-lookup"><span data-stu-id="2d63c-120">\<client></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/client.md)|<span data-ttu-id="2d63c-121">이 섹션에는 클라이언트가 서비스에 연결하는 데 사용하는 엔드포인트의 목록이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-121">This section contains a list of endpoints a client uses to connect to a service.</span></span>|  
|[<span data-ttu-id="2d63c-122">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="2d63c-122">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)|<span data-ttu-id="2d63c-123">이 섹션은 WCF 및 COM interop에 사용하도록 설정된 COM 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-123">This section defines COM contracts enabled for WCF and COM interop.</span></span>|  
|[<span data-ttu-id="2d63c-124">\<commonBehaviors></span><span class="sxs-lookup"><span data-stu-id="2d63c-124">\<commonBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md)|<span data-ttu-id="2d63c-125">이 섹션은 machine.config 파일에서만 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-125">This section can only be defined in the machine.config file.</span></span> <span data-ttu-id="2d63c-126">이 섹션은 두 자식 컬렉션 `endpointBehaviors` 및 `serviceBehaviors`를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-126">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="2d63c-127">각 컬렉션은 각각 모든 WCF 끝점 및 서비스가 컴퓨터에서 사용 하는 동작 요소를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-127">Each collection defines behavior elements consumed by all WCF endpoints and services on the machine respectively.</span></span>  <span data-ttu-id="2d63c-128">동작을 둘 다에 정의 된 경우 `<commonBehaviors>` 하 고 `<behaviors>` 섹션의 동작이 \<동작 > 섹션 우선 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-128">If a behavior is defined in both `<commonBehaviors>` and `<behaviors>` sections, the behavior in the \<behaviors> section is given preference.</span></span>|  
|[<span data-ttu-id="2d63c-129">\<diagnostics></span><span class="sxs-lookup"><span data-stu-id="2d63c-129">\<diagnostics></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|<span data-ttu-id="2d63c-130">이 섹션에는 WCF의 진단 기능에 대한 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-130">This section contains settings for the diagnostics features of WCF.</span></span> <span data-ttu-id="2d63c-131">사용자는 추적, 성능 카운터 및 WMI 공급자를 사용하거나 사용하지 않도록 설정하고 사용자 지정 메시지 필터를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-131">The user can enable/disable tracing, performance counters, and the WMI provider, and can add custom message filters.</span></span>|  
|[<span data-ttu-id="2d63c-132">\<extensions></span><span class="sxs-lookup"><span data-stu-id="2d63c-132">\<extensions></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions-section.md)|<span data-ttu-id="2d63c-133">이 섹션에는 사용자 정의 바인딩, 동작 및 확장의 기타 측면을 만들 수 있도록 하는 확장명 컬렉션이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-133">This section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>|  
|[<span data-ttu-id="2d63c-134">\<protocolMapping></span><span class="sxs-lookup"><span data-stu-id="2d63c-134">\<protocolMapping></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/protocolmapping.md)|<span data-ttu-id="2d63c-135">이 섹션에는 전송 프로토콜 체계 (예: http, net.tcp, net.pipe 등) 및 WCF 바인딩 간의 기본 프로토콜 매핑 집합을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-135">This section defines a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span>|  
|[<span data-ttu-id="2d63c-136">\<routing></span><span class="sxs-lookup"><span data-stu-id="2d63c-136">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="2d63c-137">이 섹션에서는 Windows Communication Foundation (WCF)의 형식을 결정 하는 라우팅 필터 집합을 정의<xref:System.ServiceModel.Dispatcher.MessageFilter> 사용할 라우팅 뿐만 아니라 들어오는 메시지를 평가할 때 메시지를 보낼 대상 끝점을 정의 하는 테이블을 필터와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-137">This section defines a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
|[<span data-ttu-id="2d63c-138">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="2d63c-138">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="2d63c-139">이 섹션은 특정 전송을 위해 서비스 호스팅 환경에서 인스턴스화하는 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-139">This section defines what type the service hosting environment instantiates for a particular transport.</span></span> <span data-ttu-id="2d63c-140">이 섹션이 비어 있으면 기본 형식이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-140">If this section is empty, the default type is used.</span></span>|  
|[<span data-ttu-id="2d63c-141">\<services></span><span class="sxs-lookup"><span data-stu-id="2d63c-141">\<services></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)|<span data-ttu-id="2d63c-142">이 섹션에는 서비스의 컬렉션이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-142">The section contains a collection of services.</span></span> <span data-ttu-id="2d63c-143">이 요소에는 어셈블리에 정의된 서비스별로 서비스의 설정을 지정하는 `service` 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-143">For each service defined in the assembly, this element contains a `service` element specifying settings for the service.</span></span>|  
|[<span data-ttu-id="2d63c-144">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="2d63c-144">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="2d63c-145">이 섹션은 다시 사용할 수 있는 미리 구성된 엔드포인트인 표준 엔드포인트의 컬렉션을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-145">This section defines a collection of standard endpoints, which are reusable preconfigured endpoints.</span></span> <span data-ttu-id="2d63c-146">표준 엔드포인트에는 고정 값으로 설정된 하나 이상의 주소, 바인딩 및 계약 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-146">A standard endpoint will have one or more of the address, binding and contract attributes set to a fixed value.</span></span> <span data-ttu-id="2d63c-147">예를 들어 검색 엔드포인트에서는 계약이 고정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-147">For example, in the discovery endpoint the contract is fixed.</span></span> <span data-ttu-id="2d63c-148">표준 엔드포인트를 사용자 지정 바인딩 정의와 유사한 새 속성과 함께 사용하여 서비스 엔드포인트를 확장할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-148">You can also use standard endpoints to extend service endpoint with new properties similar to defining custom bindings.</span></span>|
|[<span data-ttu-id="2d63c-149">\<tracking></span><span class="sxs-lookup"><span data-stu-id="2d63c-149">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tracking-of-wcf.md)|<span data-ttu-id="2d63c-150">이 섹션에서는 워크플로 서비스에 대 한 추적 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-150">This section defines tracking settings for a workflow service.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="2d63c-151">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2d63c-151">Parent Elements</span></span>  
  
|<span data-ttu-id="2d63c-152">요소</span><span class="sxs-lookup"><span data-stu-id="2d63c-152">Element</span></span>|<span data-ttu-id="2d63c-153">설명</span><span class="sxs-lookup"><span data-stu-id="2d63c-153">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2d63c-154">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2d63c-154">\<configuration></span></span>|<span data-ttu-id="2d63c-155">.NET 구성 파일에 있는 모든 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-155">The root element for all configuration elements in a .NET configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d63c-156">설명</span><span class="sxs-lookup"><span data-stu-id="2d63c-156">Remarks</span></span>  
 <span data-ttu-id="2d63c-157">WCF는 다른 제품의 구성 섹션에 요소를 추가 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-157">WCF does not add elements to the configuration sections of other products.</span></span>  
  
 <span data-ttu-id="2d63c-158">에 정의 된 WCF 서비스는 `services` 구성 파일의 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-158">WCF services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="2d63c-159">어셈블리에는 여러 개의 서비스가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-159">An assembly can contain any number of services.</span></span> <span data-ttu-id="2d63c-160">서비스별로 해당 `service` 구성 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-160">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="2d63c-161">해당 단원 및 내용에서는 특정 서비스의 서비스 계약, 동작 및 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-161">The section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="2d63c-162">서비스의 `name` 특성만 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-162">Only a service's `name` attribute is required.</span></span>  <span data-ttu-id="2d63c-163">기본적으로 서비스 이름은 서비스를 구현하는 데 사용되는 기본 CLR 형식을 설명하지만 <xref:System.ServiceModel.ServiceContractAttribute>에서 ConfigurationName 속성을 변경하여 CLR 형식 요구 사항을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-163">By default, a service's name describes the underlying CLR type used to implement a service; however, you may change the ConfigurationName property on a <xref:System.ServiceModel.ServiceContractAttribute> to override the CLR type requirement.</span></span>  
  
 <span data-ttu-id="2d63c-164">`behaviorConfiguration` 특성은 선택 사항이며</span><span class="sxs-lookup"><span data-stu-id="2d63c-164">The `behaviorConfiguration` attribute is optional.</span></span> <span data-ttu-id="2d63c-165">이 특성은 서비스에 사용되는 서비스 동작을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-165">It identifies the service behavior used by a service.</span></span> <span data-ttu-id="2d63c-166">이 특성에 지정된 동작은 동일한 파일이나 부모 파일과 같은 동일한 구성 파일의 범위에 정의된 서비스 동작에 연결되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-166">The behavior specified by this attribute must link to a service behavior defined in the scope of the same configuration file (i.e. the same file or a parent file).</span></span>  
  
 <span data-ttu-id="2d63c-167">각 서비스는 `endpoint` 요소에 정의된 하나 이상의 엔드포인트를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-167">Each service exposes one or more endpoints defined in an `endpoint` element.</span></span> <span data-ttu-id="2d63c-168">각 엔드포인트에는 고유한 주소와 바인딩이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-168">Each endpoint has its own address and binding.</span></span> <span data-ttu-id="2d63c-169">구성 파일 내에서 사용되는 모든 바인딩은 파일 범위 내에서 정의되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-169">All bindings used within the configuration file must be defined in the scope of the file.</span></span>  
  
 <span data-ttu-id="2d63c-170">바인딩은 `name` 및 `bindingConfiguration` 특성을 조합하여 엔드포인트에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-170">Bindings are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="2d63c-171">`binding` 특성은 바인딩이 정의된 섹션을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-171">The `binding` attribute defines in which section the binding is defined.</span></span> <span data-ttu-id="2d63c-172">`bindingConfiguration` 특성은 바인딩 섹션에서 사용되는 구성된 바인딩을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-172">The `bindingConfiguration` attribute defines which configured binding within the binding section is used.</span></span> <span data-ttu-id="2d63c-173">바인딩 섹션에서는 여러 개의 구성된 바인딩을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-173">A binding section can define several configured bindings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d63c-174">예제</span><span class="sxs-lookup"><span data-stu-id="2d63c-174">Example</span></span>  
 <span data-ttu-id="2d63c-175">다음은 WCF 구성 파일의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="2d63c-175">This is an example of a WCF configuration file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2d63c-176">참고자료</span><span class="sxs-lookup"><span data-stu-id="2d63c-176">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceModelSectionGroup>
