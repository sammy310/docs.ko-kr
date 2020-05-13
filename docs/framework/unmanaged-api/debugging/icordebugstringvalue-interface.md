---
title: ICorDebugStringValue 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue
helpviewer_keywords:
- ICorDebugStringValue interface [.NET Framework debugging]
ms.assetid: bf84d0af-53e1-4c04-bc5b-7e5f81ba2cc2
topic_type:
- apiref
ms.openlocfilehash: 5537a48fd085ce98de855fa1ec0913e2637e58e0
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83376188"
---
# <a name="icordebugstringvalue-interface"></a><span data-ttu-id="b79fa-102">ICorDebugStringValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b79fa-102">ICorDebugStringValue Interface</span></span>
<span data-ttu-id="b79fa-103">문자열 값에 적용 되는 ICorDebugHeapValue의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b79fa-103">A subclass of ICorDebugHeapValue that applies to string values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b79fa-104">메서드</span><span class="sxs-lookup"><span data-stu-id="b79fa-104">Methods</span></span>  
  
|<span data-ttu-id="b79fa-105">메서드</span><span class="sxs-lookup"><span data-stu-id="b79fa-105">Method</span></span>|<span data-ttu-id="b79fa-106">설명</span><span class="sxs-lookup"><span data-stu-id="b79fa-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b79fa-107">GetLength 메서드</span><span class="sxs-lookup"><span data-stu-id="b79fa-107">GetLength Method</span></span>](icordebugstringvalue-getlength-method.md)|<span data-ttu-id="b79fa-108">이에서 참조 하는 문자열의 문자 수를 가져옵니다 `ICorDebugStringValue` .</span><span class="sxs-lookup"><span data-stu-id="b79fa-108">Gets the number of characters in the string referenced by this `ICorDebugStringValue`.</span></span>|  
|[<span data-ttu-id="b79fa-109">GetString 메서드</span><span class="sxs-lookup"><span data-stu-id="b79fa-109">GetString Method</span></span>](icordebugstringvalue-getstring-method.md)|<span data-ttu-id="b79fa-110">이에서 참조 하는 문자열을 가져옵니다 `ICorDebugStringValue` .</span><span class="sxs-lookup"><span data-stu-id="b79fa-110">Gets the string referenced by this `ICorDebugStringValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b79fa-111">설명</span><span class="sxs-lookup"><span data-stu-id="b79fa-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b79fa-112">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b79fa-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b79fa-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b79fa-113">Requirements</span></span>  
 <span data-ttu-id="b79fa-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b79fa-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b79fa-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b79fa-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b79fa-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b79fa-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b79fa-117">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b79fa-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b79fa-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b79fa-118">See also</span></span>

- [<span data-ttu-id="b79fa-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b79fa-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
