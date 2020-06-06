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
ms.openlocfilehash: a76df48a9de084e1121a5e96b22edf7aa3acba23
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088480"
---
# <a name="clear-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="63e40-102">connectionManagement의 \<clear> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="63e40-102">\<clear> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="63e40-103">연결 관리 목록을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="63e40-103">Clears the connection management list.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="63e40-104">구문</span><span class="sxs-lookup"><span data-stu-id="63e40-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="63e40-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="63e40-105">Attributes and Elements</span></span>  
 <span data-ttu-id="63e40-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="63e40-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="63e40-107">특성</span><span class="sxs-lookup"><span data-stu-id="63e40-107">Attributes</span></span>  
 <span data-ttu-id="63e40-108">없음</span><span class="sxs-lookup"><span data-stu-id="63e40-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="63e40-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="63e40-109">Child Elements</span></span>  
 <span data-ttu-id="63e40-110">없음</span><span class="sxs-lookup"><span data-stu-id="63e40-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="63e40-111">부모 요소</span><span class="sxs-lookup"><span data-stu-id="63e40-111">Parent Elements</span></span>  
  
|<span data-ttu-id="63e40-112">**요소**</span><span class="sxs-lookup"><span data-stu-id="63e40-112">**Element**</span></span>|<span data-ttu-id="63e40-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="63e40-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="63e40-114">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="63e40-114">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="63e40-115">네트워크 호스트에 대한 최대 연결 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="63e40-115">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63e40-116">설명</span><span class="sxs-lookup"><span data-stu-id="63e40-116">Remarks</span></span>  
 <span data-ttu-id="63e40-117">`clear`요소는 연결 관리 목록에서 모든 항목을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="63e40-117">The `clear` element clears all entries from the connection management list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="63e40-118">구성 파일</span><span class="sxs-lookup"><span data-stu-id="63e40-118">Configuration Files</span></span>  
 <span data-ttu-id="63e40-119">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63e40-119">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="63e40-120">예제</span><span class="sxs-lookup"><span data-stu-id="63e40-120">Example</span></span>  
 <span data-ttu-id="63e40-121">다음 예에서는 연결 관리 목록을 지운 후 서버 `www.contoso.com` 및 다른 모든 네트워크 호스트에 대 한 새 연결 관리 항목을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="63e40-121">The following example clears the connection management list and then adds new connection management entries for the server `www.contoso.com` and all other network hosts.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="63e40-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="63e40-122">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="63e40-123">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="63e40-123">Network Settings Schema</span></span>](index.md)
