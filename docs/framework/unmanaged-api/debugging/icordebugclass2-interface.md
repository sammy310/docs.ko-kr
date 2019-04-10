---
title: ICorDebugClass2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugClass2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2
helpviewer_keywords:
- ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 5416de70-43f2-4cdf-a11f-d570759c9c0c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 015085cff23028814937dfef9aea19af7438b4f5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173812"
---
# <a name="icordebugclass2-interface"></a><span data-ttu-id="2be85-102">ICorDebugClass2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2be85-102">ICorDebugClass2 Interface</span></span>

<span data-ttu-id="2be85-103">제네릭 클래스나 <xref:System.Type> 형식의 메서드 매개 변수를 사용하는 클래스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2be85-103">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="2be85-104">이 인터페이스를 확장 [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2be85-104">This interface extends [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2be85-105">메서드</span><span class="sxs-lookup"><span data-stu-id="2be85-105">Methods</span></span>  
  
|<span data-ttu-id="2be85-106">메서드</span><span class="sxs-lookup"><span data-stu-id="2be85-106">Method</span></span>|<span data-ttu-id="2be85-107">설명</span><span class="sxs-lookup"><span data-stu-id="2be85-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2be85-108">GetParameterizedType 메서드</span><span class="sxs-lookup"><span data-stu-id="2be85-108">GetParameterizedType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-getparameterizedtype-method.md)|<span data-ttu-id="2be85-109">이 클래스에 대 한 형식 선언을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2be85-109">Gets the type declaration for this class.</span></span>|  
|[<span data-ttu-id="2be85-110">SetJMCStatus 메서드</span><span class="sxs-lookup"><span data-stu-id="2be85-110">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-setjmcstatus-method.md)|<span data-ttu-id="2be85-111">이 클래스의 각 메서드의 경우 메서드는 사용자가 정의한 코드 있는지 여부를 나타내는 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2be85-111">For each method of this class, sets a value that indicates whether the method is user-defined code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2be85-112">설명</span><span class="sxs-lookup"><span data-stu-id="2be85-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2be85-113">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2be85-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2be85-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2be85-114">Requirements</span></span>  
 <span data-ttu-id="2be85-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2be85-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2be85-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2be85-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2be85-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2be85-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="2be85-118">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="2be85-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2be85-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="2be85-119">See also</span></span>

- [<span data-ttu-id="2be85-120">ICorDebugClass 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2be85-120">ICorDebugClass Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)
- [<span data-ttu-id="2be85-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2be85-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
