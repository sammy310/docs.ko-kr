---
description: '다음에 대 한 자세한 정보: <webRequestModules> 요소 (네트워크 설정)'
title: <webRequestModules> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webRequestModules
helpviewer_keywords:
- webRequestModules element
- <webRequestModules> element
ms.assetid: 1263de11-3e0a-4f94-97c9-710b2ae53817
ms.openlocfilehash: 851aec2bf38910239874cb5792239a48de6efb70
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698429"
---
# <a name="webrequestmodules-element-network-settings"></a><span data-ttu-id="d2ad5-103">\<webRequestModules> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="d2ad5-103">\<webRequestModules> Element (Network Settings)</span></span>

<span data-ttu-id="d2ad5-104">네트워크 호스트의 정보를 요청 하는 데 사용할 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2ad5-104">Specifies modules to use to request information from network hosts.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;\<webRequestModules>  
  
## <a name="syntax"></a><span data-ttu-id="d2ad5-105">구문</span><span class="sxs-lookup"><span data-stu-id="d2ad5-105">Syntax</span></span>  
  
```xml  
<webRequestModules>
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d2ad5-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d2ad5-106">Attributes and Elements</span></span>  

 <span data-ttu-id="d2ad5-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d2ad5-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d2ad5-108">특성</span><span class="sxs-lookup"><span data-stu-id="d2ad5-108">Attributes</span></span>  

 <span data-ttu-id="d2ad5-109">없음</span><span class="sxs-lookup"><span data-stu-id="d2ad5-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d2ad5-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d2ad5-110">Child Elements</span></span>  
  
|<span data-ttu-id="d2ad5-111">**요소**</span><span class="sxs-lookup"><span data-stu-id="d2ad5-111">**Element**</span></span>|<span data-ttu-id="d2ad5-112">**설명**</span><span class="sxs-lookup"><span data-stu-id="d2ad5-112">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d2ad5-113">add</span><span class="sxs-lookup"><span data-stu-id="d2ad5-113">add</span></span>](add-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="d2ad5-114">응용 프로그램에 사용자 지정 웹 요청 모듈을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2ad5-114">Adds a custom Web request module to the application.</span></span>|  
|[<span data-ttu-id="d2ad5-115">clear</span><span class="sxs-lookup"><span data-stu-id="d2ad5-115">clear</span></span>](clear-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="d2ad5-116">응용 프로그램에서 등록 된 모든 웹 요청 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2ad5-116">Removes all registered Web request modules from the application.</span></span>|  
|[<span data-ttu-id="d2ad5-117">remove</span><span class="sxs-lookup"><span data-stu-id="d2ad5-117">remove</span></span>](remove-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="d2ad5-118">응용 프로그램에서 사용자 지정 웹 요청 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2ad5-118">Removes a custom Web request module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d2ad5-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d2ad5-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d2ad5-120">**요소**</span><span class="sxs-lookup"><span data-stu-id="d2ad5-120">**Element**</span></span>|<span data-ttu-id="d2ad5-121">**설명**</span><span class="sxs-lookup"><span data-stu-id="d2ad5-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d2ad5-122">system.net</span><span class="sxs-lookup"><span data-stu-id="d2ad5-122">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="d2ad5-123">.NET Framework의 네트워크 연결 방법을 지정하는 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d2ad5-123">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2ad5-124">설명</span><span class="sxs-lookup"><span data-stu-id="d2ad5-124">Remarks</span></span>  

 <span data-ttu-id="d2ad5-125">`webRequestModules` 요소는 <xref:System.Net.WebRequest> 클래스의 하위 클래스를 등록하여 네트워크 호스트로의 정보 요청을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="d2ad5-125">The `webRequestModules` element registers descendants of the <xref:System.Net.WebRequest> class to handle information requests to network hosts.</span></span> <span data-ttu-id="d2ad5-126">웹 요청 모듈은 인터페이스를 구현 해야 합니다 <xref:System.Net.IWebRequestCreate> .</span><span class="sxs-lookup"><span data-stu-id="d2ad5-126">Web request modules must implement the <xref:System.Net.IWebRequestCreate> interface.</span></span>  
  
 <span data-ttu-id="d2ad5-127">.NET Framework에는, 및로 시작 하는 Uri에 대 한 웹 요청 모듈이 포함 되어 있습니다 `http://` `https://` `file://` .</span><span class="sxs-lookup"><span data-stu-id="d2ad5-127">The .NET Framework includes Web request modules for URIs that begin with `http://`, `https://`, and `file://`.</span></span> <span data-ttu-id="d2ad5-128">구성 파일에서 사용자 지정 모듈을 등록 하 여 기본 모듈만 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2ad5-128">You can override the default modules only by registering a custom module in the configuration file.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="d2ad5-129">구성 파일</span><span class="sxs-lookup"><span data-stu-id="d2ad5-129">Configuration Files</span></span>  

 <span data-ttu-id="d2ad5-130">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2ad5-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2ad5-131">예제</span><span class="sxs-lookup"><span data-stu-id="d2ad5-131">Example</span></span>  

 <span data-ttu-id="d2ad5-132">다음 예제에서는 기본 HTTP 모듈을 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2ad5-132">The following example registers the default HTTP module.</span></span> <span data-ttu-id="d2ad5-133">Version 및 PublicKeyToken의 값을 지정 된 모듈의 올바른 값으로 바꾸어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2ad5-133">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d2ad5-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d2ad5-134">See also</span></span>

- <xref:System.Net.WebRequest>
- <xref:System.Net.IWebRequestCreate>
- [<span data-ttu-id="d2ad5-135">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="d2ad5-135">Network Settings Schema</span></span>](index.md)
