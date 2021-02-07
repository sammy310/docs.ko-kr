---
description: '자세히 알아보기: ICorDebugHandleValue 인터페이스'
title: ICorDebugHandleValue 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue
helpviewer_keywords:
- ICorDebugHandleValue interface [.NET Framework debugging]
ms.assetid: 66fcd2b8-ac66-414b-83a8-75a925e17772
topic_type:
- apiref
ms.openlocfilehash: 3bdb1f5668be283d8722c15f4779adfe4d7b3a2d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692045"
---
# <a name="icordebughandlevalue-interface"></a><span data-ttu-id="80509-103">ICorDebugHandleValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="80509-103">ICorDebugHandleValue Interface</span></span>

<span data-ttu-id="80509-104">디버거에서 가비지 수집에 대 한 핸들을 만든 참조 값을 나타내는 ICorDebugReferenceValue의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="80509-104">A subclass of ICorDebugReferenceValue that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="80509-105">메서드</span><span class="sxs-lookup"><span data-stu-id="80509-105">Methods</span></span>  
  
|<span data-ttu-id="80509-106">메서드</span><span class="sxs-lookup"><span data-stu-id="80509-106">Method</span></span>|<span data-ttu-id="80509-107">설명</span><span class="sxs-lookup"><span data-stu-id="80509-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="80509-108">Dispose 메서드</span><span class="sxs-lookup"><span data-stu-id="80509-108">Dispose Method</span></span>](icordebughandlevalue-dispose-method.md)|<span data-ttu-id="80509-109">`ICorDebugHandleValue`인터페이스 포인터를 명시적으로 해제 하지 않고이 개체에서 참조 하는 핸들을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="80509-109">Releases the handle referenced by this `ICorDebugHandleValue` object without explicitly releasing the interface pointer.</span></span>|  
|[<span data-ttu-id="80509-110">GetHandleType 메서드</span><span class="sxs-lookup"><span data-stu-id="80509-110">GetHandleType Method</span></span>](icordebughandlevalue-gethandletype-method.md)|<span data-ttu-id="80509-111">이에서 참조 하는 핸들의 종류를 설명 하는 CorDebugHandleType 값을 가져옵니다 `ICorDebugHandleValue` .</span><span class="sxs-lookup"><span data-stu-id="80509-111">Gets a CorDebugHandleType value that describes the kind of handle referenced by this `ICorDebugHandleValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80509-112">설명</span><span class="sxs-lookup"><span data-stu-id="80509-112">Remarks</span></span>  

 <span data-ttu-id="80509-113">`ICorDebugReferenceValue`디버깅 된 코드의 실행이 중단 되 면 개체가 무효화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80509-113">An `ICorDebugReferenceValue` object is invalidated by a break in the execution of debugged code.</span></span> <span data-ttu-id="80509-114">는 `ICorDebugHandleValue` 명시적으로 해제 될 때까지 중단 및 연속을 통해 참조를 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="80509-114">An `ICorDebugHandleValue` maintains its reference through breaks and continuations, until it is explicitly released.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="80509-115">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80509-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80509-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="80509-116">Requirements</span></span>  

 <span data-ttu-id="80509-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80509-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80509-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="80509-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="80509-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80509-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="80509-120">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80509-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80509-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="80509-121">See also</span></span>

- [<span data-ttu-id="80509-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="80509-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
