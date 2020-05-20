---
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
ms.openlocfilehash: ebb689eee4a89a70e81d8f9d958e7826c3b3421b
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420957"
---
# <a name="ixclrdatamethoddefinition-interface"></a><span data-ttu-id="4e668-102">IXCLRDataMethodDefinition 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4e668-102">IXCLRDataMethodDefinition Interface</span></span>

<span data-ttu-id="4e668-103">메서드 정의에 대 한 정보를 쿼리 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e668-103">Provides methods for querying information about a method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="4e668-104">메서드</span><span class="sxs-lookup"><span data-stu-id="4e668-104">Methods</span></span>

<span data-ttu-id="4e668-105">다음 메서드는 인터페이스에서 사용할 수 있는 몇 가지 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="4e668-105">The following methods are some of the methods available in the interface.</span></span>

| <span data-ttu-id="4e668-106">메서드</span><span class="sxs-lookup"><span data-stu-id="4e668-106">Method</span></span>                                                                                                                          | <span data-ttu-id="4e668-107">설명</span><span class="sxs-lookup"><span data-stu-id="4e668-107">Description</span></span>                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="4e668-108">StartEnumInstances</span><span class="sxs-lookup"><span data-stu-id="4e668-108">StartEnumInstances</span></span>](ixclrdatamethoddefinition-startenuminstances-method.md) | <span data-ttu-id="4e668-109">지정 된에 대 한 메서드 인스턴스의 열거형 핸들을 제공 `IXCLRDataAppDomain` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e668-109">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span> |
| [<span data-ttu-id="4e668-110">EnumInstance</span><span class="sxs-lookup"><span data-stu-id="4e668-110">EnumInstance</span></span>](ixclrdatamethoddefinition-enuminstance-method.md)             | <span data-ttu-id="4e668-111">이 메서드 정의의 인스턴스를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e668-111">Enumerates the instances of this method definition.</span></span>                                         |
| [<span data-ttu-id="4e668-112">EndEnumInstances</span><span class="sxs-lookup"><span data-stu-id="4e668-112">EndEnumInstances</span></span>](ixclrdatamethoddefinition-endenuminstances-method.md)     | <span data-ttu-id="4e668-113">인스턴스 열거 중 사용 되는 내부 반복기에서 사용 하는 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e668-113">Releases the resources used by internal iterators used during instance enumeration.</span></span>         |

## <a name="remarks"></a><span data-ttu-id="4e668-114">설명</span><span class="sxs-lookup"><span data-stu-id="4e668-114">Remarks</span></span>

<span data-ttu-id="4e668-115">이 인터페이스는 런타임 내부에 있고 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e668-115">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="4e668-116">그러나 `IUnknown` `AAF60008-FB2C-420b-8FB1-42D244A54A97` 일반적인 com 메커니즘을 통해 가져올 수 있는 GUID를 사용 하 여에서 파생 되는 COM 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="4e668-116">However, it's a COM interface that derives from `IUnknown` with GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="4e668-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4e668-117">Requirements</span></span>

<span data-ttu-id="4e668-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e668-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="4e668-119">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="4e668-119">**Header:** None</span></span>  
<span data-ttu-id="4e668-120">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="4e668-120">**Library:** None</span></span>  
<span data-ttu-id="4e668-121">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4e668-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="4e668-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e668-122">See also</span></span>

- [<span data-ttu-id="4e668-123">디버깅</span><span class="sxs-lookup"><span data-stu-id="4e668-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="4e668-124">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4e668-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
