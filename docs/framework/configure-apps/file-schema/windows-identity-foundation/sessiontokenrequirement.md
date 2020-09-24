---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: 4560c55cee5caf975e83ce9d4dc0b379ab905f8d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156851"
---
# \<sessionTokenRequirement>

<span data-ttu-id="bdd9d-101">클래스 또는 파생 클래스에 대 한 구성을 제공 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdd9d-101">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionTokenRequirement>**  
  
## <a name="syntax"></a><span data-ttu-id="bdd9d-102">구문</span><span class="sxs-lookup"><span data-stu-id="bdd9d-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bdd9d-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="bdd9d-103">Attributes and Elements</span></span>  

 <span data-ttu-id="bdd9d-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bdd9d-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bdd9d-105">특성</span><span class="sxs-lookup"><span data-stu-id="bdd9d-105">Attributes</span></span>  
  
|<span data-ttu-id="bdd9d-106">attribute</span><span class="sxs-lookup"><span data-stu-id="bdd9d-106">Attribute</span></span>|<span data-ttu-id="bdd9d-107">설명</span><span class="sxs-lookup"><span data-stu-id="bdd9d-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bdd9d-108">lifetime</span><span class="sxs-lookup"><span data-stu-id="bdd9d-108">lifetime</span></span>|<span data-ttu-id="bdd9d-109">세션 토큰의 수명을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdd9d-109">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bdd9d-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="bdd9d-110">Child Elements</span></span>  

 <span data-ttu-id="bdd9d-111">없음</span><span class="sxs-lookup"><span data-stu-id="bdd9d-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bdd9d-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="bdd9d-112">Parent Elements</span></span>  
  
|<span data-ttu-id="bdd9d-113">요소</span><span class="sxs-lookup"><span data-stu-id="bdd9d-113">Element</span></span>|<span data-ttu-id="bdd9d-114">설명</span><span class="sxs-lookup"><span data-stu-id="bdd9d-114">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="bdd9d-115">지정 된 보안 토큰 처리기를 토큰 처리기 컬렉션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdd9d-115">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bdd9d-116">예제</span><span class="sxs-lookup"><span data-stu-id="bdd9d-116">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
