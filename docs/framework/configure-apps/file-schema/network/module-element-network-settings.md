---
title: <module> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#module
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/module
helpviewer_keywords:
- module element
- <module> element
ms.assetid: 10318725-9666-4d65-ab61-b94c64e59f13
ms.openlocfilehash: ed28ae4a52085cbfa781b4baf2ee1eafbeff6eb4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154831"
---
# <a name="module-element-network-settings"></a><span data-ttu-id="9830d-102">\<모듈> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="9830d-102">\<module> Element (Network Settings)</span></span>
<span data-ttu-id="9830d-103">애플리케이션에 새 프록시 모듈을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9830d-103">Adds a new proxy module to the application.</span></span>  

<span data-ttu-id="9830d-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9830d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9830d-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="9830d-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="9830d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<기본 프록시>**](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="9830d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>\
<span data-ttu-id="9830d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<모듈>**</span><span class="sxs-lookup"><span data-stu-id="9830d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<module>**</span></span>

## <a name="syntax"></a><span data-ttu-id="9830d-108">구문</span><span class="sxs-lookup"><span data-stu-id="9830d-108">Syntax</span></span>  
  
```xml  
<module
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9830d-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9830d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9830d-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9830d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9830d-111">특성</span><span class="sxs-lookup"><span data-stu-id="9830d-111">Attributes</span></span>  
  
|<span data-ttu-id="9830d-112">**특성**</span><span class="sxs-lookup"><span data-stu-id="9830d-112">**Attribute**</span></span>|<span data-ttu-id="9830d-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="9830d-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="9830d-114">프록시를 구현하는 쉼표로 <xref:System.Type.FullName%2A> 구분된 정규화된 형식 이름(속성으로 표시됨)과 어셈블리 <xref:System.Reflection.Assembly.FullName%2A> 이름(속성으로 표시됨)입니다.</span><span class="sxs-lookup"><span data-stu-id="9830d-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements the proxy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9830d-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9830d-115">Child Elements</span></span>  
 <span data-ttu-id="9830d-116">없음</span><span class="sxs-lookup"><span data-stu-id="9830d-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9830d-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9830d-117">Parent Elements</span></span>  
  
|<span data-ttu-id="9830d-118">**요소**</span><span class="sxs-lookup"><span data-stu-id="9830d-118">**Element**</span></span>|<span data-ttu-id="9830d-119">**설명**</span><span class="sxs-lookup"><span data-stu-id="9830d-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="9830d-120">기본 프록시</span><span class="sxs-lookup"><span data-stu-id="9830d-120">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="9830d-121">HTTP(Hypertext Transfer Protocol) 프록시 서버를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9830d-121">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9830d-122">설명</span><span class="sxs-lookup"><span data-stu-id="9830d-122">Remarks</span></span>  
 <span data-ttu-id="9830d-123">`module` 요소는 인터페이스를 구현하는 프록시 <xref:System.Net.IWebProxy> 클래스를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="9830d-123">The `module` element registers proxy classes that implement the <xref:System.Net.IWebProxy> interface.</span></span> <span data-ttu-id="9830d-124">프록시 클래스를 등록한 다음에는 `module`을 사용하여 지원 프록시를 통해 정보를 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9830d-124">After registering the proxy class, `module` can be used to request information through the supported proxy.</span></span>  
  
 <span data-ttu-id="9830d-125">특성의 `type` 값은 모듈의 클래스 이름과 해당 DLL(동적 링크 라이브러리)의 이름이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9830d-125">The value for the `type` attribute should be the class name of the module and the name of its corresponding Dynamic Link Library (DLL).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="9830d-126">구성 파일</span><span class="sxs-lookup"><span data-stu-id="9830d-126">Configuration Files</span></span>  
 <span data-ttu-id="9830d-127">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9830d-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9830d-128">예제</span><span class="sxs-lookup"><span data-stu-id="9830d-128">Example</span></span>  
 <span data-ttu-id="9830d-129">다음 예제는 사용자 지정 프록시 클래스를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="9830d-129">The following example registers a custom proxy class.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9830d-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9830d-130">See also</span></span>

- <xref:System.Net.IWebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="9830d-131">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="9830d-131">Network Settings Schema</span></span>](index.md)
