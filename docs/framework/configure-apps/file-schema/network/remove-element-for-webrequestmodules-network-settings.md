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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154727"
---
# <a name="remove-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="86123-102">webRequestModules의 \<remove> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="86123-102">\<remove> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="86123-103">응용 프로그램에서 사용자 지정 웹 요청 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="86123-103">Removes a custom Web request module from the application.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**
  
## <a name="syntax"></a><span data-ttu-id="86123-104">구문</span><span class="sxs-lookup"><span data-stu-id="86123-104">Syntax</span></span>  
  
```xml  
<remove
  prefix="URI prefix"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="86123-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="86123-105">Attributes and Elements</span></span>  
 <span data-ttu-id="86123-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="86123-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="86123-107">특성</span><span class="sxs-lookup"><span data-stu-id="86123-107">Attributes</span></span>  
  
|<span data-ttu-id="86123-108">**특성**</span><span class="sxs-lookup"><span data-stu-id="86123-108">**Attribute**</span></span>|<span data-ttu-id="86123-109">**설명**</span><span class="sxs-lookup"><span data-stu-id="86123-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="86123-110">이 웹 요청 모듈에서 처리 하는 요청의 URI 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="86123-110">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="86123-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="86123-111">Child Elements</span></span>  
 <span data-ttu-id="86123-112">없음</span><span class="sxs-lookup"><span data-stu-id="86123-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="86123-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="86123-113">Parent Elements</span></span>  
  
|<span data-ttu-id="86123-114">**요소**</span><span class="sxs-lookup"><span data-stu-id="86123-114">**Element**</span></span>|<span data-ttu-id="86123-115">**설명**</span><span class="sxs-lookup"><span data-stu-id="86123-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="86123-116">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="86123-116">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="86123-117">네트워크 호스트의 정보를 요청 하는 데 사용할 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="86123-117">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86123-118">설명</span><span class="sxs-lookup"><span data-stu-id="86123-118">Remarks</span></span>  
 <span data-ttu-id="86123-119">`remove`요소는 지정 된 URI 접두사에 대해 등록 된 웹 요청 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="86123-119">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="86123-120">특성의 값은 `prefix` 유효한 URI (예: "" 또는 "")의 선행 문자 여야 합니다 `http` `http://www.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="86123-120">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "`http`", or "`http://www.contoso.com`".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="86123-121">구성 파일</span><span class="sxs-lookup"><span data-stu-id="86123-121">Configuration Files</span></span>  
 <span data-ttu-id="86123-122">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86123-122">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="86123-123">예제</span><span class="sxs-lookup"><span data-stu-id="86123-123">Example</span></span>  

<span data-ttu-id="86123-124">다음 예에서는 HTTP에 대 한 기존 웹 요청 모듈을 제거한 다음에 HTTP 요청에 대 한 새 사용자 지정 웹 요청 모듈을 등록 `www.contoso.com` 합니다.</span><span class="sxs-lookup"><span data-stu-id="86123-124">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to `www.contoso.com`.</span></span>
  
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
  
## <a name="see-also"></a><span data-ttu-id="86123-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="86123-125">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="86123-126">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="86123-126">Network Settings Schema</span></span>](index.md)
