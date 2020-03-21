---
title: ICorDebugProcess4::P로케이스스테이트변경방법
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
ms.openlocfilehash: a6f36f5b86b4fa58ce2a4ef4aa23d527f797a5a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178638"
---
# <a name="icordebugprocess4processstatechanged-method"></a><span data-ttu-id="26e2f-102">ICorDebugProcess4::P로케이스스테이트변경방법</span><span class="sxs-lookup"><span data-stu-id="26e2f-102">ICorDebugProcess4::ProcessStateChanged Method</span></span>

<span data-ttu-id="26e2f-103">ICorDebug 파이프라인에 프로세스 디버거에서 디버거가 debugee의 실행을 계속하고 있음을 알리고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26e2f-103">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span>

## <a name="syntax"></a><span data-ttu-id="26e2f-104">구문</span><span class="sxs-lookup"><span data-stu-id="26e2f-104">Syntax</span></span>

```cpp
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a><span data-ttu-id="26e2f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="26e2f-105">Parameters</span></span>

 `eChange`\
<span data-ttu-id="26e2f-106">【인】 프로세스의 실행 상태의 변경을 설명하는 [CorDebugStateChange 열거형의](cordebugstatechange-enumeration.md) 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="26e2f-106">[in] A member of the [CorDebugStateChange enumeration](cordebugstatechange-enumeration.md) describing a change in the process's execution state.</span></span>

## <a name="remarks"></a><span data-ttu-id="26e2f-107">설명</span><span class="sxs-lookup"><span data-stu-id="26e2f-107">Remarks</span></span>

<span data-ttu-id="26e2f-108">제공된 메서드는 `ICorDebugProcess4` 인터페이스의 일부이며 가상 메서드 테이블의 네 번째 슬롯에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="26e2f-108">The provided method is part of the `ICorDebugProcess4` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="26e2f-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="26e2f-109">Requirements</span></span>

 <span data-ttu-id="26e2f-110">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="26e2f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="26e2f-111">**헤더:** 없음</span><span class="sxs-lookup"><span data-stu-id="26e2f-111">**Header:** None</span></span>

 <span data-ttu-id="26e2f-112">**라이브러리:** 없음</span><span class="sxs-lookup"><span data-stu-id="26e2f-112">**Library:** None</span></span>

 <span data-ttu-id="26e2f-113">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26e2f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="26e2f-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="26e2f-114">See also</span></span>

- [<span data-ttu-id="26e2f-115">ICorDebugProcess4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="26e2f-115">ICorDebugProcess4 Interface</span></span>](icordebugprocess4-interface.md)
- [<span data-ttu-id="26e2f-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="26e2f-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="26e2f-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="26e2f-117">Debugging</span></span>](index.md)
