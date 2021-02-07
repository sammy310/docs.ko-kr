---
description: '자세한 정보: <clear> bypasslist 요소에 대 한 요소 (네트워크 설정)'
title: bypasslist의 <clear> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- clear element, bypasslist
- <clear> element, bypasslist
- <bypasslist>, clear element
- bypasslist, clear element
ms.assetid: 301584ca-a914-4100-b180-3b288d3b099e
ms.openlocfilehash: 4ddb66c837c55391a19826c44c6df7a3e88c8e0b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729902"
---
# <a name="clear-element-for-bypasslist-network-settings"></a><span data-ttu-id="9cc3c-103">bypasslist의 \<clear> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="9cc3c-103">\<clear> Element for bypasslist (Network Settings)</span></span>

<span data-ttu-id="9cc3c-104">프록시 무시 목록을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="9cc3c-104">Clears the proxy bypass list.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="9cc3c-105">구문</span><span class="sxs-lookup"><span data-stu-id="9cc3c-105">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9cc3c-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9cc3c-106">Attributes and Elements</span></span>  

 <span data-ttu-id="9cc3c-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9cc3c-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9cc3c-108">특성</span><span class="sxs-lookup"><span data-stu-id="9cc3c-108">Attributes</span></span>  

 <span data-ttu-id="9cc3c-109">없음</span><span class="sxs-lookup"><span data-stu-id="9cc3c-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9cc3c-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9cc3c-110">Child Elements</span></span>  

 <span data-ttu-id="9cc3c-111">없음</span><span class="sxs-lookup"><span data-stu-id="9cc3c-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9cc3c-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9cc3c-112">Parent Elements</span></span>  
  
|<span data-ttu-id="9cc3c-113">**요소**</span><span class="sxs-lookup"><span data-stu-id="9cc3c-113">**Element**</span></span>|<span data-ttu-id="9cc3c-114">**설명**</span><span class="sxs-lookup"><span data-stu-id="9cc3c-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="9cc3c-115">bypasslist</span><span class="sxs-lookup"><span data-stu-id="9cc3c-115">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="9cc3c-116">프록시를 사용 하지 않는 주소를 설명 하는 정규식 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cc3c-116">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9cc3c-117">설명</span><span class="sxs-lookup"><span data-stu-id="9cc3c-117">Remarks</span></span>  

 <span data-ttu-id="9cc3c-118">`clear`요소는 바이패스 목록에서 모든 항목을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="9cc3c-118">The `clear` element clears all entries from the bypass list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="9cc3c-119">구성 파일</span><span class="sxs-lookup"><span data-stu-id="9cc3c-119">Configuration Files</span></span>  

 <span data-ttu-id="9cc3c-120">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cc3c-120">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9cc3c-121">예제</span><span class="sxs-lookup"><span data-stu-id="9cc3c-121">Example</span></span>  

 <span data-ttu-id="9cc3c-122">다음 예에서는 바이패스 목록을 지운 다음 바이패스 목록에 두 개의 주소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cc3c-122">The following example clears the bypass list and then adds two addresses to the bypass list.</span></span> <span data-ttu-id="9cc3c-123">첫 번째는 contoso.com 도메인에 있는 모든 서버에 대 한 프록시를 무시 합니다. 두 번째는 IP 주소가 192.168으로 시작 하는 모든 서버에 대해 프록시를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cc3c-123">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
         <clear/>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="9cc3c-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9cc3c-124">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="9cc3c-125">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="9cc3c-125">Network Settings Schema</span></span>](index.md)
