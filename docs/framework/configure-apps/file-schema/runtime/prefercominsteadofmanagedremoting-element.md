---
description: '다음에 대 한 자세한 정보: <PreferComInsteadOfManagedRemoting> 요소'
title: <PreferComInsteadOfManagedRemoting> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
ms.openlocfilehash: b621af9b584d1ea2623ffe5a44f74b5b7bd520e7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782275"
---
# <a name="prefercominsteadofmanagedremoting-element"></a><span data-ttu-id="7e484-103">\<PreferComInsteadOfManagedRemoting> 요소</span><span class="sxs-lookup"><span data-stu-id="7e484-103">\<PreferComInsteadOfManagedRemoting> Element</span></span>

<span data-ttu-id="7e484-104">런타임이 응용 프로그램 도메인 경계를 넘어 모든 호출에 대해 원격 대신 COM interop을 사용할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e484-104">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<PreferComInsteadOfManagedRemoting>**  
  
## <a name="syntax"></a><span data-ttu-id="7e484-105">구문</span><span class="sxs-lookup"><span data-stu-id="7e484-105">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e484-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7e484-106">Attributes and Elements</span></span>  

 <span data-ttu-id="7e484-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7e484-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e484-108">특성</span><span class="sxs-lookup"><span data-stu-id="7e484-108">Attributes</span></span>  
  
|<span data-ttu-id="7e484-109">attribute</span><span class="sxs-lookup"><span data-stu-id="7e484-109">Attribute</span></span>|<span data-ttu-id="7e484-110">설명</span><span class="sxs-lookup"><span data-stu-id="7e484-110">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="7e484-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="7e484-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="7e484-112">런타임이 응용 프로그램 도메인 경계를 넘어 원격이 아닌 COM interop 사용 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7e484-112">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="7e484-113">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="7e484-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="7e484-114">값</span><span class="sxs-lookup"><span data-stu-id="7e484-114">Value</span></span>|<span data-ttu-id="7e484-115">설명</span><span class="sxs-lookup"><span data-stu-id="7e484-115">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="7e484-116">런타임은 응용 프로그램 도메인 경계에서 원격 기능을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e484-116">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="7e484-117">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="7e484-117">This is the default.</span></span>|  
|`true`|<span data-ttu-id="7e484-118">런타임은 응용 프로그램 도메인 경계에 걸쳐 COM interop를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e484-118">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7e484-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7e484-119">Child Elements</span></span>  

 <span data-ttu-id="7e484-120">없음</span><span class="sxs-lookup"><span data-stu-id="7e484-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7e484-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7e484-121">Parent Elements</span></span>  
  
|<span data-ttu-id="7e484-122">요소</span><span class="sxs-lookup"><span data-stu-id="7e484-122">Element</span></span>|<span data-ttu-id="7e484-123">설명</span><span class="sxs-lookup"><span data-stu-id="7e484-123">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7e484-124">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7e484-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="7e484-125">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7e484-125">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e484-126">설명</span><span class="sxs-lookup"><span data-stu-id="7e484-126">Remarks</span></span>  

 <span data-ttu-id="7e484-127">특성을로 설정 하면 런타임은 다음과 같이 `enabled` `true` 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e484-127">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
- <span data-ttu-id="7e484-128">런타임은 [iunknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) 인터페이스가 COM 인터페이스를 통해 도메인에 들어가면 [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) 인터페이스에 대해 [iunknown:: QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) 를 호출 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e484-128">The runtime does not call [IUnknown::QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="7e484-129">대신, 개체 주위에서 RCW ( [런타임 호출 가능 래퍼](../../../../standard/native-interop/runtime-callable-wrapper.md) )를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e484-129">Instead, it constructs a [Runtime Callable Wrapper](../../../../standard/native-interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
- <span data-ttu-id="7e484-130">런타임은 `QueryInterface` 이 도메인에 생성 된 ccw ( [COM 호출 가능 래퍼](../../../../standard/native-interop/com-callable-wrapper.md) )에 대 한 [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) 인터페이스 호출을 받을 때 E_NOINTERFACE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e484-130">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../standard/native-interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="7e484-131">이러한 두 동작은 응용 프로그램 도메인 경계에서 관리 되는 개체 간의 COM 인터페이스에 대 한 모든 호출이 원격 대신 COM 및 COM interop을 사용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e484-131">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e484-132">예제</span><span class="sxs-lookup"><span data-stu-id="7e484-132">Example</span></span>  

 <span data-ttu-id="7e484-133">다음 예제에서는 런타임이 격리 경계를 넘어 COM interop를 사용 하도록 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7e484-133">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7e484-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7e484-134">See also</span></span>

- [<span data-ttu-id="7e484-135">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="7e484-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="7e484-136">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="7e484-136">Configuration File Schema</span></span>](../index.md)
