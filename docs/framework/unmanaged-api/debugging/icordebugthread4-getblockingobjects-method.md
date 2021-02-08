---
description: '자세히 알아보기: ICorDebugThread4:: GetBlockingObjects 메서드'
title: ICorDebugThread4::GetBlockingObjects 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.GetBlockingObjects Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::GetBlockingObjects
helpviewer_keywords:
- GetBlockingObjects method [.NET Framework debugging]
- ICorDebugThread4::GetBlockingObjects method [.NET Framework debugging]
ms.assetid: a7e6c54e-7be9-4e52-bbb4-95f52458e8e4
topic_type:
- apiref
ms.openlocfilehash: 6a60ebe6f5f6dac93dcb11dad7658aba9c934329
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800957"
---
# <a name="icordebugthread4getblockingobjects-method"></a><span data-ttu-id="40fe7-103">ICorDebugThread4::GetBlockingObjects 메서드</span><span class="sxs-lookup"><span data-stu-id="40fe7-103">ICorDebugThread4::GetBlockingObjects Method</span></span>

<span data-ttu-id="40fe7-104">스레드 차단 정보를 제공 하는 [CorDebugBlockingObject](cordebugblockingobject-structure.md) 구조의 순서가 지정 된 열거형을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="40fe7-104">Provides an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40fe7-105">구문</span><span class="sxs-lookup"><span data-stu-id="40fe7-105">Syntax</span></span>  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
```  
  
## <a name="parameters"></a><span data-ttu-id="40fe7-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="40fe7-106">Parameters</span></span>  

 `ppBlockingObjectEnum`  
 <span data-ttu-id="40fe7-107">제한이 [CorDebugBlockingObject](cordebugblockingobject-structure.md) 구조체의 정렬 된 열거에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="40fe7-107">[out] A pointer to an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40fe7-108">설명</span><span class="sxs-lookup"><span data-stu-id="40fe7-108">Remarks</span></span>  

 <span data-ttu-id="40fe7-109">반환 된 열거형의 첫 번째 요소는 스레드를 차단 하는 첫 번째 구조체에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="40fe7-109">The first element in the returned enumeration corresponds to the first structure that is blocking the thread.</span></span> <span data-ttu-id="40fe7-110">두 번째 요소는 첫 번째에서 차단 될 때 APC (비동기 프로시저 호출)를 실행 하는 동안 발생 한 차단 항목에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="40fe7-110">The second element corresponds to a blocking item that is encountered while running an asynchronous procedure call (APC) when blocked on the first, and so on.</span></span>  
  
 <span data-ttu-id="40fe7-111">열거형은 현재 동기화 된 상태의 기간에 대해서만 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="40fe7-111">The enumeration is valid only for the duration of the current synchronized state.</span></span>  
  
 <span data-ttu-id="40fe7-112">디버기가 synchronized 상태에 있는 동안에는이 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40fe7-112">This method must be called while the debuggee is in a synchronized state.</span></span>  
  
 <span data-ttu-id="40fe7-113">`ppBlockingObjectEnum`가 유효한 포인터가 아닌 경우 결과가 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40fe7-113">If `ppBlockingObjectEnum` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="40fe7-114">스레드가 차단 되 고 오류를 확인할 수 없는 경우 메서드는 실패를 나타내는 HRESULT를 반환 합니다. 그렇지 않으면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="40fe7-114">If a thread is blocked and the error cannot be determined, the method returns an HRESULT that indicates failure; otherwise, it returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40fe7-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="40fe7-115">Requirements</span></span>  

 <span data-ttu-id="40fe7-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="40fe7-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40fe7-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="40fe7-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="40fe7-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40fe7-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40fe7-119">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40fe7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40fe7-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="40fe7-120">See also</span></span>

- [<span data-ttu-id="40fe7-121">ICorDebugThread4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="40fe7-121">ICorDebugThread4 Interface</span></span>](icordebugthread4-interface.md)
- [<span data-ttu-id="40fe7-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="40fe7-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="40fe7-123">디버깅</span><span class="sxs-lookup"><span data-stu-id="40fe7-123">Debugging</span></span>](index.md)
