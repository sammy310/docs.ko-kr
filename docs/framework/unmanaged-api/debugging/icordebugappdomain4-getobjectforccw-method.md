---
title: ICorDebugAppDomain4::GetObjectForCCW 메서드
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
ms.openlocfilehash: 10d32314e46aba4f030b294cadc3cbb36e8742f8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179044"
---
# <a name="icordebugappdomain4getobjectforccw-method"></a><span data-ttu-id="89987-102">ICorDebugAppDomain4::GetObjectForCCW 메서드</span><span class="sxs-lookup"><span data-stu-id="89987-102">ICorDebugAppDomain4::GetObjectForCCW Method</span></span>
<span data-ttu-id="89987-103">CCW(COM 호출 가능 래퍼) 포인터에서 관리되는 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="89987-103">Gets a managed object from a COM callable wrapper (CCW) pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89987-104">구문</span><span class="sxs-lookup"><span data-stu-id="89987-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89987-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="89987-105">Parameters</span></span>  
 `ccwPointer`  
 <span data-ttu-id="89987-106">[in] CCW(COM 호출 가능 래퍼) 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="89987-106">[in] A COM callable wrapper (CCW) pointer.</span></span>  
  
 `ppManagedObject`  
 <span data-ttu-id="89987-107">【아웃】 지정된 CCW 포인터에 해당하는 관리 되는 개체를 나타내는 "ICorDebugValue" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="89987-107">[out] A pointer to the address of an "ICorDebugValue" object that represents the managed object that corresponds to the given CCW pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89987-108">설명</span><span class="sxs-lookup"><span data-stu-id="89987-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89987-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="89987-109">Requirements</span></span>  
 <span data-ttu-id="89987-110">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89987-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89987-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="89987-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="89987-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89987-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89987-113">**.NET Framework 버전:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89987-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89987-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="89987-114">See also</span></span>

- [<span data-ttu-id="89987-115">ICorDebugAppDomain4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="89987-115">ICorDebugAppDomain4 Interface</span></span>](icordebugappdomain4-interface.md)
- [<span data-ttu-id="89987-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="89987-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
