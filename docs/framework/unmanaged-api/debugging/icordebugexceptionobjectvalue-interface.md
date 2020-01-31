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
ms.openlocfilehash: fa154d0bb48f4ecd4fc6a50ce22fd13c592b7c40
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782741"
---
# <a name="icordebugexceptionobjectvalue-interface"></a><span data-ttu-id="a7111-102">ICorDebugExceptionObjectValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a7111-102">ICorDebugExceptionObjectValue Interface</span></span>
<span data-ttu-id="a7111-103">"ICorDebugObjectValue" 인터페이스를 확장 하 여 관리 되는 예외 개체의 스택 추적 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7111-103">Extends the "ICorDebugObjectValue" interface to provide stack trace information from a managed exception object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a7111-104">메서드</span><span class="sxs-lookup"><span data-stu-id="a7111-104">Methods</span></span>  
  
|<span data-ttu-id="a7111-105">메서드</span><span class="sxs-lookup"><span data-stu-id="a7111-105">Method</span></span>|<span data-ttu-id="a7111-106">설명</span><span class="sxs-lookup"><span data-stu-id="a7111-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a7111-107">EnumerateExceptionCallStack 메서드</span><span class="sxs-lookup"><span data-stu-id="a7111-107">EnumerateExceptionCallStack Method</span></span>](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)|<span data-ttu-id="a7111-108">예외 개체에 포함 된 호출 스택에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a7111-108">Gets an enumerator to the call stack embedded in an exception object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7111-109">주의</span><span class="sxs-lookup"><span data-stu-id="a7111-109">Remarks</span></span>  
 <span data-ttu-id="a7111-110">`QueryInterface`에 대 한 호출은 <xref:System.Exception?displayProperty=nameWithType>에서 파생 되는 관리 되는 개체에 대해 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7111-110">The call to `QueryInterface` will succeed for managed objects that derive from <xref:System.Exception?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7111-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a7111-111">Requirements</span></span>  
 <span data-ttu-id="a7111-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a7111-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7111-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a7111-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a7111-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7111-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7111-115">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7111-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7111-116">참조</span><span class="sxs-lookup"><span data-stu-id="a7111-116">See also</span></span>

- [<span data-ttu-id="a7111-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a7111-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a7111-118">디버깅</span><span class="sxs-lookup"><span data-stu-id="a7111-118">Debugging</span></span>](index.md)
