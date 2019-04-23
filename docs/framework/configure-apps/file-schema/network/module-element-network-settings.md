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
ms.openlocfilehash: 0d108f2350d82666e3dc24f0f6854fe64ea4755f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59084117"
---
# <a name="module-element-network-settings"></a><span data-ttu-id="f6663-102">\<모듈 > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="f6663-102">\<module> Element (Network Settings)</span></span>
<span data-ttu-id="f6663-103">응용 프로그램에 새 프록시 모듈을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f6663-103">Adds a new proxy module to the application.</span></span>  
  
 <span data-ttu-id="f6663-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f6663-104">\<configuration></span></span>  
<span data-ttu-id="f6663-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="f6663-105">\<system.net></span></span>  
<span data-ttu-id="f6663-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="f6663-106">\<defaultProxy></span></span>  
<span data-ttu-id="f6663-107">\<module></span><span class="sxs-lookup"><span data-stu-id="f6663-107">\<module></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6663-108">구문</span><span class="sxs-lookup"><span data-stu-id="f6663-108">Syntax</span></span>  
  
```xml  
<module   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f6663-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f6663-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f6663-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f6663-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f6663-111">특성</span><span class="sxs-lookup"><span data-stu-id="f6663-111">Attributes</span></span>  
  
|<span data-ttu-id="f6663-112">**특성**</span><span class="sxs-lookup"><span data-stu-id="f6663-112">**Attribute**</span></span>|<span data-ttu-id="f6663-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="f6663-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="f6663-114">정규화 된 형식 이름을 (나타난 합니다 <xref:System.Type.FullName%2A> 속성)와 어셈블리 이름 (나타난는 <xref:System.Reflection.Assembly.FullName%2A> 속성) 프록시를 구현 하는 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6663-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements the proxy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f6663-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f6663-115">Child Elements</span></span>  
 <span data-ttu-id="f6663-116">없음</span><span class="sxs-lookup"><span data-stu-id="f6663-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f6663-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f6663-117">Parent Elements</span></span>  
  
|<span data-ttu-id="f6663-118">**요소**</span><span class="sxs-lookup"><span data-stu-id="f6663-118">**Element**</span></span>|<span data-ttu-id="f6663-119">**설명**</span><span class="sxs-lookup"><span data-stu-id="f6663-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f6663-120">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="f6663-120">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="f6663-121">HTTP(Hypertext Transfer Protocol) 프록시 서버를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f6663-121">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6663-122">설명</span><span class="sxs-lookup"><span data-stu-id="f6663-122">Remarks</span></span>  
 <span data-ttu-id="f6663-123">합니다 `module` 를 구현 하는 프록시 클래스를 등록 하는 요소는 <xref:System.Net.IWebProxy> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="f6663-123">The `module` element registers proxy classes that implement the <xref:System.Net.IWebProxy> interface.</span></span> <span data-ttu-id="f6663-124">프록시 클래스를 등록한 다음에는 `module`을 사용하여 지원 프록시를 통해 정보를 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6663-124">After registering the proxy class, `module` can be used to request information through the supported proxy.</span></span>  
  
 <span data-ttu-id="f6663-125">에 대 한 값을 `type` 특성은 모듈의 클래스 이름과의 해당 해당 동적 링크 라이브러리 (DLL) 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6663-125">The value for the `type` attribute should be the class name of the module and the name of its corresponding Dynamic Link Library (DLL).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="f6663-126">구성 파일</span><span class="sxs-lookup"><span data-stu-id="f6663-126">Configuration Files</span></span>  
 <span data-ttu-id="f6663-127">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6663-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6663-128">예제</span><span class="sxs-lookup"><span data-stu-id="f6663-128">Example</span></span>  
 <span data-ttu-id="f6663-129">다음 예제에서는 사용자 지정 프록시 클래스를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="f6663-129">The following example registers a custom proxy class.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f6663-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="f6663-130">See also</span></span>

- <xref:System.Net.IWebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="f6663-131">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="f6663-131">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
