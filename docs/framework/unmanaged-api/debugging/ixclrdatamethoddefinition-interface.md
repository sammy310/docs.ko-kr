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
ms.openlocfilehash: 4b1e8cb1cf34bb1c5ade1353351aab953e2b734a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670107"
---
# <a name="ixclrdatamethoddefinition-interface"></a><span data-ttu-id="739c7-102">IXCLRDataMethodDefinition 인터페이스</span><span class="sxs-lookup"><span data-stu-id="739c7-102">IXCLRDataMethodDefinition Interface</span></span>

<span data-ttu-id="739c7-103">메서드 정의 대 한 정보를 쿼리 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="739c7-103">Provides methods for querying information about a method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="739c7-104">메서드</span><span class="sxs-lookup"><span data-stu-id="739c7-104">Methods</span></span>

<span data-ttu-id="739c7-105">다음 메서드를 사용 하면 인터페이스에서 사용할 수 있는 방법의 같습니다.</span><span class="sxs-lookup"><span data-stu-id="739c7-105">The following methods are some of the methods available in the interface.</span></span>

| <span data-ttu-id="739c7-106">메서드</span><span class="sxs-lookup"><span data-stu-id="739c7-106">Method</span></span>                                                                                                                          | <span data-ttu-id="739c7-107">설명</span><span class="sxs-lookup"><span data-stu-id="739c7-107">Description</span></span>                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="739c7-108">StartEnumInstances</span><span class="sxs-lookup"><span data-stu-id="739c7-108">StartEnumInstances</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-startenuminstances-method.md) | <span data-ttu-id="739c7-109">에 대 한 메서드 인스턴스의 열거형에 대 한 핸들을 제공 된 지정 `IXCLRDataAppDomain`합니다.</span><span class="sxs-lookup"><span data-stu-id="739c7-109">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span> |
| [<span data-ttu-id="739c7-110">EnumInstance</span><span class="sxs-lookup"><span data-stu-id="739c7-110">EnumInstance</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-enuminstance-method.md)             | <span data-ttu-id="739c7-111">이 메서드 정의의 인스턴스를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="739c7-111">Enumerates the instances of this method definition.</span></span>                                         |
| [<span data-ttu-id="739c7-112">EndEnumInstances</span><span class="sxs-lookup"><span data-stu-id="739c7-112">EndEnumInstances</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-endenuminstances-method.md)     | <span data-ttu-id="739c7-113">인스턴스 열거 하는 동안 사용 되는 내부 반복기 사용 하는 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="739c7-113">Releases the resources used by internal iterators used during instance enumeration.</span></span>         |

## <a name="remarks"></a><span data-ttu-id="739c7-114">설명</span><span class="sxs-lookup"><span data-stu-id="739c7-114">Remarks</span></span>

<span data-ttu-id="739c7-115">이 인터페이스는 런타임 내에서 있으며 모든 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="739c7-115">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="739c7-116">그러나 COM 인터페이스에서 파생 되는 것 `IUnknown` GUID를 사용 하 여 `AAF60008-FB2C-420b-8FB1-42D244A54A97` 일반적인 COM 메커니즘을 통해 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="739c7-116">However, it's a COM interface that derives from `IUnknown` with GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="739c7-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="739c7-117">Requirements</span></span>

<span data-ttu-id="739c7-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="739c7-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="739c7-119">**헤더:** 없음</span><span class="sxs-lookup"><span data-stu-id="739c7-119">**Header:** None</span></span>  
<span data-ttu-id="739c7-120">**라이브러리:** 없음</span><span class="sxs-lookup"><span data-stu-id="739c7-120">**Library:** None</span></span>  
<span data-ttu-id="739c7-121">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="739c7-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="739c7-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="739c7-122">See also</span></span>

- [<span data-ttu-id="739c7-123">디버깅</span><span class="sxs-lookup"><span data-stu-id="739c7-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="739c7-124">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="739c7-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
