---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: 254d34149892abeaf31b9227f7567eb0a66ec0b6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943672"
---
# <a name="sessiontokenrequirement"></a><span data-ttu-id="0e9f1-101">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="0e9f1-101">\<sessionTokenRequirement></span></span>
<span data-ttu-id="0e9f1-102"><xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> 클래스 또는 파생 클래스에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e9f1-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="0e9f1-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="0e9f1-103">\<system.identityModel></span></span>  
<span data-ttu-id="0e9f1-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="0e9f1-104">\<identityConfiguration></span></span>  
<span data-ttu-id="0e9f1-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="0e9f1-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="0e9f1-106">\<add></span><span class="sxs-lookup"><span data-stu-id="0e9f1-106">\<add></span></span>  
<span data-ttu-id="0e9f1-107">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="0e9f1-107">\<sessionTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e9f1-108">구문</span><span class="sxs-lookup"><span data-stu-id="0e9f1-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0e9f1-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0e9f1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0e9f1-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0e9f1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0e9f1-111">특성</span><span class="sxs-lookup"><span data-stu-id="0e9f1-111">Attributes</span></span>  
  
|<span data-ttu-id="0e9f1-112">특성</span><span class="sxs-lookup"><span data-stu-id="0e9f1-112">Attribute</span></span>|<span data-ttu-id="0e9f1-113">Description</span><span class="sxs-lookup"><span data-stu-id="0e9f1-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0e9f1-114">lifetime</span><span class="sxs-lookup"><span data-stu-id="0e9f1-114">lifetime</span></span>|<span data-ttu-id="0e9f1-115">세션 토큰의 수명을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e9f1-115">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0e9f1-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0e9f1-116">Child Elements</span></span>  
 <span data-ttu-id="0e9f1-117">없음</span><span class="sxs-lookup"><span data-stu-id="0e9f1-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0e9f1-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0e9f1-118">Parent Elements</span></span>  
  
|<span data-ttu-id="0e9f1-119">요소</span><span class="sxs-lookup"><span data-stu-id="0e9f1-119">Element</span></span>|<span data-ttu-id="0e9f1-120">설명</span><span class="sxs-lookup"><span data-stu-id="0e9f1-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0e9f1-121">\<add></span><span class="sxs-lookup"><span data-stu-id="0e9f1-121">\<add></span></span>](add.md)|<span data-ttu-id="0e9f1-122">지정 된 보안 토큰 처리기를 토큰 처리기 컬렉션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e9f1-122">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0e9f1-123">예제</span><span class="sxs-lookup"><span data-stu-id="0e9f1-123">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
