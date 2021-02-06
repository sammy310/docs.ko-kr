---
description: '자세히 알아보기: ICorDebugThread:: GetCurrentException 메서드'
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
ms.openlocfilehash: cb241995520f26ca0e35f2b9e3b3187c2a2906a2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659168"
---
# <a name="icordebugthreadgetcurrentexception-method"></a><span data-ttu-id="7b6ec-103">ICorDebugThread::GetCurrentException 메서드</span><span class="sxs-lookup"><span data-stu-id="7b6ec-103">ICorDebugThread::GetCurrentException Method</span></span>

<span data-ttu-id="7b6ec-104">관리 코드에서 현재 throw 되는 예외를 나타내는 ICorDebugValue 개체에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7b6ec-104">Gets an interface pointer to an ICorDebugValue object that represents an exception that is currently being thrown by managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b6ec-105">구문</span><span class="sxs-lookup"><span data-stu-id="7b6ec-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentException (  
    [out] ICorDebugValue **ppExceptionObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b6ec-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7b6ec-106">Parameters</span></span>  

 `ppExceptionObject`  
 <span data-ttu-id="7b6ec-107">제한이 `ICorDebugValue` 관리 코드에서 현재 throw 되는 예외를 나타내는 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7b6ec-107">[out] A pointer to the address of an `ICorDebugValue` object that represents the exception that is currently being thrown by managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b6ec-108">설명</span><span class="sxs-lookup"><span data-stu-id="7b6ec-108">Remarks</span></span>  

 <span data-ttu-id="7b6ec-109">예외 개체는 블록이 끝날 때까지 예외가 throw 되는 시점에서 존재 합니다 `catch` .</span><span class="sxs-lookup"><span data-stu-id="7b6ec-109">The exception object will exist from the time the exception is thrown until the end of the `catch` block.</span></span> <span data-ttu-id="7b6ec-110">ICorDebugEval 메서드에서 수행 하는 함수 실행은 설치 시 예외 개체를 지우고 완료 시 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b6ec-110">A function evaluation, which is performed by the ICorDebugEval methods, will clear out the exception object on setup and restore it on completion.</span></span>  
  
 <span data-ttu-id="7b6ec-111">예외는 중첩 될 수 있습니다. 예를 들어 필터나 함수 실행에서 예외가 throw 되는 경우에는 단일 스레드에 처리 되지 않은 예외가 여러 개 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b6ec-111">Exceptions can be nested (for example, if an exception is thrown in a filter or in a function evaluation), so there may be multiple outstanding exceptions on a single thread.</span></span> <span data-ttu-id="7b6ec-112">`GetCurrentException` 최신 예외를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b6ec-112">`GetCurrentException` returns the most current exception.</span></span>  
  
 <span data-ttu-id="7b6ec-113">예외 개체와 형식은 예외 수명 내내 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b6ec-113">The exception object and type may change throughout the life of the exception.</span></span> <span data-ttu-id="7b6ec-114">예를 들어, x 형식의 예외가 throw 되 면 CLR (공용 언어 런타임)에서 메모리가 부족 하 여 메모리 부족 예외로 승격할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b6ec-114">For example, after an exception of type x is thrown, the common language runtime (CLR) may run out of memory and promote it to an out-of-memory exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b6ec-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7b6ec-115">Requirements</span></span>  

 <span data-ttu-id="7b6ec-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7b6ec-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b6ec-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b6ec-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b6ec-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b6ec-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b6ec-119">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b6ec-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
