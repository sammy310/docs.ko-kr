---
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
ms.openlocfilehash: 528db447df4d71d67441b05ad29e6a900c59afbb
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892816"
---
# <a name="icordebugcomobjectvalue-interface"></a><span data-ttu-id="20353-102">ICorDebugComObjectValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="20353-102">ICorDebugComObjectValue Interface</span></span>
<span data-ttu-id="20353-103">RCW (런타임 호출 가능 래퍼)와 관련 된 정보를 검색 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="20353-103">Provides methods to retrieve information associated with a runtime callable wrapper (RCW).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="20353-104">메서드</span><span class="sxs-lookup"><span data-stu-id="20353-104">Methods</span></span>  
  
|<span data-ttu-id="20353-105">메서드</span><span class="sxs-lookup"><span data-stu-id="20353-105">Method</span></span>|<span data-ttu-id="20353-106">설명</span><span class="sxs-lookup"><span data-stu-id="20353-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="20353-107">GetCachedInterfacePointers 메서드</span><span class="sxs-lookup"><span data-stu-id="20353-107">GetCachedInterfacePointers Method</span></span>](icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|<span data-ttu-id="20353-108">현재 RCW에 캐시 된 원시 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="20353-108">Gets the raw interface pointers cached on the current RCW.</span></span>|  
|[<span data-ttu-id="20353-109">GetCachedInterfaceTypes 메서드</span><span class="sxs-lookup"><span data-stu-id="20353-109">GetCachedInterfaceTypes Method</span></span>](icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|<span data-ttu-id="20353-110">현재 개체의 대/소문자를 사용 하거나로 사용 하는 인터페이스 형식에 대 한 열거자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="20353-110">Provides an enumerator for the interface types that the current object has been cased to or used as.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20353-111">설명</span><span class="sxs-lookup"><span data-stu-id="20353-111">Remarks</span></span>  
 <span data-ttu-id="20353-112">"ICorDebugValue" 인터페이스의 인스턴스가 RCW를 나타내는지 여부를 확인 하려면 디버거는를 사용 하 `QueryInterface` 여 `IID_ICorDebugComObjectValue`"icordebugvalue"를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="20353-112">To check whether an instance of an "ICorDebugValue" interface represents an RCW, a debugger calls `QueryInterface` on "ICorDebugValue" with `IID_ICorDebugComObjectValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20353-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="20353-113">Requirements</span></span>  
 <span data-ttu-id="20353-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="20353-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20353-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="20353-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="20353-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20353-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20353-117">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20353-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20353-118">참조</span><span class="sxs-lookup"><span data-stu-id="20353-118">See also</span></span>

- [<span data-ttu-id="20353-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="20353-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="20353-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="20353-120">Debugging</span></span>](index.md)
