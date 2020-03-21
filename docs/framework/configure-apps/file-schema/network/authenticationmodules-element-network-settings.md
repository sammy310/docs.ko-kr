---
title: <authenticationModules> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#authenticationModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules
helpviewer_keywords:
- authenticationModules element
- <authenticationModules> element
ms.assetid: 10fcfaad-82ef-4692-871a-0aec9dfbe75e
ms.openlocfilehash: b502cc4a0958f074018d4b0ce6b3fb118b811c2f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154974"
---
# <a name="authenticationmodules-element-network-settings"></a><span data-ttu-id="5bbe6-102">\<authenticationModules> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="5bbe6-102">\<authenticationModules> Element (Network Settings)</span></span>
<span data-ttu-id="5bbe6-103">네트워크 요청을 인증하는 데 사용되는 모듈을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbe6-103">Specifies modules used to authenticate network requests.</span></span>  

<span data-ttu-id="5bbe6-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5bbe6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5bbe6-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="5bbe6-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="5bbe6-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<인증모듈>**</span><span class="sxs-lookup"><span data-stu-id="5bbe6-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<authenticationModules>**</span></span>

## <a name="syntax"></a><span data-ttu-id="5bbe6-107">구문</span><span class="sxs-lookup"><span data-stu-id="5bbe6-107">Syntax</span></span>  
  
```xml  
<authenticationModules>
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5bbe6-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5bbe6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5bbe6-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbe6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5bbe6-110">특성</span><span class="sxs-lookup"><span data-stu-id="5bbe6-110">Attributes</span></span>  
 <span data-ttu-id="5bbe6-111">없음</span><span class="sxs-lookup"><span data-stu-id="5bbe6-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5bbe6-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5bbe6-112">Child Elements</span></span>  
  
|<span data-ttu-id="5bbe6-113">**요소**</span><span class="sxs-lookup"><span data-stu-id="5bbe6-113">**Element**</span></span>|<span data-ttu-id="5bbe6-114">**설명**</span><span class="sxs-lookup"><span data-stu-id="5bbe6-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="5bbe6-115">추가</span><span class="sxs-lookup"><span data-stu-id="5bbe6-115">add</span></span>](add-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="5bbe6-116">응용 프로그램에 인증 모듈을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbe6-116">Adds an authentication module to the application.</span></span>|  
|[<span data-ttu-id="5bbe6-117">명확한</span><span class="sxs-lookup"><span data-stu-id="5bbe6-117">clear</span></span>](clear-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="5bbe6-118">응용 프로그램에서 모든 인증 모듈을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="5bbe6-118">Clears all authentication modules from the application.</span></span>|  
|[<span data-ttu-id="5bbe6-119">제거</span><span class="sxs-lookup"><span data-stu-id="5bbe6-119">remove</span></span>](remove-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="5bbe6-120">응용 프로그램에서 인증 모듈을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbe6-120">Removes an authentication module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5bbe6-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5bbe6-121">Parent Elements</span></span>  
  
|<span data-ttu-id="5bbe6-122">**요소**</span><span class="sxs-lookup"><span data-stu-id="5bbe6-122">**Element**</span></span>|<span data-ttu-id="5bbe6-123">**설명**</span><span class="sxs-lookup"><span data-stu-id="5bbe6-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="5bbe6-124">system.net</span><span class="sxs-lookup"><span data-stu-id="5bbe6-124">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="5bbe6-125">.NET Framework의 네트워크 연결 방법을 지정하는 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbe6-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5bbe6-126">설명</span><span class="sxs-lookup"><span data-stu-id="5bbe6-126">Remarks</span></span>  
 <span data-ttu-id="5bbe6-127">요소는 `authenticationModule` 서버에서 인증 프로세스를 수행하는 인증 모듈을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbe6-127">The `authenticationModule` element specifies the authentication modules that conduct the authentication process with a server.</span></span> <span data-ttu-id="5bbe6-128">인증 모듈은 인터페이스를 <xref:System.Net.IAuthenticationModule> 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbe6-128">An authentication module must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="5bbe6-129">구성 파일</span><span class="sxs-lookup"><span data-stu-id="5bbe6-129">Configuration Files</span></span>  
 <span data-ttu-id="5bbe6-130">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bbe6-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5bbe6-131">예제</span><span class="sxs-lookup"><span data-stu-id="5bbe6-131">Example</span></span>  
 <span data-ttu-id="5bbe6-132">다음 예제는 인증 모듈을 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbe6-132">The following example enables an authentication module.</span></span> <span data-ttu-id="5bbe6-133">버전 및 PublicKeyToken의 값을 지정된 모듈의 올바른 값으로 바꿔야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbe6-133">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5bbe6-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5bbe6-134">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="5bbe6-135">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="5bbe6-135">Network Settings Schema</span></span>](index.md)
