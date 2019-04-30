---
title: ICorDebugType::GetFirstTypeParameter 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetFirstTypeParameter
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetFirstTypeParameter
helpviewer_keywords:
- ICorDebugType::GetFirstTypeParameter method [.NET Framework debugging]
- GetFirstTypeParameter method [.NET Framework debugging]
ms.assetid: 35bb594f-af6a-4349-83fe-e98702674e03
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4d872e4a65c0556dddac468336e6a42dd7d7923c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986988"
---
# <a name="icordebugtypegetfirsttypeparameter-method"></a><span data-ttu-id="97080-102">ICorDebugType::GetFirstTypeParameter 메서드</span><span class="sxs-lookup"><span data-stu-id="97080-102">ICorDebugType::GetFirstTypeParameter Method</span></span>
<span data-ttu-id="97080-103">첫 번째 나타내는 ICorDebugType에 대 한 인터페이스 포인터를 가져옵니다 <xref:System.Type> 이 나타내는 형식의 매개 변수 `ICorDebugType`합니다.</span><span class="sxs-lookup"><span data-stu-id="97080-103">Gets an interface pointer to an ICorDebugType that represents the first <xref:System.Type> parameter of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97080-104">구문</span><span class="sxs-lookup"><span data-stu-id="97080-104">Syntax</span></span>  
  
```  
HRESULT GetFirstTypeParameter (  
    [out] ICorDebugType   **value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97080-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="97080-105">Parameters</span></span>  
 `value`  
 <span data-ttu-id="97080-106">[out] 주소에 대 한 포인터는 `ICorDebugType` 첫 번째 매개 변수를 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="97080-106">[out] A pointer to the address of an `ICorDebugType` object that represents the first parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97080-107">설명</span><span class="sxs-lookup"><span data-stu-id="97080-107">Remarks</span></span>  
 <span data-ttu-id="97080-108">`GetFirstTypeParameter` 호출할 수 있습니다 최대 유형에 대 한 추가 정보는 있는 경우에서 하나의 형식 매개 변수.</span><span class="sxs-lookup"><span data-stu-id="97080-108">`GetFirstTypeParameter` can be called in cases where the additional information about the type involves, at most, one type parameter.</span></span> <span data-ttu-id="97080-109">특히, 사용할 수 있습니다 형식 ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, 또는 ELEMENT_TYPE_PTR, 경우에 표시 된 대로 합니다 [icordebugtype:: Gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="97080-109">In particular, it can be used if the type is an ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR, as indicated by the [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97080-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="97080-110">Requirements</span></span>  
 <span data-ttu-id="97080-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="97080-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97080-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="97080-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97080-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97080-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97080-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97080-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
