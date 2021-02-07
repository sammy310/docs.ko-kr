---
description: '자세한 정보: <clear> webRequestModules의 요소 (네트워크 설정)'
title: webRequestModules의 <clear> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- <clear> element, webRequestModules
- <webRequestModules>, clear element
- webRequestModules, clear element
- clear element, webRequestModules
ms.assetid: 48f38bcb-f30c-4b74-a8f0-1a3caf1aa96f
ms.openlocfilehash: 0782bf9edeafed2d61a368c3f6a8b37ef226c990
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740420"
---
# <a name="clear-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="4877a-103">webRequestModules의 \<clear> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="4877a-103">\<clear> Element for webRequestModules (Network Settings)</span></span>

<span data-ttu-id="4877a-104">응용 프로그램에서 등록 된 모든 웹 요청 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="4877a-104">Removes all registered Web request modules from the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="4877a-105">구문</span><span class="sxs-lookup"><span data-stu-id="4877a-105">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4877a-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4877a-106">Attributes and Elements</span></span>  

 <span data-ttu-id="4877a-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4877a-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4877a-108">특성</span><span class="sxs-lookup"><span data-stu-id="4877a-108">Attributes</span></span>  

 <span data-ttu-id="4877a-109">없음</span><span class="sxs-lookup"><span data-stu-id="4877a-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4877a-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4877a-110">Child Elements</span></span>  

 <span data-ttu-id="4877a-111">없음</span><span class="sxs-lookup"><span data-stu-id="4877a-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4877a-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4877a-112">Parent Elements</span></span>  
  
|<span data-ttu-id="4877a-113">**요소**</span><span class="sxs-lookup"><span data-stu-id="4877a-113">**Element**</span></span>|<span data-ttu-id="4877a-114">**설명**</span><span class="sxs-lookup"><span data-stu-id="4877a-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4877a-115">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="4877a-115">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="4877a-116">네트워크 호스트의 정보를 요청 하는 데 사용할 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4877a-116">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4877a-117">설명</span><span class="sxs-lookup"><span data-stu-id="4877a-117">Remarks</span></span>  

 <span data-ttu-id="4877a-118">`clear`요소는 구성 파일 또는 구성 계층 구조에서 상위 수준에 정의 된 등록 된 모든 웹 요청 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="4877a-118">The `clear` element removes all registered Web request modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4877a-119">구성 파일</span><span class="sxs-lookup"><span data-stu-id="4877a-119">Configuration Files</span></span>  

 <span data-ttu-id="4877a-120">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4877a-120">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4877a-121">예제</span><span class="sxs-lookup"><span data-stu-id="4877a-121">Example</span></span>  

 <span data-ttu-id="4877a-122">다음 예제에서는 모든 웹 요청 모듈을 지운 다음 HTTP에 대 한 웹 요청 모듈을 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4877a-122">The following example clears all Web request modules and then registers a Web request module for HTTP.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <clear/>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4877a-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4877a-123">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="4877a-124">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="4877a-124">Network Settings Schema</span></span>](index.md)
