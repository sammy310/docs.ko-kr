---
description: '자세한 정보: <clear> authenticationModules의 요소 (네트워크 설정)'
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
ms.openlocfilehash: ccfc9f53ef53268cdb1155673fc47a862a63419c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698572"
---
# <a name="clear-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="4b077-103">authenticationModules의 \<clear> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="4b077-103">\<clear> Element for authenticationModules (Network Settings)</span></span>

<span data-ttu-id="4b077-104">응용 프로그램에서 모든 인증 모듈을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="4b077-104">Clears all authentication modules from the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="4b077-105">구문</span><span class="sxs-lookup"><span data-stu-id="4b077-105">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4b077-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4b077-106">Attributes and Elements</span></span>  

 <span data-ttu-id="4b077-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4b077-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4b077-108">특성</span><span class="sxs-lookup"><span data-stu-id="4b077-108">Attributes</span></span>  

 <span data-ttu-id="4b077-109">없음</span><span class="sxs-lookup"><span data-stu-id="4b077-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4b077-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4b077-110">Child Elements</span></span>  

 <span data-ttu-id="4b077-111">없음</span><span class="sxs-lookup"><span data-stu-id="4b077-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4b077-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4b077-112">Parent Elements</span></span>  
  
|<span data-ttu-id="4b077-113">**요소**</span><span class="sxs-lookup"><span data-stu-id="4b077-113">**Element**</span></span>|<span data-ttu-id="4b077-114">**설명**</span><span class="sxs-lookup"><span data-stu-id="4b077-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4b077-115">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="4b077-115">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="4b077-116">네트워크 요청을 인증 하는 데 사용 되는 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b077-116">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b077-117">설명</span><span class="sxs-lookup"><span data-stu-id="4b077-117">Remarks</span></span>  

 <span data-ttu-id="4b077-118">요소는 구성 `clear` 파일 또는 구성 계층 구조에서 더 높은 수준에서 정의 된 모든 인증 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b077-118">The `clear` element removes all authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4b077-119">구성 파일</span><span class="sxs-lookup"><span data-stu-id="4b077-119">Configuration Files</span></span>  

 <span data-ttu-id="4b077-120">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b077-120">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b077-121">예제</span><span class="sxs-lookup"><span data-stu-id="4b077-121">Example</span></span>  

 <span data-ttu-id="4b077-122">다음 예제에서는 구성 된 모든 인증 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b077-122">The following example removes all configured authentication modules.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <clear/>  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4b077-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b077-123">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="4b077-124">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="4b077-124">Network Settings Schema</span></span>](index.md)
