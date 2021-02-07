---
description: '자세히 알아보기: ICorDebugComObjectValue 인터페이스'
title: ICorDebugComObjectValue 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugComObjectValue
helpviewer_keywords:
- ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 505a7f6c-d92b-42b4-b539-433f5102ea9b
topic_type:
- apiref
ms.openlocfilehash: 3c071c371ae6e330431630cfb1934b538d62efe6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710818"
---
# <a name="icordebugcomobjectvalue-interface"></a><span data-ttu-id="ac60a-103">ICorDebugComObjectValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ac60a-103">ICorDebugComObjectValue Interface</span></span>

<span data-ttu-id="ac60a-104">RCW (런타임 호출 가능 래퍼)와 관련 된 정보를 검색 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac60a-104">Provides methods to retrieve information associated with a runtime callable wrapper (RCW).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ac60a-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ac60a-105">Methods</span></span>  
  
|<span data-ttu-id="ac60a-106">메서드</span><span class="sxs-lookup"><span data-stu-id="ac60a-106">Method</span></span>|<span data-ttu-id="ac60a-107">설명</span><span class="sxs-lookup"><span data-stu-id="ac60a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ac60a-108">GetCachedInterfacePointers 메서드</span><span class="sxs-lookup"><span data-stu-id="ac60a-108">GetCachedInterfacePointers Method</span></span>](icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|<span data-ttu-id="ac60a-109">현재 RCW에 캐시 된 원시 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ac60a-109">Gets the raw interface pointers cached on the current RCW.</span></span>|  
|[<span data-ttu-id="ac60a-110">GetCachedInterfaceTypes 메서드</span><span class="sxs-lookup"><span data-stu-id="ac60a-110">GetCachedInterfaceTypes Method</span></span>](icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|<span data-ttu-id="ac60a-111">현재 개체의 대/소문자를 사용 하거나로 사용 하는 인터페이스 형식에 대 한 열거자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac60a-111">Provides an enumerator for the interface types that the current object has been cased to or used as.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac60a-112">설명</span><span class="sxs-lookup"><span data-stu-id="ac60a-112">Remarks</span></span>  

 <span data-ttu-id="ac60a-113">"ICorDebugValue" 인터페이스의 인스턴스가 RCW를 나타내는지 여부를 확인 하려면 디버거는 `QueryInterface` 를 사용 하 여 "icordebugvalue"를 호출 `IID_ICorDebugComObjectValue` 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac60a-113">To check whether an instance of an "ICorDebugValue" interface represents an RCW, a debugger calls `QueryInterface` on "ICorDebugValue" with `IID_ICorDebugComObjectValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac60a-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ac60a-114">Requirements</span></span>  

 <span data-ttu-id="ac60a-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ac60a-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac60a-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ac60a-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ac60a-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac60a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac60a-118">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac60a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac60a-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ac60a-119">See also</span></span>

- [<span data-ttu-id="ac60a-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ac60a-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="ac60a-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="ac60a-121">Debugging</span></span>](index.md)
