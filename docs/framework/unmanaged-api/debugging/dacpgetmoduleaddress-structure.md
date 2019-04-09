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
ms.openlocfilehash: cbea6c0562c68ae5d18247dc97bc53eb9dfbfd7e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59104112"
---
# <a name="dacpgetmoduleaddress-structure"></a><span data-ttu-id="b1f8c-102">DacpGetModuleAddress 구조</span><span class="sxs-lookup"><span data-stu-id="b1f8c-102">DacpGetModuleAddress Structure</span></span>

<span data-ttu-id="b1f8c-103">모듈 주소 요청에 대 한 컨테이너를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f8c-103">Defines the container for a module address request.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="b1f8c-104">구문</span><span class="sxs-lookup"><span data-stu-id="b1f8c-104">Syntax</span></span>

```
struct DacpGetModuleAddress
{
    CLRDATA_ADDRESS ModulePtr;
};
```

## <a name="members"></a><span data-ttu-id="b1f8c-105">멤버</span><span class="sxs-lookup"><span data-stu-id="b1f8c-105">Members</span></span>

| <span data-ttu-id="b1f8c-106">멤버</span><span class="sxs-lookup"><span data-stu-id="b1f8c-106">Member</span></span>      | <span data-ttu-id="b1f8c-107">설명</span><span class="sxs-lookup"><span data-stu-id="b1f8c-107">Description</span></span>                |
| ----------- | -------------------------- |
| `ModulePtr` | <span data-ttu-id="b1f8c-108">모듈에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b1f8c-108">The pointer to the module.</span></span> |

## <a name="methods"></a><span data-ttu-id="b1f8c-109">메서드</span><span class="sxs-lookup"><span data-stu-id="b1f8c-109">Methods</span></span>

| <span data-ttu-id="b1f8c-110">메서드</span><span class="sxs-lookup"><span data-stu-id="b1f8c-110">Method</span></span>                                                                                               | <span data-ttu-id="b1f8c-111">설명</span><span class="sxs-lookup"><span data-stu-id="b1f8c-111">Description</span></span>                                                                    |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [<span data-ttu-id="b1f8c-112">요청</span><span class="sxs-lookup"><span data-stu-id="b1f8c-112">Request</span></span>](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-request-method.md) | <span data-ttu-id="b1f8c-113">지정 된 런타임 구조에서 구조를 채우는 데 요청을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f8c-113">Performs a request to populate the structure from the given runtime structure.</span></span> |

## <a name="remarks"></a><span data-ttu-id="b1f8c-114">설명</span><span class="sxs-lookup"><span data-stu-id="b1f8c-114">Remarks</span></span>

<span data-ttu-id="b1f8c-115">이 구조는 런타임 내에서 있으며 모든 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f8c-115">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="b1f8c-116">를 사용 하려면 구조를 정의 위에 지정 된 대로 위치 `CLRDATA_ADDRESS` 는 64 비트 부호 없는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="b1f8c-116">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="b1f8c-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b1f8c-117">Requirements</span></span>
<span data-ttu-id="b1f8c-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b1f8c-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="b1f8c-119">**헤더:** 없음</span><span class="sxs-lookup"><span data-stu-id="b1f8c-119">**Header:** None</span></span>  
<span data-ttu-id="b1f8c-120">**라이브러리:** 없음</span><span class="sxs-lookup"><span data-stu-id="b1f8c-120">**Library:** None</span></span>  
**<span data-ttu-id="b1f8c-121">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="b1f8c-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a><span data-ttu-id="b1f8c-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="b1f8c-122">See also</span></span>

- [<span data-ttu-id="b1f8c-123">디버깅</span><span class="sxs-lookup"><span data-stu-id="b1f8c-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="b1f8c-124">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="b1f8c-124">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
