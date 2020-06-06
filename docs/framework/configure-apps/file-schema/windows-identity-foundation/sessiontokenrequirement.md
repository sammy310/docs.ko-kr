---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: ade55a5b26826633faf2e7ef7598a4071d613bbc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152543"
---
# \<sessionTokenRequirement>
<span data-ttu-id="61654-101">클래스 또는 파생 클래스에 대 한 구성을 제공 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> 합니다.</span><span class="sxs-lookup"><span data-stu-id="61654-101">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionTokenRequirement>**  
  
## <a name="syntax"></a><span data-ttu-id="61654-102">구문</span><span class="sxs-lookup"><span data-stu-id="61654-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="61654-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="61654-103">Attributes and Elements</span></span>  
 <span data-ttu-id="61654-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="61654-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="61654-105">특성</span><span class="sxs-lookup"><span data-stu-id="61654-105">Attributes</span></span>  
  
|<span data-ttu-id="61654-106">attribute</span><span class="sxs-lookup"><span data-stu-id="61654-106">Attribute</span></span>|<span data-ttu-id="61654-107">Description</span><span class="sxs-lookup"><span data-stu-id="61654-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="61654-108">lifetime</span><span class="sxs-lookup"><span data-stu-id="61654-108">lifetime</span></span>|<span data-ttu-id="61654-109">세션 토큰의 수명을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="61654-109">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="61654-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="61654-110">Child Elements</span></span>  
 <span data-ttu-id="61654-111">None</span><span class="sxs-lookup"><span data-stu-id="61654-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="61654-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="61654-112">Parent Elements</span></span>  
  
|<span data-ttu-id="61654-113">요소</span><span class="sxs-lookup"><span data-stu-id="61654-113">Element</span></span>|<span data-ttu-id="61654-114">Description</span><span class="sxs-lookup"><span data-stu-id="61654-114">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="61654-115">지정 된 보안 토큰 처리기를 토큰 처리기 컬렉션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="61654-115">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="61654-116">예제</span><span class="sxs-lookup"><span data-stu-id="61654-116">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
