---
title: <PreferComInsteadOfManagedRemoting> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c7a558af17493c955b4f148d0abf7f42c9dd6f8
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629427"
---
# <a name="prefercominsteadofmanagedremoting-element"></a><span data-ttu-id="ec6b4-102">\<PreferComInsteadOfManagedRemoting > 요소</span><span class="sxs-lookup"><span data-stu-id="ec6b4-102">\<PreferComInsteadOfManagedRemoting> Element</span></span>
<span data-ttu-id="ec6b4-103">런타임이 응용 프로그램 도메인 경계를 넘어 모든 호출에 대해 원격 대신 COM interop을 사용할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b4-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
 <span data-ttu-id="ec6b4-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ec6b4-104">\<configuration></span></span>  
<span data-ttu-id="ec6b4-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="ec6b4-105">\<runtime></span></span>  
<span data-ttu-id="ec6b4-106">\<PreferComInsteadOfManagedRemoting></span><span class="sxs-lookup"><span data-stu-id="ec6b4-106">\<PreferComInsteadOfManagedRemoting></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec6b4-107">구문</span><span class="sxs-lookup"><span data-stu-id="ec6b4-107">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ec6b4-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ec6b4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ec6b4-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ec6b4-110">특성</span><span class="sxs-lookup"><span data-stu-id="ec6b4-110">Attributes</span></span>  
  
|<span data-ttu-id="ec6b4-111">특성</span><span class="sxs-lookup"><span data-stu-id="ec6b4-111">Attribute</span></span>|<span data-ttu-id="ec6b4-112">설명</span><span class="sxs-lookup"><span data-stu-id="ec6b4-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="ec6b4-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b4-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="ec6b4-114">런타임이 응용 프로그램 도메인 경계를 넘어 원격이 아닌 COM interop 사용 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b4-114">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="ec6b4-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="ec6b4-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="ec6b4-116">값</span><span class="sxs-lookup"><span data-stu-id="ec6b4-116">Value</span></span>|<span data-ttu-id="ec6b4-117">설명</span><span class="sxs-lookup"><span data-stu-id="ec6b4-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="ec6b4-118">런타임은 응용 프로그램 도메인 경계에서 원격 기능을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b4-118">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="ec6b4-119">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b4-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="ec6b4-120">런타임은 응용 프로그램 도메인 경계에 걸쳐 COM interop를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b4-120">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ec6b4-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ec6b4-121">Child Elements</span></span>  
 <span data-ttu-id="ec6b4-122">없음</span><span class="sxs-lookup"><span data-stu-id="ec6b4-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ec6b4-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ec6b4-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ec6b4-124">요소</span><span class="sxs-lookup"><span data-stu-id="ec6b4-124">Element</span></span>|<span data-ttu-id="ec6b4-125">설명</span><span class="sxs-lookup"><span data-stu-id="ec6b4-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ec6b4-126">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b4-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="ec6b4-127">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b4-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec6b4-128">설명</span><span class="sxs-lookup"><span data-stu-id="ec6b4-128">Remarks</span></span>  
 <span data-ttu-id="ec6b4-129">`enabled` 특성을로 `true`설정 하면 런타임은 다음과 같이 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b4-129">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
- <span data-ttu-id="ec6b4-130">런타임은 [iunknown](https://go.microsoft.com/fwlink/?LinkId=148003) 인터페이스가 COM 인터페이스를 통해 도메인에 들어가면 [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) 인터페이스에 대해 [iunknown:: QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) 를 호출 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b4-130">The runtime does not call [IUnknown::QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="ec6b4-131">대신, 개체 주위에서 RCW ( [런타임 호출 가능 래퍼](../../../../../docs/standard/native-interop/runtime-callable-wrapper.md) )를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b4-131">Instead, it constructs a [Runtime Callable Wrapper](../../../../../docs/standard/native-interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
- <span data-ttu-id="ec6b4-132">런타임은이 도메인에서 만들어진 ccw ( `QueryInterface` [COM 호출 가능 래퍼](../../../../../docs/standard/native-interop/com-callable-wrapper.md) )에 대 한 [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) 인터페이스 호출을 받을 때 E_NOINTERFACE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b4-132">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../../docs/standard/native-interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="ec6b4-133">이러한 두 동작은 응용 프로그램 도메인 경계에서 관리 되는 개체 간의 COM 인터페이스에 대 한 모든 호출이 원격 대신 COM 및 COM interop을 사용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b4-133">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec6b4-134">예제</span><span class="sxs-lookup"><span data-stu-id="ec6b4-134">Example</span></span>  
 <span data-ttu-id="ec6b4-135">다음 예제에서는 런타임이 격리 경계를 넘어 COM interop를 사용 하도록 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b4-135">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ec6b4-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="ec6b4-136">See also</span></span>

- [<span data-ttu-id="ec6b4-137">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="ec6b4-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="ec6b4-138">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="ec6b4-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
