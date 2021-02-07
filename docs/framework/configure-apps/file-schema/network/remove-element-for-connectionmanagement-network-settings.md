---
description: '자세한 정보: <remove> connectionManagement의 요소 (네트워크 설정)'
title: connectionManagement의 <remove> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- connectionManagement, remove element
- <remove> element, connectionManagement
- <connectionManagement>, remove element
- remove element, connectionManagement
ms.assetid: 94b81775-5a22-4975-8c47-8620c40c3f35
ms.openlocfilehash: 98916846fb5de93ee93a7e25530e983cbd3719ff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740251"
---
# <a name="remove-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="21f1e-103">connectionManagement의 \<remove> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="21f1e-103">\<remove> Element for connectionManagement (Network Settings)</span></span>

<span data-ttu-id="21f1e-104">연결 관리 목록에서 IP 주소 또는 DNS 이름을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="21f1e-104">Removes an IP address or DNS name from the connection management list.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="21f1e-105">구문</span><span class="sxs-lookup"><span data-stu-id="21f1e-105">Syntax</span></span>  
  
```xml  
<remove
  address="server name or IP address"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="21f1e-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="21f1e-106">Attributes and Elements</span></span>  

 <span data-ttu-id="21f1e-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="21f1e-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="21f1e-108">특성</span><span class="sxs-lookup"><span data-stu-id="21f1e-108">Attributes</span></span>  
  
|<span data-ttu-id="21f1e-109">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="21f1e-109">**Attribute**</span></span>|<span data-ttu-id="21f1e-110">**설명**</span><span class="sxs-lookup"><span data-stu-id="21f1e-110">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="21f1e-111">IP 주소 또는 DNS 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="21f1e-111">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="21f1e-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="21f1e-112">Child Elements</span></span>  

 <span data-ttu-id="21f1e-113">없음</span><span class="sxs-lookup"><span data-stu-id="21f1e-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="21f1e-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="21f1e-114">Parent Elements</span></span>  
  
|<span data-ttu-id="21f1e-115">**요소**</span><span class="sxs-lookup"><span data-stu-id="21f1e-115">**Element**</span></span>|<span data-ttu-id="21f1e-116">**설명**</span><span class="sxs-lookup"><span data-stu-id="21f1e-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="21f1e-117">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="21f1e-117">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="21f1e-118">네트워크 호스트에 대한 최대 연결 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="21f1e-118">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21f1e-119">설명</span><span class="sxs-lookup"><span data-stu-id="21f1e-119">Remarks</span></span>  

 <span data-ttu-id="21f1e-120">`remove`요소는 지정 된 서버에 대 한 연결 관리 목록 항목을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="21f1e-120">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="21f1e-121">특성 값은 `address` 올바른 IP 주소 또는 호스트 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21f1e-121">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="21f1e-122">구성 파일</span><span class="sxs-lookup"><span data-stu-id="21f1e-122">Configuration Files</span></span>  

 <span data-ttu-id="21f1e-123">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21f1e-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="21f1e-124">예제</span><span class="sxs-lookup"><span data-stu-id="21f1e-124">Example</span></span>  

 <span data-ttu-id="21f1e-125">다음 예에서는 서버에 대 한 연결 관리 목록 항목을 제거한 `www.adventure-works.com` 다음 서버에 대 한 4 개의 연결과 `www.contoso.com` 다른 모든 서버에 대 한 두 개의 연결을 사용 하도록 응용 프로그램을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="21f1e-125">The following example removes any connection management list entries for the server `www.adventure-works.com` and then configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <remove address="http://www.adventure-works.com" />  
      <add address="http://www.contoso.com" maxconnection="4" />  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="21f1e-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="21f1e-126">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="21f1e-127">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="21f1e-127">Network Settings Schema</span></span>](index.md)
