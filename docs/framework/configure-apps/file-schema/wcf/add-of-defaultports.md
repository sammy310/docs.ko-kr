---
title: <defaultPorts>의 <add>
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: f5de2aa897a3bc37d08932451a2c7b94bc603b9e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400644"
---
# <a name="add-of-defaultports"></a><span data-ttu-id="149d1-102">\<defaultports의 \<> 추가 ></span><span class="sxs-lookup"><span data-stu-id="149d1-102">\<add> of \<defaultPorts></span></span>
<span data-ttu-id="149d1-103">클라이언트 애플리케이션에서 수신하는 기본 통신 엔드포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="149d1-103">A default communications endpoint that the client application listens to.</span></span>  
  
<span data-ttu-id="149d1-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="149d1-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="149d1-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="149d1-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="149d1-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="149d1-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="149d1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="149d1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="149d1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="149d1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="149d1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<useRequestHeadersForMetadataAddress >** ](userequestheadersformetadataaddress.md)</span><span class="sxs-lookup"><span data-stu-id="149d1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<useRequestHeadersForMetadataAddress>**](userequestheadersformetadataaddress.md)</span></span>\
<span data-ttu-id="149d1-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<defaultPorts >** ](defaultports.md)</span><span class="sxs-lookup"><span data-stu-id="149d1-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultPorts>**](defaultports.md)</span></span>\
<span data-ttu-id="149d1-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> 추가**</span><span class="sxs-lookup"><span data-stu-id="149d1-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="149d1-112">구문</span><span class="sxs-lookup"><span data-stu-id="149d1-112">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="149d1-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="149d1-113">Attributes and Elements</span></span>  
 <span data-ttu-id="149d1-114">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="149d1-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="149d1-115">특성</span><span class="sxs-lookup"><span data-stu-id="149d1-115">Attributes</span></span>  
  
|<span data-ttu-id="149d1-116">특성</span><span class="sxs-lookup"><span data-stu-id="149d1-116">Attribute</span></span>|<span data-ttu-id="149d1-117">Description</span><span class="sxs-lookup"><span data-stu-id="149d1-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="149d1-118">포트</span><span class="sxs-lookup"><span data-stu-id="149d1-118">port</span></span>|<span data-ttu-id="149d1-119">기본 통신 포트 번호를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="149d1-119">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="149d1-120">scheme</span><span class="sxs-lookup"><span data-stu-id="149d1-120">scheme</span></span>|<span data-ttu-id="149d1-121">통신 포트와 연결된 프로토콜 설정 그룹을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="149d1-121">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="149d1-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="149d1-122">Child Elements</span></span>  
 <span data-ttu-id="149d1-123">없음</span><span class="sxs-lookup"><span data-stu-id="149d1-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="149d1-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="149d1-124">Parent Elements</span></span>  
  
|<span data-ttu-id="149d1-125">요소</span><span class="sxs-lookup"><span data-stu-id="149d1-125">Element</span></span>|<span data-ttu-id="149d1-126">Description</span><span class="sxs-lookup"><span data-stu-id="149d1-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="149d1-127">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="149d1-127">\<defaultPorts></span></span>](defaultports.md)|<span data-ttu-id="149d1-128">클라이언트 애플리케이션에서 수신하는 기본 통신 엔드포인트를 나열하는 기본 포트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="149d1-128">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="149d1-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="149d1-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElement>
