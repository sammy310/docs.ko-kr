---
title: ICorDebugAppDomain4::GetObjectForCCW 메서드
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
ms.openlocfilehash: 50f46394c809321f0bd256e4c8d75b76fc7c2c70
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784858"
---
# <a name="icordebugappdomain4getobjectforccw-method"></a><span data-ttu-id="b0d30-102">ICorDebugAppDomain4::GetObjectForCCW 메서드</span><span class="sxs-lookup"><span data-stu-id="b0d30-102">ICorDebugAppDomain4::GetObjectForCCW Method</span></span>
<span data-ttu-id="b0d30-103">CCW(COM 호출 가능 래퍼) 포인터에서 관리되는 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b0d30-103">Gets a managed object from a COM callable wrapper (CCW) pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0d30-104">구문</span><span class="sxs-lookup"><span data-stu-id="b0d30-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,   
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0d30-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b0d30-105">Parameters</span></span>  
 `ccwPointer`  
 <span data-ttu-id="b0d30-106">[in] CCW(COM 호출 가능 래퍼) 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b0d30-106">[in] A COM callable wrapper (CCW) pointer.</span></span>  
  
 `ppManagedObject`  
 <span data-ttu-id="b0d30-107">제한이 지정 된 CCW 포인터에 해당 하는 관리 되는 개체를 나타내는 "ICorDebugValue" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b0d30-107">[out] A pointer to the address of an "ICorDebugValue" object that represents the managed object that corresponds to the given CCW pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0d30-108">주의</span><span class="sxs-lookup"><span data-stu-id="b0d30-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0d30-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b0d30-109">Requirements</span></span>  
 <span data-ttu-id="b0d30-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0d30-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0d30-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0d30-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0d30-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0d30-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0d30-113">**.NET Framework 버전:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0d30-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0d30-114">참조</span><span class="sxs-lookup"><span data-stu-id="b0d30-114">See also</span></span>

- [<span data-ttu-id="b0d30-115">ICorDebugAppDomain4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0d30-115">ICorDebugAppDomain4 Interface</span></span>](icordebugappdomain4-interface.md)
- [<span data-ttu-id="b0d30-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0d30-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
