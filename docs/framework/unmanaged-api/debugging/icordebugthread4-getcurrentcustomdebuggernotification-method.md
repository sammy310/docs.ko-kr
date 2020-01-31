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
ms.openlocfilehash: a8a377074ca1005ad8089dfd8e2a6a464bb86f60
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791362"
---
# <a name="icordebugthread4getcurrentcustomdebuggernotification-method"></a><span data-ttu-id="d8730-102">ICorDebugThread4::GetCurrentCustomDebuggerNotification 메서드</span><span class="sxs-lookup"><span data-stu-id="d8730-102">ICorDebugThread4::GetCurrentCustomDebuggerNotification Method</span></span>

<span data-ttu-id="d8730-103">현재 스레드의 현재 [ICorDebugManagedCallback3:: CustomNotification](icordebugmanagedcallback3-customnotification-method.md) 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d8730-103">Gets the current [ICorDebugManagedCallback3::CustomNotification](icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>

## <a name="syntax"></a><span data-ttu-id="d8730-104">구문</span><span class="sxs-lookup"><span data-stu-id="d8730-104">Syntax</span></span>

```cpp
HRESULT GetCurrentCustomDebuggerNotification(
    [out] ICorDebugValue **ppNotificationObject
    );
```

## <a name="parameters"></a><span data-ttu-id="d8730-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d8730-105">Parameters</span></span>

`ppNotificationObject`\
<span data-ttu-id="d8730-106">제한이 현재 스레드의 현재 `ICorDebugManagedCallback3::CustomNotification` 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d8730-106">[out] A pointer to the current `ICorDebugManagedCallback3::CustomNotification` object on the current thread.</span></span>

## <a name="remarks"></a><span data-ttu-id="d8730-107">주의</span><span class="sxs-lookup"><span data-stu-id="d8730-107">Remarks</span></span>

<span data-ttu-id="d8730-108">`ICorDebugManagedCallback3::CustomNotification` 콜백 내에서 메서드가 호출 되지 않거나 현재 알림 개체가 없는 경우 `ppNotificationObject` 값은 null입니다.</span><span class="sxs-lookup"><span data-stu-id="d8730-108">The value of `ppNotificationObject` is null if the method is not called from within a `ICorDebugManagedCallback3::CustomNotification` callback, or if no current notification object exists.</span></span>

## <a name="requirements"></a><span data-ttu-id="d8730-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d8730-109">Requirements</span></span>

<span data-ttu-id="d8730-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8730-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="d8730-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d8730-111">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="d8730-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8730-112">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="d8730-113">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8730-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d8730-114">참조</span><span class="sxs-lookup"><span data-stu-id="d8730-114">See also</span></span>

- [<span data-ttu-id="d8730-115">ICorDebugThread4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d8730-115">ICorDebugThread4 Interface</span></span>](icordebugthread4-interface.md)
- [<span data-ttu-id="d8730-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d8730-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="d8730-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="d8730-117">Debugging</span></span>](index.md)
