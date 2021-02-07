---
description: 다음에 대해 자세히 알아보세요. <transportConfigurationTypes>
title: <transportConfigurationTypes>
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: d6ef92cf3bdd10fdc9b374f10aaa748cf4300529
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749274"
---
# \<transportConfigurationTypes>

<span data-ttu-id="1a8b7-102">특정 전송의 형식을 식별하는 구성 요소 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1a8b7-102">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="1a8b7-103">사용자 지정 WAS 프로토콜을 추가하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a8b7-103">This can be used to add custom WAS protocols.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transportConfigurationTypes>**  
  
## <a name="syntax"></a><span data-ttu-id="1a8b7-104">구문</span><span class="sxs-lookup"><span data-stu-id="1a8b7-104">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1a8b7-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1a8b7-105">Attributes and Elements</span></span>  

 <span data-ttu-id="1a8b7-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1a8b7-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1a8b7-107">특성</span><span class="sxs-lookup"><span data-stu-id="1a8b7-107">Attributes</span></span>  
  
|<span data-ttu-id="1a8b7-108">attribute</span><span class="sxs-lookup"><span data-stu-id="1a8b7-108">Attribute</span></span>|<span data-ttu-id="1a8b7-109">설명</span><span class="sxs-lookup"><span data-stu-id="1a8b7-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1a8b7-110">name</span><span class="sxs-lookup"><span data-stu-id="1a8b7-110">name</span></span>|<span data-ttu-id="1a8b7-111">전송의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1a8b7-111">The name of the transport</span></span>|  
|<span data-ttu-id="1a8b7-112">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="1a8b7-112">transportConfigurationType</span></span>|<span data-ttu-id="1a8b7-113">전송을 구현하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1a8b7-113">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1a8b7-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1a8b7-114">Child Elements</span></span>  
  
|<span data-ttu-id="1a8b7-115">요소</span><span class="sxs-lookup"><span data-stu-id="1a8b7-115">Element</span></span>|<span data-ttu-id="1a8b7-116">설명</span><span class="sxs-lookup"><span data-stu-id="1a8b7-116">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-transportconfigurationtype.md)|<span data-ttu-id="1a8b7-117">특정 전송의 형식을 식별하는 구성 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1a8b7-117">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1a8b7-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1a8b7-118">Parent Elements</span></span>  
  
|<span data-ttu-id="1a8b7-119">요소</span><span class="sxs-lookup"><span data-stu-id="1a8b7-119">Element</span></span>|<span data-ttu-id="1a8b7-120">설명</span><span class="sxs-lookup"><span data-stu-id="1a8b7-120">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|<span data-ttu-id="1a8b7-121">특정 전송을 위해 서비스 호스팅 환경에서 인스턴스화하는 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1a8b7-121">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1a8b7-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1a8b7-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [<span data-ttu-id="1a8b7-123">호스팅</span><span class="sxs-lookup"><span data-stu-id="1a8b7-123">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
