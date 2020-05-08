---
title: ICorDebugAppDomain4::GetObjectForCCW 메서드
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
ms.openlocfilehash: a175a6b6c91c284348580e1d9dc9ef0c5f5fc5df
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895126"
---
# <a name="icordebugappdomain4getobjectforccw-method"></a><span data-ttu-id="b6645-102">ICorDebugAppDomain4::GetObjectForCCW 메서드</span><span class="sxs-lookup"><span data-stu-id="b6645-102">ICorDebugAppDomain4::GetObjectForCCW Method</span></span>
<span data-ttu-id="b6645-103">CCW(COM 호출 가능 래퍼) 포인터에서 관리되는 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b6645-103">Gets a managed object from a COM callable wrapper (CCW) pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6645-104">구문</span><span class="sxs-lookup"><span data-stu-id="b6645-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6645-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b6645-105">Parameters</span></span>  
 `ccwPointer`  
 <span data-ttu-id="b6645-106">[in] CCW(COM 호출 가능 래퍼) 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b6645-106">[in] A COM callable wrapper (CCW) pointer.</span></span>  
  
 `ppManagedObject`  
 <span data-ttu-id="b6645-107">제한이 지정 된 CCW 포인터에 해당 하는 관리 되는 개체를 나타내는 "ICorDebugValue" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b6645-107">[out] A pointer to the address of an "ICorDebugValue" object that represents the managed object that corresponds to the given CCW pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6645-108">설명</span><span class="sxs-lookup"><span data-stu-id="b6645-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6645-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b6645-109">Requirements</span></span>  
 <span data-ttu-id="b6645-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6645-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6645-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b6645-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b6645-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6645-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6645-113">**.NET Framework 버전:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6645-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6645-114">참조</span><span class="sxs-lookup"><span data-stu-id="b6645-114">See also</span></span>

- [<span data-ttu-id="b6645-115">ICorDebugAppDomain4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b6645-115">ICorDebugAppDomain4 Interface</span></span>](icordebugappdomain4-interface.md)
- [<span data-ttu-id="b6645-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b6645-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
