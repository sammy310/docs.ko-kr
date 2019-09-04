---
title: <clear>
ms.date: 03/30/2017
ms.assetid: 54dcd1d1-038f-4fc8-a3a4-56ba7a1ca0fd
author: BrucePerlerMS
ms.openlocfilehash: e96349c72fc4a952e3dc7efeea5f69ebaa1fd0ad
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252040"
---
# <a name="clear"></a><span data-ttu-id="924f0-101">\<clear></span><span class="sxs-lookup"><span data-stu-id="924f0-101">\<clear></span></span>
<span data-ttu-id="924f0-102">현재 토큰 처리기 컬렉션에서 모든 보안 토큰 처리기를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="924f0-102">Clears all security token handlers from the current token handler collection.</span></span>  
  
<span data-ttu-id="924f0-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="924f0-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="924f0-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="924f0-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="924f0-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="924f0-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="924f0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="924f0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="924f0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> 지우기**</span><span class="sxs-lookup"><span data-stu-id="924f0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="924f0-108">구문</span><span class="sxs-lookup"><span data-stu-id="924f0-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <clear>  
      </clear>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="924f0-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="924f0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="924f0-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="924f0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="924f0-111">특성</span><span class="sxs-lookup"><span data-stu-id="924f0-111">Attributes</span></span>  
 <span data-ttu-id="924f0-112">없음</span><span class="sxs-lookup"><span data-stu-id="924f0-112">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="924f0-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="924f0-113">Child Elements</span></span>  
 <span data-ttu-id="924f0-114">없음</span><span class="sxs-lookup"><span data-stu-id="924f0-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="924f0-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="924f0-115">Parent Elements</span></span>  
  
|<span data-ttu-id="924f0-116">요소</span><span class="sxs-lookup"><span data-stu-id="924f0-116">Element</span></span>|<span data-ttu-id="924f0-117">Description</span><span class="sxs-lookup"><span data-stu-id="924f0-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="924f0-118">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="924f0-118">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="924f0-119">끝점에 등록 된 보안 토큰 처리기의 컬렉션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="924f0-119">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|
