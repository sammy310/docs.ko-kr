---
title: CLRDATA_ADDRESS_RANGE 구조체
ms.date: 01/16/2019
api.name:
- CLRDATA_ADDRESS_RANGE Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- CLRDATA_ADDRESS_RANGE Structure
helpviewer.keywords:
- CLRDATA_ADDRESS_RANGE Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 8eb841b4c4f06a3932805ae6222bdd693def5ea0
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274305"
---
# <a name="clrdata_address_range-structure"></a><span data-ttu-id="f674e-102">CLRDATA_ADDRESS_RANGE 구조체</span><span class="sxs-lookup"><span data-stu-id="f674e-102">CLRDATA_ADDRESS_RANGE Structure</span></span>

<span data-ttu-id="f674e-103">주소 범위를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f674e-103">Defines an address range.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="f674e-104">구문</span><span class="sxs-lookup"><span data-stu-id="f674e-104">Syntax</span></span>

```cpp
typedef struct
{
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
} CLRDATA_ADDRESS_RANGE;
```

## <a name="members"></a><span data-ttu-id="f674e-105">멤버</span><span class="sxs-lookup"><span data-stu-id="f674e-105">Members</span></span>

| <span data-ttu-id="f674e-106">멤버</span><span class="sxs-lookup"><span data-stu-id="f674e-106">Member</span></span>         | <span data-ttu-id="f674e-107">설명</span><span class="sxs-lookup"><span data-stu-id="f674e-107">Description</span></span>                     |
| -------------- | ------------------------------- |
| `startAddress` | <span data-ttu-id="f674e-108">범위의 시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="f674e-108">The start address of the range.</span></span> |
| `endAddress`   | <span data-ttu-id="f674e-109">범위의 끝 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="f674e-109">The end address of the range.</span></span>   |

## <a name="remarks"></a><span data-ttu-id="f674e-110">설명</span><span class="sxs-lookup"><span data-stu-id="f674e-110">Remarks</span></span>

<span data-ttu-id="f674e-111">이 구조체는 런타임 내에 있으며 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f674e-111">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="f674e-112">이를 사용 하려면 위에 지정 된 대로 구조를 정의 합니다 `CLRDATA_ADDRESS` . 여기서은 64 비트의 부호 없는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="f674e-112">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="f674e-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f674e-113">Requirements</span></span>

<span data-ttu-id="f674e-114">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f674e-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="f674e-115">**헤더:** 없음</span><span class="sxs-lookup"><span data-stu-id="f674e-115">**Header:** None</span></span>  
<span data-ttu-id="f674e-116">**라이브러리** 없음</span><span class="sxs-lookup"><span data-stu-id="f674e-116">**Library:** None</span></span>  
<span data-ttu-id="f674e-117">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f674e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="f674e-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f674e-118">See also</span></span>

- [<span data-ttu-id="f674e-119">디버깅</span><span class="sxs-lookup"><span data-stu-id="f674e-119">Debugging</span></span>](index.md)
- [<span data-ttu-id="f674e-120">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="f674e-120">Debugging Structures</span></span>](debugging-structures.md)
