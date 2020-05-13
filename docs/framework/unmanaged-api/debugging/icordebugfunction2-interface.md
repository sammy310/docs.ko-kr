---
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
ms.openlocfilehash: 611091d39da6d7f646457457f20ce1eaf37db361
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213207"
---
# <a name="icordebugfunction2-interface"></a><span data-ttu-id="7a77f-102">ICorDebugFunction2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7a77f-102">ICorDebugFunction2 Interface</span></span>

<span data-ttu-id="7a77f-103">ICorDebugFunction 인터페이스를 논리적으로 확장 하 여 사용자가 지정 하지 않은 코드를 건너뛰는 내 코드만 단계별 디버깅을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a77f-103">Logically extends the ICorDebugFunction interface to provide support for Just My Code step-through debugging, which skips non-user code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7a77f-104">메서드</span><span class="sxs-lookup"><span data-stu-id="7a77f-104">Methods</span></span>  
  
|<span data-ttu-id="7a77f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="7a77f-105">Method</span></span>|<span data-ttu-id="7a77f-106">설명</span><span class="sxs-lookup"><span data-stu-id="7a77f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7a77f-107">EnumerateNativeCode 메서드</span><span class="sxs-lookup"><span data-stu-id="7a77f-107">EnumerateNativeCode Method</span></span>](icordebugfunction2-enumeratenativecode-method.md)|<span data-ttu-id="7a77f-108">아직 구현 되지 않았습니다. 이 ICorDebugFunction2 개체가 참조 하는 함수에 네이티브 코드 문이 포함 된 ICorDebugCodeEnum에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7a77f-108">(Not yet implemented.) Gets an interface pointer to an ICorDebugCodeEnum that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>|  
|[<span data-ttu-id="7a77f-109">GetJMCStatus 메서드</span><span class="sxs-lookup"><span data-stu-id="7a77f-109">GetJMCStatus Method</span></span>](icordebugfunction2-getjmcstatus-method.md)|<span data-ttu-id="7a77f-110">이 함수가 사용자 코드로 표시 되었는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7a77f-110">Gets a value that indicates whether this function is marked as user code.</span></span>|  
|[<span data-ttu-id="7a77f-111">GetVersionNumber 메서드</span><span class="sxs-lookup"><span data-stu-id="7a77f-111">GetVersionNumber Method</span></span>](icordebugfunction2-getversionnumber-method.md)|<span data-ttu-id="7a77f-112">이 함수의 편집 하며 계속 하기 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7a77f-112">Gets the Edit and Continue version of this function.</span></span>|  
|[<span data-ttu-id="7a77f-113">SetJMCStatus 메서드</span><span class="sxs-lookup"><span data-stu-id="7a77f-113">SetJMCStatus Method</span></span>](icordebugfunction2-setjmcstatus-method.md)|<span data-ttu-id="7a77f-114">내 코드만 단계별 실행을 위해이 함수를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a77f-114">Marks this function for Just My Code stepping.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a77f-115">설명</span><span class="sxs-lookup"><span data-stu-id="7a77f-115">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7a77f-116">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a77f-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a77f-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7a77f-117">Requirements</span></span>  
 <span data-ttu-id="7a77f-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7a77f-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a77f-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7a77f-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7a77f-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a77f-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a77f-121">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a77f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a77f-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7a77f-122">See also</span></span>

- [<span data-ttu-id="7a77f-123">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7a77f-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
