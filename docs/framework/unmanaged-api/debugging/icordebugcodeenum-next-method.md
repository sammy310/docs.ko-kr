---
title: ICorDebugCodeEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugCodeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCodeEnum::Next
helpviewer_keywords:
- ICorDebugCodeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 644ece86-384d-4c63-9fba-52c789616ff7
topic_type:
- apiref
ms.openlocfilehash: 04c36d1e5f0e79b71963683a3b613a9ad7392bcf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125520"
---
# <a name="icordebugcodeenumnext-method"></a><span data-ttu-id="1074b-102">ICorDebugCodeEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="1074b-102">ICorDebugCodeEnum::Next Method</span></span>

<span data-ttu-id="1074b-103">현재 위치에서 시작 하 여 열거형에서 지정 된 수의 "ICorDebugCode" 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1074b-103">Gets the specified number of "ICorDebugCode" instances from the enumeration, starting at the current position.</span></span>

## <a name="syntax"></a><span data-ttu-id="1074b-104">구문</span><span class="sxs-lookup"><span data-stu-id="1074b-104">Syntax</span></span>

```cpp
HRESULT Next (
    [in] ULONG  celt,
    [out, size_is(celt), length_is(*pceltFetched)]
        ICorDebugCode *values[],
    [out] ULONG *pceltFetched
);
```

## <a name="parameters"></a><span data-ttu-id="1074b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1074b-105">Parameters</span></span>

`celt`  
<span data-ttu-id="1074b-106">진행 검색할 `ICorDebugCode` 인스턴스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1074b-106">[in] The number of `ICorDebugCode` instances to be retrieved.</span></span>

`values`  
<span data-ttu-id="1074b-107">제한이 각각 `ICorDebugCode` 개체를 가리키는 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="1074b-107">[out] An array of pointers, each of which points to an `ICorDebugCode` object.</span></span>

`pceltFetched`  
<span data-ttu-id="1074b-108">제한이 실제로 반환 된 `ICorDebugCode` 인스턴스 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1074b-108">[out] A pointer to the number of `ICorDebugCode` instances actually returned.</span></span> <span data-ttu-id="1074b-109">`celt` 일 경우이 값은 null 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1074b-109">This value may be null if `celt` is one.</span></span>

## <a name="requirements"></a><span data-ttu-id="1074b-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1074b-110">Requirements</span></span>

<span data-ttu-id="1074b-111">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1074b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="1074b-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1074b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="1074b-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1074b-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="1074b-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1074b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
