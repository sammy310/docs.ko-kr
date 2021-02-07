---
description: '자세한 정보: <remove> webRequestModules의 요소 (네트워크 설정)'
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
ms.openlocfilehash: db65c91417af2538e27b65e0ae28d06a6bfcde0a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99713002"
---
# <a name="remove-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="91fba-103">webRequestModules의 \<remove> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="91fba-103">\<remove> Element for webRequestModules (Network Settings)</span></span>

<span data-ttu-id="91fba-104">응용 프로그램에서 사용자 지정 웹 요청 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="91fba-104">Removes a custom Web request module from the application.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**
  
## <a name="syntax"></a><span data-ttu-id="91fba-105">구문</span><span class="sxs-lookup"><span data-stu-id="91fba-105">Syntax</span></span>  
  
```xml  
<remove
  prefix="URI prefix"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91fba-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="91fba-106">Attributes and Elements</span></span>  

 <span data-ttu-id="91fba-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="91fba-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91fba-108">특성</span><span class="sxs-lookup"><span data-stu-id="91fba-108">Attributes</span></span>  
  
|<span data-ttu-id="91fba-109">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="91fba-109">**Attribute**</span></span>|<span data-ttu-id="91fba-110">**설명**</span><span class="sxs-lookup"><span data-stu-id="91fba-110">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="91fba-111">이 웹 요청 모듈에서 처리 하는 요청의 URI 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="91fba-111">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="91fba-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="91fba-112">Child Elements</span></span>  

 <span data-ttu-id="91fba-113">없음</span><span class="sxs-lookup"><span data-stu-id="91fba-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="91fba-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="91fba-114">Parent Elements</span></span>  
  
|<span data-ttu-id="91fba-115">**요소**</span><span class="sxs-lookup"><span data-stu-id="91fba-115">**Element**</span></span>|<span data-ttu-id="91fba-116">**설명**</span><span class="sxs-lookup"><span data-stu-id="91fba-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="91fba-117">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="91fba-117">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="91fba-118">네트워크 호스트의 정보를 요청 하는 데 사용할 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="91fba-118">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91fba-119">설명</span><span class="sxs-lookup"><span data-stu-id="91fba-119">Remarks</span></span>  

 <span data-ttu-id="91fba-120">`remove`요소는 지정 된 URI 접두사에 대해 등록 된 웹 요청 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="91fba-120">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="91fba-121">특성의 값은 `prefix` 유효한 URI (예: "" 또는 "")의 선행 문자 여야 합니다 `http` `http://www.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="91fba-121">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "`http`", or "`http://www.contoso.com`".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="91fba-122">구성 파일</span><span class="sxs-lookup"><span data-stu-id="91fba-122">Configuration Files</span></span>  

 <span data-ttu-id="91fba-123">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91fba-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="91fba-124">예제</span><span class="sxs-lookup"><span data-stu-id="91fba-124">Example</span></span>  

<span data-ttu-id="91fba-125">다음 예에서는 HTTP에 대 한 기존 웹 요청 모듈을 제거한 다음에 HTTP 요청에 대 한 새 사용자 지정 웹 요청 모듈을 등록 `www.contoso.com` 합니다.</span><span class="sxs-lookup"><span data-stu-id="91fba-125">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to `www.contoso.com`.</span></span>
  
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
  
## <a name="see-also"></a><span data-ttu-id="91fba-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="91fba-126">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="91fba-127">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="91fba-127">Network Settings Schema</span></span>](index.md)
