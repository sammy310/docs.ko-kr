---
title: ICorDebugThread4::GetCurrentCustomDebuggerNotification 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.GetCurrentCustomDebuggerNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::GetCurrentCustomDebuggerNotification
helpviewer_keywords:
- GetCurrentCustomDebuggerNotification method [.NET Framework debugging]
- ICorDebugThread4::GetCurrentCustomDebuggerNotification method [.NET Framework debugging]
ms.assetid: 57e0f2d2-5f0e-4e2d-99ec-3f26632eb693
topic_type:
- apiref
ms.openlocfilehash: ba4375511fe7f5aaee032c4e132de54808041111
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122442"
---
# <a name="icordebugthread4getcurrentcustomdebuggernotification-method"></a><span data-ttu-id="40577-102">ICorDebugThread4::GetCurrentCustomDebuggerNotification 메서드</span><span class="sxs-lookup"><span data-stu-id="40577-102">ICorDebugThread4::GetCurrentCustomDebuggerNotification Method</span></span>

<span data-ttu-id="40577-103">현재 스레드의 현재 [ICorDebugManagedCallback3:: CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="40577-103">Gets the current [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>

## <a name="syntax"></a><span data-ttu-id="40577-104">구문</span><span class="sxs-lookup"><span data-stu-id="40577-104">Syntax</span></span>

```cpp
HRESULT GetCurrentCustomDebuggerNotification(
    [out] ICorDebugValue **ppNotificationObject
    );
```

## <a name="parameters"></a><span data-ttu-id="40577-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="40577-105">Parameters</span></span>

`ppNotificationObject`\
<span data-ttu-id="40577-106">제한이 현재 스레드의 현재 `ICorDebugManagedCallback3::CustomNotification` 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="40577-106">[out] A pointer to the current `ICorDebugManagedCallback3::CustomNotification` object on the current thread.</span></span>

## <a name="remarks"></a><span data-ttu-id="40577-107">주의</span><span class="sxs-lookup"><span data-stu-id="40577-107">Remarks</span></span>

<span data-ttu-id="40577-108">`ICorDebugManagedCallback3::CustomNotification` 콜백 내에서 메서드가 호출 되지 않거나 현재 알림 개체가 없는 경우 `ppNotificationObject` 값은 null입니다.</span><span class="sxs-lookup"><span data-stu-id="40577-108">The value of `ppNotificationObject` is null if the method is not called from within a `ICorDebugManagedCallback3::CustomNotification` callback, or if no current notification object exists.</span></span>

## <a name="requirements"></a><span data-ttu-id="40577-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="40577-109">Requirements</span></span>

<span data-ttu-id="40577-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="40577-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="40577-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="40577-111">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="40577-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40577-112">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="40577-113">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40577-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="40577-114">참조</span><span class="sxs-lookup"><span data-stu-id="40577-114">See also</span></span>

- [<span data-ttu-id="40577-115">ICorDebugThread4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="40577-115">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)
- [<span data-ttu-id="40577-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="40577-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="40577-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="40577-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
