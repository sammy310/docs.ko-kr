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
ms.openlocfilehash: 8e4f745440936a39e22faf60d10a05a0bb110606
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975955"
---
# <a name="icordebugexceptionobjectvalue-interface"></a><span data-ttu-id="fafa4-102">ICorDebugExceptionObjectValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fafa4-102">ICorDebugExceptionObjectValue Interface</span></span>
<span data-ttu-id="fafa4-103">"ICorDebugObjectValue" 인터페이스를 확장 하 여 관리 되는 예외 개체의 스택 추적 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fafa4-103">Extends the "ICorDebugObjectValue" interface to provide stack trace information from a managed exception object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fafa4-104">메서드</span><span class="sxs-lookup"><span data-stu-id="fafa4-104">Methods</span></span>  
  
|<span data-ttu-id="fafa4-105">메서드</span><span class="sxs-lookup"><span data-stu-id="fafa4-105">Method</span></span>|<span data-ttu-id="fafa4-106">Description</span><span class="sxs-lookup"><span data-stu-id="fafa4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fafa4-107">EnumerateExceptionCallStack 메서드</span><span class="sxs-lookup"><span data-stu-id="fafa4-107">EnumerateExceptionCallStack Method</span></span>](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)|<span data-ttu-id="fafa4-108">예외 개체에 포함 된 호출 스택에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fafa4-108">Gets an enumerator to the call stack embedded in an exception object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fafa4-109">설명</span><span class="sxs-lookup"><span data-stu-id="fafa4-109">Remarks</span></span>  
 <span data-ttu-id="fafa4-110">에서 <xref:System.Exception?displayProperty=nameWithType>파생 된 `QueryInterface` 관리 되는 개체에 대 한 호출이 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fafa4-110">The call to `QueryInterface` will succeed for managed objects that derive from <xref:System.Exception?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fafa4-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fafa4-111">Requirements</span></span>  
 <span data-ttu-id="fafa4-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fafa4-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fafa4-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fafa4-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fafa4-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fafa4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fafa4-115">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fafa4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fafa4-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fafa4-116">See also</span></span>

- [<span data-ttu-id="fafa4-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fafa4-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="fafa4-118">디버깅</span><span class="sxs-lookup"><span data-stu-id="fafa4-118">Debugging</span></span>](index.md)
