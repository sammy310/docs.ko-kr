---
title: authenticationModules의 <clear> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- clear element, authenticationModules
- <authenticationModules>, clear element
- <clear> element, authenticationModules
- authenticationModules, clear element
ms.assetid: dc522c45-4a80-4831-8955-f7b68a47edfd
ms.openlocfilehash: e3abd1b4c76ebda885703ccf961d58657b582f19
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087507"
---
# <a name="clear-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="912ed-102">authenticationModules의 \<clear > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="912ed-102">\<clear> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="912ed-103">응용 프로그램에서 모든 인증 모듈을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="912ed-103">Clears all authentication modules from the application.</span></span>  

<span data-ttu-id="912ed-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="912ed-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="912ed-105">&nbsp;[ **\<.net >를**](system-net-element-network-settings.md) &nbsp;</span><span class="sxs-lookup"><span data-stu-id="912ed-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="912ed-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**authenticationModules**](authenticationmodules-element-network-settings.md) ></span><span class="sxs-lookup"><span data-stu-id="912ed-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)\</span></span>
<span data-ttu-id="912ed-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="912ed-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="912ed-108">구문</span><span class="sxs-lookup"><span data-stu-id="912ed-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="912ed-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="912ed-109">Attributes and Elements</span></span>  
 <span data-ttu-id="912ed-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="912ed-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="912ed-111">특성</span><span class="sxs-lookup"><span data-stu-id="912ed-111">Attributes</span></span>  
 <span data-ttu-id="912ed-112">없음.</span><span class="sxs-lookup"><span data-stu-id="912ed-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="912ed-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="912ed-113">Child Elements</span></span>  
 <span data-ttu-id="912ed-114">없음.</span><span class="sxs-lookup"><span data-stu-id="912ed-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="912ed-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="912ed-115">Parent Elements</span></span>  
  
|<span data-ttu-id="912ed-116">**요소**</span><span class="sxs-lookup"><span data-stu-id="912ed-116">**Element**</span></span>|<span data-ttu-id="912ed-117">**설명**</span><span class="sxs-lookup"><span data-stu-id="912ed-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="912ed-118">Authenticationmodules></span><span class="sxs-lookup"><span data-stu-id="912ed-118">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="912ed-119">네트워크 요청을 인증 하는 데 사용 되는 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="912ed-119">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="912ed-120">주의</span><span class="sxs-lookup"><span data-stu-id="912ed-120">Remarks</span></span>  
 <span data-ttu-id="912ed-121">`clear` 요소는 구성 파일에서 이전에 정의 되었거나 구성 계층 구조에서 상위 수준에 정의 된 모든 인증 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="912ed-121">The `clear` element removes all authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="912ed-122">구성 파일</span><span class="sxs-lookup"><span data-stu-id="912ed-122">Configuration Files</span></span>  
 <span data-ttu-id="912ed-123">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="912ed-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="912ed-124">예제</span><span class="sxs-lookup"><span data-stu-id="912ed-124">Example</span></span>  
 <span data-ttu-id="912ed-125">다음 예제에서는 구성 된 모든 인증 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="912ed-125">The following example removes all configured authentication modules.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <clear/>  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="912ed-126">참조</span><span class="sxs-lookup"><span data-stu-id="912ed-126">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="912ed-127">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="912ed-127">Network Settings Schema</span></span>](index.md)
