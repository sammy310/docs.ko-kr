---
description: '자세히 알아보기: CLRDataSourceType 열거형'
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
ms.openlocfilehash: 06590e21aa4cdf6e89977a79da36a413d5ff4f1c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747244"
---
# <a name="clrdatasourcetype-enumeration"></a><span data-ttu-id="dcdb1-103">CLRDataSourceType 열거형</span><span class="sxs-lookup"><span data-stu-id="dcdb1-103">CLRDataSourceType Enumeration</span></span>

<span data-ttu-id="dcdb1-104">CLRDATA_IL_ADDRESS_MAP 구조체에서 사용 되는 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcdb1-104">Provides values that are used by the CLRDATA_IL_ADDRESS_MAP structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="dcdb1-105">구문</span><span class="sxs-lookup"><span data-stu-id="dcdb1-105">Syntax</span></span>

```cpp
typedef enum
{
    CLRDATA_SOURCE_TYPE_INVALID        = 0x00, // To indicate that nothing else applies
} CLRDataSourceType;
```

## <a name="members"></a><span data-ttu-id="dcdb1-106">구성원</span><span class="sxs-lookup"><span data-stu-id="dcdb1-106">Members</span></span>

| <span data-ttu-id="dcdb1-107">멤버</span><span class="sxs-lookup"><span data-stu-id="dcdb1-107">Member</span></span>                        | <span data-ttu-id="dcdb1-108">설명</span><span class="sxs-lookup"><span data-stu-id="dcdb1-108">Description</span></span>                           |
| ----------------------------- | ------------------------------------- |
| `CLRDATA_SOURCE_TYPE_INVALID` | <span data-ttu-id="dcdb1-109">다른 항목이 적용 되지 않음을 나타내려면</span><span class="sxs-lookup"><span data-stu-id="dcdb1-109">To indicate that nothing else applies</span></span> |

## <a name="remarks"></a><span data-ttu-id="dcdb1-110">설명</span><span class="sxs-lookup"><span data-stu-id="dcdb1-110">Remarks</span></span>

<span data-ttu-id="dcdb1-111">이 열거형은 런타임 내부에 있고 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dcdb1-111">This enumeration lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="dcdb1-112">이를 사용 하려면 코드에서 위에 정의 된 열거형을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcdb1-112">To use it, define an enumeration as defined above in your code.</span></span> <span data-ttu-id="dcdb1-113">또한 `CLRDATA_ENUM` [공통 데이터 형식](../common-data-types-unmanaged-api-reference.md)에 설명 된 대로이 별칭을로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcdb1-113">This is also aliased to `CLRDATA_ENUM` as mentioned in [Common Data Types](../common-data-types-unmanaged-api-reference.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="dcdb1-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dcdb1-114">Requirements</span></span>

<span data-ttu-id="dcdb1-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dcdb1-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="dcdb1-116">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="dcdb1-116">**Header:** None</span></span>  
<span data-ttu-id="dcdb1-117">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="dcdb1-117">**Library:** None</span></span>  
<span data-ttu-id="dcdb1-118">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="dcdb1-118">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="dcdb1-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dcdb1-119">See also</span></span>

- [<span data-ttu-id="dcdb1-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="dcdb1-120">Debugging</span></span>](index.md)
- [<span data-ttu-id="dcdb1-121">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="dcdb1-121">Debugging Enumerations</span></span>](debugging-enumerations.md)
