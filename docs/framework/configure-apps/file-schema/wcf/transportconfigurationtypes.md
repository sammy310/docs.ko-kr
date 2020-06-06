---
title: <transportConfigurationTypes>
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: 4be08f780c1095b0016bd130b5719a2a7307d019
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854933"
---
# \<transportConfigurationTypes>
<span data-ttu-id="ee21b-101">특정 전송의 형식을 식별하는 구성 요소 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ee21b-101">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="ee21b-102">사용자 지정 WAS 프로토콜을 추가하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee21b-102">This can be used to add custom WAS protocols.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transportConfigurationTypes>**  
  
## <a name="syntax"></a><span data-ttu-id="ee21b-103">구문</span><span class="sxs-lookup"><span data-stu-id="ee21b-103">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ee21b-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ee21b-104">Attributes and Elements</span></span>  
 <span data-ttu-id="ee21b-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ee21b-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ee21b-106">특성</span><span class="sxs-lookup"><span data-stu-id="ee21b-106">Attributes</span></span>  
  
|<span data-ttu-id="ee21b-107">attribute</span><span class="sxs-lookup"><span data-stu-id="ee21b-107">Attribute</span></span>|<span data-ttu-id="ee21b-108">Description</span><span class="sxs-lookup"><span data-stu-id="ee21b-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ee21b-109">name</span><span class="sxs-lookup"><span data-stu-id="ee21b-109">name</span></span>|<span data-ttu-id="ee21b-110">전송의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ee21b-110">The name of the transport</span></span>|  
|<span data-ttu-id="ee21b-111">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="ee21b-111">transportConfigurationType</span></span>|<span data-ttu-id="ee21b-112">전송을 구현하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ee21b-112">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ee21b-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ee21b-113">Child Elements</span></span>  
  
|<span data-ttu-id="ee21b-114">요소</span><span class="sxs-lookup"><span data-stu-id="ee21b-114">Element</span></span>|<span data-ttu-id="ee21b-115">Description</span><span class="sxs-lookup"><span data-stu-id="ee21b-115">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-transportconfigurationtype.md)|<span data-ttu-id="ee21b-116">특정 전송의 형식을 식별하는 구성 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ee21b-116">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ee21b-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ee21b-117">Parent Elements</span></span>  
  
|<span data-ttu-id="ee21b-118">요소</span><span class="sxs-lookup"><span data-stu-id="ee21b-118">Element</span></span>|<span data-ttu-id="ee21b-119">Description</span><span class="sxs-lookup"><span data-stu-id="ee21b-119">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|<span data-ttu-id="ee21b-120">특정 전송을 위해 서비스 호스팅 환경에서 인스턴스화하는 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ee21b-120">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ee21b-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ee21b-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [<span data-ttu-id="ee21b-122">호스팅</span><span class="sxs-lookup"><span data-stu-id="ee21b-122">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
