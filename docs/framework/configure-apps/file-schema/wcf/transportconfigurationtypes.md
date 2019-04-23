---
title: <transportConfigurationTypes>
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: b3683a198ec403fb9966bb902c936108fd043bfa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083649"
---
# <a name="transportconfigurationtypes"></a><span data-ttu-id="94a0b-101">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="94a0b-101">\<transportConfigurationTypes></span></span>
<span data-ttu-id="94a0b-102">특정 전송의 형식을 식별하는 구성 요소 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="94a0b-102">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="94a0b-103">사용자 지정 WAS 프로토콜을 추가하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94a0b-103">This can be used to add custom WAS protocols.</span></span>  
  
 <span data-ttu-id="94a0b-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="94a0b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="94a0b-105">\<ServiceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="94a0b-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="94a0b-106">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="94a0b-106">\<transportConfigurationTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94a0b-107">구문</span><span class="sxs-lookup"><span data-stu-id="94a0b-107">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="94a0b-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="94a0b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="94a0b-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="94a0b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="94a0b-110">특성</span><span class="sxs-lookup"><span data-stu-id="94a0b-110">Attributes</span></span>  
  
|<span data-ttu-id="94a0b-111">특성</span><span class="sxs-lookup"><span data-stu-id="94a0b-111">Attribute</span></span>|<span data-ttu-id="94a0b-112">설명</span><span class="sxs-lookup"><span data-stu-id="94a0b-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="94a0b-113">name</span><span class="sxs-lookup"><span data-stu-id="94a0b-113">name</span></span>|<span data-ttu-id="94a0b-114">전송의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="94a0b-114">The name of the transport</span></span>|  
|<span data-ttu-id="94a0b-115">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="94a0b-115">transportConfigurationType</span></span>|<span data-ttu-id="94a0b-116">전송을 구현하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="94a0b-116">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="94a0b-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="94a0b-117">Child Elements</span></span>  
  
|<span data-ttu-id="94a0b-118">요소</span><span class="sxs-lookup"><span data-stu-id="94a0b-118">Element</span></span>|<span data-ttu-id="94a0b-119">설명</span><span class="sxs-lookup"><span data-stu-id="94a0b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="94a0b-120">\<add></span><span class="sxs-lookup"><span data-stu-id="94a0b-120">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-transportconfigurationtype.md)|<span data-ttu-id="94a0b-121">특정 전송의 형식을 식별하는 구성 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="94a0b-121">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="94a0b-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="94a0b-122">Parent Elements</span></span>  
  
|<span data-ttu-id="94a0b-123">요소</span><span class="sxs-lookup"><span data-stu-id="94a0b-123">Element</span></span>|<span data-ttu-id="94a0b-124">설명</span><span class="sxs-lookup"><span data-stu-id="94a0b-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="94a0b-125">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="94a0b-125">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="94a0b-126">특정 전송을 위해 서비스 호스팅 환경에서 인스턴스화하는 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="94a0b-126">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="94a0b-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="94a0b-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [<span data-ttu-id="94a0b-128">호스팅</span><span class="sxs-lookup"><span data-stu-id="94a0b-128">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
