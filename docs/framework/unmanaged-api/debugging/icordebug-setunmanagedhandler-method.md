---
description: '자세히 알아보기: ICorDebug:: SetUnmanagedHandler 메서드'
title: ICorDebug::SetUnmanagedHandler 메서드
ms.date: 03/30/2017
api_name:
- ICorDebug.SetUnmanagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetUnmanagerHandler
helpviewer_keywords:
- SetUnmanagedHandler method [.NET Framework debugging]
- ICorDebug::SetUnmanagedHandler method [.NET Framework debugging]
ms.assetid: 6b546be4-f86d-4536-8cfc-1d08e5066eb6
topic_type:
- apiref
ms.openlocfilehash: ffd4eb7ff0056a2468ec53eb3534434c2c8d556a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754318"
---
# <a name="icordebugsetunmanagedhandler-method"></a><span data-ttu-id="cfbe2-103">ICorDebug::SetUnmanagedHandler 메서드</span><span class="sxs-lookup"><span data-stu-id="cfbe2-103">ICorDebug::SetUnmanagedHandler Method</span></span>

<span data-ttu-id="cfbe2-104">관리 되지 않는 이벤트에 대 한 이벤트 처리기 개체를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfbe2-104">Specifies the event handler object for unmanaged events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfbe2-105">구문</span><span class="sxs-lookup"><span data-stu-id="cfbe2-105">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmanagedHandler (  
    [in] ICorDebugUnmanagedCallback  *pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cfbe2-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cfbe2-106">Parameters</span></span>  

 `pCallback`  
 <span data-ttu-id="cfbe2-107">진행 관리 되지 않는 이벤트에 대 한 이벤트 처리기를 나타내는 [ICorDebugUnmanagedCallback](icordebugunmanagedcallback-interface.md) 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cfbe2-107">[in] A pointer to an [ICorDebugUnmanagedCallback](icordebugunmanagedcallback-interface.md) object that represents the event handler for unmanaged events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cfbe2-108">설명</span><span class="sxs-lookup"><span data-stu-id="cfbe2-108">Remarks</span></span>  

 <span data-ttu-id="cfbe2-109">관리 되지 않는 이벤트에 대 한 이벤트 처리기 개체는 [ICorDebug:: Initialize](icordebug-initialize-method.md) 를 호출한 후 [ICorDebug:: CreateProcess](icordebug-createprocess-method.md) 또는 [ICorDebug::D e버그 activeprocess](icordebug-debugactiveprocess-method.md)를 호출 하기 전에 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfbe2-109">The event handler object for unmanaged events must be set after a call to [ICorDebug::Initialize](icordebug-initialize-method.md) and before any calls to [ICorDebug::CreateProcess](icordebug-createprocess-method.md) or [ICorDebug::DebugActiveProcess](icordebug-debugactiveprocess-method.md).</span></span> <span data-ttu-id="cfbe2-110">그러나 레거시를 위해 첫 번째 네이티브 디버그 이벤트가 발생할 때까지 관리 되지 않는 이벤트에 대 한 이벤트 처리기 개체를 설정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cfbe2-110">However, for legacy purposes, you are not required to set the event handler object for unmanaged events until the first native debug event is raised.</span></span> <span data-ttu-id="cfbe2-111">특히 `ICorDebug::CreateProcess` 가 CREATE_SUSPENDED 플래그를 설정한 경우 주 스레드를 다시 시작할 때까지 네이티브 디버그 이벤트를 발송할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cfbe2-111">Specifically, if `ICorDebug::CreateProcess` has set the CREATE_SUSPENDED flag, native debug events cannot be dispatched until the main thread is resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfbe2-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cfbe2-112">Requirements</span></span>  

 <span data-ttu-id="cfbe2-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cfbe2-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfbe2-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cfbe2-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cfbe2-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cfbe2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cfbe2-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfbe2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfbe2-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cfbe2-117">See also</span></span>

- [<span data-ttu-id="cfbe2-118">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cfbe2-118">ICorDebug Interface</span></span>](icordebug-interface.md)
