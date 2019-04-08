---
title: ICorDebugExceptionObjectValue 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectValue
helpviewer_keywords:
- ICorDebugExceptionObjectValue interface [.NET Framework debugging]
ms.assetid: 43416dd5-8892-4106-9f59-f9143b19ddb4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b5328442ceaee05b3f81466b785f04a361d456a8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59098483"
---
# <a name="icordebugexceptionobjectvalue-interface"></a><span data-ttu-id="7b002-102">ICorDebugExceptionObjectValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7b002-102">ICorDebugExceptionObjectValue Interface</span></span>
<span data-ttu-id="7b002-103">관리 되는 예외 개체에서 스택 추적 정보를 제공 하는 "ICorDebugObjectValue" 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b002-103">Extends the "ICorDebugObjectValue" interface to provide stack trace information from a managed exception object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7b002-104">메서드</span><span class="sxs-lookup"><span data-stu-id="7b002-104">Methods</span></span>  
  
|<span data-ttu-id="7b002-105">메서드</span><span class="sxs-lookup"><span data-stu-id="7b002-105">Method</span></span>|<span data-ttu-id="7b002-106">설명</span><span class="sxs-lookup"><span data-stu-id="7b002-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7b002-107">EnumerateExceptionCallStack 메서드</span><span class="sxs-lookup"><span data-stu-id="7b002-107">EnumerateExceptionCallStack Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)|<span data-ttu-id="7b002-108">예외 개체에 포함 된 호출 스택에 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7b002-108">Gets an enumerator to the call stack embedded in an exception object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b002-109">설명</span><span class="sxs-lookup"><span data-stu-id="7b002-109">Remarks</span></span>  
 <span data-ttu-id="7b002-110">에 대 한 호출 `QueryInterface` 에서 파생 되는 관리 되는 개체에 대 한 성공할 <xref:System.Exception?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="7b002-110">The call to `QueryInterface` will succeed for managed objects that derive from <xref:System.Exception?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b002-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7b002-111">Requirements</span></span>  
 <span data-ttu-id="7b002-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7b002-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b002-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b002-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b002-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b002-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="7b002-115">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="7b002-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7b002-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="7b002-116">See also</span></span>

- [<span data-ttu-id="7b002-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7b002-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="7b002-118">디버깅</span><span class="sxs-lookup"><span data-stu-id="7b002-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
