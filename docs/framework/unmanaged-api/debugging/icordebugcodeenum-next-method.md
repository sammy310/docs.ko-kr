---
description: '자세히 알아보기: ICorDebugCodeEnum:: Next 메서드'
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
ms.openlocfilehash: 51d46718891ce3df537c675175eacc4e33b92f79
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764751"
---
# <a name="icordebugcodeenumnext-method"></a><span data-ttu-id="a032a-103">ICorDebugCodeEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="a032a-103">ICorDebugCodeEnum::Next Method</span></span>

<span data-ttu-id="a032a-104">현재 위치에서 시작 하 여 열거형에서 지정 된 수의 "ICorDebugCode" 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a032a-104">Gets the specified number of "ICorDebugCode" instances from the enumeration, starting at the current position.</span></span>

## <a name="syntax"></a><span data-ttu-id="a032a-105">구문</span><span class="sxs-lookup"><span data-stu-id="a032a-105">Syntax</span></span>

```cpp
HRESULT Next (
    [in] ULONG  celt,
    [out, size_is(celt), length_is(*pceltFetched)]
        ICorDebugCode *values[],
    [out] ULONG *pceltFetched
);
```

## <a name="parameters"></a><span data-ttu-id="a032a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a032a-106">Parameters</span></span>

`celt`  
<span data-ttu-id="a032a-107">진행 `ICorDebugCode` 검색할 인스턴스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a032a-107">[in] The number of `ICorDebugCode` instances to be retrieved.</span></span>

`values`  
<span data-ttu-id="a032a-108">제한이 각각 개체를 가리키는 포인터의 배열입니다 `ICorDebugCode` .</span><span class="sxs-lookup"><span data-stu-id="a032a-108">[out] An array of pointers, each of which points to an `ICorDebugCode` object.</span></span>

`pceltFetched`  
<span data-ttu-id="a032a-109">제한이 실제로 반환 된 인스턴스 수에 대 한 포인터 `ICorDebugCode` 입니다.</span><span class="sxs-lookup"><span data-stu-id="a032a-109">[out] A pointer to the number of `ICorDebugCode` instances actually returned.</span></span> <span data-ttu-id="a032a-110">이 일 경우이 값은 null 일 수 있습니다 `celt` .</span><span class="sxs-lookup"><span data-stu-id="a032a-110">This value may be null if `celt` is one.</span></span>

## <a name="requirements"></a><span data-ttu-id="a032a-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a032a-111">Requirements</span></span>

<span data-ttu-id="a032a-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a032a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="a032a-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a032a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="a032a-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a032a-114">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="a032a-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a032a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
