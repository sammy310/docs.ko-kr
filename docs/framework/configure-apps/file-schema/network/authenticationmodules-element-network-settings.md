---
description: '다음에 대 한 자세한 정보: <authenticationModules> 요소 (네트워크 설정)'
title: <authenticationModules> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#authenticationModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules
helpviewer_keywords:
- authenticationModules element
- <authenticationModules> element
ms.assetid: 10fcfaad-82ef-4692-871a-0aec9dfbe75e
ms.openlocfilehash: 2c2dc3c6a3d8fc064bb24c3d86a4441c269e43f0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698612"
---
# <a name="authenticationmodules-element-network-settings"></a><span data-ttu-id="8dd07-103">\<authenticationModules> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="8dd07-103">\<authenticationModules> Element (Network Settings)</span></span>

<span data-ttu-id="8dd07-104">네트워크 요청을 인증 하는 데 사용 되는 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd07-104">Specifies modules used to authenticate network requests.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<authenticationModules>**

## <a name="syntax"></a><span data-ttu-id="8dd07-105">구문</span><span class="sxs-lookup"><span data-stu-id="8dd07-105">Syntax</span></span>  
  
```xml  
<authenticationModules>
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8dd07-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8dd07-106">Attributes and Elements</span></span>  

 <span data-ttu-id="8dd07-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd07-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8dd07-108">특성</span><span class="sxs-lookup"><span data-stu-id="8dd07-108">Attributes</span></span>  

 <span data-ttu-id="8dd07-109">없음</span><span class="sxs-lookup"><span data-stu-id="8dd07-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8dd07-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8dd07-110">Child Elements</span></span>  
  
|<span data-ttu-id="8dd07-111">**요소**</span><span class="sxs-lookup"><span data-stu-id="8dd07-111">**Element**</span></span>|<span data-ttu-id="8dd07-112">**설명**</span><span class="sxs-lookup"><span data-stu-id="8dd07-112">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8dd07-113">add</span><span class="sxs-lookup"><span data-stu-id="8dd07-113">add</span></span>](add-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="8dd07-114">응용 프로그램에 인증 모듈을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd07-114">Adds an authentication module to the application.</span></span>|  
|[<span data-ttu-id="8dd07-115">clear</span><span class="sxs-lookup"><span data-stu-id="8dd07-115">clear</span></span>](clear-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="8dd07-116">응용 프로그램에서 모든 인증 모듈을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="8dd07-116">Clears all authentication modules from the application.</span></span>|  
|[<span data-ttu-id="8dd07-117">remove</span><span class="sxs-lookup"><span data-stu-id="8dd07-117">remove</span></span>](remove-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="8dd07-118">응용 프로그램에서 인증 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd07-118">Removes an authentication module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8dd07-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8dd07-119">Parent Elements</span></span>  
  
|<span data-ttu-id="8dd07-120">**요소**</span><span class="sxs-lookup"><span data-stu-id="8dd07-120">**Element**</span></span>|<span data-ttu-id="8dd07-121">**설명**</span><span class="sxs-lookup"><span data-stu-id="8dd07-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8dd07-122">system.net</span><span class="sxs-lookup"><span data-stu-id="8dd07-122">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="8dd07-123">.NET Framework의 네트워크 연결 방법을 지정하는 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd07-123">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8dd07-124">설명</span><span class="sxs-lookup"><span data-stu-id="8dd07-124">Remarks</span></span>  

 <span data-ttu-id="8dd07-125">요소는 서버를 사용 하 여 `authenticationModule` 인증 프로세스를 수행 하는 인증 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd07-125">The `authenticationModule` element specifies the authentication modules that conduct the authentication process with a server.</span></span> <span data-ttu-id="8dd07-126">인증 모듈은 인터페이스를 구현 해야 합니다 <xref:System.Net.IAuthenticationModule> .</span><span class="sxs-lookup"><span data-stu-id="8dd07-126">An authentication module must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="8dd07-127">구성 파일</span><span class="sxs-lookup"><span data-stu-id="8dd07-127">Configuration Files</span></span>  

 <span data-ttu-id="8dd07-128">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd07-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8dd07-129">예제</span><span class="sxs-lookup"><span data-stu-id="8dd07-129">Example</span></span>  

 <span data-ttu-id="8dd07-130">다음 예에서는 인증 모듈을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd07-130">The following example enables an authentication module.</span></span> <span data-ttu-id="8dd07-131">Version 및 PublicKeyToken의 값을 지정 된 모듈의 올바른 값으로 바꾸어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd07-131">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8dd07-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8dd07-132">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="8dd07-133">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="8dd07-133">Network Settings Schema</span></span>](index.md)
