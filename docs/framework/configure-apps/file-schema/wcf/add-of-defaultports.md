---
title: <defaultPorts>의 <add>
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: 2c6b5de51e6508965daf6022a47d12d8d73f2a4d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149129"
---
# <a name="add-of-defaultports"></a><span data-ttu-id="10db9-102">\<defaultPorts>의 \<add></span><span class="sxs-lookup"><span data-stu-id="10db9-102">\<add> of \<defaultPorts></span></span>

<span data-ttu-id="10db9-103">클라이언트 애플리케이션에서 수신하는 기본 통신 엔드포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="10db9-103">A default communications endpoint that the client application listens to.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<useRequestHeadersForMetadataAddress>**](userequestheadersformetadataaddress.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultPorts>**](defaultports.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="10db9-104">구문</span><span class="sxs-lookup"><span data-stu-id="10db9-104">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10db9-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="10db9-105">Attributes and Elements</span></span>  

 <span data-ttu-id="10db9-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="10db9-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10db9-107">특성</span><span class="sxs-lookup"><span data-stu-id="10db9-107">Attributes</span></span>  
  
|<span data-ttu-id="10db9-108">attribute</span><span class="sxs-lookup"><span data-stu-id="10db9-108">Attribute</span></span>|<span data-ttu-id="10db9-109">설명</span><span class="sxs-lookup"><span data-stu-id="10db9-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="10db9-110">포트</span><span class="sxs-lookup"><span data-stu-id="10db9-110">port</span></span>|<span data-ttu-id="10db9-111">기본 통신 포트 번호를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="10db9-111">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="10db9-112">scheme</span><span class="sxs-lookup"><span data-stu-id="10db9-112">scheme</span></span>|<span data-ttu-id="10db9-113">통신 포트와 연결된 프로토콜 설정 그룹을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="10db9-113">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="10db9-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="10db9-114">Child Elements</span></span>  

 <span data-ttu-id="10db9-115">없음</span><span class="sxs-lookup"><span data-stu-id="10db9-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="10db9-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="10db9-116">Parent Elements</span></span>  
  
|<span data-ttu-id="10db9-117">요소</span><span class="sxs-lookup"><span data-stu-id="10db9-117">Element</span></span>|<span data-ttu-id="10db9-118">설명</span><span class="sxs-lookup"><span data-stu-id="10db9-118">Description</span></span>|  
|-------------|-----------------|  
|[\<defaultPorts>](defaultports.md)|<span data-ttu-id="10db9-119">클라이언트 애플리케이션에서 수신하는 기본 통신 엔드포인트를 나열하는 기본 포트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="10db9-119">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="10db9-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="10db9-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElement>
