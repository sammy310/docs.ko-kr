---
description: '다음에 대 한 자세한 정보: CLRDATA_ADDRESS_RANGE 구조체'
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
ms.openlocfilehash: 5d671a08064781b71756efc3c753468e6769d4ce
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662340"
---
# <a name="clrdata_address_range-structure"></a><span data-ttu-id="c6958-103">CLRDATA_ADDRESS_RANGE 구조체</span><span class="sxs-lookup"><span data-stu-id="c6958-103">CLRDATA_ADDRESS_RANGE Structure</span></span>

<span data-ttu-id="c6958-104">주소 범위를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6958-104">Defines an address range.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="c6958-105">구문</span><span class="sxs-lookup"><span data-stu-id="c6958-105">Syntax</span></span>

```cpp
typedef struct
{
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
} CLRDATA_ADDRESS_RANGE;
```

## <a name="members"></a><span data-ttu-id="c6958-106">구성원</span><span class="sxs-lookup"><span data-stu-id="c6958-106">Members</span></span>

| <span data-ttu-id="c6958-107">멤버</span><span class="sxs-lookup"><span data-stu-id="c6958-107">Member</span></span>         | <span data-ttu-id="c6958-108">설명</span><span class="sxs-lookup"><span data-stu-id="c6958-108">Description</span></span>                     |
| -------------- | ------------------------------- |
| `startAddress` | <span data-ttu-id="c6958-109">범위의 시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="c6958-109">The start address of the range.</span></span> |
| `endAddress`   | <span data-ttu-id="c6958-110">범위의 끝 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="c6958-110">The end address of the range.</span></span>   |

## <a name="remarks"></a><span data-ttu-id="c6958-111">설명</span><span class="sxs-lookup"><span data-stu-id="c6958-111">Remarks</span></span>

<span data-ttu-id="c6958-112">이 구조체는 런타임 내에 있으며 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c6958-112">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="c6958-113">이를 사용 하려면 위에 지정 된 대로 구조를 정의 합니다 `CLRDATA_ADDRESS` . 여기서은 64 비트의 부호 없는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="c6958-113">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="c6958-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c6958-114">Requirements</span></span>

<span data-ttu-id="c6958-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c6958-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="c6958-116">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="c6958-116">**Header:** None</span></span>  
<span data-ttu-id="c6958-117">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="c6958-117">**Library:** None</span></span>  
<span data-ttu-id="c6958-118">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c6958-118">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="c6958-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c6958-119">See also</span></span>

- [<span data-ttu-id="c6958-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="c6958-120">Debugging</span></span>](index.md)
- [<span data-ttu-id="c6958-121">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="c6958-121">Debugging Structures</span></span>](debugging-structures.md)
