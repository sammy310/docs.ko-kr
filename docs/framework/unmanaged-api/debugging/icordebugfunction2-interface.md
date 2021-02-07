---
description: '자세히 알아보기: ICorDebugFunction2 인터페이스'
title: ICorDebugFunction2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2
helpviewer_keywords:
- ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 2b936bef-9b75-48bf-859f-42e419c65f1c
topic_type:
- apiref
ms.openlocfilehash: e5297d46acb9b174537363fc185fa2d540d55a75
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692201"
---
# <a name="icordebugfunction2-interface"></a><span data-ttu-id="0e034-103">ICorDebugFunction2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0e034-103">ICorDebugFunction2 Interface</span></span>

<span data-ttu-id="0e034-104">ICorDebugFunction 인터페이스를 논리적으로 확장 하 여 사용자가 지정 하지 않은 코드를 건너뛰는 내 코드만 단계별 디버깅을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e034-104">Logically extends the ICorDebugFunction interface to provide support for Just My Code step-through debugging, which skips non-user code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0e034-105">메서드</span><span class="sxs-lookup"><span data-stu-id="0e034-105">Methods</span></span>  
  
|<span data-ttu-id="0e034-106">메서드</span><span class="sxs-lookup"><span data-stu-id="0e034-106">Method</span></span>|<span data-ttu-id="0e034-107">설명</span><span class="sxs-lookup"><span data-stu-id="0e034-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0e034-108">EnumerateNativeCode 메서드</span><span class="sxs-lookup"><span data-stu-id="0e034-108">EnumerateNativeCode Method</span></span>](icordebugfunction2-enumeratenativecode-method.md)|<span data-ttu-id="0e034-109">아직 구현 되지 않았습니다. 이 ICorDebugFunction2 개체가 참조 하는 함수에 네이티브 코드 문이 포함 된 ICorDebugCodeEnum에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0e034-109">(Not yet implemented.) Gets an interface pointer to an ICorDebugCodeEnum that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>|  
|[<span data-ttu-id="0e034-110">GetJMCStatus 메서드</span><span class="sxs-lookup"><span data-stu-id="0e034-110">GetJMCStatus Method</span></span>](icordebugfunction2-getjmcstatus-method.md)|<span data-ttu-id="0e034-111">이 함수가 사용자 코드로 표시 되었는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0e034-111">Gets a value that indicates whether this function is marked as user code.</span></span>|  
|[<span data-ttu-id="0e034-112">GetVersionNumber 메서드</span><span class="sxs-lookup"><span data-stu-id="0e034-112">GetVersionNumber Method</span></span>](icordebugfunction2-getversionnumber-method.md)|<span data-ttu-id="0e034-113">이 함수의 편집 하며 계속 하기 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0e034-113">Gets the Edit and Continue version of this function.</span></span>|  
|[<span data-ttu-id="0e034-114">SetJMCStatus 메서드</span><span class="sxs-lookup"><span data-stu-id="0e034-114">SetJMCStatus Method</span></span>](icordebugfunction2-setjmcstatus-method.md)|<span data-ttu-id="0e034-115">내 코드만 단계별 실행을 위해이 함수를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e034-115">Marks this function for Just My Code stepping.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e034-116">설명</span><span class="sxs-lookup"><span data-stu-id="0e034-116">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0e034-117">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0e034-117">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e034-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0e034-118">Requirements</span></span>  

 <span data-ttu-id="0e034-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0e034-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e034-120">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0e034-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e034-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e034-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e034-122">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e034-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e034-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0e034-123">See also</span></span>

- [<span data-ttu-id="0e034-124">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0e034-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
