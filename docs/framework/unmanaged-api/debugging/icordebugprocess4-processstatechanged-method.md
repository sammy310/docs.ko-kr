---
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
ms.openlocfilehash: 910c411d2c63ce2c6cf262e28e08546657dc2a4c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213571"
---
# <a name="icordebugprocess4processstatechanged-method"></a><span data-ttu-id="98c3a-102">ICorDebugProcess4::P rocessStateChanged 메서드</span><span class="sxs-lookup"><span data-stu-id="98c3a-102">ICorDebugProcess4::ProcessStateChanged Method</span></span>

<span data-ttu-id="98c3a-103">ICorDebug 파이프라인에 out of process 디버거가 디버기의의 실행을 계속 진행 중임을 알립니다.</span><span class="sxs-lookup"><span data-stu-id="98c3a-103">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span>

## <a name="syntax"></a><span data-ttu-id="98c3a-104">구문</span><span class="sxs-lookup"><span data-stu-id="98c3a-104">Syntax</span></span>

```cpp
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a><span data-ttu-id="98c3a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="98c3a-105">Parameters</span></span>

 `eChange`\
<span data-ttu-id="98c3a-106">진행 프로세스 실행 상태의 변경을 설명 하는 [CorDebugStateChange 열거형](cordebugstatechange-enumeration.md) 의 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="98c3a-106">[in] A member of the [CorDebugStateChange enumeration](cordebugstatechange-enumeration.md) describing a change in the process's execution state.</span></span>

## <a name="remarks"></a><span data-ttu-id="98c3a-107">설명</span><span class="sxs-lookup"><span data-stu-id="98c3a-107">Remarks</span></span>

<span data-ttu-id="98c3a-108">제공 된 메서드는 인터페이스의 일부 `ICorDebugProcess4` 이며 가상 메서드 테이블의 네 번째 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c3a-108">The provided method is part of the `ICorDebugProcess4` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="98c3a-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="98c3a-109">Requirements</span></span>

 <span data-ttu-id="98c3a-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="98c3a-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="98c3a-111">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="98c3a-111">**Header:** None</span></span>

 <span data-ttu-id="98c3a-112">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="98c3a-112">**Library:** None</span></span>

 <span data-ttu-id="98c3a-113">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98c3a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="98c3a-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="98c3a-114">See also</span></span>

- [<span data-ttu-id="98c3a-115">ICorDebugProcess4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="98c3a-115">ICorDebugProcess4 Interface</span></span>](icordebugprocess4-interface.md)
- [<span data-ttu-id="98c3a-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="98c3a-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="98c3a-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="98c3a-117">Debugging</span></span>](index.md)
