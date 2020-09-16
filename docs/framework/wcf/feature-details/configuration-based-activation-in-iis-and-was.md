---
title: IIS 및 WAS에서 구성 기반 활성화
ms.date: 03/30/2017
ms.assetid: 6a927e1f-b905-4ee5-ad0f-78265da38238
ms.openlocfilehash: f947a64acdf602d12fcd2319a1b994912ecb331e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556631"
---
# <a name="configuration-based-activation-in-iis-and-was"></a><span data-ttu-id="b8a3c-102">IIS 및 WAS에서 구성 기반 활성화</span><span class="sxs-lookup"><span data-stu-id="b8a3c-102">Configuration-Based Activation in IIS and WAS</span></span>

<span data-ttu-id="b8a3c-103">일반적으로 인터넷 정보 서비스 (IIS) 또는 WAS (Windows Process Activation Service)에서 WCF (Windows Communication Foundation) 서비스를 호스팅하는 경우 .svc 파일을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a3c-103">Normally when hosting a Windows Communication Foundation (WCF) service under Internet Information Services (IIS) or Windows Process Activation Service (WAS), you must provide a .svc file.</span></span> <span data-ttu-id="b8a3c-104">.svc 파일에는 서비스 이름과 선택적 사용자 지정 서비스 호스트 팩터리가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8a3c-104">The .svc file contains the name of the service and an optional custom service host factory.</span></span> <span data-ttu-id="b8a3c-105">이 추가 파일을 사용하면 관리 효율성이 떨어지지만</span><span class="sxs-lookup"><span data-stu-id="b8a3c-105">This additional file adds manageability overhead.</span></span> <span data-ttu-id="b8a3c-106">구성 기반 활성화 기능을 사용하면 .svc 파일이 필요 없기 때문에 이로 인한 관리 효율성 저하도 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8a3c-106">The configuration-based activation feature removes the requirement to have a .svc file and therefore the associated overhead.</span></span>

## <a name="configuration-based-activation"></a><span data-ttu-id="b8a3c-107">구성 기반 활성화</span><span class="sxs-lookup"><span data-stu-id="b8a3c-107">Configuration-Based Activation</span></span>

<span data-ttu-id="b8a3c-108">구성 기반 활성화는 이전에 .svc 파일에 있던 메타데이터를 가져와서 Web.config 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a3c-108">Configuration-based activation takes the metadata that used to be placed in the .svc file and places it in the Web.config file.</span></span> <span data-ttu-id="b8a3c-109"><`serviceHostingEnvironment`> 요소 내에는 <`serviceActivations`> 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8a3c-109">Within the<`serviceHostingEnvironment`> element there is a <`serviceActivations`> element.</span></span> <span data-ttu-id="b8a3c-110"><`serviceActivations`> 요소 내에는 `add` 호스팅된 각 서비스에 대 한 하나 이상의 <> 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8a3c-110">Within the <`serviceActivations`> element are one or more <`add`> elements, one for each hosted service.</span></span> <span data-ttu-id="b8a3c-111"><> 요소에는 서비스 `add` 의 상대 주소와 서비스 유형 또는 서비스 호스트 팩터리를 설정 하는 데 사용할 수 있는 특성이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8a3c-111">The <`add`> element contains attributes that let you set the relative address for the service and the service type or a service host factory.</span></span> <span data-ttu-id="b8a3c-112">다음 구성 예제 코드에서는 이 섹션을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8a3c-112">The following configuration example code shows how this section is used.</span></span>

> [!NOTE]
> <span data-ttu-id="b8a3c-113">각 <`add`> 요소는 서비스 또는 팩터리 특성을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a3c-113">Each <`add`> element must specify a service or a factory attribute.</span></span> <span data-ttu-id="b8a3c-114">서비스 특성과 팩터리 특성을 모두 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8a3c-114">Specifying both service and factory attributes is allowed.</span></span>

```xml
<serviceHostingEnvironment>
  <serviceActivations>
    <add relativeAddress="MyServiceAddress" service="Service" factory="MyServiceHostFactory"/>
  </serviceActivations>
</serviceHostingEnvironment>
```

 <span data-ttu-id="b8a3c-115">Web.config 파일에 이 섹션이 있으면 애플리케이션의 App_Code 디렉터리에 서비스 소스 코드를 저장하거나 애플리케이션의 Bin 디렉터리에 컴파일된 어셈블리를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8a3c-115">With this in the Web.config file, you can place the service source code in the App_Code directory of the application or a complied assembly in the Bin directory of the application.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="b8a3c-116">구성 기반 활성화를 사용하는 경우 .svc 파일의 인라인 코드는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8a3c-116">When using configuration-based activation, inline code in .svc files is not supported.</span></span>
> - <span data-ttu-id="b8a3c-117">특성은 "/cistststs `relativeAddress` \<sub-directory> " 또는 "~/ \< sub-directory/service .svc"와 같은 상대 주소로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a3c-117">The `relativeAddress` attribute must be set to a relative address such as "\<sub-directory>/service.svc" or "~/\<sub-directory/service.svc".</span></span>
> - <span data-ttu-id="b8a3c-118">WCF와 연결된 알려진 확장명이 없는 상대 주소를 등록하면 구성 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8a3c-118">A configuration exception is thrown if you register a relative address that does not have a known extension associated with WCF.</span></span>
> - <span data-ttu-id="b8a3c-119">지정된 상대 주소는 가상 애플리케이션의 루트를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a3c-119">The relative address specified is relative to the root of the virtual application.</span></span>
> - <span data-ttu-id="b8a3c-120">구성의 계층적 모델로 인해 가상 애플리케이션은 컴퓨터 또는 사이트 수준에서 등록된 상대 주소를 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a3c-120">Due to the hierarchical model of configuration, the registered relative addresses at machine and site level are inherited by virtual applications.</span></span>
> - <span data-ttu-id="b8a3c-121">구성 파일의 등록이 .svc, .xamlx, .xoml 또는 기타 파일의 설정보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a3c-121">Registrations in a configuration file take precedence over settings in a .svc, .xamlx, .xoml, or other file.</span></span>
> - <span data-ttu-id="b8a3c-122">IIS/WAS에 보내진 URI의 ‘\’(백슬래시)는 자동으로 ‘/’(슬래시)로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8a3c-122">Any ‘\’ (backslashes) in a URI sent to IIS/WAS are automatically converted to a ‘/’ (forward slash).</span></span> <span data-ttu-id="b8a3c-123">‘\’가 포함된 상대 주소가 추가된 경우 IIS에 이 상대 주소를 사용하는 URI를 보내면 백슬래시가 슬래시로 변환되기 때문에 IIS가 이 URI를 상대 주소와 일치시킬 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8a3c-123">If a relative address is added that contains a ‘\’ and you send IIS a URI that uses the relative address, the backslash is converted to a forward slash and IIS cannot match it to the relative address.</span></span> <span data-ttu-id="b8a3c-124">따라서 IIS가 일치하는 항목을 찾을 수 없음을 나타내는 추적 정보를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b8a3c-124">IIS sends out trace information that indicates that there are no matches found.</span></span>

## <a name="see-also"></a><span data-ttu-id="b8a3c-125">참조</span><span class="sxs-lookup"><span data-stu-id="b8a3c-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection.ServiceActivations%2A>
- [<span data-ttu-id="b8a3c-126">서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="b8a3c-126">Hosting Services</span></span>](../hosting-services.md)
- [<span data-ttu-id="b8a3c-127">워크플로 서비스 호스팅 개요</span><span class="sxs-lookup"><span data-stu-id="b8a3c-127">Hosting Workflow Services Overview</span></span>](hosting-workflow-services-overview.md)
- [\<serviceHostingEnvironment>](../../configure-apps/file-schema/wcf/servicehostingenvironment.md)
- <span data-ttu-id="b8a3c-128">[Windows Server App Fabric 호스팅 기능](/previous-versions/appfabric/ee677189(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="b8a3c-128">[Windows Server App Fabric Hosting Features](/previous-versions/appfabric/ee677189(v=azure.10))</span></span>
