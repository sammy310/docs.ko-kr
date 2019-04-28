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
ms.openlocfilehash: c8b3f338659e2784db8deca3e1776e7926c30c32
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609696"
---
# <a name="clrdatasourcetype-enumeration"></a><span data-ttu-id="9897e-102">CLRDataSourceType 열거형</span><span class="sxs-lookup"><span data-stu-id="9897e-102">CLRDataSourceType Enumeration</span></span>

<span data-ttu-id="9897e-103">CLRDATA_IL_ADDRESS_MAP 구조에서 사용 되는 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9897e-103">Provides values that are used by the CLRDATA_IL_ADDRESS_MAP structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="9897e-104">구문</span><span class="sxs-lookup"><span data-stu-id="9897e-104">Syntax</span></span>

```
typedef enum
{
    CLRDATA_SOURCE_TYPE_INVALID        = 0x00, // To indicate that nothing else applies
} CLRDataSourceType;
```

## <a name="members"></a><span data-ttu-id="9897e-105">멤버</span><span class="sxs-lookup"><span data-stu-id="9897e-105">Members</span></span>

| <span data-ttu-id="9897e-106">멤버</span><span class="sxs-lookup"><span data-stu-id="9897e-106">Member</span></span>                        | <span data-ttu-id="9897e-107">설명</span><span class="sxs-lookup"><span data-stu-id="9897e-107">Description</span></span>                           |
| ----------------------------- | ------------------------------------- |
| `CLRDATA_SOURCE_TYPE_INVALID` | <span data-ttu-id="9897e-108">아무 적용 되도록 나타내려면</span><span class="sxs-lookup"><span data-stu-id="9897e-108">To indicate that nothing else applies</span></span> |

## <a name="remarks"></a><span data-ttu-id="9897e-109">설명</span><span class="sxs-lookup"><span data-stu-id="9897e-109">Remarks</span></span>

<span data-ttu-id="9897e-110">이 열거형은 런타임 내에서 있으며 모든 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9897e-110">This enumeration lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="9897e-111">를 사용 하려면 코드에서 위에 정의 된 열거형을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="9897e-111">To use it, define an enumeration as defined above in your code.</span></span> <span data-ttu-id="9897e-112">별칭으로 이기도 `CLRDATA_ENUM` 에 설명 된 대로 [공통 데이터 형식](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9897e-112">This is also aliased to `CLRDATA_ENUM` as mentioned in [Common Data Types](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="9897e-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9897e-113">Requirements</span></span>

<span data-ttu-id="9897e-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9897e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="9897e-115">**헤더:** 없음</span><span class="sxs-lookup"><span data-stu-id="9897e-115">**Header:** None</span></span>  
<span data-ttu-id="9897e-116">**라이브러리:** 없음</span><span class="sxs-lookup"><span data-stu-id="9897e-116">**Library:** None</span></span>  
<span data-ttu-id="9897e-117">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9897e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="9897e-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="9897e-118">See also</span></span>

- [<span data-ttu-id="9897e-119">디버깅</span><span class="sxs-lookup"><span data-stu-id="9897e-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="9897e-120">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="9897e-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
