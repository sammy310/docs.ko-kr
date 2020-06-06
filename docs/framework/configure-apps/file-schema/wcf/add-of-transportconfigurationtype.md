---
title: <transportConfigurationType>의 <add>
ms.date: 03/30/2017
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
ms.openlocfilehash: adf4cd7f02db6535c5950443d09476a9a5ff63fb
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850313"
---
# <a name="add-of-transportconfigurationtype"></a><span data-ttu-id="c10bc-102">\<transportConfigurationType>의 \<add></span><span class="sxs-lookup"><span data-stu-id="c10bc-102">\<add> of \<transportConfigurationType></span></span>
<span data-ttu-id="c10bc-103">이 요소는 특정 전송 형식을 식별하는 키/값 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="c10bc-103">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<transportConfigurationTypes>**](transportconfigurationtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="c10bc-104">구문</span><span class="sxs-lookup"><span data-stu-id="c10bc-104">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c10bc-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c10bc-105">Attributes and Elements</span></span>  
 <span data-ttu-id="c10bc-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c10bc-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c10bc-107">특성</span><span class="sxs-lookup"><span data-stu-id="c10bc-107">Attributes</span></span>  
  
|<span data-ttu-id="c10bc-108">attribute</span><span class="sxs-lookup"><span data-stu-id="c10bc-108">Attribute</span></span>|<span data-ttu-id="c10bc-109">Description</span><span class="sxs-lookup"><span data-stu-id="c10bc-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c10bc-110">name</span><span class="sxs-lookup"><span data-stu-id="c10bc-110">name</span></span>|<span data-ttu-id="c10bc-111">필수 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="c10bc-111">Required String attribute.</span></span><br /><br /> <span data-ttu-id="c10bc-112">전송 형식을 고유하게 식별하는 사용자 정의 키를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c10bc-112">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="c10bc-113">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="c10bc-113">transportConfigurationType</span></span>|<span data-ttu-id="c10bc-114">특정 전송을 구현하는 형식을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c10bc-114">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c10bc-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c10bc-115">Child Elements</span></span>  
 <span data-ttu-id="c10bc-116">None</span><span class="sxs-lookup"><span data-stu-id="c10bc-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c10bc-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c10bc-117">Parent Elements</span></span>  
  
|<span data-ttu-id="c10bc-118">요소</span><span class="sxs-lookup"><span data-stu-id="c10bc-118">Element</span></span>|<span data-ttu-id="c10bc-119">Description</span><span class="sxs-lookup"><span data-stu-id="c10bc-119">Description</span></span>|  
|-------------|-----------------|  
|[\<transportConfigurationTypes>](transportconfigurationtypes.md)|<span data-ttu-id="c10bc-120">특정 전송을 구현하는 형식의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="c10bc-120">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c10bc-121">예제</span><span class="sxs-lookup"><span data-stu-id="c10bc-121">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="net.udp"
         transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="see-also"></a><span data-ttu-id="c10bc-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c10bc-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="c10bc-123">호스팅</span><span class="sxs-lookup"><span data-stu-id="c10bc-123">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
