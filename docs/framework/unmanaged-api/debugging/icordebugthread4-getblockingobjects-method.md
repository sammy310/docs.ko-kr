---
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
ms.openlocfilehash: e4d5582b7a3df16db58ea0ed001dcbffcdcaab79
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122456"
---
# <a name="icordebugthread4getblockingobjects-method"></a><span data-ttu-id="c2fdc-102">ICorDebugThread4::GetBlockingObjects 메서드</span><span class="sxs-lookup"><span data-stu-id="c2fdc-102">ICorDebugThread4::GetBlockingObjects Method</span></span>
<span data-ttu-id="c2fdc-103">스레드 차단 정보를 제공 하는 [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) 구조의 순서가 지정 된 열거형을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2fdc-103">Provides an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2fdc-104">구문</span><span class="sxs-lookup"><span data-stu-id="c2fdc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2fdc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c2fdc-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="c2fdc-106">제한이 [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) 구조체의 정렬 된 열거에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c2fdc-106">[out] A pointer to an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2fdc-107">주의</span><span class="sxs-lookup"><span data-stu-id="c2fdc-107">Remarks</span></span>  
 <span data-ttu-id="c2fdc-108">반환 된 열거형의 첫 번째 요소는 스레드를 차단 하는 첫 번째 구조체에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2fdc-108">The first element in the returned enumeration corresponds to the first structure that is blocking the thread.</span></span> <span data-ttu-id="c2fdc-109">두 번째 요소는 첫 번째에서 차단 될 때 APC (비동기 프로시저 호출)를 실행 하는 동안 발생 한 차단 항목에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2fdc-109">The second element corresponds to a blocking item that is encountered while running an asynchronous procedure call (APC) when blocked on the first, and so on.</span></span>  
  
 <span data-ttu-id="c2fdc-110">열거형은 현재 동기화 된 상태의 기간에 대해서만 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2fdc-110">The enumeration is valid only for the duration of the current synchronized state.</span></span>  
  
 <span data-ttu-id="c2fdc-111">디버기가 synchronized 상태에 있는 동안에는이 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2fdc-111">This method must be called while the debuggee is in a synchronized state.</span></span>  
  
 <span data-ttu-id="c2fdc-112">`ppBlockingObjectEnum` 잘못 된 포인터인 경우 결과가 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2fdc-112">If `ppBlockingObjectEnum` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="c2fdc-113">스레드가 차단 되 고 오류를 확인할 수 없는 경우 메서드는 실패를 나타내는 HRESULT를 반환 합니다. 그렇지 않으면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2fdc-113">If a thread is blocked and the error cannot be determined, the method returns an HRESULT that indicates failure; otherwise, it returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2fdc-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c2fdc-114">Requirements</span></span>  
 <span data-ttu-id="c2fdc-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2fdc-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2fdc-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c2fdc-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c2fdc-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2fdc-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2fdc-118">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2fdc-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2fdc-119">참조</span><span class="sxs-lookup"><span data-stu-id="c2fdc-119">See also</span></span>

- [<span data-ttu-id="c2fdc-120">ICorDebugThread4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2fdc-120">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)
- [<span data-ttu-id="c2fdc-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2fdc-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="c2fdc-122">디버깅</span><span class="sxs-lookup"><span data-stu-id="c2fdc-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
