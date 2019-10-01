---
title: webRequestModules의 <remove> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, webRequestModules
- webRequestModules, remove element
- <remove> element, webRequestModules
- <webRequestModules>, remove element
ms.assetid: dd84d2fe-2f4f-457a-9d3c-441d0d21cc10
ms.openlocfilehash: f8209ea89ac8cd214389feddee8c475e10bc939a
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697812"
---
# <a name="remove-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="3e7b9-102">\<webrequestmodules의 > 요소 제거 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="3e7b9-102">\<remove> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="3e7b9-103">응용 프로그램에서 사용자 지정 웹 요청 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e7b9-103">Removes a custom Web request module from the application.</span></span>  
  
[<span data-ttu-id="3e7b9-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="3e7b9-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="3e7b9-105">&nbsp; @ no__t-1[ **@no__t -4c.net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="3e7b9-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="3e7b9-106">&nbsp; @ no__t-1 @ no__t @ no__t[ **\<webRequestModules >** ](webrequestmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="3e7b9-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)</span></span>  
<span data-ttu-id="3e7b9-107">&nbsp; @ no__t-1 @ no__t @ no__t @ @ no__t-4 @ no__t-5 **\<remove >**</span><span class="sxs-lookup"><span data-stu-id="3e7b9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e7b9-108">구문</span><span class="sxs-lookup"><span data-stu-id="3e7b9-108">Syntax</span></span>  
  
```xml  
<remove   
  prefix="URI prefix"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3e7b9-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3e7b9-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3e7b9-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3e7b9-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3e7b9-111">특성</span><span class="sxs-lookup"><span data-stu-id="3e7b9-111">Attributes</span></span>  
  
|<span data-ttu-id="3e7b9-112">**특성**</span><span class="sxs-lookup"><span data-stu-id="3e7b9-112">**Attribute**</span></span>|<span data-ttu-id="3e7b9-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="3e7b9-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="3e7b9-114">이 웹 요청 모듈에서 처리 하는 요청의 URI 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="3e7b9-114">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3e7b9-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3e7b9-115">Child Elements</span></span>  
 <span data-ttu-id="3e7b9-116">없음</span><span class="sxs-lookup"><span data-stu-id="3e7b9-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3e7b9-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3e7b9-117">Parent Elements</span></span>  
  
|<span data-ttu-id="3e7b9-118">**요소**</span><span class="sxs-lookup"><span data-stu-id="3e7b9-118">**Element**</span></span>|<span data-ttu-id="3e7b9-119">**설명**</span><span class="sxs-lookup"><span data-stu-id="3e7b9-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="3e7b9-120">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="3e7b9-120">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="3e7b9-121">네트워크 호스트의 정보를 요청 하는 데 사용할 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e7b9-121">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e7b9-122">설명</span><span class="sxs-lookup"><span data-stu-id="3e7b9-122">Remarks</span></span>  
 <span data-ttu-id="3e7b9-123">@No__t-0 요소는 지정 된 URI 접두사에 대해 등록 된 웹 요청 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e7b9-123">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="3e7b9-124">@No__t-0 특성의 값은 유효한 URI (예: "`http`" 또는 "`http://www.contoso.com`")의 선행 문자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e7b9-124">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "`http`", or "`http://www.contoso.com`".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="3e7b9-125">구성 파일</span><span class="sxs-lookup"><span data-stu-id="3e7b9-125">Configuration Files</span></span>  
 <span data-ttu-id="3e7b9-126">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e7b9-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e7b9-127">예제</span><span class="sxs-lookup"><span data-stu-id="3e7b9-127">Example</span></span>  

<span data-ttu-id="3e7b9-128">다음 예제에서는 HTTP에 대 한 기존 웹 요청 모듈을 제거한 다음 `www.contoso.com`에 HTTP 요청에 대 한 새 사용자 지정 웹 요청 모듈을 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e7b9-128">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to `www.contoso.com`.</span></span>
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <remove prefix="http">  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3e7b9-129">참조</span><span class="sxs-lookup"><span data-stu-id="3e7b9-129">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="3e7b9-130">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="3e7b9-130">Network Settings Schema</span></span>](index.md)
