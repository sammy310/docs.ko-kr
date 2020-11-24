---
title: ICorDebugThread::CreateStepper 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateStepper
helpviewer_keywords:
- ICorDebugThread::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 4657443f-dd12-431b-a648-175c23f13c83
topic_type:
- apiref
ms.openlocfilehash: dcaa5adc41a9e451b123b088dd900f01d9161689
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688278"
---
# <a name="icordebugthreadcreatestepper-method"></a><span data-ttu-id="cbfe5-102">ICorDebugThread::CreateStepper 메서드</span><span class="sxs-lookup"><span data-stu-id="cbfe5-102">ICorDebugThread::CreateStepper Method</span></span>

<span data-ttu-id="cbfe5-103">이 ICorDebugThread의 활성 프레임을 단계별로 실행할 수 있도록 하는 ICorDebugStepper 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cbfe5-103">Creates an ICorDebugStepper object that allows stepping through the active frame of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbfe5-104">구문</span><span class="sxs-lookup"><span data-stu-id="cbfe5-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cbfe5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cbfe5-105">Parameters</span></span>  

 `ppStepper`  
 <span data-ttu-id="cbfe5-106">제한이 `ICorDebugStepper` 이 스레드의 활성 프레임을 단계별로 실행할 수 있도록 하는 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cbfe5-106">[out] A pointer to the address of an `ICorDebugStepper` object that allows stepping through the active frame of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cbfe5-107">설명</span><span class="sxs-lookup"><span data-stu-id="cbfe5-107">Remarks</span></span>  

 <span data-ttu-id="cbfe5-108">활성 프레임은 비관리 코드 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbfe5-108">The active frame may be unmanaged code.</span></span>  
  
 <span data-ttu-id="cbfe5-109">`ICorDebugStepper`실제 단계를 수행 하려면 인터페이스를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbfe5-109">The `ICorDebugStepper` interface must be used to perform the actual stepping.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbfe5-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cbfe5-110">Requirements</span></span>  

 <span data-ttu-id="cbfe5-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cbfe5-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbfe5-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cbfe5-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cbfe5-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cbfe5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cbfe5-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbfe5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
