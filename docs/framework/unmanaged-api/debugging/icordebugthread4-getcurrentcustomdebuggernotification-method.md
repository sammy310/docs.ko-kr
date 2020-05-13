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
ms.openlocfilehash: 76ad1c0ac421f05cf30f6d3d1f3e65848796a0c7
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378691"
---
# <a name="icordebugthread4getcurrentcustomdebuggernotification-method"></a><span data-ttu-id="3f4ee-102">ICorDebugThread4::GetCurrentCustomDebuggerNotification 메서드</span><span class="sxs-lookup"><span data-stu-id="3f4ee-102">ICorDebugThread4::GetCurrentCustomDebuggerNotification Method</span></span>

<span data-ttu-id="3f4ee-103">현재 스레드의 현재 [ICorDebugManagedCallback3:: CustomNotification](icordebugmanagedcallback3-customnotification-method.md) 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3f4ee-103">Gets the current [ICorDebugManagedCallback3::CustomNotification](icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>

## <a name="syntax"></a><span data-ttu-id="3f4ee-104">구문</span><span class="sxs-lookup"><span data-stu-id="3f4ee-104">Syntax</span></span>

```cpp
HRESULT GetCurrentCustomDebuggerNotification(
    [out] ICorDebugValue **ppNotificationObject
    );
```

## <a name="parameters"></a><span data-ttu-id="3f4ee-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3f4ee-105">Parameters</span></span>

`ppNotificationObject`\
<span data-ttu-id="3f4ee-106">제한이 현재 스레드의 현재 개체에 대 한 포인터 `ICorDebugManagedCallback3::CustomNotification` 입니다.</span><span class="sxs-lookup"><span data-stu-id="3f4ee-106">[out] A pointer to the current `ICorDebugManagedCallback3::CustomNotification` object on the current thread.</span></span>

## <a name="remarks"></a><span data-ttu-id="3f4ee-107">설명</span><span class="sxs-lookup"><span data-stu-id="3f4ee-107">Remarks</span></span>

<span data-ttu-id="3f4ee-108">`ppNotificationObject`콜백 내에서 메서드를 호출 하지 않거나 `ICorDebugManagedCallback3::CustomNotification` 현재 알림 개체가 없는 경우 값은 null입니다.</span><span class="sxs-lookup"><span data-stu-id="3f4ee-108">The value of `ppNotificationObject` is null if the method is not called from within a `ICorDebugManagedCallback3::CustomNotification` callback, or if no current notification object exists.</span></span>

## <a name="requirements"></a><span data-ttu-id="3f4ee-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3f4ee-109">Requirements</span></span>

<span data-ttu-id="3f4ee-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f4ee-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="3f4ee-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f4ee-111">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="3f4ee-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f4ee-112">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="3f4ee-113">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f4ee-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="3f4ee-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3f4ee-114">See also</span></span>

- [<span data-ttu-id="3f4ee-115">ICorDebugThread4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f4ee-115">ICorDebugThread4 Interface</span></span>](icordebugthread4-interface.md)
- [<span data-ttu-id="3f4ee-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f4ee-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="3f4ee-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="3f4ee-117">Debugging</span></span>](index.md)
