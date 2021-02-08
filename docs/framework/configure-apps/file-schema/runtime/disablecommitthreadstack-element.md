---
description: '다음에 대 한 자세한 정보: <disableCommitThreadStack> 요소'
title: <disableCommitThreadStack> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCommitThreadStack
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCommitThreadStack
helpviewer_keywords:
- <disableCommitThreadStack> element
- disableCommitThreadStack element
ms.assetid: 3559d46a-7640-4c72-9a11-7e980768929e
ms.openlocfilehash: f80a23b12f67b9f3df1ddb010edb735225f6f7a8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787099"
---
# <a name="disablecommitthreadstack-element"></a><span data-ttu-id="03d46-103">\<disableCommitThreadStack> 요소</span><span class="sxs-lookup"><span data-stu-id="03d46-103">\<disableCommitThreadStack> Element</span></span>

<span data-ttu-id="03d46-104">스레드가 시작될 때 전체 스레드 스택을 커밋할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="03d46-104">Specifies whether the full thread stack is committed when a thread is started.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<disableCommitThreadStack>**  
  
## <a name="syntax"></a><span data-ttu-id="03d46-105">구문</span><span class="sxs-lookup"><span data-stu-id="03d46-105">Syntax</span></span>  
  
```xml  
<disableCommitThreadStack enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03d46-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="03d46-106">Attributes and Elements</span></span>  

 <span data-ttu-id="03d46-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="03d46-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03d46-108">특성</span><span class="sxs-lookup"><span data-stu-id="03d46-108">Attributes</span></span>  
  
|<span data-ttu-id="03d46-109">attribute</span><span class="sxs-lookup"><span data-stu-id="03d46-109">Attribute</span></span>|<span data-ttu-id="03d46-110">설명</span><span class="sxs-lookup"><span data-stu-id="03d46-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="03d46-111">사용</span><span class="sxs-lookup"><span data-stu-id="03d46-111">enabled</span></span>|<span data-ttu-id="03d46-112">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="03d46-112">Required attribute.</span></span><br /><br /> <span data-ttu-id="03d46-113">스레드 시작 시 전체 스레드 스택 커밋하기(기본 동작)의 해제 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="03d46-113">Specifies whether committing the full thread stack on thread startup (the default behavior) is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="03d46-114">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="03d46-114">enabled Attribute</span></span>  
  
|<span data-ttu-id="03d46-115">값</span><span class="sxs-lookup"><span data-stu-id="03d46-115">Value</span></span>|<span data-ttu-id="03d46-116">설명</span><span class="sxs-lookup"><span data-stu-id="03d46-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="03d46-117">0</span><span class="sxs-lookup"><span data-stu-id="03d46-117">0</span></span>|<span data-ttu-id="03d46-118">스레드가 시작될 때 전체 스레드 스택을 커밋하는 공용 언어 런타임의 기본 동작을 해제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03d46-118">Do not disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
|<span data-ttu-id="03d46-119">1</span><span class="sxs-lookup"><span data-stu-id="03d46-119">1</span></span>|<span data-ttu-id="03d46-120">스레드가 시작될 때 전체 스레드 스택을 커밋하는 공용 언어 런타임의 기본 동작을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="03d46-120">Disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="03d46-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="03d46-121">Child Elements</span></span>  

 <span data-ttu-id="03d46-122">없음</span><span class="sxs-lookup"><span data-stu-id="03d46-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="03d46-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="03d46-123">Parent Elements</span></span>  
  
|<span data-ttu-id="03d46-124">요소</span><span class="sxs-lookup"><span data-stu-id="03d46-124">Element</span></span>|<span data-ttu-id="03d46-125">설명</span><span class="sxs-lookup"><span data-stu-id="03d46-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="03d46-126">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="03d46-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="03d46-127">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="03d46-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03d46-128">설명</span><span class="sxs-lookup"><span data-stu-id="03d46-128">Remarks</span></span>  

 <span data-ttu-id="03d46-129">공용 언어 런타임의 기본 동작은 스레드가 시작될 때 전체 스레드 스택을 커밋하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="03d46-129">The default behavior of the common language runtime is to commit the full thread stack when a thread is started.</span></span> <span data-ttu-id="03d46-130">메모리가 제한적인 서버에서 대량의 스레드를 만들어야 하며 이러한 스레드 대부분이 스택 공간을 매우 적게 사용하는 경우, 스레드가 시작될 때 공용 언어 런타임이 전체 스레드 스택을 즉시 커밋하지 않는다면 서버 성능이 개선될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03d46-130">If a large number of threads must be created on a server that has limited memory, and most of those threads will use very little stack space, the server might perform better if the common language runtime does not commit the full thread stack immediately when a thread is started.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="03d46-131">관리되지 않는 호스트는 `STARTUP_DISABLE_COMMITTHREADSTACK` STARTUP_FLAGS [열거형에서](../../../unmanaged-api/hosting/startup-flags-enumeration.md) 시작 플래그를 사용하면 동일한 결과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03d46-131">Unmanaged hosts can use the `STARTUP_DISABLE_COMMITTHREADSTACK` startup flag in the [STARTUP_FLAGS](../../../unmanaged-api/hosting/startup-flags-enumeration.md) enumeration to accomplish the same result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03d46-132">예제</span><span class="sxs-lookup"><span data-stu-id="03d46-132">Example</span></span>  

 <span data-ttu-id="03d46-133">다음 예제에서는 스레드 시작 시 전체 스레드 스택을 커밋하는 공용 언어 런타임의 기본 동작을 해제하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="03d46-133">The following example shows how to disable the default behavior of the common language runtime, which is to commit the full thread stack on thread startup.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCommitThreadStack enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="03d46-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="03d46-134">See also</span></span>

- [<span data-ttu-id="03d46-135">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="03d46-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="03d46-136">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="03d46-136">Configuration File Schema</span></span>](../index.md)
