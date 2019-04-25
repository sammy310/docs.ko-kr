---
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
ms.openlocfilehash: 7499d15f1d57887ffc3e78b83ed686c0c0f46cf4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674638"
---
# <a name="clear-element-for-bypasslist-network-settings"></a><span data-ttu-id="a6268-102">\<지우기 > bypasslist (네트워크 설정)에 대 한 요소</span><span class="sxs-lookup"><span data-stu-id="a6268-102">\<clear> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="a6268-103">프록시 무시 목록을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="a6268-103">Clears the proxy bypass list.</span></span>  
  
 <span data-ttu-id="a6268-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a6268-104">\<configuration></span></span>  
<span data-ttu-id="a6268-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="a6268-105">\<system.net></span></span>  
<span data-ttu-id="a6268-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="a6268-106">\<defaultProxy></span></span>  
<span data-ttu-id="a6268-107">\<bypasslist></span><span class="sxs-lookup"><span data-stu-id="a6268-107">\<bypasslist></span></span>  
<span data-ttu-id="a6268-108">\<clear></span><span class="sxs-lookup"><span data-stu-id="a6268-108">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6268-109">구문</span><span class="sxs-lookup"><span data-stu-id="a6268-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a6268-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a6268-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a6268-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a6268-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a6268-112">특성</span><span class="sxs-lookup"><span data-stu-id="a6268-112">Attributes</span></span>  
 <span data-ttu-id="a6268-113">없음</span><span class="sxs-lookup"><span data-stu-id="a6268-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a6268-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a6268-114">Child Elements</span></span>  
 <span data-ttu-id="a6268-115">없음</span><span class="sxs-lookup"><span data-stu-id="a6268-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a6268-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a6268-116">Parent Elements</span></span>  
  
|<span data-ttu-id="a6268-117">**요소**</span><span class="sxs-lookup"><span data-stu-id="a6268-117">**Element**</span></span>|<span data-ttu-id="a6268-118">**설명**</span><span class="sxs-lookup"><span data-stu-id="a6268-118">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a6268-119">bypasslist</span><span class="sxs-lookup"><span data-stu-id="a6268-119">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="a6268-120">프록시를 사용 하지 않는 주소를 설명 하는 정규식 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6268-120">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6268-121">설명</span><span class="sxs-lookup"><span data-stu-id="a6268-121">Remarks</span></span>  
 <span data-ttu-id="a6268-122">`clear` 요소 무시 목록에서 모든 항목을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6268-122">The `clear` element clears all entries from the bypass list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a6268-123">구성 파일</span><span class="sxs-lookup"><span data-stu-id="a6268-123">Configuration Files</span></span>  
 <span data-ttu-id="a6268-124">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6268-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6268-125">예제</span><span class="sxs-lookup"><span data-stu-id="a6268-125">Example</span></span>  
 <span data-ttu-id="a6268-126">다음 예제에서는 바이패스 목록에는 지우고 바이패스 목록에 두 개의 주소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6268-126">The following example clears the bypass list and then adds two addresses to the bypass list.</span></span> <span data-ttu-id="a6268-127">첫 번째는 contoso.com 도메인의 모든 서버에 대 한 프록시를 무시합니다. 두 번째 192.168 사용 하 여 IP 주소가 시작 되는 모든 서버에 대 한 프록시를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6268-127">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a6268-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="a6268-128">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="a6268-129">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="a6268-129">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
