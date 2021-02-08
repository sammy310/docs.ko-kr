---
description: '다음에 대 한 자세한 정보:: <add><defaultPorts>'
title: <defaultPorts>의 <add>
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: 9db7afa5183b185eb842530b051d98236e7fa381
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803960"
---
# <a name="add-of-defaultports"></a><span data-ttu-id="fe9b8-103">\<defaultPorts>의 \<add></span><span class="sxs-lookup"><span data-stu-id="fe9b8-103">\<add> of \<defaultPorts></span></span>

<span data-ttu-id="fe9b8-104">클라이언트 애플리케이션에서 수신하는 기본 통신 엔드포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="fe9b8-104">A default communications endpoint that the client application listens to.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<useRequestHeadersForMetadataAddress>**](userequestheadersformetadataaddress.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultPorts>**](defaultports.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="fe9b8-105">구문</span><span class="sxs-lookup"><span data-stu-id="fe9b8-105">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fe9b8-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fe9b8-106">Attributes and Elements</span></span>  

 <span data-ttu-id="fe9b8-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fe9b8-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fe9b8-108">특성</span><span class="sxs-lookup"><span data-stu-id="fe9b8-108">Attributes</span></span>  
  
|<span data-ttu-id="fe9b8-109">attribute</span><span class="sxs-lookup"><span data-stu-id="fe9b8-109">Attribute</span></span>|<span data-ttu-id="fe9b8-110">설명</span><span class="sxs-lookup"><span data-stu-id="fe9b8-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fe9b8-111">포트</span><span class="sxs-lookup"><span data-stu-id="fe9b8-111">port</span></span>|<span data-ttu-id="fe9b8-112">기본 통신 포트 번호를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="fe9b8-112">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="fe9b8-113">scheme</span><span class="sxs-lookup"><span data-stu-id="fe9b8-113">scheme</span></span>|<span data-ttu-id="fe9b8-114">통신 포트와 연결된 프로토콜 설정 그룹을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="fe9b8-114">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fe9b8-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fe9b8-115">Child Elements</span></span>  

 <span data-ttu-id="fe9b8-116">없음</span><span class="sxs-lookup"><span data-stu-id="fe9b8-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fe9b8-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fe9b8-117">Parent Elements</span></span>  
  
|<span data-ttu-id="fe9b8-118">요소</span><span class="sxs-lookup"><span data-stu-id="fe9b8-118">Element</span></span>|<span data-ttu-id="fe9b8-119">설명</span><span class="sxs-lookup"><span data-stu-id="fe9b8-119">Description</span></span>|  
|-------------|-----------------|  
|[\<defaultPorts>](defaultports.md)|<span data-ttu-id="fe9b8-120">클라이언트 애플리케이션에서 수신하는 기본 통신 엔드포인트를 나열하는 기본 포트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="fe9b8-120">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fe9b8-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fe9b8-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElement>
