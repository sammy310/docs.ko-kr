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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95a00e8646589e7897636c1698b7c2647cd233fd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771807"
---
# <a name="icordebugthreadcreatestepper-method"></a><span data-ttu-id="68694-102">ICorDebugThread::CreateStepper 메서드</span><span class="sxs-lookup"><span data-stu-id="68694-102">ICorDebugThread::CreateStepper Method</span></span>
<span data-ttu-id="68694-103">이 ICorDebugThread의 활성 프레임을 단계별로 있도록 ICorDebugStepper 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="68694-103">Creates an ICorDebugStepper object that allows stepping through the active frame of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68694-104">구문</span><span class="sxs-lookup"><span data-stu-id="68694-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68694-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="68694-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="68694-106">[out] 주소에 대 한 포인터는 `ICorDebugStepper` 이 스레드에 대 한 활성 프레임을 단계별로 허용 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="68694-106">[out] A pointer to the address of an `ICorDebugStepper` object that allows stepping through the active frame of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68694-107">설명</span><span class="sxs-lookup"><span data-stu-id="68694-107">Remarks</span></span>  
 <span data-ttu-id="68694-108">활성 프레임에는 관리 되지 않는 코드 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68694-108">The active frame may be unmanaged code.</span></span>  
  
 <span data-ttu-id="68694-109">`ICorDebugStepper` 인터페이스의 실제 단계별 실행 하는 데 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68694-109">The `ICorDebugStepper` interface must be used to perform the actual stepping.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68694-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="68694-110">Requirements</span></span>  
 <span data-ttu-id="68694-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="68694-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68694-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="68694-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="68694-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="68694-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="68694-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68694-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
