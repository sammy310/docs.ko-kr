---
title: <transportConfigurationTypes>
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: 6545e1f1be2695d165b89a38c7218e0acdc88bfc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162025"
---
# \<transportConfigurationTypes>

<span data-ttu-id="f1275-101">특정 전송의 형식을 식별하는 구성 요소 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f1275-101">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="f1275-102">사용자 지정 WAS 프로토콜을 추가하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1275-102">This can be used to add custom WAS protocols.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transportConfigurationTypes>**  
  
## <a name="syntax"></a><span data-ttu-id="f1275-103">구문</span><span class="sxs-lookup"><span data-stu-id="f1275-103">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f1275-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f1275-104">Attributes and Elements</span></span>  

 <span data-ttu-id="f1275-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f1275-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f1275-106">특성</span><span class="sxs-lookup"><span data-stu-id="f1275-106">Attributes</span></span>  
  
|<span data-ttu-id="f1275-107">attribute</span><span class="sxs-lookup"><span data-stu-id="f1275-107">Attribute</span></span>|<span data-ttu-id="f1275-108">Description</span><span class="sxs-lookup"><span data-stu-id="f1275-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f1275-109">name</span><span class="sxs-lookup"><span data-stu-id="f1275-109">name</span></span>|<span data-ttu-id="f1275-110">전송의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f1275-110">The name of the transport</span></span>|  
|<span data-ttu-id="f1275-111">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="f1275-111">transportConfigurationType</span></span>|<span data-ttu-id="f1275-112">전송을 구현하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f1275-112">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f1275-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f1275-113">Child Elements</span></span>  
  
|<span data-ttu-id="f1275-114">요소</span><span class="sxs-lookup"><span data-stu-id="f1275-114">Element</span></span>|<span data-ttu-id="f1275-115">설명</span><span class="sxs-lookup"><span data-stu-id="f1275-115">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-transportconfigurationtype.md)|<span data-ttu-id="f1275-116">특정 전송의 형식을 식별하는 구성 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f1275-116">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f1275-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f1275-117">Parent Elements</span></span>  
  
|<span data-ttu-id="f1275-118">요소</span><span class="sxs-lookup"><span data-stu-id="f1275-118">Element</span></span>|<span data-ttu-id="f1275-119">설명</span><span class="sxs-lookup"><span data-stu-id="f1275-119">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|<span data-ttu-id="f1275-120">특정 전송을 위해 서비스 호스팅 환경에서 인스턴스화하는 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f1275-120">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f1275-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f1275-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [<span data-ttu-id="f1275-122">호스팅</span><span class="sxs-lookup"><span data-stu-id="f1275-122">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
