---
title: <webRequestModules> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webRequestModules
helpviewer_keywords:
- webRequestModules element
- <webRequestModules> element
ms.assetid: 1263de11-3e0a-4f94-97c9-710b2ae53817
ms.openlocfilehash: e5d1780a204b2e99593d51179a479845fd49e608
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59187007"
---
# <a name="webrequestmodules-element-network-settings"></a><span data-ttu-id="0c066-102">\<webRequestModules > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="0c066-102">\<webRequestModules> Element (Network Settings)</span></span>
<span data-ttu-id="0c066-103">네트워크 호스트에서 정보를 요청 하는 데는 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c066-103">Specifies modules to use to request information from network hosts.</span></span>  
  
 <span data-ttu-id="0c066-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="0c066-104">\<configuration></span></span>  
<span data-ttu-id="0c066-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="0c066-105">\<system.net></span></span>  
<span data-ttu-id="0c066-106">\<webRequestModules></span><span class="sxs-lookup"><span data-stu-id="0c066-106">\<webRequestModules></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c066-107">구문</span><span class="sxs-lookup"><span data-stu-id="0c066-107">Syntax</span></span>  
  
```xml  
<webRequestModules>   
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c066-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0c066-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0c066-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0c066-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c066-110">특성</span><span class="sxs-lookup"><span data-stu-id="0c066-110">Attributes</span></span>  
 <span data-ttu-id="0c066-111">없음</span><span class="sxs-lookup"><span data-stu-id="0c066-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0c066-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0c066-112">Child Elements</span></span>  
  
|<span data-ttu-id="0c066-113">**요소**</span><span class="sxs-lookup"><span data-stu-id="0c066-113">**Element**</span></span>|<span data-ttu-id="0c066-114">**설명**</span><span class="sxs-lookup"><span data-stu-id="0c066-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="0c066-115">add</span><span class="sxs-lookup"><span data-stu-id="0c066-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="0c066-116">응용 프로그램에 사용자 지정 웹 요청 모듈을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0c066-116">Adds a custom Web request module to the application.</span></span>|  
|[<span data-ttu-id="0c066-117">clear</span><span class="sxs-lookup"><span data-stu-id="0c066-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="0c066-118">응용 프로그램에서 등록 된 모든 웹 요청 모듈을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="0c066-118">Removes all registered Web request modules from the application.</span></span>|  
|[<span data-ttu-id="0c066-119">remove</span><span class="sxs-lookup"><span data-stu-id="0c066-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="0c066-120">응용 프로그램에서 사용자 지정 웹 요청 모듈을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="0c066-120">Removes a custom Web request module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0c066-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0c066-121">Parent Elements</span></span>  
  
|<span data-ttu-id="0c066-122">**요소**</span><span class="sxs-lookup"><span data-stu-id="0c066-122">**Element**</span></span>|<span data-ttu-id="0c066-123">**설명**</span><span class="sxs-lookup"><span data-stu-id="0c066-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="0c066-124">system.net</span><span class="sxs-lookup"><span data-stu-id="0c066-124">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="0c066-125">.NET Framework의 네트워크 연결 방법을 지정하는 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0c066-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c066-126">설명</span><span class="sxs-lookup"><span data-stu-id="0c066-126">Remarks</span></span>  
 <span data-ttu-id="0c066-127">`webRequestModules` 요소는 <xref:System.Net.WebRequest> 클래스의 하위 클래스를 등록하여 네트워크 호스트로의 정보 요청을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="0c066-127">The `webRequestModules` element registers descendants of the <xref:System.Net.WebRequest> class to handle information requests to network hosts.</span></span> <span data-ttu-id="0c066-128">웹 요청 모듈을 구현 해야 합니다는 <xref:System.Net.IWebRequestCreate> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="0c066-128">Web request modules must implement the <xref:System.Net.IWebRequestCreate> interface.</span></span>  
  
 <span data-ttu-id="0c066-129">로 시작 하는 Uri에 대 한 웹 요청 모듈을 포함 하는.NET Framework `http://`하십시오 `https://`, 및 `file://`합니다.</span><span class="sxs-lookup"><span data-stu-id="0c066-129">The .NET Framework includes Web request modules for URIs that begin with `http://`, `https://`, and `file://`.</span></span> <span data-ttu-id="0c066-130">구성 파일에서 사용자 지정 모듈을 등록에 의해서만 기본 모듈을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c066-130">You can override the default modules only by registering a custom module in the configuration file.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="0c066-131">구성 파일</span><span class="sxs-lookup"><span data-stu-id="0c066-131">Configuration Files</span></span>  
 <span data-ttu-id="0c066-132">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c066-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c066-133">예제</span><span class="sxs-lookup"><span data-stu-id="0c066-133">Example</span></span>  
 <span data-ttu-id="0c066-134">다음 예제에서는 기본 HTTP 모듈을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="0c066-134">The following example registers the default HTTP module.</span></span> <span data-ttu-id="0c066-135">지정된 된 모듈에 대 한 올바른 값을 사용 하 여 PublicKeyToken 및 버전에 대 한 값을 바꿔야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c066-135">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0c066-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="0c066-136">See also</span></span>

- <xref:System.Net.WebRequest>
- <xref:System.Net.IWebRequestCreate>
- [<span data-ttu-id="0c066-137">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="0c066-137">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
