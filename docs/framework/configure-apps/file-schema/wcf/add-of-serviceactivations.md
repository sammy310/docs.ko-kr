---
title: <serviceActivations>의 <add>
ms.date: 03/30/2017
ms.assetid: e5b01fc8-ee84-48b7-95fd-95ab54fa871f
ms.openlocfilehash: 929773fcb6b6a3ee5c75aa970147277d9dbe7b45
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920020"
---
# <a name="add-of-serviceactivations"></a><span data-ttu-id="01cb5-102">\<\<serviceactivations > > 추가</span><span class="sxs-lookup"><span data-stu-id="01cb5-102">\<add> of \<serviceActivations></span></span>

<span data-ttu-id="01cb5-103">WCF (Windows Communication Foundation) 서비스 형식에 매핑되는 가상 서비스 활성화 설정을 정의할 수 있는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="01cb5-103">A configuration element that allows you to define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="01cb5-104">.svc 파일 없이도 WAS/IIS에서 호스트되는 서비스를 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01cb5-104">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>

<span data-ttu-id="01cb5-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="01cb5-105">\<system.ServiceModel></span></span>\
<span data-ttu-id="01cb5-106">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="01cb5-106">\<serviceHostingEnvironment></span></span>

## <a name="syntax"></a><span data-ttu-id="01cb5-107">구문</span><span class="sxs-lookup"><span data-stu-id="01cb5-107">Syntax</span></span>

```xml
<serviceHostingEnvironment>
    <serviceActivations>
      <add factory="String"
           service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="01cb5-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="01cb5-108">Attributes and Elements</span></span>

<span data-ttu-id="01cb5-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="01cb5-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="01cb5-110">특성</span><span class="sxs-lookup"><span data-stu-id="01cb5-110">Attributes</span></span>

|<span data-ttu-id="01cb5-111">특성</span><span class="sxs-lookup"><span data-stu-id="01cb5-111">Attribute</span></span>|<span data-ttu-id="01cb5-112">Description</span><span class="sxs-lookup"><span data-stu-id="01cb5-112">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="01cb5-113">factory</span><span class="sxs-lookup"><span data-stu-id="01cb5-113">factory</span></span>|<span data-ttu-id="01cb5-114">서비스 활성화 요소를 생성하는 팩터리의 CLR 형식 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="01cb5-114">A string that specifies the CLR type name of the factory that generates a service activation element.</span></span>|
|<span data-ttu-id="01cb5-115">서비스</span><span class="sxs-lookup"><span data-stu-id="01cb5-115">service</span></span>|<span data-ttu-id="01cb5-116">서비스를 구현하는 ServiceType입니다(App_Code 폴더에 있는 경우 정규화된 Typename 또는 짧은 Typename).</span><span class="sxs-lookup"><span data-stu-id="01cb5-116">The ServiceType that implements the service (either the full qualified Typename or the short Typename (when it is placed in the App_Code folder).</span></span>|
|<span data-ttu-id="01cb5-117">relativeAddress</span><span class="sxs-lookup"><span data-stu-id="01cb5-117">relativeAddress</span></span>|<span data-ttu-id="01cb5-118">현재 IIS 애플리케이션 내에서의 상대 주소입니다(예: &quot;Service.svc&quot;).</span><span class="sxs-lookup"><span data-stu-id="01cb5-118">The relative address within the current IIS application - for example "Service.svc".</span></span> <span data-ttu-id="01cb5-119">WCF 4.0에서는 이 상대 주소에 알려진 파일 확장명(.svc, .xamlx, ...) 중 하나가 포함되어야 합니다. relativeUrl에 대한 물리적 파일이 존재할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="01cb5-119">In WCF 4.0 this relative address has to contain one of the known file extensions (.svc, .xamlx, ...). No physical file has to exist for the relativeUrl</span></span>|

### <a name="child-elements"></a><span data-ttu-id="01cb5-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="01cb5-120">Child Elements</span></span>

<span data-ttu-id="01cb5-121">없음</span><span class="sxs-lookup"><span data-stu-id="01cb5-121">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="01cb5-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="01cb5-122">Parent Elements</span></span>

|<span data-ttu-id="01cb5-123">요소</span><span class="sxs-lookup"><span data-stu-id="01cb5-123">Element</span></span>|<span data-ttu-id="01cb5-124">설명</span><span class="sxs-lookup"><span data-stu-id="01cb5-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="01cb5-125">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="01cb5-125">\<serviceHostingEnvironment></span></span>](servicehostingenvironment.md)|<span data-ttu-id="01cb5-126">활성화 설정을 설명하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="01cb5-126">A configuration section that describes activation settings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="01cb5-127">설명</span><span class="sxs-lookup"><span data-stu-id="01cb5-127">Remarks</span></span>

<span data-ttu-id="01cb5-128">다음 예제에서는 web.config 파일 내에서 활성화 설정을 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="01cb5-128">The following example shows how to configure activation settings within your web.config file.</span></span>

```xml
<configuration>
  <system.serviceModel>
    <serviceHostingEnvironment>
      <serviceActivations>
        <add service="GreetingService" />
      </serviceActivations>
    </serviceHostingEnvironment>
  </system.serviceModel>
</configuration>
```

<span data-ttu-id="01cb5-129">이 구성을 사용하여 .svc 파일을 사용하지 않고도 GreetingService를 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01cb5-129">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>

<span data-ttu-id="01cb5-130">`<serviceHostingEnvironment>`는 애플리케이션 수준 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="01cb5-130">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="01cb5-131">구성을 포함하는 `web.config`를 가상 애플리케이션의 루트 아래에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01cb5-131">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="01cb5-132">또한 `serviceHostingEnvironment` 는 machineToApplication 된 상속 가능 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="01cb5-132">In addition, `serviceHostingEnvironment` is a machineToApplication inheritable section.</span></span> <span data-ttu-id="01cb5-133">컴퓨터의 루트에 단일 서비스를 등록하는 경우 애플리케이션의 모든 서비스가 이 서비스를 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="01cb5-133">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>

<span data-ttu-id="01cb5-134">구성 기반 활성화는 http 및 http가 아닌 프로토콜을 통한 활성화를 모두 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="01cb5-134">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="01cb5-135">이 클래스에는 relativeAddress,. .svc 또는. .xamlx의 확장이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="01cb5-135">It requires extensions in the relativeAddress, i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="01cb5-136">직접 작성한 확장을 알려진 buildProviders에 매핑할 수 있으며, 이렇게 하면 모든 확장에서 서비스를 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01cb5-136">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="01cb5-137">충돌이 발생하면 `<serviceActivations>` 섹션이 .svc 등록을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="01cb5-137">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>

## <a name="see-also"></a><span data-ttu-id="01cb5-138">참고자료</span><span class="sxs-lookup"><span data-stu-id="01cb5-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceActivationElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
