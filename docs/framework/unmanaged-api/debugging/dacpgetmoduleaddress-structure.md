---
title: DacpGetModuleAddress 구조체
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
ms.openlocfilehash: 1e3a62de3259c012438c64ece26e696682ec96e6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789198"
---
# <a name="dacpgetmoduleaddress-structure"></a><span data-ttu-id="84cca-102">DacpGetModuleAddress 구조체</span><span class="sxs-lookup"><span data-stu-id="84cca-102">DacpGetModuleAddress Structure</span></span>

<span data-ttu-id="84cca-103">모듈 주소 요청에 대 한 컨테이너를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="84cca-103">Defines the container for a module address request.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="84cca-104">구문</span><span class="sxs-lookup"><span data-stu-id="84cca-104">Syntax</span></span>

```cpp
struct DacpGetModuleAddress
{
    CLRDATA_ADDRESS ModulePtr;
};
```

## <a name="members"></a><span data-ttu-id="84cca-105">Members</span><span class="sxs-lookup"><span data-stu-id="84cca-105">Members</span></span>

| <span data-ttu-id="84cca-106">Member</span><span class="sxs-lookup"><span data-stu-id="84cca-106">Member</span></span>      | <span data-ttu-id="84cca-107">설명</span><span class="sxs-lookup"><span data-stu-id="84cca-107">Description</span></span>                |
| ----------- | -------------------------- |
| `ModulePtr` | <span data-ttu-id="84cca-108">모듈에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="84cca-108">The pointer to the module.</span></span> |

## <a name="methods"></a><span data-ttu-id="84cca-109">메서드</span><span class="sxs-lookup"><span data-stu-id="84cca-109">Methods</span></span>

| <span data-ttu-id="84cca-110">메서드</span><span class="sxs-lookup"><span data-stu-id="84cca-110">Method</span></span>                                                                                               | <span data-ttu-id="84cca-111">설명</span><span class="sxs-lookup"><span data-stu-id="84cca-111">Description</span></span>                                                                    |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [<span data-ttu-id="84cca-112">요청</span><span class="sxs-lookup"><span data-stu-id="84cca-112">Request</span></span>](dacpgetmoduleaddress-request-method.md) | <span data-ttu-id="84cca-113">지정 된 런타임 구조체에서 구조체를 채우도록 요청을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="84cca-113">Performs a request to populate the structure from the given runtime structure.</span></span> |

## <a name="remarks"></a><span data-ttu-id="84cca-114">주의</span><span class="sxs-lookup"><span data-stu-id="84cca-114">Remarks</span></span>

<span data-ttu-id="84cca-115">이 구조체는 런타임 내에 있으며 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84cca-115">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="84cca-116">이를 사용 하려면 위에 지정 된 대로 구조를 정의 합니다. 여기서 `CLRDATA_ADDRESS`는 64 비트 부호 없는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="84cca-116">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="84cca-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="84cca-117">Requirements</span></span>
<span data-ttu-id="84cca-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84cca-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="84cca-119">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="84cca-119">**Header:** None</span></span>  
<span data-ttu-id="84cca-120">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="84cca-120">**Library:** None</span></span>  
<span data-ttu-id="84cca-121">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="84cca-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="84cca-122">참조</span><span class="sxs-lookup"><span data-stu-id="84cca-122">See also</span></span>

- [<span data-ttu-id="84cca-123">디버깅</span><span class="sxs-lookup"><span data-stu-id="84cca-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="84cca-124">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="84cca-124">Debugging Structures</span></span>](debugging-structures.md)
