---
description: '자세한 정보: <clear> connectionManagement의 요소 (네트워크 설정)'
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
ms.openlocfilehash: e6e756e1065e48e79d59e02858963ded70d30f7e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698589"
---
# <a name="clear-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="8c7c1-103">connectionManagement의 \<clear> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="8c7c1-103">\<clear> Element for connectionManagement (Network Settings)</span></span>

<span data-ttu-id="8c7c1-104">연결 관리 목록을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="8c7c1-104">Clears the connection management list.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="8c7c1-105">구문</span><span class="sxs-lookup"><span data-stu-id="8c7c1-105">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c7c1-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8c7c1-106">Attributes and Elements</span></span>  

 <span data-ttu-id="8c7c1-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8c7c1-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c7c1-108">특성</span><span class="sxs-lookup"><span data-stu-id="8c7c1-108">Attributes</span></span>  

 <span data-ttu-id="8c7c1-109">없음</span><span class="sxs-lookup"><span data-stu-id="8c7c1-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8c7c1-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8c7c1-110">Child Elements</span></span>  

 <span data-ttu-id="8c7c1-111">없음</span><span class="sxs-lookup"><span data-stu-id="8c7c1-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8c7c1-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8c7c1-112">Parent Elements</span></span>  
  
|<span data-ttu-id="8c7c1-113">**요소**</span><span class="sxs-lookup"><span data-stu-id="8c7c1-113">**Element**</span></span>|<span data-ttu-id="8c7c1-114">**설명**</span><span class="sxs-lookup"><span data-stu-id="8c7c1-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8c7c1-115">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="8c7c1-115">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="8c7c1-116">네트워크 호스트에 대한 최대 연결 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c7c1-116">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c7c1-117">설명</span><span class="sxs-lookup"><span data-stu-id="8c7c1-117">Remarks</span></span>  

 <span data-ttu-id="8c7c1-118">`clear`요소는 연결 관리 목록에서 모든 항목을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="8c7c1-118">The `clear` element clears all entries from the connection management list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="8c7c1-119">구성 파일</span><span class="sxs-lookup"><span data-stu-id="8c7c1-119">Configuration Files</span></span>  

 <span data-ttu-id="8c7c1-120">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c7c1-120">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c7c1-121">예제</span><span class="sxs-lookup"><span data-stu-id="8c7c1-121">Example</span></span>  

 <span data-ttu-id="8c7c1-122">다음 예에서는 연결 관리 목록을 지운 후 서버 `www.contoso.com` 및 다른 모든 네트워크 호스트에 대 한 새 연결 관리 항목을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c7c1-122">The following example clears the connection management list and then adds new connection management entries for the server `www.contoso.com` and all other network hosts.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8c7c1-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8c7c1-123">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="8c7c1-124">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="8c7c1-124">Network Settings Schema</span></span>](index.md)
