---
description: 다음에 대해 자세히 알아보세요. <clear>
title: <clear>
ms.date: 03/30/2017
ms.assetid: 54dcd1d1-038f-4fc8-a3a4-56ba7a1ca0fd
author: BrucePerlerMS
ms.openlocfilehash: 460add2722779a61dacc5c7510ea0a94aaef4a3a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664134"
---
# \<clear>

<span data-ttu-id="08e74-102">현재 토큰 처리기 컬렉션에서 모든 보안 토큰 처리기를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="08e74-102">Clears all security token handlers from the current token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**  
  
## <a name="syntax"></a><span data-ttu-id="08e74-103">구문</span><span class="sxs-lookup"><span data-stu-id="08e74-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="08e74-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="08e74-104">Attributes and Elements</span></span>  

 <span data-ttu-id="08e74-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="08e74-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="08e74-106">특성</span><span class="sxs-lookup"><span data-stu-id="08e74-106">Attributes</span></span>  

 <span data-ttu-id="08e74-107">None</span><span class="sxs-lookup"><span data-stu-id="08e74-107">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="08e74-108">자식 요소</span><span class="sxs-lookup"><span data-stu-id="08e74-108">Child Elements</span></span>  

 <span data-ttu-id="08e74-109">없음</span><span class="sxs-lookup"><span data-stu-id="08e74-109">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="08e74-110">부모 요소</span><span class="sxs-lookup"><span data-stu-id="08e74-110">Parent Elements</span></span>  
  
|<span data-ttu-id="08e74-111">요소</span><span class="sxs-lookup"><span data-stu-id="08e74-111">Element</span></span>|<span data-ttu-id="08e74-112">설명</span><span class="sxs-lookup"><span data-stu-id="08e74-112">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="08e74-113">끝점에 등록 된 보안 토큰 처리기의 컬렉션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="08e74-113">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|
