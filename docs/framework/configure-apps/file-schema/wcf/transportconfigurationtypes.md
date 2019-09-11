---
title: <transportConfigurationTypes>
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: 4be08f780c1095b0016bd130b5719a2a7307d019
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854933"
---
# <a name="transportconfigurationtypes"></a><span data-ttu-id="dfcc7-101">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="dfcc7-101">\<transportConfigurationTypes></span></span>
<span data-ttu-id="dfcc7-102">특정 전송의 형식을 식별하는 구성 요소 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dfcc7-102">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="dfcc7-103">사용자 지정 WAS 프로토콜을 추가하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfcc7-103">This can be used to add custom WAS protocols.</span></span>  
  
<span data-ttu-id="dfcc7-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="dfcc7-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="dfcc7-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="dfcc7-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="dfcc7-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceHostingEnvironment >** ](servicehostingenvironment.md)</span><span class="sxs-lookup"><span data-stu-id="dfcc7-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)</span></span>\
<span data-ttu-id="dfcc7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> Configurationtypes**</span><span class="sxs-lookup"><span data-stu-id="dfcc7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transportConfigurationTypes>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfcc7-108">구문</span><span class="sxs-lookup"><span data-stu-id="dfcc7-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dfcc7-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="dfcc7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="dfcc7-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcc7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dfcc7-111">특성</span><span class="sxs-lookup"><span data-stu-id="dfcc7-111">Attributes</span></span>  
  
|<span data-ttu-id="dfcc7-112">특성</span><span class="sxs-lookup"><span data-stu-id="dfcc7-112">Attribute</span></span>|<span data-ttu-id="dfcc7-113">Description</span><span class="sxs-lookup"><span data-stu-id="dfcc7-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dfcc7-114">name</span><span class="sxs-lookup"><span data-stu-id="dfcc7-114">name</span></span>|<span data-ttu-id="dfcc7-115">전송의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="dfcc7-115">The name of the transport</span></span>|  
|<span data-ttu-id="dfcc7-116">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="dfcc7-116">transportConfigurationType</span></span>|<span data-ttu-id="dfcc7-117">전송을 구현하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="dfcc7-117">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dfcc7-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="dfcc7-118">Child Elements</span></span>  
  
|<span data-ttu-id="dfcc7-119">요소</span><span class="sxs-lookup"><span data-stu-id="dfcc7-119">Element</span></span>|<span data-ttu-id="dfcc7-120">설명</span><span class="sxs-lookup"><span data-stu-id="dfcc7-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dfcc7-121">\<add></span><span class="sxs-lookup"><span data-stu-id="dfcc7-121">\<add></span></span>](add-of-transportconfigurationtype.md)|<span data-ttu-id="dfcc7-122">특정 전송의 형식을 식별하는 구성 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcc7-122">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dfcc7-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="dfcc7-123">Parent Elements</span></span>  
  
|<span data-ttu-id="dfcc7-124">요소</span><span class="sxs-lookup"><span data-stu-id="dfcc7-124">Element</span></span>|<span data-ttu-id="dfcc7-125">설명</span><span class="sxs-lookup"><span data-stu-id="dfcc7-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dfcc7-126">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="dfcc7-126">\<serviceHostingEnvironment></span></span>](servicehostingenvironment.md)|<span data-ttu-id="dfcc7-127">특정 전송을 위해 서비스 호스팅 환경에서 인스턴스화하는 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcc7-127">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dfcc7-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="dfcc7-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [<span data-ttu-id="dfcc7-129">호스팅</span><span class="sxs-lookup"><span data-stu-id="dfcc7-129">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
