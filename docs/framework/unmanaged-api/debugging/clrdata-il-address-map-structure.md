---
title: CLRDATA_IL_ADDRESS_MAP 구조체
ms.date: 01/16/2019
api.name:
- CLRDATA_IL_ADDRESS_MAP Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- CLRDATA_IL_ADDRESS_MAP Structure
helpviewer.keywords:
- CLRDATA_IL_ADDRESS_MAP Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: e680a7a0dc3209d1988f6c84be0864572a74b3a4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179373"
---
# <a name="clrdata_il_address_map-structure"></a><span data-ttu-id="7bc5e-102">CLRDATA_IL_ADDRESS_MAP 구조체</span><span class="sxs-lookup"><span data-stu-id="7bc5e-102">CLRDATA_IL_ADDRESS_MAP Structure</span></span>

<span data-ttu-id="7bc5e-103">주소 매핑에 대한 IL을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7bc5e-103">Defines an IL to address mapping.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="7bc5e-104">구문</span><span class="sxs-lookup"><span data-stu-id="7bc5e-104">Syntax</span></span>

```cpp
typedef struct
{
    ULONG32 ilOffset;
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
    CLRDataSourceType type;
} CLRDATA_IL_ADDRESS_MAP;
```

## <a name="members"></a><span data-ttu-id="7bc5e-105">구성원</span><span class="sxs-lookup"><span data-stu-id="7bc5e-105">Members</span></span>

| <span data-ttu-id="7bc5e-106">멤버</span><span class="sxs-lookup"><span data-stu-id="7bc5e-106">Member</span></span>         | <span data-ttu-id="7bc5e-107">Description</span><span class="sxs-lookup"><span data-stu-id="7bc5e-107">Description</span></span>                                            |
| -------------- | ------------------------------------------------------ |
| `ilOffset`     | <span data-ttu-id="7bc5e-108">포함된 주소 범위에 대한 IL 오프셋</span><span class="sxs-lookup"><span data-stu-id="7bc5e-108">IL offset for the contained address range</span></span>              |
| `startAddress` | <span data-ttu-id="7bc5e-109">범위의 시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="7bc5e-109">The start address of the range.</span></span>                        |
| `endAddress`   | <span data-ttu-id="7bc5e-110">범위의 끝 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="7bc5e-110">The end address of the range.</span></span>                          |
| `type`         | <span data-ttu-id="7bc5e-111">데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7bc5e-111">The type of the data.</span></span> <span data-ttu-id="7bc5e-112">이 값은 현재 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bc5e-112">This value is currently not used</span></span> |

## <a name="remarks"></a><span data-ttu-id="7bc5e-113">설명</span><span class="sxs-lookup"><span data-stu-id="7bc5e-113">Remarks</span></span>

<span data-ttu-id="7bc5e-114">이 구조는 런타임 내에 있으며 헤더 나 라이브러리 파일을 통해 노출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bc5e-114">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="7bc5e-115">이를 사용하려면 위에 지정된 구조체를 `CLRDATA_ADDRESS` 정의하고, 여기서 64비트 서명되지 않은 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="7bc5e-115">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="7bc5e-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7bc5e-116">Requirements</span></span>

<span data-ttu-id="7bc5e-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7bc5e-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="7bc5e-118">**헤더:** 없음</span><span class="sxs-lookup"><span data-stu-id="7bc5e-118">**Header:** None</span></span>  
<span data-ttu-id="7bc5e-119">**라이브러리:** 없음 **.NET 프레임워크 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7bc5e-119">**Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="7bc5e-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7bc5e-120">See also</span></span>

- [<span data-ttu-id="7bc5e-121">CLRDataSource유형 열거형</span><span class="sxs-lookup"><span data-stu-id="7bc5e-121">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="7bc5e-122">디버깅</span><span class="sxs-lookup"><span data-stu-id="7bc5e-122">Debugging</span></span>](index.md)
- [<span data-ttu-id="7bc5e-123">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="7bc5e-123">Debugging Structures</span></span>](debugging-structures.md)
