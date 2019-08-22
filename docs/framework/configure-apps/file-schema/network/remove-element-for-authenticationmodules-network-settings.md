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
ms.openlocfilehash: 7f923ce73760fa42a2c435d346f9d1097a5ed82f
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664047"
---
# <a name="remove-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="b20fb-102">\<authenticationModules의 > 요소 제거 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="b20fb-102">\<remove> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="b20fb-103">응용 프로그램에서 인증 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b20fb-103">Removes an authentication module from the application.</span></span>  
  
 <span data-ttu-id="b20fb-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b20fb-104">\<configuration></span></span>  
<span data-ttu-id="b20fb-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="b20fb-105">\<system.net></span></span>  
<span data-ttu-id="b20fb-106">\<authenticationModules></span><span class="sxs-lookup"><span data-stu-id="b20fb-106">\<authenticationModules></span></span>  
<span data-ttu-id="b20fb-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="b20fb-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b20fb-108">구문</span><span class="sxs-lookup"><span data-stu-id="b20fb-108">Syntax</span></span>  
  
```xml  
<remove   
   type="authentication module name"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b20fb-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b20fb-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b20fb-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b20fb-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b20fb-111">특성</span><span class="sxs-lookup"><span data-stu-id="b20fb-111">Attributes</span></span>  
  
|<span data-ttu-id="b20fb-112">**특성**</span><span class="sxs-lookup"><span data-stu-id="b20fb-112">**Attribute**</span></span>|<span data-ttu-id="b20fb-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="b20fb-113">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="b20fb-114">**type**</span><span class="sxs-lookup"><span data-stu-id="b20fb-114">**type**</span></span>|<span data-ttu-id="b20fb-115">제거할 인증 모듈의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b20fb-115">The name of the authentication module to remove.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b20fb-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b20fb-116">Child Elements</span></span>  
 <span data-ttu-id="b20fb-117">없음</span><span class="sxs-lookup"><span data-stu-id="b20fb-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b20fb-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b20fb-118">Parent Elements</span></span>  
  
|<span data-ttu-id="b20fb-119">**요소**</span><span class="sxs-lookup"><span data-stu-id="b20fb-119">**Element**</span></span>|<span data-ttu-id="b20fb-120">**설명**</span><span class="sxs-lookup"><span data-stu-id="b20fb-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b20fb-121">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="b20fb-121">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="b20fb-122">네트워크 요청을 인증 하는 데 사용 되는 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b20fb-122">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b20fb-123">설명</span><span class="sxs-lookup"><span data-stu-id="b20fb-123">Remarks</span></span>  
 <span data-ttu-id="b20fb-124">요소 `remove` 는 구성 파일에서 이전에 정의 되었거나 구성 계층 구조에서 상위 수준에 정의 된 인증 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b20fb-124">The `remove` element removes authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="b20fb-125">`type` 특성 값은 올바른 클래스 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b20fb-125">The value for the `type` attribute should be a valid class name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b20fb-126">구성 파일</span><span class="sxs-lookup"><span data-stu-id="b20fb-126">Configuration Files</span></span>  
 <span data-ttu-id="b20fb-127">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b20fb-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b20fb-128">예제</span><span class="sxs-lookup"><span data-stu-id="b20fb-128">Example</span></span>  
 <span data-ttu-id="b20fb-129">다음 예에서는 인증 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b20fb-129">The following example removes an authentication module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b20fb-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="b20fb-130">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="b20fb-131">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="b20fb-131">Network Settings Schema</span></span>](index.md)
