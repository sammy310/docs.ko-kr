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
ms.openlocfilehash: 467ba53f90081f0c3499fb22acab96b5e380a3f4
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395837"
---
# <a name="icordebugvaluegetaddress-method"></a><span data-ttu-id="35092-102">ICorDebugValue::GetAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="35092-102">ICorDebugValue::GetAddress Method</span></span>
<span data-ttu-id="35092-103">디버깅 중인이 "ICorDebugValue" 개체의 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="35092-103">Gets the address of this "ICorDebugValue" object, which is in the process of being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35092-104">구문</span><span class="sxs-lookup"><span data-stu-id="35092-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35092-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="35092-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="35092-106">제한이 `CORDB_ADDRESS`이 값 개체의 주소를 지정 하는 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="35092-106">[out] Pointer to a `CORDB_ADDRESS` object that specifies the address of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35092-107">설명</span><span class="sxs-lookup"><span data-stu-id="35092-107">Remarks</span></span>  
 <span data-ttu-id="35092-108">값을 사용할 수 없는 경우 0이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35092-108">If the value is unavailable, 0 (zero) is returned.</span></span> <span data-ttu-id="35092-109">이는 값이 최소한 레지스터에 있거나 가비지 수집기 핸들 ()에 저장 된 경우에 발생할 수 있습니다 `GCHandle` .</span><span class="sxs-lookup"><span data-stu-id="35092-109">This could happen if the value is at least partly in registers or stored in a garbage collector handle (`GCHandle`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35092-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="35092-110">Requirements</span></span>  
 <span data-ttu-id="35092-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="35092-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35092-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="35092-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="35092-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35092-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35092-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35092-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35092-115">참조</span><span class="sxs-lookup"><span data-stu-id="35092-115">See also</span></span>
