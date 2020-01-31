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
ms.openlocfilehash: 708c681a98113a406249a360c2fc81087e5b97f8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790420"
---
# <a name="ixclrdatamethoddefinition-interface"></a><span data-ttu-id="8c22b-102">IXCLRDataMethodDefinition 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8c22b-102">IXCLRDataMethodDefinition Interface</span></span>

<span data-ttu-id="8c22b-103">메서드 정의에 대 한 정보를 쿼리 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c22b-103">Provides methods for querying information about a method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="8c22b-104">메서드</span><span class="sxs-lookup"><span data-stu-id="8c22b-104">Methods</span></span>

<span data-ttu-id="8c22b-105">다음 메서드는 인터페이스에서 사용할 수 있는 몇 가지 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="8c22b-105">The following methods are some of the methods available in the interface.</span></span>

| <span data-ttu-id="8c22b-106">메서드</span><span class="sxs-lookup"><span data-stu-id="8c22b-106">Method</span></span>                                                                                                                          | <span data-ttu-id="8c22b-107">설명</span><span class="sxs-lookup"><span data-stu-id="8c22b-107">Description</span></span>                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="8c22b-108">StartEnumInstances</span><span class="sxs-lookup"><span data-stu-id="8c22b-108">StartEnumInstances</span></span>](ixclrdatamethoddefinition-startenuminstances-method.md) | <span data-ttu-id="8c22b-109">지정 된 `IXCLRDataAppDomain`에 대 한 메서드 인스턴스의 열거형 핸들을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c22b-109">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span> |
| [<span data-ttu-id="8c22b-110">EnumInstance</span><span class="sxs-lookup"><span data-stu-id="8c22b-110">EnumInstance</span></span>](ixclrdatamethoddefinition-enuminstance-method.md)             | <span data-ttu-id="8c22b-111">이 메서드 정의의 인스턴스를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c22b-111">Enumerates the instances of this method definition.</span></span>                                         |
| [<span data-ttu-id="8c22b-112">EndEnumInstances</span><span class="sxs-lookup"><span data-stu-id="8c22b-112">EndEnumInstances</span></span>](ixclrdatamethoddefinition-endenuminstances-method.md)     | <span data-ttu-id="8c22b-113">인스턴스 열거 중 사용 되는 내부 반복기에서 사용 하는 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c22b-113">Releases the resources used by internal iterators used during instance enumeration.</span></span>         |

## <a name="remarks"></a><span data-ttu-id="8c22b-114">주의</span><span class="sxs-lookup"><span data-stu-id="8c22b-114">Remarks</span></span>

<span data-ttu-id="8c22b-115">이 인터페이스는 런타임 내부에 있고 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8c22b-115">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="8c22b-116">그러나 일반적인 COM 메커니즘을 통해 가져올 수 있는 GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97`를 사용 하 여 `IUnknown`에서 파생 되는 COM 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="8c22b-116">However, it's a COM interface that derives from `IUnknown` with GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="8c22b-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8c22b-117">Requirements</span></span>

<span data-ttu-id="8c22b-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8c22b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="8c22b-119">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="8c22b-119">**Header:** None</span></span>  
<span data-ttu-id="8c22b-120">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="8c22b-120">**Library:** None</span></span>  
<span data-ttu-id="8c22b-121">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8c22b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="8c22b-122">참조</span><span class="sxs-lookup"><span data-stu-id="8c22b-122">See also</span></span>

- [<span data-ttu-id="8c22b-123">디버깅</span><span class="sxs-lookup"><span data-stu-id="8c22b-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="8c22b-124">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8c22b-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
