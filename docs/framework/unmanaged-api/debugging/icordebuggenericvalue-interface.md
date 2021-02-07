---
description: '자세히 알아보기: ICorDebugGenericValue 인터페이스'
title: ICorDebugGenericValue 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue
helpviewer_keywords:
- ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: bc14f408-b359-4c8c-ade2-888ccdf7261b
topic_type:
- apiref
ms.openlocfilehash: 7c81855849d7b72bc509d20072b96bb64f5d395a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692036"
---
# <a name="icordebuggenericvalue-interface"></a><span data-ttu-id="95bc1-103">ICorDebugGenericValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="95bc1-103">ICorDebugGenericValue Interface</span></span>

<span data-ttu-id="95bc1-104">모든 값에 적용 되는 "ICorDebugValue"의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="95bc1-104">A subclass of "ICorDebugValue" that applies to all values.</span></span> <span data-ttu-id="95bc1-105">이 인터페이스에서는 값의 Get 및 Set 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="95bc1-105">This interface provides Get and Set methods for the value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="95bc1-106">메서드</span><span class="sxs-lookup"><span data-stu-id="95bc1-106">Methods</span></span>  
  
|<span data-ttu-id="95bc1-107">메서드</span><span class="sxs-lookup"><span data-stu-id="95bc1-107">Method</span></span>|<span data-ttu-id="95bc1-108">설명</span><span class="sxs-lookup"><span data-stu-id="95bc1-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="95bc1-109">GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="95bc1-109">GetValue Method</span></span>](icordebuggenericvalue-getvalue-method.md)|<span data-ttu-id="95bc1-110">값을 지정 된 버퍼에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="95bc1-110">Copies the value into the specified buffer.</span></span>|  
|[<span data-ttu-id="95bc1-111">SetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="95bc1-111">SetValue Method</span></span>](icordebuggenericvalue-setvalue-method.md)|<span data-ttu-id="95bc1-112">지정 된 버퍼에서 새 값을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="95bc1-112">Copies a new value from the specified buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95bc1-113">설명</span><span class="sxs-lookup"><span data-stu-id="95bc1-113">Remarks</span></span>  

 <span data-ttu-id="95bc1-114">`ICorDebugGenericValue` 는 원격으로 가능 하지 않으므로 하위 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="95bc1-114">`ICorDebugGenericValue` is a sub-interface because it is non-remotable.</span></span>  
  
 <span data-ttu-id="95bc1-115">참조 형식의 경우 값은 참조의 내용이 아닌 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="95bc1-115">For reference types, the value is the reference rather than the contents of the reference.</span></span>  
  
 <span data-ttu-id="95bc1-116">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95bc1-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="95bc1-117">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95bc1-117">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95bc1-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="95bc1-118">Requirements</span></span>  

 <span data-ttu-id="95bc1-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95bc1-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95bc1-120">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="95bc1-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95bc1-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95bc1-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95bc1-122">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95bc1-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95bc1-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="95bc1-123">See also</span></span>

- [<span data-ttu-id="95bc1-124">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="95bc1-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
