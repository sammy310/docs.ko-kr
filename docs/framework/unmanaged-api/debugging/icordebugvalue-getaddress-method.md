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
ms.openlocfilehash: 906ca2540e421953b3ce39300aa7b2376f789929
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137095"
---
# <a name="icordebugvaluegetaddress-method"></a><span data-ttu-id="f1f2b-102">ICorDebugValue::GetAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="f1f2b-102">ICorDebugValue::GetAddress Method</span></span>
<span data-ttu-id="f1f2b-103">디버깅 중인이 "ICorDebugValue" 개체의 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f1f2b-103">Gets the address of this "ICorDebugValue" object, which is in the process of being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1f2b-104">구문</span><span class="sxs-lookup"><span data-stu-id="f1f2b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1f2b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f1f2b-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="f1f2b-106">제한이 이 값 개체의 주소를 지정 하는 `CORDB_ADDRESS` 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f1f2b-106">[out] Pointer to a `CORDB_ADDRESS` object that specifies the address of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1f2b-107">주의</span><span class="sxs-lookup"><span data-stu-id="f1f2b-107">Remarks</span></span>  
 <span data-ttu-id="f1f2b-108">값을 사용할 수 없는 경우 0이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1f2b-108">If the value is unavailable, 0 (zero) is returned.</span></span> <span data-ttu-id="f1f2b-109">이는 값이 최소한 레지스터에 있거나 가비지 수집기 핸들 (`GCHandle`)에 저장 된 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1f2b-109">This could happen if the value is at least partly in registers or stored in a garbage collector handle (`GCHandle`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1f2b-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f1f2b-110">Requirements</span></span>  
 <span data-ttu-id="f1f2b-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f1f2b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1f2b-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1f2b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1f2b-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1f2b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1f2b-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1f2b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1f2b-115">참조</span><span class="sxs-lookup"><span data-stu-id="f1f2b-115">See also</span></span>
