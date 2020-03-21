---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: ade55a5b26826633faf2e7ef7598a4071d613bbc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152543"
---
# <a name="sessiontokenrequirement"></a><span data-ttu-id="5c3b0-101">\<세션토큰요구 사항></span><span class="sxs-lookup"><span data-stu-id="5c3b0-101">\<sessionTokenRequirement></span></span>
<span data-ttu-id="5c3b0-102">클래스 또는 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> 파생 클래스에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c3b0-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="5c3b0-103">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5c3b0-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5c3b0-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="5c3b0-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="5c3b0-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<ID구성>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="5c3b0-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="5c3b0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<보안토큰처리기>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="5c3b0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="5c3b0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>추가**](add.md)</span><span class="sxs-lookup"><span data-stu-id="5c3b0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="5c3b0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<세션토큰요구 사항>**</span><span class="sxs-lookup"><span data-stu-id="5c3b0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionTokenRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c3b0-109">구문</span><span class="sxs-lookup"><span data-stu-id="5c3b0-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5c3b0-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5c3b0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5c3b0-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5c3b0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5c3b0-112">특성</span><span class="sxs-lookup"><span data-stu-id="5c3b0-112">Attributes</span></span>  
  
|<span data-ttu-id="5c3b0-113">attribute</span><span class="sxs-lookup"><span data-stu-id="5c3b0-113">Attribute</span></span>|<span data-ttu-id="5c3b0-114">Description</span><span class="sxs-lookup"><span data-stu-id="5c3b0-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5c3b0-115">lifetime</span><span class="sxs-lookup"><span data-stu-id="5c3b0-115">lifetime</span></span>|<span data-ttu-id="5c3b0-116">세션 토큰의 수명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5c3b0-116">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5c3b0-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5c3b0-117">Child Elements</span></span>  
 <span data-ttu-id="5c3b0-118">None</span><span class="sxs-lookup"><span data-stu-id="5c3b0-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5c3b0-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5c3b0-119">Parent Elements</span></span>  
  
|<span data-ttu-id="5c3b0-120">요소</span><span class="sxs-lookup"><span data-stu-id="5c3b0-120">Element</span></span>|<span data-ttu-id="5c3b0-121">Description</span><span class="sxs-lookup"><span data-stu-id="5c3b0-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5c3b0-122">\<>추가</span><span class="sxs-lookup"><span data-stu-id="5c3b0-122">\<add></span></span>](add.md)|<span data-ttu-id="5c3b0-123">지정된 보안 토큰 처리기를 토큰 처리기 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5c3b0-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5c3b0-124">예제</span><span class="sxs-lookup"><span data-stu-id="5c3b0-124">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
