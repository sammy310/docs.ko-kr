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
ms.openlocfilehash: d1b058aef66ed32c2cadcc3cfd72320dd8eb7729
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133589"
---
# <a name="icordebugthreadcreatestepper-method"></a><span data-ttu-id="1b30d-102">ICorDebugThread::CreateStepper 메서드</span><span class="sxs-lookup"><span data-stu-id="1b30d-102">ICorDebugThread::CreateStepper Method</span></span>
<span data-ttu-id="1b30d-103">이 ICorDebugThread의 활성 프레임을 단계별로 실행할 수 있도록 하는 ICorDebugStepper 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1b30d-103">Creates an ICorDebugStepper object that allows stepping through the active frame of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b30d-104">구문</span><span class="sxs-lookup"><span data-stu-id="1b30d-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b30d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1b30d-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="1b30d-106">제한이 이 스레드의 활성 프레임을 단계별로 실행할 수 있도록 하는 `ICorDebugStepper` 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1b30d-106">[out] A pointer to the address of an `ICorDebugStepper` object that allows stepping through the active frame of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b30d-107">주의</span><span class="sxs-lookup"><span data-stu-id="1b30d-107">Remarks</span></span>  
 <span data-ttu-id="1b30d-108">활성 프레임은 비관리 코드 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b30d-108">The active frame may be unmanaged code.</span></span>  
  
 <span data-ttu-id="1b30d-109">실제 단계별 실행을 수행 하려면 `ICorDebugStepper` 인터페이스를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b30d-109">The `ICorDebugStepper` interface must be used to perform the actual stepping.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b30d-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1b30d-110">Requirements</span></span>  
 <span data-ttu-id="1b30d-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1b30d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b30d-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1b30d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1b30d-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b30d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b30d-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b30d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
