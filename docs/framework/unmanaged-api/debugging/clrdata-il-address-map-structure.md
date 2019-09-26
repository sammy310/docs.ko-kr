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
ms.openlocfilehash: 3f6928832d822422177ebd7def142422953468a0
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274289"
---
# <a name="clrdata_il_address_map-structure"></a><span data-ttu-id="1ad52-102">CLRDATA_IL_ADDRESS_MAP 구조체</span><span class="sxs-lookup"><span data-stu-id="1ad52-102">CLRDATA_IL_ADDRESS_MAP Structure</span></span>

<span data-ttu-id="1ad52-103">매핑을 처리할 IL을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ad52-103">Defines an IL to address mapping.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="1ad52-104">구문</span><span class="sxs-lookup"><span data-stu-id="1ad52-104">Syntax</span></span>

```cpp
typedef struct
{
    ULONG32 ilOffset;
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
    CLRDataSourceType type;
} CLRDATA_IL_ADDRESS_MAP;
```

## <a name="members"></a><span data-ttu-id="1ad52-105">멤버</span><span class="sxs-lookup"><span data-stu-id="1ad52-105">Members</span></span>

| <span data-ttu-id="1ad52-106">멤버</span><span class="sxs-lookup"><span data-stu-id="1ad52-106">Member</span></span>         | <span data-ttu-id="1ad52-107">설명</span><span class="sxs-lookup"><span data-stu-id="1ad52-107">Description</span></span>                                            |
| -------------- | ------------------------------------------------------ |
| `ilOffset`     | <span data-ttu-id="1ad52-108">포함 된 주소 범위에 대 한 IL 오프셋</span><span class="sxs-lookup"><span data-stu-id="1ad52-108">IL offset for the contained address range</span></span>              |
| `startAddress` | <span data-ttu-id="1ad52-109">범위의 시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="1ad52-109">The start address of the range.</span></span>                        |
| `endAddress`   | <span data-ttu-id="1ad52-110">범위의 끝 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="1ad52-110">The end address of the range.</span></span>                          |
| `type`         | <span data-ttu-id="1ad52-111">데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1ad52-111">The type of the data.</span></span> <span data-ttu-id="1ad52-112">이 값은 현재 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ad52-112">This value is currently not used</span></span> |

## <a name="remarks"></a><span data-ttu-id="1ad52-113">설명</span><span class="sxs-lookup"><span data-stu-id="1ad52-113">Remarks</span></span>

<span data-ttu-id="1ad52-114">이 구조체는 런타임 내에 있으며 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ad52-114">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="1ad52-115">이를 사용 하려면 위에 지정 된 대로 구조를 정의 합니다 `CLRDATA_ADDRESS` . 여기서은 64 비트의 부호 없는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="1ad52-115">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="1ad52-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1ad52-116">Requirements</span></span>

<span data-ttu-id="1ad52-117">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1ad52-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="1ad52-118">**헤더:** 없음</span><span class="sxs-lookup"><span data-stu-id="1ad52-118">**Header:** None</span></span>  
<span data-ttu-id="1ad52-119">**라이브러리** 없음</span><span class="sxs-lookup"><span data-stu-id="1ad52-119">**Library:** None</span></span>   
<span data-ttu-id="1ad52-120">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1ad52-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="1ad52-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1ad52-121">See also</span></span>

- [<span data-ttu-id="1ad52-122">CLRDataSourceType 열거형</span><span class="sxs-lookup"><span data-stu-id="1ad52-122">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="1ad52-123">디버깅</span><span class="sxs-lookup"><span data-stu-id="1ad52-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="1ad52-124">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="1ad52-124">Debugging Structures</span></span>](debugging-structures.md)
