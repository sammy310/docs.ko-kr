---
title: ICorDebugExceptionDebugEvent::GetFlags 메서드
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb92deee21c63c935454ff7c7c4e70be6f770436
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70895007"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="3f4df-102">ICorDebugExceptionDebugEvent::GetFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="3f4df-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="3f4df-103">예외를 가로챌 수 있는지 여부를 나타내는 플래그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3f4df-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f4df-104">구문</span><span class="sxs-lookup"><span data-stu-id="3f4df-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f4df-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3f4df-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="3f4df-106">제한이 예외를 가로챌 수 있는지 여부를 나타내는 [Cordebugexceptionflags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3f4df-106">[out] A pointer to a [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f4df-107">설명</span><span class="sxs-lookup"><span data-stu-id="3f4df-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3f4df-108">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f4df-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f4df-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3f4df-109">Requirements</span></span>  
 <span data-ttu-id="3f4df-110">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3f4df-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f4df-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f4df-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f4df-112">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f4df-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f4df-113">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f4df-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f4df-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="3f4df-114">See also</span></span>

- [<span data-ttu-id="3f4df-115">ICorDebugExceptionDebugEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f4df-115">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="3f4df-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f4df-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
