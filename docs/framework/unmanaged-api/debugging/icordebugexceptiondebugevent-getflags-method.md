---
description: '자세히 알아보기: ICorDebugExceptionDebugEvent:: GetFlags 메서드'
title: ICorDebugExceptionDebugEvent::GetFlags 메서드
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
ms.openlocfilehash: 54a6c9b0dff2346ca130f80e72fe06dbb3017f10
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693475"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="99c56-103">ICorDebugExceptionDebugEvent::GetFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="99c56-103">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>

<span data-ttu-id="99c56-104">예외를 가로챌 수 있는지 여부를 나타내는 플래그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="99c56-104">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99c56-105">구문</span><span class="sxs-lookup"><span data-stu-id="99c56-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99c56-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="99c56-106">Parameters</span></span>  

 `pdwFlags`  
 <span data-ttu-id="99c56-107">제한이 예외를 가로챌 수 있는지 여부를 나타내는 [Cordebugexceptionflags](cordebugexceptionflags-enumeration.md) 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="99c56-107">[out] A pointer to a [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99c56-108">설명</span><span class="sxs-lookup"><span data-stu-id="99c56-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="99c56-109">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99c56-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99c56-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="99c56-110">Requirements</span></span>  

 <span data-ttu-id="99c56-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99c56-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99c56-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="99c56-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="99c56-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99c56-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99c56-114">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99c56-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99c56-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="99c56-115">See also</span></span>

- [<span data-ttu-id="99c56-116">ICorDebugExceptionDebugEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="99c56-116">ICorDebugExceptionDebugEvent Interface</span></span>](icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="99c56-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="99c56-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
