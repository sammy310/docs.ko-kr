---
title: <transportConfigurationType>의 <add>
ms.date: 03/30/2017
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
ms.openlocfilehash: c71a58b13e89bedb5eed24d784c82fb1525f7625
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701439"
---
# <a name="add-of-transportconfigurationtype"></a><span data-ttu-id="1c104-102">\<추가 >의 \<transportConfigurationType ></span><span class="sxs-lookup"><span data-stu-id="1c104-102">\<add> of \<transportConfigurationType></span></span>
<span data-ttu-id="1c104-103">이 요소는 특정 전송 형식을 식별하는 키/값 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="1c104-103">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
 <span data-ttu-id="1c104-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1c104-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1c104-105">\<ServiceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="1c104-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="1c104-106">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="1c104-106">\<transportConfigurationTypes></span></span>  
<span data-ttu-id="1c104-107">\<add></span><span class="sxs-lookup"><span data-stu-id="1c104-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c104-108">구문</span><span class="sxs-lookup"><span data-stu-id="1c104-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1c104-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1c104-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1c104-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1c104-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1c104-111">특성</span><span class="sxs-lookup"><span data-stu-id="1c104-111">Attributes</span></span>  
  
|<span data-ttu-id="1c104-112">특성</span><span class="sxs-lookup"><span data-stu-id="1c104-112">Attribute</span></span>|<span data-ttu-id="1c104-113">설명</span><span class="sxs-lookup"><span data-stu-id="1c104-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1c104-114">name</span><span class="sxs-lookup"><span data-stu-id="1c104-114">name</span></span>|<span data-ttu-id="1c104-115">필수 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1c104-115">Required String attribute.</span></span><br /><br /> <span data-ttu-id="1c104-116">전송 형식을 고유하게 식별하는 사용자 정의 키를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1c104-116">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="1c104-117">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="1c104-117">transportConfigurationType</span></span>|<span data-ttu-id="1c104-118">특정 전송을 구현하는 형식을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1c104-118">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1c104-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1c104-119">Child Elements</span></span>  
 <span data-ttu-id="1c104-120">없음</span><span class="sxs-lookup"><span data-stu-id="1c104-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1c104-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1c104-121">Parent Elements</span></span>  
  
|<span data-ttu-id="1c104-122">요소</span><span class="sxs-lookup"><span data-stu-id="1c104-122">Element</span></span>|<span data-ttu-id="1c104-123">설명</span><span class="sxs-lookup"><span data-stu-id="1c104-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1c104-124">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="1c104-124">\<transportConfigurationTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transportconfigurationtypes.md)|<span data-ttu-id="1c104-125">특정 전송을 구현하는 형식의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="1c104-125">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1c104-126">예제</span><span class="sxs-lookup"><span data-stu-id="1c104-126">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="net.udp"
         transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="see-also"></a><span data-ttu-id="1c104-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="1c104-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="1c104-128">호스팅</span><span class="sxs-lookup"><span data-stu-id="1c104-128">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
