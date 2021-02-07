---
description: '다음에 대 한 자세한 정보:: <add><transportConfigurationType>'
title: <transportConfigurationType>의 <add>
ms.date: 03/30/2017
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
ms.openlocfilehash: 4a4a68e1f70bcb2ec7d55d5d6c3b530e71ddc55d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99750015"
---
# <a name="add-of-transportconfigurationtype"></a><span data-ttu-id="4c3f8-103">\<transportConfigurationType>의 \<add></span><span class="sxs-lookup"><span data-stu-id="4c3f8-103">\<add> of \<transportConfigurationType></span></span>

<span data-ttu-id="4c3f8-104">이 요소는 특정 전송 형식을 식별하는 키/값 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-104">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<transportConfigurationTypes>**](transportconfigurationtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="4c3f8-105">구문</span><span class="sxs-lookup"><span data-stu-id="4c3f8-105">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c3f8-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4c3f8-106">Attributes and Elements</span></span>  

 <span data-ttu-id="4c3f8-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4c3f8-108">특성</span><span class="sxs-lookup"><span data-stu-id="4c3f8-108">Attributes</span></span>  
  
|<span data-ttu-id="4c3f8-109">attribute</span><span class="sxs-lookup"><span data-stu-id="4c3f8-109">Attribute</span></span>|<span data-ttu-id="4c3f8-110">설명</span><span class="sxs-lookup"><span data-stu-id="4c3f8-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4c3f8-111">name</span><span class="sxs-lookup"><span data-stu-id="4c3f8-111">name</span></span>|<span data-ttu-id="4c3f8-112">필수 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-112">Required String attribute.</span></span><br /><br /> <span data-ttu-id="4c3f8-113">전송 형식을 고유하게 식별하는 사용자 정의 키를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-113">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="4c3f8-114">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="4c3f8-114">transportConfigurationType</span></span>|<span data-ttu-id="4c3f8-115">특정 전송을 구현하는 형식을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-115">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4c3f8-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4c3f8-116">Child Elements</span></span>  

 <span data-ttu-id="4c3f8-117">없음</span><span class="sxs-lookup"><span data-stu-id="4c3f8-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4c3f8-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4c3f8-118">Parent Elements</span></span>  
  
|<span data-ttu-id="4c3f8-119">요소</span><span class="sxs-lookup"><span data-stu-id="4c3f8-119">Element</span></span>|<span data-ttu-id="4c3f8-120">설명</span><span class="sxs-lookup"><span data-stu-id="4c3f8-120">Description</span></span>|  
|-------------|-----------------|  
|[\<transportConfigurationTypes>](transportconfigurationtypes.md)|<span data-ttu-id="4c3f8-121">특정 전송을 구현하는 형식의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-121">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4c3f8-122">예제</span><span class="sxs-lookup"><span data-stu-id="4c3f8-122">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="net.udp"
         transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="see-also"></a><span data-ttu-id="4c3f8-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4c3f8-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="4c3f8-124">호스팅</span><span class="sxs-lookup"><span data-stu-id="4c3f8-124">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
