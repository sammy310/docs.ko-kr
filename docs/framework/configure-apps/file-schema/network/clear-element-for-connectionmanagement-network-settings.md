---
title: connectionManagement의 <clear> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- <clear> element, connectionManagement
- connectionManagement, clear element
- clear element, connectionManagement
- <connectionManagement>, clear element
ms.assetid: fb259282-84c4-4dc4-a226-78d904a6edc3
ms.openlocfilehash: 17b380b12977423669fd413132d69a3082daca41
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698367"
---
# <a name="clear-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="c7bc6-102">connectionManagement (네트워크 설정)에 대 한 \<clear > 요소</span><span class="sxs-lookup"><span data-stu-id="c7bc6-102">\<clear> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="c7bc6-103">연결 관리 목록을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="c7bc6-103">Clears the connection management list.</span></span>  
  
[<span data-ttu-id="c7bc6-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="c7bc6-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="c7bc6-105">&nbsp; @ no__t-1[ **@no__t -4c.net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c7bc6-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="c7bc6-106">&nbsp; @ no__t-1 @ no__t @ no__t[ **\<connectionManagement >** ](connectionmanagement-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c7bc6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)</span></span>  
<span data-ttu-id="c7bc6-107">&nbsp; @ no__t-1 @ no__t @ no__t @ @ no__t-4 @ no__t-5 **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="c7bc6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7bc6-108">구문</span><span class="sxs-lookup"><span data-stu-id="c7bc6-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c7bc6-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c7bc6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c7bc6-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c7bc6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c7bc6-111">특성</span><span class="sxs-lookup"><span data-stu-id="c7bc6-111">Attributes</span></span>  
 <span data-ttu-id="c7bc6-112">없음</span><span class="sxs-lookup"><span data-stu-id="c7bc6-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c7bc6-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c7bc6-113">Child Elements</span></span>  
 <span data-ttu-id="c7bc6-114">없음</span><span class="sxs-lookup"><span data-stu-id="c7bc6-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c7bc6-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c7bc6-115">Parent Elements</span></span>  
  
|<span data-ttu-id="c7bc6-116">**요소**</span><span class="sxs-lookup"><span data-stu-id="c7bc6-116">**Element**</span></span>|<span data-ttu-id="c7bc6-117">**설명**</span><span class="sxs-lookup"><span data-stu-id="c7bc6-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c7bc6-118">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="c7bc6-118">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="c7bc6-119">네트워크 호스트에 대한 최대 연결 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c7bc6-119">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7bc6-120">설명</span><span class="sxs-lookup"><span data-stu-id="c7bc6-120">Remarks</span></span>  
 <span data-ttu-id="c7bc6-121">@No__t-0 요소는 연결 관리 목록에서 모든 항목을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="c7bc6-121">The `clear` element clears all entries from the connection management list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="c7bc6-122">구성 파일</span><span class="sxs-lookup"><span data-stu-id="c7bc6-122">Configuration Files</span></span>  
 <span data-ttu-id="c7bc6-123">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7bc6-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7bc6-124">예제</span><span class="sxs-lookup"><span data-stu-id="c7bc6-124">Example</span></span>  
 <span data-ttu-id="c7bc6-125">다음 예에서는 연결 관리 목록을 지운 다음 서버 `www.contoso.com` 및 기타 모든 네트워크 호스트에 대 한 새 연결 관리 항목을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7bc6-125">The following example clears the connection management list and then adds new connection management entries for the server `www.contoso.com` and all other network hosts.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <clear/>  
      <add address = "http://www.contoso.com" maxconnection = "4" />  
      <add address = "*" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c7bc6-126">참조</span><span class="sxs-lookup"><span data-stu-id="c7bc6-126">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="c7bc6-127">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="c7bc6-127">Network Settings Schema</span></span>](index.md)
