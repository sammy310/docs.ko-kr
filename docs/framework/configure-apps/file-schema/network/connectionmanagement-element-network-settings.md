---
title: <connectionManagement> 요소(네트워크 설정)
description: <connectionManagement>네트워크 설정 요소는 .NET Framework의 네트워크 호스트에 대 한 최대 연결 수를 지정 합니다.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement
- http://schemas.microsoft.com/.NetConfiguration/v2.0#connectionManagement
helpviewer_keywords:
- <connectionManagement> element
- connectionManagement element
ms.assetid: bedccaab-12a2-4511-8f67-e961f249aec6
ms.openlocfilehash: 4ceec06fb0e21bfae67038efe0ce758d3d5b708f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504617"
---
# <a name="connectionmanagement-element-network-settings"></a><span data-ttu-id="1edaa-103">\<connectionManagement> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="1edaa-103">\<connectionManagement> Element (Network Settings)</span></span>
<span data-ttu-id="1edaa-104">네트워크 호스트에 대한 최대 연결 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1edaa-104">Specifies the maximum number of connections to a network host.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionManagement>**

## <a name="syntax"></a><span data-ttu-id="1edaa-105">구문</span><span class="sxs-lookup"><span data-stu-id="1edaa-105">Syntax</span></span>  
  
```xml  
<connectionManagement>
</connectionManagement>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1edaa-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1edaa-106">Attributes and Elements</span></span>  
 <span data-ttu-id="1edaa-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1edaa-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1edaa-108">특성</span><span class="sxs-lookup"><span data-stu-id="1edaa-108">Attributes</span></span>  
 <span data-ttu-id="1edaa-109">없음</span><span class="sxs-lookup"><span data-stu-id="1edaa-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1edaa-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1edaa-110">Child Elements</span></span>  
  
|<span data-ttu-id="1edaa-111">**요소**</span><span class="sxs-lookup"><span data-stu-id="1edaa-111">**Element**</span></span>|<span data-ttu-id="1edaa-112">**설명**</span><span class="sxs-lookup"><span data-stu-id="1edaa-112">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="1edaa-113">추가</span><span class="sxs-lookup"><span data-stu-id="1edaa-113">add</span></span>](add-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="1edaa-114">연결 관리 목록에 IP 주소 또는 DNS 이름을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1edaa-114">Adds an IP address or DNS name to the connection management list.</span></span>|  
|[<span data-ttu-id="1edaa-115">해제</span><span class="sxs-lookup"><span data-stu-id="1edaa-115">clear</span></span>](clear-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="1edaa-116">연결 관리 목록을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="1edaa-116">Clears the connection management list.</span></span>|  
|[<span data-ttu-id="1edaa-117">remove</span><span class="sxs-lookup"><span data-stu-id="1edaa-117">remove</span></span>](remove-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="1edaa-118">연결 관리 목록에서 IP 주소 또는 DNS 이름을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="1edaa-118">Removes an IP address or DNS name from the connection management list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1edaa-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1edaa-119">Parent Elements</span></span>  
  
|<span data-ttu-id="1edaa-120">**요소**</span><span class="sxs-lookup"><span data-stu-id="1edaa-120">**Element**</span></span>|<span data-ttu-id="1edaa-121">**설명**</span><span class="sxs-lookup"><span data-stu-id="1edaa-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="1edaa-122">system.net</span><span class="sxs-lookup"><span data-stu-id="1edaa-122">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="1edaa-123">.NET Framework의 네트워크 연결 방법을 지정하는 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1edaa-123">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1edaa-124">설명</span><span class="sxs-lookup"><span data-stu-id="1edaa-124">Remarks</span></span>  
 <span data-ttu-id="1edaa-125">`connectionManagement`요소는 서버 또는 서버 그룹에 대 한 최대 연결 수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="1edaa-125">The `connectionManagement` element defines the maximum number of connections to a server or group of servers.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="1edaa-126">구성 파일</span><span class="sxs-lookup"><span data-stu-id="1edaa-126">Configuration Files</span></span>  
 <span data-ttu-id="1edaa-127">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1edaa-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1edaa-128">예제</span><span class="sxs-lookup"><span data-stu-id="1edaa-128">Example</span></span>  
 <span data-ttu-id="1edaa-129">다음 예에서는 서버에 대 한 4 개의 연결과 `www.contoso.com` 다른 모든 서버에 대 한 두 개의 연결을 사용 하도록 응용 프로그램을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1edaa-129">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address = "http://www.contoso.com" maxconnection = "4" />  
      <add address = "*" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1edaa-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1edaa-130">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="1edaa-131">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="1edaa-131">Network Settings Schema</span></span>](index.md)
