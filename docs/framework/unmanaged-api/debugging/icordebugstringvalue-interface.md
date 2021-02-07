---
description: '자세히 알아보기: ICorDebugStringValue 인터페이스'
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
ms.openlocfilehash: b4e762d8c0a62c1b76b59364e9d29c4b8d2386fa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717331"
---
# <a name="icordebugstringvalue-interface"></a><span data-ttu-id="be6b4-103">ICorDebugStringValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="be6b4-103">ICorDebugStringValue Interface</span></span>

<span data-ttu-id="be6b4-104">문자열 값에 적용 되는 ICorDebugHeapValue의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="be6b4-104">A subclass of ICorDebugHeapValue that applies to string values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="be6b4-105">메서드</span><span class="sxs-lookup"><span data-stu-id="be6b4-105">Methods</span></span>  
  
|<span data-ttu-id="be6b4-106">메서드</span><span class="sxs-lookup"><span data-stu-id="be6b4-106">Method</span></span>|<span data-ttu-id="be6b4-107">설명</span><span class="sxs-lookup"><span data-stu-id="be6b4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="be6b4-108">GetLength 메서드</span><span class="sxs-lookup"><span data-stu-id="be6b4-108">GetLength Method</span></span>](icordebugstringvalue-getlength-method.md)|<span data-ttu-id="be6b4-109">이에서 참조 하는 문자열의 문자 수를 가져옵니다 `ICorDebugStringValue` .</span><span class="sxs-lookup"><span data-stu-id="be6b4-109">Gets the number of characters in the string referenced by this `ICorDebugStringValue`.</span></span>|  
|[<span data-ttu-id="be6b4-110">GetString 메서드</span><span class="sxs-lookup"><span data-stu-id="be6b4-110">GetString Method</span></span>](icordebugstringvalue-getstring-method.md)|<span data-ttu-id="be6b4-111">이에서 참조 하는 문자열을 가져옵니다 `ICorDebugStringValue` .</span><span class="sxs-lookup"><span data-stu-id="be6b4-111">Gets the string referenced by this `ICorDebugStringValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be6b4-112">설명</span><span class="sxs-lookup"><span data-stu-id="be6b4-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="be6b4-113">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be6b4-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be6b4-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="be6b4-114">Requirements</span></span>  

 <span data-ttu-id="be6b4-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="be6b4-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be6b4-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="be6b4-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="be6b4-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be6b4-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be6b4-118">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be6b4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be6b4-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="be6b4-119">See also</span></span>

- [<span data-ttu-id="be6b4-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="be6b4-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
