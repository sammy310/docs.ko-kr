---
description: '자세히 알아보기: ICorDebugMutableDataTarget:: ContinueStatusChanged 메서드'
title: ICorDebugMutableDataTarget::ContinueStatusChanged 메서드
ms.date: 03/30/2017
ms.assetid: 5a66d3f4-dd16-4d62-9dcc-0eab7041d894
ms.openlocfilehash: 6655d6f1a115b4879c73e356faa8e8785a110078
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722505"
---
# <a name="icordebugmutabledatatargetcontinuestatuschanged-method"></a><span data-ttu-id="6b917-103">ICorDebugMutableDataTarget::ContinueStatusChanged 메서드</span><span class="sxs-lookup"><span data-stu-id="6b917-103">ICorDebugMutableDataTarget::ContinueStatusChanged Method</span></span>

<span data-ttu-id="6b917-104">지정된 스레드에서 해결되지 않은 디버그 이벤트의 연속 상태를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="6b917-104">Changes the continuation status for the outstanding debug event on the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b917-105">구문</span><span class="sxs-lookup"><span data-stu-id="6b917-105">Syntax</span></span>  
  
```cpp  
HRESULT ContinueStatusChanged(  
   [in] DWORD dwThreadId,  
   [in] CORDB_CONTINUE_STATUS continueStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b917-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6b917-106">Parameters</span></span>  

 `dwThreadId`  
 <span data-ttu-id="6b917-107">운영 체제에서 정의된 스레드 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="6b917-107">The operating system-defined thread identifier.</span></span>  
  
 `continueStatus`  
 <span data-ttu-id="6b917-108">요청된 새 연속 상태를 나타내는 [COREDB_CONTINUE_STATUS](../common-data-types-unmanaged-api-reference.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6b917-108">A [COREDB_CONTINUE_STATUS](../common-data-types-unmanaged-api-reference.md) value that represents the new requested continuation status.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b917-109">설명</span><span class="sxs-lookup"><span data-stu-id="6b917-109">Remarks</span></span>  

 <span data-ttu-id="6b917-110">디버거는 정상적일 경우 처리되는 방식과 다른 방식으로 현재 디버그 이벤트가 처리되도록 요구하는 ICorDebug 메서드를 호출할 때 `ContinueStatusChanged` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="6b917-110">The debugger calls the `ContinueStatusChanged` method when it calls an ICorDebug method that requires the current debug event to be handled in a way that is potentially different from the way in which it normally would be handled.</span></span> <span data-ttu-id="6b917-111">예를 들어 해결되지 않은 예외가 있고 디버거가 예외를 취소하는 작업(예: [ICorDebugILFrame::SetIP`FuncEval` 또는 ](icordebugilframe-setip-method.md))을 요청하는 경우 이 API는 예외가 취소되도록 요청하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b917-111">For example, if there is an outstanding exception, and the debugger requests an operation that would cancel the exception (such as [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) or `FuncEval`), this API is used to request that the exception be cancelled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b917-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6b917-112">Requirements</span></span>  

 <span data-ttu-id="6b917-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b917-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b917-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6b917-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b917-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b917-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b917-116">**.NET Framework 버전:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b917-116">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b917-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6b917-117">See also</span></span>

- [<span data-ttu-id="6b917-118">ICorDebugMutableDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6b917-118">ICorDebugMutableDataTarget Interface</span></span>](icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="6b917-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6b917-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
