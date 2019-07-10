---
title: DacpGetModuleAddress 구조
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress Structure
helpviewer.keywords:
- DacpGetModuleAddress Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 145b06f89b45b165b9d6329a4c16ac5739406113
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739187"
---
# <a name="dacpgetmoduleaddress-structure"></a><span data-ttu-id="c9a0f-102">DacpGetModuleAddress 구조</span><span class="sxs-lookup"><span data-stu-id="c9a0f-102">DacpGetModuleAddress Structure</span></span>

<span data-ttu-id="c9a0f-103">모듈 주소 요청에 대 한 컨테이너를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c9a0f-103">Defines the container for a module address request.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="c9a0f-104">구문</span><span class="sxs-lookup"><span data-stu-id="c9a0f-104">Syntax</span></span>

```cpp
struct DacpGetModuleAddress
{
    CLRDATA_ADDRESS ModulePtr;
};
```

## <a name="members"></a><span data-ttu-id="c9a0f-105">멤버</span><span class="sxs-lookup"><span data-stu-id="c9a0f-105">Members</span></span>

| <span data-ttu-id="c9a0f-106">멤버</span><span class="sxs-lookup"><span data-stu-id="c9a0f-106">Member</span></span>      | <span data-ttu-id="c9a0f-107">설명</span><span class="sxs-lookup"><span data-stu-id="c9a0f-107">Description</span></span>                |
| ----------- | -------------------------- |
| `ModulePtr` | <span data-ttu-id="c9a0f-108">모듈에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c9a0f-108">The pointer to the module.</span></span> |

## <a name="methods"></a><span data-ttu-id="c9a0f-109">메서드</span><span class="sxs-lookup"><span data-stu-id="c9a0f-109">Methods</span></span>

| <span data-ttu-id="c9a0f-110">메서드</span><span class="sxs-lookup"><span data-stu-id="c9a0f-110">Method</span></span>                                                                                               | <span data-ttu-id="c9a0f-111">설명</span><span class="sxs-lookup"><span data-stu-id="c9a0f-111">Description</span></span>                                                                    |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [<span data-ttu-id="c9a0f-112">요청</span><span class="sxs-lookup"><span data-stu-id="c9a0f-112">Request</span></span>](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-request-method.md) | <span data-ttu-id="c9a0f-113">지정 된 런타임 구조에서 구조를 채우는 데 요청을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9a0f-113">Performs a request to populate the structure from the given runtime structure.</span></span> |

## <a name="remarks"></a><span data-ttu-id="c9a0f-114">설명</span><span class="sxs-lookup"><span data-stu-id="c9a0f-114">Remarks</span></span>

<span data-ttu-id="c9a0f-115">이 구조는 런타임 내에서 있으며 모든 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9a0f-115">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="c9a0f-116">를 사용 하려면 구조를 정의 위에 지정 된 대로 위치 `CLRDATA_ADDRESS` 는 64 비트 부호 없는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="c9a0f-116">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="c9a0f-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c9a0f-117">Requirements</span></span>
<span data-ttu-id="c9a0f-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c9a0f-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="c9a0f-119">**헤더:** 없음</span><span class="sxs-lookup"><span data-stu-id="c9a0f-119">**Header:** None</span></span>  
<span data-ttu-id="c9a0f-120">**라이브러리:** 없음</span><span class="sxs-lookup"><span data-stu-id="c9a0f-120">**Library:** None</span></span>  
<span data-ttu-id="c9a0f-121">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c9a0f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="c9a0f-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="c9a0f-122">See also</span></span>

- [<span data-ttu-id="c9a0f-123">디버깅</span><span class="sxs-lookup"><span data-stu-id="c9a0f-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="c9a0f-124">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="c9a0f-124">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
