---
description: '다음에 대 한 자세한 정보: <module> 요소 (네트워크 설정)'
title: <module> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#module
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/module
helpviewer_keywords:
- module element
- <module> element
ms.assetid: 10318725-9666-4d65-ab61-b94c64e59f13
ms.openlocfilehash: d498b79ae6046367bc81add5ea387e178ab6c29d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652837"
---
# <a name="module-element-network-settings"></a><span data-ttu-id="c117f-103">\<module> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="c117f-103">\<module> Element (Network Settings)</span></span>

<span data-ttu-id="c117f-104">애플리케이션에 새 프록시 모듈을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c117f-104">Adds a new proxy module to the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<module>**

## <a name="syntax"></a><span data-ttu-id="c117f-105">구문</span><span class="sxs-lookup"><span data-stu-id="c117f-105">Syntax</span></span>  
  
```xml  
<module
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c117f-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c117f-106">Attributes and Elements</span></span>  

 <span data-ttu-id="c117f-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c117f-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c117f-108">특성</span><span class="sxs-lookup"><span data-stu-id="c117f-108">Attributes</span></span>  
  
|<span data-ttu-id="c117f-109">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="c117f-109">**Attribute**</span></span>|<span data-ttu-id="c117f-110">**설명**</span><span class="sxs-lookup"><span data-stu-id="c117f-110">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="c117f-111">속성으로 표시 되는 정규화 된 형식 이름 <xref:System.Type.FullName%2A> 및 속성으로 표시 되는 어셈블리 이름 (속성으로 표시 <xref:System.Reflection.Assembly.FullName%2A> 됨)을 쉼표로 구분 하 여 프록시를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="c117f-111">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements the proxy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c117f-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c117f-112">Child Elements</span></span>  

 <span data-ttu-id="c117f-113">없음</span><span class="sxs-lookup"><span data-stu-id="c117f-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c117f-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c117f-114">Parent Elements</span></span>  
  
|<span data-ttu-id="c117f-115">**요소**</span><span class="sxs-lookup"><span data-stu-id="c117f-115">**Element**</span></span>|<span data-ttu-id="c117f-116">**설명**</span><span class="sxs-lookup"><span data-stu-id="c117f-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c117f-117">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="c117f-117">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="c117f-118">HTTP(Hypertext Transfer Protocol) 프록시 서버를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c117f-118">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c117f-119">설명</span><span class="sxs-lookup"><span data-stu-id="c117f-119">Remarks</span></span>  

 <span data-ttu-id="c117f-120">`module`요소는 인터페이스를 구현 하는 프록시 클래스를 등록 <xref:System.Net.IWebProxy> 합니다.</span><span class="sxs-lookup"><span data-stu-id="c117f-120">The `module` element registers proxy classes that implement the <xref:System.Net.IWebProxy> interface.</span></span> <span data-ttu-id="c117f-121">프록시 클래스를 등록한 다음에는 `module`을 사용하여 지원 프록시를 통해 정보를 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c117f-121">After registering the proxy class, `module` can be used to request information through the supported proxy.</span></span>  
  
 <span data-ttu-id="c117f-122">특성의 값은 `type` 모듈의 클래스 이름과 해당 DLL (동적 연결 라이브러리)의 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c117f-122">The value for the `type` attribute should be the class name of the module and the name of its corresponding Dynamic Link Library (DLL).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="c117f-123">구성 파일</span><span class="sxs-lookup"><span data-stu-id="c117f-123">Configuration Files</span></span>  

 <span data-ttu-id="c117f-124">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c117f-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c117f-125">예제</span><span class="sxs-lookup"><span data-stu-id="c117f-125">Example</span></span>  

 <span data-ttu-id="c117f-126">다음 예제에서는 사용자 지정 프록시 클래스를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c117f-126">The following example registers a custom proxy class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <module  
        type="Test.CustomWebProxy, TestProxy, Version=2.0.3600.0, Culture=neutral, PublicKeyToken=b23a5c561934e385"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c117f-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c117f-127">See also</span></span>

- <xref:System.Net.IWebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="c117f-128">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="c117f-128">Network Settings Schema</span></span>](index.md)
