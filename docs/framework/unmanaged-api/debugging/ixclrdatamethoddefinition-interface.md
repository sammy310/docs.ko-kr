---
description: '자세히 알아보기: IXCLRDataMethodDefinition 인터페이스'
title: IXCLRDataMethodDefinition 인터페이스
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition Interface
helpviewer.keywords:
- IXCLRDataMethodDefinition Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: d73246b42a0bfb982c87b04d5490e945f7caa745
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790349"
---
# <a name="ixclrdatamethoddefinition-interface"></a><span data-ttu-id="e9ae3-103">IXCLRDataMethodDefinition 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e9ae3-103">IXCLRDataMethodDefinition Interface</span></span>

<span data-ttu-id="e9ae3-104">메서드 정의에 대 한 정보를 쿼리 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9ae3-104">Provides methods for querying information about a method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="e9ae3-105">메서드</span><span class="sxs-lookup"><span data-stu-id="e9ae3-105">Methods</span></span>

<span data-ttu-id="e9ae3-106">다음 메서드는 인터페이스에서 사용할 수 있는 몇 가지 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="e9ae3-106">The following methods are some of the methods available in the interface.</span></span>

| <span data-ttu-id="e9ae3-107">메서드</span><span class="sxs-lookup"><span data-stu-id="e9ae3-107">Method</span></span>                                                                                                                          | <span data-ttu-id="e9ae3-108">설명</span><span class="sxs-lookup"><span data-stu-id="e9ae3-108">Description</span></span>                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="e9ae3-109">StartEnumInstances</span><span class="sxs-lookup"><span data-stu-id="e9ae3-109">StartEnumInstances</span></span>](ixclrdatamethoddefinition-startenuminstances-method.md) | <span data-ttu-id="e9ae3-110">지정 된에 대 한 메서드 인스턴스의 열거형 핸들을 제공 `IXCLRDataAppDomain` 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9ae3-110">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span> |
| [<span data-ttu-id="e9ae3-111">EnumInstance</span><span class="sxs-lookup"><span data-stu-id="e9ae3-111">EnumInstance</span></span>](ixclrdatamethoddefinition-enuminstance-method.md)             | <span data-ttu-id="e9ae3-112">이 메서드 정의의 인스턴스를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9ae3-112">Enumerates the instances of this method definition.</span></span>                                         |
| [<span data-ttu-id="e9ae3-113">EndEnumInstances</span><span class="sxs-lookup"><span data-stu-id="e9ae3-113">EndEnumInstances</span></span>](ixclrdatamethoddefinition-endenuminstances-method.md)     | <span data-ttu-id="e9ae3-114">인스턴스 열거 중 사용 되는 내부 반복기에서 사용 하는 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9ae3-114">Releases the resources used by internal iterators used during instance enumeration.</span></span>         |

## <a name="remarks"></a><span data-ttu-id="e9ae3-115">설명</span><span class="sxs-lookup"><span data-stu-id="e9ae3-115">Remarks</span></span>

<span data-ttu-id="e9ae3-116">이 인터페이스는 런타임 내부에 있고 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e9ae3-116">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="e9ae3-117">그러나 `IUnknown` `AAF60008-FB2C-420b-8FB1-42D244A54A97` 일반적인 com 메커니즘을 통해 가져올 수 있는 GUID를 사용 하 여에서 파생 되는 COM 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="e9ae3-117">However, it's a COM interface that derives from `IUnknown` with GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="e9ae3-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e9ae3-118">Requirements</span></span>

<span data-ttu-id="e9ae3-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e9ae3-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="e9ae3-120">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="e9ae3-120">**Header:** None</span></span>  
<span data-ttu-id="e9ae3-121">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="e9ae3-121">**Library:** None</span></span>  
<span data-ttu-id="e9ae3-122">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e9ae3-122">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="e9ae3-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e9ae3-123">See also</span></span>

- [<span data-ttu-id="e9ae3-124">디버깅</span><span class="sxs-lookup"><span data-stu-id="e9ae3-124">Debugging</span></span>](index.md)
- [<span data-ttu-id="e9ae3-125">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e9ae3-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
