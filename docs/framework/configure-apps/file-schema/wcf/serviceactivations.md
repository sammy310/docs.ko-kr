---
title: <serviceActivations>
ms.date: 03/30/2017
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
ms.openlocfilehash: fb7c699612ef12aae39aaeadaf170d0e8f2553cd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936437"
---
# <a name="serviceactivations"></a><span data-ttu-id="d6e12-101">\<serviceActivations></span><span class="sxs-lookup"><span data-stu-id="d6e12-101">\<serviceActivations></span></span>

<span data-ttu-id="d6e12-102">WCF (Windows Communication Foundation) 서비스 형식에 매핑되는 가상 서비스 활성화 설정을 정의 하는 설정을 추가할 수 있는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e12-102">A configuration element that allows you to add settings that define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="d6e12-103">.svc 파일 없이도 WAS/IIS에서 호스트되는 서비스를 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e12-103">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>

<span data-ttu-id="d6e12-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d6e12-104">\<system.ServiceModel></span></span>\
<span data-ttu-id="d6e12-105">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="d6e12-105">\<serviceHostingEnvironment></span></span>\
<span data-ttu-id="d6e12-106">\<serviceActivations></span><span class="sxs-lookup"><span data-stu-id="d6e12-106">\<serviceActivations></span></span>

## <a name="syntax"></a><span data-ttu-id="d6e12-107">구문</span><span class="sxs-lookup"><span data-stu-id="d6e12-107">Syntax</span></span>

```xml
<serviceHostingEnvironment>
  <serviceActivations>
    <add factory="String"
         service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d6e12-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d6e12-108">Attributes and Elements</span></span>

<span data-ttu-id="d6e12-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e12-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="d6e12-110">특성</span><span class="sxs-lookup"><span data-stu-id="d6e12-110">Attributes</span></span>

<span data-ttu-id="d6e12-111">없음</span><span class="sxs-lookup"><span data-stu-id="d6e12-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d6e12-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d6e12-112">Child Elements</span></span>

|<span data-ttu-id="d6e12-113">요소</span><span class="sxs-lookup"><span data-stu-id="d6e12-113">Element</span></span>|<span data-ttu-id="d6e12-114">설명</span><span class="sxs-lookup"><span data-stu-id="d6e12-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d6e12-115">\<add></span><span class="sxs-lookup"><span data-stu-id="d6e12-115">\<add></span></span>](add-of-serviceactivations.md)|<span data-ttu-id="d6e12-116">서비스 애플리케이션의 활성화를 지정하는 구성 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e12-116">Adds a configuration element that specifies the activation of a service application.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d6e12-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d6e12-117">Parent Elements</span></span>

|<span data-ttu-id="d6e12-118">요소</span><span class="sxs-lookup"><span data-stu-id="d6e12-118">Element</span></span>|<span data-ttu-id="d6e12-119">설명</span><span class="sxs-lookup"><span data-stu-id="d6e12-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d6e12-120">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="d6e12-120">\<serviceHostingEnvironment></span></span>](servicehostingenvironment.md)|<span data-ttu-id="d6e12-121">특정 전송을 위해 서비스 호스팅 환경에서 인스턴스화하는 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e12-121">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d6e12-122">설명</span><span class="sxs-lookup"><span data-stu-id="d6e12-122">Remarks</span></span>

<span data-ttu-id="d6e12-123">다음 예제에서는 web.config 파일 내에서 활성화 설정을 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d6e12-123">The following example shows how to configure activation settings within your web.config file.</span></span>

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

<span data-ttu-id="d6e12-124">이 구성을 사용하여 .svc 파일을 사용하지 않고도 GreetingService를 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e12-124">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>

<span data-ttu-id="d6e12-125">`<serviceHostingEnvironment>`는 애플리케이션 수준 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e12-125">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="d6e12-126">구성을 포함하는 `web.config`를 가상 애플리케이션의 루트 아래에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e12-126">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="d6e12-127">또한 `serviceHostingEnvironment` 는 machineToApplication 된 상속 가능 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e12-127">In addition, `serviceHostingEnvironment` is a machineToApplication inheritable section.</span></span> <span data-ttu-id="d6e12-128">컴퓨터의 루트에 단일 서비스를 등록하는 경우 애플리케이션의 모든 서비스가 이 서비스를 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e12-128">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>

<span data-ttu-id="d6e12-129">구성 기반 활성화는 http 및 http가 아닌 프로토콜을 통한 활성화를 모두 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e12-129">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="d6e12-130">이 클래스에는 relativeAddress, xoml 또는. .xamlx의 확장이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e12-130">It requires extensions in the relativeAddress i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="d6e12-131">직접 작성한 확장을 알려진 buildProviders에 매핑할 수 있으며, 이렇게 하면 모든 확장에서 서비스를 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e12-131">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="d6e12-132">충돌이 발생하면 `<serviceActivations>` 섹션이 .svc 등록을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e12-132">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>

## <a name="see-also"></a><span data-ttu-id="d6e12-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="d6e12-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
