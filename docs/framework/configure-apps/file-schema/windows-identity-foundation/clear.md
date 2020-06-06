---
title: <clear>
ms.date: 03/30/2017
ms.assetid: 54dcd1d1-038f-4fc8-a3a4-56ba7a1ca0fd
author: BrucePerlerMS
ms.openlocfilehash: e96349c72fc4a952e3dc7efeea5f69ebaa1fd0ad
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252040"
---
# \<clear>
<span data-ttu-id="e5809-101">현재 토큰 처리기 컬렉션에서 모든 보안 토큰 처리기를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="e5809-101">Clears all security token handlers from the current token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**  
  
## <a name="syntax"></a><span data-ttu-id="e5809-102">구문</span><span class="sxs-lookup"><span data-stu-id="e5809-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5809-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e5809-103">Attributes and Elements</span></span>  
 <span data-ttu-id="e5809-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e5809-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5809-105">특성</span><span class="sxs-lookup"><span data-stu-id="e5809-105">Attributes</span></span>  
 <span data-ttu-id="e5809-106">None</span><span class="sxs-lookup"><span data-stu-id="e5809-106">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e5809-107">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e5809-107">Child Elements</span></span>  
 <span data-ttu-id="e5809-108">None</span><span class="sxs-lookup"><span data-stu-id="e5809-108">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e5809-109">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e5809-109">Parent Elements</span></span>  
  
|<span data-ttu-id="e5809-110">요소</span><span class="sxs-lookup"><span data-stu-id="e5809-110">Element</span></span>|<span data-ttu-id="e5809-111">Description</span><span class="sxs-lookup"><span data-stu-id="e5809-111">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="e5809-112">끝점에 등록 된 보안 토큰 처리기의 컬렉션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5809-112">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|
