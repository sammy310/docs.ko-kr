---
description: '자세히 알아보기: ICorDebugExceptionObjectValue 인터페이스'
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
ms.openlocfilehash: 67672f9921bab31019a42b742480176e6d0bf3d4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693202"
---
# <a name="icordebugexceptionobjectvalue-interface"></a><span data-ttu-id="15a9f-103">ICorDebugExceptionObjectValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15a9f-103">ICorDebugExceptionObjectValue Interface</span></span>

<span data-ttu-id="15a9f-104">"ICorDebugObjectValue" 인터페이스를 확장 하 여 관리 되는 예외 개체의 스택 추적 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="15a9f-104">Extends the "ICorDebugObjectValue" interface to provide stack trace information from a managed exception object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="15a9f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="15a9f-105">Methods</span></span>  
  
|<span data-ttu-id="15a9f-106">메서드</span><span class="sxs-lookup"><span data-stu-id="15a9f-106">Method</span></span>|<span data-ttu-id="15a9f-107">설명</span><span class="sxs-lookup"><span data-stu-id="15a9f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="15a9f-108">EnumerateExceptionCallStack 메서드</span><span class="sxs-lookup"><span data-stu-id="15a9f-108">EnumerateExceptionCallStack Method</span></span>](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)|<span data-ttu-id="15a9f-109">예외 개체에 포함 된 호출 스택에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="15a9f-109">Gets an enumerator to the call stack embedded in an exception object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15a9f-110">설명</span><span class="sxs-lookup"><span data-stu-id="15a9f-110">Remarks</span></span>  

 <span data-ttu-id="15a9f-111">`QueryInterface`에서 파생 된 관리 되는 개체에 대 한 호출이 성공 합니다 <xref:System.Exception?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="15a9f-111">The call to `QueryInterface` will succeed for managed objects that derive from <xref:System.Exception?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15a9f-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="15a9f-112">Requirements</span></span>  

 <span data-ttu-id="15a9f-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="15a9f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15a9f-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="15a9f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="15a9f-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15a9f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15a9f-116">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15a9f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15a9f-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="15a9f-117">See also</span></span>

- [<span data-ttu-id="15a9f-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15a9f-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="15a9f-119">디버깅</span><span class="sxs-lookup"><span data-stu-id="15a9f-119">Debugging</span></span>](index.md)
