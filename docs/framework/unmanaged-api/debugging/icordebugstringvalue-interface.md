---
title: ICorDebugStringValue 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue
helpviewer_keywords:
- ICorDebugStringValue interface [.NET Framework debugging]
ms.assetid: bf84d0af-53e1-4c04-bc5b-7e5f81ba2cc2
topic_type:
- apiref
ms.openlocfilehash: 6c232163f7c18086804eca7990a0890a507ef00b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791684"
---
# <a name="icordebugstringvalue-interface"></a><span data-ttu-id="21e60-102">ICorDebugStringValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="21e60-102">ICorDebugStringValue Interface</span></span>
<span data-ttu-id="21e60-103">문자열 값에 적용 되는 ICorDebugHeapValue의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="21e60-103">A subclass of ICorDebugHeapValue that applies to string values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="21e60-104">메서드</span><span class="sxs-lookup"><span data-stu-id="21e60-104">Methods</span></span>  
  
|<span data-ttu-id="21e60-105">메서드</span><span class="sxs-lookup"><span data-stu-id="21e60-105">Method</span></span>|<span data-ttu-id="21e60-106">설명</span><span class="sxs-lookup"><span data-stu-id="21e60-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="21e60-107">GetLength 메서드</span><span class="sxs-lookup"><span data-stu-id="21e60-107">GetLength Method</span></span>](icordebugstringvalue-getlength-method.md)|<span data-ttu-id="21e60-108">이 `ICorDebugStringValue`에서 참조 하는 문자열의 문자 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="21e60-108">Gets the number of characters in the string referenced by this `ICorDebugStringValue`.</span></span>|  
|[<span data-ttu-id="21e60-109">GetString 메서드</span><span class="sxs-lookup"><span data-stu-id="21e60-109">GetString Method</span></span>](icordebugstringvalue-getstring-method.md)|<span data-ttu-id="21e60-110">이 `ICorDebugStringValue`에서 참조 하는 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="21e60-110">Gets the string referenced by this `ICorDebugStringValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21e60-111">주의</span><span class="sxs-lookup"><span data-stu-id="21e60-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="21e60-112">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="21e60-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21e60-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="21e60-113">Requirements</span></span>  
 <span data-ttu-id="21e60-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="21e60-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21e60-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="21e60-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="21e60-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21e60-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21e60-117">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21e60-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21e60-118">참조</span><span class="sxs-lookup"><span data-stu-id="21e60-118">See also</span></span>

- [<span data-ttu-id="21e60-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="21e60-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
