---
description: ICorDebugProcess4::P rocessStateChanged 메서드에 대해 자세히 알아보세요.
title: ICorDebugProcess4::P rocessStateChanged 메서드
ms.date: 02/07/2019
api_name:
- ICorDebugProcess4::ProcessStateChanged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess4::ProcessStateChanged
helpviewer_keywords:
- ICorDebugProcess4::ProcessStateChanged method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 35a76b3c6dd9b37d3f06f23bc2ffea82f125a29e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746473"
---
# <a name="icordebugprocess4processstatechanged-method"></a><span data-ttu-id="7218d-103">ICorDebugProcess4::P rocessStateChanged 메서드</span><span class="sxs-lookup"><span data-stu-id="7218d-103">ICorDebugProcess4::ProcessStateChanged Method</span></span>

<span data-ttu-id="7218d-104">ICorDebug 파이프라인에 out of process 디버거가 디버기의의 실행을 계속 진행 중임을 알립니다.</span><span class="sxs-lookup"><span data-stu-id="7218d-104">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span>

## <a name="syntax"></a><span data-ttu-id="7218d-105">구문</span><span class="sxs-lookup"><span data-stu-id="7218d-105">Syntax</span></span>

```cpp
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a><span data-ttu-id="7218d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7218d-106">Parameters</span></span>

 `eChange`\
<span data-ttu-id="7218d-107">진행 프로세스 실행 상태의 변경을 설명 하는 [CorDebugStateChange 열거형](cordebugstatechange-enumeration.md) 의 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="7218d-107">[in] A member of the [CorDebugStateChange enumeration](cordebugstatechange-enumeration.md) describing a change in the process's execution state.</span></span>

## <a name="remarks"></a><span data-ttu-id="7218d-108">설명</span><span class="sxs-lookup"><span data-stu-id="7218d-108">Remarks</span></span>

<span data-ttu-id="7218d-109">제공 된 메서드는 인터페이스의 일부 `ICorDebugProcess4` 이며 가상 메서드 테이블의 네 번째 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="7218d-109">The provided method is part of the `ICorDebugProcess4` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="7218d-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7218d-110">Requirements</span></span>

 <span data-ttu-id="7218d-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7218d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="7218d-112">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="7218d-112">**Header:** None</span></span>

 <span data-ttu-id="7218d-113">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="7218d-113">**Library:** None</span></span>

 <span data-ttu-id="7218d-114">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7218d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="7218d-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7218d-115">See also</span></span>

- [<span data-ttu-id="7218d-116">ICorDebugProcess4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7218d-116">ICorDebugProcess4 Interface</span></span>](icordebugprocess4-interface.md)
- [<span data-ttu-id="7218d-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7218d-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="7218d-118">디버깅</span><span class="sxs-lookup"><span data-stu-id="7218d-118">Debugging</span></span>](index.md)
