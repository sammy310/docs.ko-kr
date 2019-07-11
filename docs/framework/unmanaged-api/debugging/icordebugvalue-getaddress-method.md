---
title: ICorDebugValue::GetAddress 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetAddress
helpviewer_keywords:
- ICorDebugValue::GetAddress method [.NET Framework debugging]
- GetAddress method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: a247c792-45e1-4538-9e1f-b46acca4a463
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5dc29663153f837b660262eae51b6f032617d027
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765074"
---
# <a name="icordebugvaluegetaddress-method"></a><span data-ttu-id="9a3ba-102">ICorDebugValue::GetAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="9a3ba-102">ICorDebugValue::GetAddress Method</span></span>
<span data-ttu-id="9a3ba-103">디버깅 중인 프로세스에 있는이 "ICorDebugValue" 개체의 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9a3ba-103">Gets the address of this "ICorDebugValue" object, which is in the process of being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a3ba-104">구문</span><span class="sxs-lookup"><span data-stu-id="9a3ba-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a3ba-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9a3ba-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="9a3ba-106">[out] 에 대 한 포인터를 `CORDB_ADDRESS` 이 값 개체의 주소를 지정 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="9a3ba-106">[out] Pointer to a `CORDB_ADDRESS` object that specifies the address of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a3ba-107">설명</span><span class="sxs-lookup"><span data-stu-id="9a3ba-107">Remarks</span></span>  
 <span data-ttu-id="9a3ba-108">값을 사용할 수 없는 경우 0 (영)이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a3ba-108">If the value is unavailable, 0 (zero) is returned.</span></span> <span data-ttu-id="9a3ba-109">이 값은 적어도 부분적으로 등록 하는 경우 발생할 수 있습니다 또는 가비지 수집기 핸들에 저장 (`GCHandle`).</span><span class="sxs-lookup"><span data-stu-id="9a3ba-109">This could happen if the value is at least partly in registers or stored in a garbage collector handle (`GCHandle`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a3ba-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9a3ba-110">Requirements</span></span>  
 <span data-ttu-id="9a3ba-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9a3ba-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a3ba-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a3ba-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a3ba-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a3ba-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a3ba-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a3ba-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a3ba-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="9a3ba-115">See also</span></span>
