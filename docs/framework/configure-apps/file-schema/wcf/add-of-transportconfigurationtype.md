---
title: <transportConfigurationType>의 <add>
ms.date: 03/30/2017
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
ms.openlocfilehash: adf4cd7f02db6535c5950443d09476a9a5ff63fb
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850313"
---
# <a name="add-of-transportconfigurationtype"></a><span data-ttu-id="5546f-102">\<\<transportConfigurationType > > 추가</span><span class="sxs-lookup"><span data-stu-id="5546f-102">\<add> of \<transportConfigurationType></span></span>
<span data-ttu-id="5546f-103">이 요소는 특정 전송 형식을 식별하는 키/값 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="5546f-103">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
<span data-ttu-id="5546f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5546f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5546f-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="5546f-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="5546f-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceHostingEnvironment >** ](servicehostingenvironment.md)</span><span class="sxs-lookup"><span data-stu-id="5546f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)</span></span>\
<span data-ttu-id="5546f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> Configurationtypes**](transportconfigurationtypes.md)</span><span class="sxs-lookup"><span data-stu-id="5546f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<transportConfigurationTypes>**](transportconfigurationtypes.md)</span></span>\
<span data-ttu-id="5546f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> 추가**</span><span class="sxs-lookup"><span data-stu-id="5546f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5546f-109">구문</span><span class="sxs-lookup"><span data-stu-id="5546f-109">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5546f-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5546f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5546f-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5546f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5546f-112">특성</span><span class="sxs-lookup"><span data-stu-id="5546f-112">Attributes</span></span>  
  
|<span data-ttu-id="5546f-113">특성</span><span class="sxs-lookup"><span data-stu-id="5546f-113">Attribute</span></span>|<span data-ttu-id="5546f-114">Description</span><span class="sxs-lookup"><span data-stu-id="5546f-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5546f-115">name</span><span class="sxs-lookup"><span data-stu-id="5546f-115">name</span></span>|<span data-ttu-id="5546f-116">필수 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="5546f-116">Required String attribute.</span></span><br /><br /> <span data-ttu-id="5546f-117">전송 형식을 고유하게 식별하는 사용자 정의 키를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5546f-117">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="5546f-118">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="5546f-118">transportConfigurationType</span></span>|<span data-ttu-id="5546f-119">특정 전송을 구현하는 형식을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5546f-119">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5546f-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5546f-120">Child Elements</span></span>  
 <span data-ttu-id="5546f-121">없음</span><span class="sxs-lookup"><span data-stu-id="5546f-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5546f-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5546f-122">Parent Elements</span></span>  
  
|<span data-ttu-id="5546f-123">요소</span><span class="sxs-lookup"><span data-stu-id="5546f-123">Element</span></span>|<span data-ttu-id="5546f-124">설명</span><span class="sxs-lookup"><span data-stu-id="5546f-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5546f-125">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="5546f-125">\<transportConfigurationTypes></span></span>](transportconfigurationtypes.md)|<span data-ttu-id="5546f-126">특정 전송을 구현하는 형식의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="5546f-126">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5546f-127">예제</span><span class="sxs-lookup"><span data-stu-id="5546f-127">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="net.udp"
         transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="see-also"></a><span data-ttu-id="5546f-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="5546f-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="5546f-129">호스팅</span><span class="sxs-lookup"><span data-stu-id="5546f-129">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
