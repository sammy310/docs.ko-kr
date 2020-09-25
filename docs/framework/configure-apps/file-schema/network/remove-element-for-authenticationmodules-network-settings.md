---
title: authenticationModules의 <remove> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, authenticationModules
- <authenticationModules>, remove element
- <remove> element, authenticationModules
- authenticationModules, remove element
ms.assetid: abf79949-b05c-465a-b51c-bbeda9a74173
ms.openlocfilehash: 0829f57d8dca91c2d895085dceaeea422229537c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176203"
---
# <a name="remove-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="8458b-102">authenticationModules의 \<remove> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="8458b-102">\<remove> Element for authenticationModules (Network Settings)</span></span>

<span data-ttu-id="8458b-103">응용 프로그램에서 인증 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="8458b-103">Removes an authentication module from the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="8458b-104">구문</span><span class="sxs-lookup"><span data-stu-id="8458b-104">Syntax</span></span>  
  
```xml  
<remove
   type="authentication module name"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8458b-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8458b-105">Attributes and Elements</span></span>  

 <span data-ttu-id="8458b-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8458b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8458b-107">특성</span><span class="sxs-lookup"><span data-stu-id="8458b-107">Attributes</span></span>  
  
|<span data-ttu-id="8458b-108">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="8458b-108">**Attribute**</span></span>|<span data-ttu-id="8458b-109">**설명**</span><span class="sxs-lookup"><span data-stu-id="8458b-109">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="8458b-110">**type**</span><span class="sxs-lookup"><span data-stu-id="8458b-110">**type**</span></span>|<span data-ttu-id="8458b-111">제거할 인증 모듈의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8458b-111">The name of the authentication module to remove.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8458b-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8458b-112">Child Elements</span></span>  

 <span data-ttu-id="8458b-113">없음</span><span class="sxs-lookup"><span data-stu-id="8458b-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8458b-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8458b-114">Parent Elements</span></span>  
  
|<span data-ttu-id="8458b-115">**요소**</span><span class="sxs-lookup"><span data-stu-id="8458b-115">**Element**</span></span>|<span data-ttu-id="8458b-116">**설명**</span><span class="sxs-lookup"><span data-stu-id="8458b-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8458b-117">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="8458b-117">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="8458b-118">네트워크 요청을 인증 하는 데 사용 되는 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8458b-118">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8458b-119">설명</span><span class="sxs-lookup"><span data-stu-id="8458b-119">Remarks</span></span>  

 <span data-ttu-id="8458b-120">요소는 구성 `remove` 파일에서 이전에 정의 되었거나 구성 계층 구조에서 상위 수준에 정의 된 인증 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="8458b-120">The `remove` element removes authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="8458b-121">특성 값은 `type` 올바른 클래스 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8458b-121">The value for the `type` attribute should be a valid class name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="8458b-122">구성 파일</span><span class="sxs-lookup"><span data-stu-id="8458b-122">Configuration Files</span></span>  

 <span data-ttu-id="8458b-123">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8458b-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8458b-124">예제</span><span class="sxs-lookup"><span data-stu-id="8458b-124">Example</span></span>  

 <span data-ttu-id="8458b-125">다음 예에서는 인증 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="8458b-125">The following example removes an authentication module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8458b-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8458b-126">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="8458b-127">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="8458b-127">Network Settings Schema</span></span>](index.md)
