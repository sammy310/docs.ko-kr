---
description: '자세히 알아보기: ICorDebugAppDomain4:: GetObjectForCCW 메서드'
title: ICorDebugAppDomain4::GetObjectForCCW 메서드
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
ms.openlocfilehash: 5ba4923c933d02f5d6ad5c1fd8c4d0e2ddb410d3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754136"
---
# <a name="icordebugappdomain4getobjectforccw-method"></a><span data-ttu-id="114aa-103">ICorDebugAppDomain4::GetObjectForCCW 메서드</span><span class="sxs-lookup"><span data-stu-id="114aa-103">ICorDebugAppDomain4::GetObjectForCCW Method</span></span>

<span data-ttu-id="114aa-104">CCW(COM 호출 가능 래퍼) 포인터에서 관리되는 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="114aa-104">Gets a managed object from a COM callable wrapper (CCW) pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="114aa-105">구문</span><span class="sxs-lookup"><span data-stu-id="114aa-105">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="114aa-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="114aa-106">Parameters</span></span>  

 `ccwPointer`  
 <span data-ttu-id="114aa-107">[in] CCW(COM 호출 가능 래퍼) 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="114aa-107">[in] A COM callable wrapper (CCW) pointer.</span></span>  
  
 `ppManagedObject`  
 <span data-ttu-id="114aa-108">제한이 지정 된 CCW 포인터에 해당 하는 관리 되는 개체를 나타내는 "ICorDebugValue" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="114aa-108">[out] A pointer to the address of an "ICorDebugValue" object that represents the managed object that corresponds to the given CCW pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="114aa-109">설명</span><span class="sxs-lookup"><span data-stu-id="114aa-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="114aa-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="114aa-110">Requirements</span></span>  

 <span data-ttu-id="114aa-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="114aa-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="114aa-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="114aa-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="114aa-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="114aa-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="114aa-114">**.NET Framework 버전:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="114aa-114">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="114aa-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="114aa-115">See also</span></span>

- [<span data-ttu-id="114aa-116">ICorDebugAppDomain4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="114aa-116">ICorDebugAppDomain4 Interface</span></span>](icordebugappdomain4-interface.md)
- [<span data-ttu-id="114aa-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="114aa-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
