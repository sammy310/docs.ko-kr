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
ms.openlocfilehash: 8082b2a3654f1605f18f3b68f54464dc83c8e60a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133483"
---
# <a name="icordebugthreadgetcurrentexception-method"></a><span data-ttu-id="b974e-102">ICorDebugThread::GetCurrentException 메서드</span><span class="sxs-lookup"><span data-stu-id="b974e-102">ICorDebugThread::GetCurrentException Method</span></span>
<span data-ttu-id="b974e-103">관리 코드에서 현재 throw 되는 예외를 나타내는 ICorDebugValue 개체에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b974e-103">Gets an interface pointer to an ICorDebugValue object that represents an exception that is currently being thrown by managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b974e-104">구문</span><span class="sxs-lookup"><span data-stu-id="b974e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentException (  
    [out] ICorDebugValue **ppExceptionObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b974e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b974e-105">Parameters</span></span>  
 `ppExceptionObject`  
 <span data-ttu-id="b974e-106">제한이 관리 코드에서 현재 throw 되는 예외를 나타내는 `ICorDebugValue` 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b974e-106">[out] A pointer to the address of an `ICorDebugValue` object that represents the exception that is currently being thrown by managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b974e-107">주의</span><span class="sxs-lookup"><span data-stu-id="b974e-107">Remarks</span></span>  
 <span data-ttu-id="b974e-108">예외 개체는 예외가 throw 된 시간부터 `catch` 블록의 끝까지 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="b974e-108">The exception object will exist from the time the exception is thrown until the end of the `catch` block.</span></span> <span data-ttu-id="b974e-109">ICorDebugEval 메서드에서 수행 하는 함수 실행은 설치 시 예외 개체를 지우고 완료 시 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b974e-109">A function evaluation, which is performed by the ICorDebugEval methods, will clear out the exception object on setup and restore it on completion.</span></span>  
  
 <span data-ttu-id="b974e-110">예외는 중첩 될 수 있습니다. 예를 들어 필터나 함수 실행에서 예외가 throw 되는 경우에는 단일 스레드에 처리 되지 않은 예외가 여러 개 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b974e-110">Exceptions can be nested (for example, if an exception is thrown in a filter or in a function evaluation), so there may be multiple outstanding exceptions on a single thread.</span></span> <span data-ttu-id="b974e-111">`GetCurrentException`는 최신 예외를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b974e-111">`GetCurrentException` returns the most current exception.</span></span>  
  
 <span data-ttu-id="b974e-112">예외 개체와 형식은 예외 수명 내내 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b974e-112">The exception object and type may change throughout the life of the exception.</span></span> <span data-ttu-id="b974e-113">예를 들어, x 형식의 예외가 throw 되 면 CLR (공용 언어 런타임)에서 메모리가 부족 하 여 메모리 부족 예외로 승격할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b974e-113">For example, after an exception of type x is thrown, the common language runtime (CLR) may run out of memory and promote it to an out-of-memory exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b974e-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b974e-114">Requirements</span></span>  
 <span data-ttu-id="b974e-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b974e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b974e-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b974e-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b974e-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b974e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b974e-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b974e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
