---
description: 다음에 대해 자세히 알아보세요. <sessionTokenRequirement>
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: 8f2868df4939dc0dc7c779eb9ca5a35a6b996fc6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698273"
---
# \<sessionTokenRequirement>

<span data-ttu-id="a2546-102">클래스 또는 파생 클래스에 대 한 구성을 제공 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2546-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionTokenRequirement>**  
  
## <a name="syntax"></a><span data-ttu-id="a2546-103">구문</span><span class="sxs-lookup"><span data-stu-id="a2546-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a2546-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a2546-104">Attributes and Elements</span></span>  

 <span data-ttu-id="a2546-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a2546-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a2546-106">특성</span><span class="sxs-lookup"><span data-stu-id="a2546-106">Attributes</span></span>  
  
|<span data-ttu-id="a2546-107">attribute</span><span class="sxs-lookup"><span data-stu-id="a2546-107">Attribute</span></span>|<span data-ttu-id="a2546-108">설명</span><span class="sxs-lookup"><span data-stu-id="a2546-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a2546-109">lifetime</span><span class="sxs-lookup"><span data-stu-id="a2546-109">lifetime</span></span>|<span data-ttu-id="a2546-110">세션 토큰의 수명을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2546-110">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a2546-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a2546-111">Child Elements</span></span>  

 <span data-ttu-id="a2546-112">없음</span><span class="sxs-lookup"><span data-stu-id="a2546-112">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a2546-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a2546-113">Parent Elements</span></span>  
  
|<span data-ttu-id="a2546-114">요소</span><span class="sxs-lookup"><span data-stu-id="a2546-114">Element</span></span>|<span data-ttu-id="a2546-115">설명</span><span class="sxs-lookup"><span data-stu-id="a2546-115">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="a2546-116">지정 된 보안 토큰 처리기를 토큰 처리기 컬렉션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2546-116">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a2546-117">예제</span><span class="sxs-lookup"><span data-stu-id="a2546-117">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
