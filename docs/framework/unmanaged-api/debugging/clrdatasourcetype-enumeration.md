---
title: CLRDataSourceType 열거형
ms.date: 01/16/2019
api.name:
- CLRDataSourceType Enumeration
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- CLRDataSourceType Enumeration
helpviewer.keywords:
- CLRDataSourceType Enumeration [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 7ace405e2624f15b1cdb6d383222ae87c93289bb
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274103"
---
# <a name="clrdatasourcetype-enumeration"></a><span data-ttu-id="6f68c-102">CLRDataSourceType 열거형</span><span class="sxs-lookup"><span data-stu-id="6f68c-102">CLRDataSourceType Enumeration</span></span>

<span data-ttu-id="6f68c-103">CLRDATA_IL_ADDRESS_MAP 구조체에서 사용 되는 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f68c-103">Provides values that are used by the CLRDATA_IL_ADDRESS_MAP structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="6f68c-104">구문</span><span class="sxs-lookup"><span data-stu-id="6f68c-104">Syntax</span></span>

```cpp
typedef enum
{
    CLRDATA_SOURCE_TYPE_INVALID        = 0x00, // To indicate that nothing else applies
} CLRDataSourceType;
```

## <a name="members"></a><span data-ttu-id="6f68c-105">멤버</span><span class="sxs-lookup"><span data-stu-id="6f68c-105">Members</span></span>

| <span data-ttu-id="6f68c-106">멤버</span><span class="sxs-lookup"><span data-stu-id="6f68c-106">Member</span></span>                        | <span data-ttu-id="6f68c-107">설명</span><span class="sxs-lookup"><span data-stu-id="6f68c-107">Description</span></span>                           |
| ----------------------------- | ------------------------------------- |
| `CLRDATA_SOURCE_TYPE_INVALID` | <span data-ttu-id="6f68c-108">다른 항목이 적용 되지 않음을 나타내려면</span><span class="sxs-lookup"><span data-stu-id="6f68c-108">To indicate that nothing else applies</span></span> |

## <a name="remarks"></a><span data-ttu-id="6f68c-109">설명</span><span class="sxs-lookup"><span data-stu-id="6f68c-109">Remarks</span></span>

<span data-ttu-id="6f68c-110">이 열거형은 런타임 내부에 있고 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6f68c-110">This enumeration lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="6f68c-111">이를 사용 하려면 코드에서 위에 정의 된 열거형을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f68c-111">To use it, define an enumeration as defined above in your code.</span></span> <span data-ttu-id="6f68c-112">또한 [공통 데이터 형식](../common-data-types-unmanaged-api-reference.md)에 `CLRDATA_ENUM` 설명 된 대로이 별칭을로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f68c-112">This is also aliased to `CLRDATA_ENUM` as mentioned in [Common Data Types](../common-data-types-unmanaged-api-reference.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="6f68c-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6f68c-113">Requirements</span></span>

<span data-ttu-id="6f68c-114">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6f68c-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="6f68c-115">**헤더:** 없음</span><span class="sxs-lookup"><span data-stu-id="6f68c-115">**Header:** None</span></span>  
<span data-ttu-id="6f68c-116">**라이브러리** 없음</span><span class="sxs-lookup"><span data-stu-id="6f68c-116">**Library:** None</span></span>  
<span data-ttu-id="6f68c-117">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6f68c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="6f68c-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6f68c-118">See also</span></span>

- [<span data-ttu-id="6f68c-119">디버깅</span><span class="sxs-lookup"><span data-stu-id="6f68c-119">Debugging</span></span>](index.md)
- [<span data-ttu-id="6f68c-120">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="6f68c-120">Debugging Enumerations</span></span>](debugging-enumerations.md)
