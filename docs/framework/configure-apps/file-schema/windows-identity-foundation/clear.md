---
title: <clear>
ms.date: 03/30/2017
ms.assetid: 54dcd1d1-038f-4fc8-a3a4-56ba7a1ca0fd
author: BrucePerlerMS
ms.openlocfilehash: 0f043442fb8edd9bf95a839a26cc42e8122d9100
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167069"
---
# \<clear>

<span data-ttu-id="50e26-101">현재 토큰 처리기 컬렉션에서 모든 보안 토큰 처리기를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="50e26-101">Clears all security token handlers from the current token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**  
  
## <a name="syntax"></a><span data-ttu-id="50e26-102">구문</span><span class="sxs-lookup"><span data-stu-id="50e26-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="50e26-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="50e26-103">Attributes and Elements</span></span>  

 <span data-ttu-id="50e26-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="50e26-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="50e26-105">특성</span><span class="sxs-lookup"><span data-stu-id="50e26-105">Attributes</span></span>  

 <span data-ttu-id="50e26-106">없음</span><span class="sxs-lookup"><span data-stu-id="50e26-106">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="50e26-107">자식 요소</span><span class="sxs-lookup"><span data-stu-id="50e26-107">Child Elements</span></span>  

 <span data-ttu-id="50e26-108">없음</span><span class="sxs-lookup"><span data-stu-id="50e26-108">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="50e26-109">부모 요소</span><span class="sxs-lookup"><span data-stu-id="50e26-109">Parent Elements</span></span>  
  
|<span data-ttu-id="50e26-110">요소</span><span class="sxs-lookup"><span data-stu-id="50e26-110">Element</span></span>|<span data-ttu-id="50e26-111">설명</span><span class="sxs-lookup"><span data-stu-id="50e26-111">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="50e26-112">끝점에 등록 된 보안 토큰 처리기의 컬렉션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="50e26-112">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|
