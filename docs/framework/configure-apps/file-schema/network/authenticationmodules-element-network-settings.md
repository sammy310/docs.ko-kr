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
ms.openlocfilehash: bacaaf92464a355804a9ea8307f6e6f1caac1f05
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087606"
---
# <a name="authenticationmodules-element-network-settings"></a><span data-ttu-id="1de6d-102">\<authenticationModules > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="1de6d-102">\<authenticationModules> Element (Network Settings)</span></span>
<span data-ttu-id="1de6d-103">네트워크 요청을 인증 하는 데 사용 되는 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de6d-103">Specifies modules used to authenticate network requests.</span></span>  

<span data-ttu-id="1de6d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1de6d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1de6d-105">&nbsp;[ **\<.net >를**](system-net-element-network-settings.md) &nbsp;</span><span class="sxs-lookup"><span data-stu-id="1de6d-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="1de6d-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<authenticationModules >**</span><span class="sxs-lookup"><span data-stu-id="1de6d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<authenticationModules>**</span></span>

## <a name="syntax"></a><span data-ttu-id="1de6d-107">구문</span><span class="sxs-lookup"><span data-stu-id="1de6d-107">Syntax</span></span>  
  
```xml  
<authenticationModules>   
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1de6d-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1de6d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1de6d-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1de6d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1de6d-110">특성</span><span class="sxs-lookup"><span data-stu-id="1de6d-110">Attributes</span></span>  
 <span data-ttu-id="1de6d-111">없음.</span><span class="sxs-lookup"><span data-stu-id="1de6d-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1de6d-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1de6d-112">Child Elements</span></span>  
  
|<span data-ttu-id="1de6d-113">**요소**</span><span class="sxs-lookup"><span data-stu-id="1de6d-113">**Element**</span></span>|<span data-ttu-id="1de6d-114">**설명**</span><span class="sxs-lookup"><span data-stu-id="1de6d-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="1de6d-115">add</span><span class="sxs-lookup"><span data-stu-id="1de6d-115">add</span></span>](add-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="1de6d-116">응용 프로그램에 인증 모듈을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de6d-116">Adds an authentication module to the application.</span></span>|  
|[<span data-ttu-id="1de6d-117">clear</span><span class="sxs-lookup"><span data-stu-id="1de6d-117">clear</span></span>](clear-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="1de6d-118">응용 프로그램에서 모든 인증 모듈을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="1de6d-118">Clears all authentication modules from the application.</span></span>|  
|[<span data-ttu-id="1de6d-119">remove</span><span class="sxs-lookup"><span data-stu-id="1de6d-119">remove</span></span>](remove-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="1de6d-120">응용 프로그램에서 인증 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de6d-120">Removes an authentication module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1de6d-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1de6d-121">Parent Elements</span></span>  
  
|<span data-ttu-id="1de6d-122">**요소**</span><span class="sxs-lookup"><span data-stu-id="1de6d-122">**Element**</span></span>|<span data-ttu-id="1de6d-123">**설명**</span><span class="sxs-lookup"><span data-stu-id="1de6d-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="1de6d-124">system.net</span><span class="sxs-lookup"><span data-stu-id="1de6d-124">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="1de6d-125">.NET Framework의 네트워크 연결 방법을 지정하는 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1de6d-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1de6d-126">주의</span><span class="sxs-lookup"><span data-stu-id="1de6d-126">Remarks</span></span>  
 <span data-ttu-id="1de6d-127">`authenticationModule` 요소는 서버를 사용 하 여 인증 프로세스를 수행 하는 인증 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de6d-127">The `authenticationModule` element specifies the authentication modules that conduct the authentication process with a server.</span></span> <span data-ttu-id="1de6d-128">인증 모듈은 <xref:System.Net.IAuthenticationModule> 인터페이스를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de6d-128">An authentication module must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="1de6d-129">구성 파일</span><span class="sxs-lookup"><span data-stu-id="1de6d-129">Configuration Files</span></span>  
 <span data-ttu-id="1de6d-130">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1de6d-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1de6d-131">예제</span><span class="sxs-lookup"><span data-stu-id="1de6d-131">Example</span></span>  
 <span data-ttu-id="1de6d-132">다음 예에서는 인증 모듈을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de6d-132">The following example enables an authentication module.</span></span> <span data-ttu-id="1de6d-133">Version 및 PublicKeyToken의 값을 지정 된 모듈의 올바른 값으로 바꾸어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de6d-133">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1de6d-134">참조</span><span class="sxs-lookup"><span data-stu-id="1de6d-134">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="1de6d-135">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="1de6d-135">Network Settings Schema</span></span>](index.md)
