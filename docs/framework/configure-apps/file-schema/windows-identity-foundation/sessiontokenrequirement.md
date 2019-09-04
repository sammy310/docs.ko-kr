---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: 968c48df9e92a1dfbfb6e248b06cf4f97cece8b4
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251824"
---
# <a name="sessiontokenrequirement"></a><span data-ttu-id="c3ff0-101">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="c3ff0-101">\<sessionTokenRequirement></span></span>
<span data-ttu-id="c3ff0-102"><xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> 클래스 또는 파생 클래스에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff0-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="c3ff0-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c3ff0-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c3ff0-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="c3ff0-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="c3ff0-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="c3ff0-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="c3ff0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="c3ff0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="c3ff0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> 추가**](add.md)</span><span class="sxs-lookup"><span data-stu-id="c3ff0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="c3ff0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<sessionTokenRequirement >**</span><span class="sxs-lookup"><span data-stu-id="c3ff0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionTokenRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3ff0-109">구문</span><span class="sxs-lookup"><span data-stu-id="c3ff0-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">  
        <sessionTokenRequirement lifetime=TimeSpan >  
        </sessionTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c3ff0-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c3ff0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c3ff0-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c3ff0-112">특성</span><span class="sxs-lookup"><span data-stu-id="c3ff0-112">Attributes</span></span>  
  
|<span data-ttu-id="c3ff0-113">특성</span><span class="sxs-lookup"><span data-stu-id="c3ff0-113">Attribute</span></span>|<span data-ttu-id="c3ff0-114">Description</span><span class="sxs-lookup"><span data-stu-id="c3ff0-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c3ff0-115">lifetime</span><span class="sxs-lookup"><span data-stu-id="c3ff0-115">lifetime</span></span>|<span data-ttu-id="c3ff0-116">세션 토큰의 수명을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff0-116">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c3ff0-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c3ff0-117">Child Elements</span></span>  
 <span data-ttu-id="c3ff0-118">없음</span><span class="sxs-lookup"><span data-stu-id="c3ff0-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c3ff0-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c3ff0-119">Parent Elements</span></span>  
  
|<span data-ttu-id="c3ff0-120">요소</span><span class="sxs-lookup"><span data-stu-id="c3ff0-120">Element</span></span>|<span data-ttu-id="c3ff0-121">설명</span><span class="sxs-lookup"><span data-stu-id="c3ff0-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c3ff0-122">\<add></span><span class="sxs-lookup"><span data-stu-id="c3ff0-122">\<add></span></span>](add.md)|<span data-ttu-id="c3ff0-123">지정 된 보안 토큰 처리기를 토큰 처리기 컬렉션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff0-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c3ff0-124">예제</span><span class="sxs-lookup"><span data-stu-id="c3ff0-124">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
