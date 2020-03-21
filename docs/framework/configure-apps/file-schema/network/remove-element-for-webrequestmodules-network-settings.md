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
ms.openlocfilehash: afa1aef8ea71f43a136987ec5b6e1925c6d9fb40
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154727"
---
# <a name="remove-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="4c8fd-102">\<웹요청모듈(네트워크 설정)에 대한> 요소 제거</span><span class="sxs-lookup"><span data-stu-id="4c8fd-102">\<remove> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="4c8fd-103">응용 프로그램에서 사용자 지정 웹 요청 모듈을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="4c8fd-103">Removes a custom Web request module from the application.</span></span>  
  
<span data-ttu-id="4c8fd-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4c8fd-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4c8fd-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="4c8fd-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="4c8fd-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<웹 리퍼모듈>**](webrequestmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="4c8fd-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="4c8fd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>제거**</span><span class="sxs-lookup"><span data-stu-id="4c8fd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="4c8fd-108">구문</span><span class="sxs-lookup"><span data-stu-id="4c8fd-108">Syntax</span></span>  
  
```xml  
<remove
  prefix="URI prefix"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c8fd-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4c8fd-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4c8fd-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4c8fd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4c8fd-111">특성</span><span class="sxs-lookup"><span data-stu-id="4c8fd-111">Attributes</span></span>  
  
|<span data-ttu-id="4c8fd-112">**특성**</span><span class="sxs-lookup"><span data-stu-id="4c8fd-112">**Attribute**</span></span>|<span data-ttu-id="4c8fd-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="4c8fd-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="4c8fd-114">이 웹 요청 모듈에서 처리하는 요청에 대한 URI 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="4c8fd-114">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4c8fd-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4c8fd-115">Child Elements</span></span>  
 <span data-ttu-id="4c8fd-116">없음</span><span class="sxs-lookup"><span data-stu-id="4c8fd-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4c8fd-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4c8fd-117">Parent Elements</span></span>  
  
|<span data-ttu-id="4c8fd-118">**요소**</span><span class="sxs-lookup"><span data-stu-id="4c8fd-118">**Element**</span></span>|<span data-ttu-id="4c8fd-119">**설명**</span><span class="sxs-lookup"><span data-stu-id="4c8fd-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4c8fd-120">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="4c8fd-120">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="4c8fd-121">네트워크 호스트에서 정보를 요청하는 데 사용할 모듈을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4c8fd-121">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c8fd-122">설명</span><span class="sxs-lookup"><span data-stu-id="4c8fd-122">Remarks</span></span>  
 <span data-ttu-id="4c8fd-123">`remove` 요소는 지정된 URI 접두사에 대해 등록된 웹 요청 모듈을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="4c8fd-123">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="4c8fd-124">특성의 `prefix` 값은 유효한 URI의 선행 문자(예: "`http`" 또는`http://www.contoso.com`"")여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c8fd-124">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "`http`", or "`http://www.contoso.com`".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4c8fd-125">구성 파일</span><span class="sxs-lookup"><span data-stu-id="4c8fd-125">Configuration Files</span></span>  
 <span data-ttu-id="4c8fd-126">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c8fd-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c8fd-127">예제</span><span class="sxs-lookup"><span data-stu-id="4c8fd-127">Example</span></span>  

<span data-ttu-id="4c8fd-128">다음 예제는 HTTP에 대한 기존 웹 요청 모듈을 제거한 다음 HTTP `www.contoso.com`요청에 대한 새 사용자 지정 웹 요청 모듈을 에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="4c8fd-128">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to `www.contoso.com`.</span></span>
  
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
  
## <a name="see-also"></a><span data-ttu-id="4c8fd-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4c8fd-129">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="4c8fd-130">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="4c8fd-130">Network Settings Schema</span></span>](index.md)
