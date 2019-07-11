---
title: ICorDebugThread::GetCurrentException 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetCurrentException
helpviewer_keywords:
- ICorDebugThread::GetCurrentException method [.NET Framework debugging]
- GetCurrentException method [.NET Framework debugging]
ms.assetid: 331ed465-a195-4359-8584-b82c6098b29b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a6d53ebfebb8c883065ce119c2338a2225f0472
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762488"
---
# <a name="icordebugthreadgetcurrentexception-method"></a><span data-ttu-id="43d0a-102">ICorDebugThread::GetCurrentException 메서드</span><span class="sxs-lookup"><span data-stu-id="43d0a-102">ICorDebugThread::GetCurrentException Method</span></span>
<span data-ttu-id="43d0a-103">현재 관리 코드에 의해 throw 되는 예외를 나타내는 ICorDebugValue 개체에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="43d0a-103">Gets an interface pointer to an ICorDebugValue object that represents an exception that is currently being thrown by managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43d0a-104">구문</span><span class="sxs-lookup"><span data-stu-id="43d0a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentException (  
    [out] ICorDebugValue **ppExceptionObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43d0a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="43d0a-105">Parameters</span></span>  
 `ppExceptionObject`  
 <span data-ttu-id="43d0a-106">[out] 주소에 대 한 포인터는 `ICorDebugValue` 관리 코드에서 throw 되는 예외를 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="43d0a-106">[out] A pointer to the address of an `ICorDebugValue` object that represents the exception that is currently being thrown by managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43d0a-107">설명</span><span class="sxs-lookup"><span data-stu-id="43d0a-107">Remarks</span></span>  
 <span data-ttu-id="43d0a-108">예외 개체는 끝날 때까지 예외가 throw 된 시점부터 존재는 `catch` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="43d0a-108">The exception object will exist from the time the exception is thrown until the end of the `catch` block.</span></span> <span data-ttu-id="43d0a-109">ICorDebugEval 메서드에서 수행 하는 함수 평가 설정에 예외 개체를 지우고 완료 되 면 복원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43d0a-109">A function evaluation, which is performed by the ICorDebugEval methods, will clear out the exception object on setup and restore it on completion.</span></span>  
  
 <span data-ttu-id="43d0a-110">예외 (예를 들어, 예외가 throw 되 면 필터 또는 함수 실행) 중첩 될 수 있도록 단일 스레드에서 여러 처리 되지 않은 예외가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43d0a-110">Exceptions can be nested (for example, if an exception is thrown in a filter or in a function evaluation), so there may be multiple outstanding exceptions on a single thread.</span></span> <span data-ttu-id="43d0a-111">`GetCurrentException` 가장 최근 예외를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="43d0a-111">`GetCurrentException` returns the most current exception.</span></span>  
  
 <span data-ttu-id="43d0a-112">예외 개체 및 형식 예외의 수명 동안 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43d0a-112">The exception object and type may change throughout the life of the exception.</span></span> <span data-ttu-id="43d0a-113">예를 들어, x 형식의 예외가 throw 되 면 공용 언어 런타임 (CLR) 고 수 있습니다 메모리 부족의 메모리 부족 예외가 수준을 올립니다.</span><span class="sxs-lookup"><span data-stu-id="43d0a-113">For example, after an exception of type x is thrown, the common language runtime (CLR) may run out of memory and promote it to an out-of-memory exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43d0a-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="43d0a-114">Requirements</span></span>  
 <span data-ttu-id="43d0a-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="43d0a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43d0a-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43d0a-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43d0a-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43d0a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43d0a-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43d0a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
