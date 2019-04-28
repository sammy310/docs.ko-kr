---
title: ICorDebugReferenceValue::GetValue 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::GetValue
helpviewer_keywords:
- GetValue method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::GetValue method [.NET Framework debugging]
ms.assetid: 5da07f99-6c70-46ec-b997-5ab6fb7106cd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e52ef20f2b8e3937911dc37e68f8a338ab0d85d9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782969"
---
# <a name="icordebugreferencevaluegetvalue-method"></a><span data-ttu-id="535b2-102">ICorDebugReferenceValue::GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="535b2-102">ICorDebugReferenceValue::GetValue Method</span></span>
<span data-ttu-id="535b2-103">참조 된 개체의 현재 메모리 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="535b2-103">Gets the current memory address of the referenced object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="535b2-104">구문</span><span class="sxs-lookup"><span data-stu-id="535b2-104">Syntax</span></span>  
  
```  
HRESULT GetValue (  
    [out] CORDB_ADDRESS   *pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="535b2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="535b2-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="535b2-106">[out] 에 대 한 포인터를 `CORDB_ADDRESS` 이 ICorDebugReferenceValue 개체가 가리키는 개체의 주소를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="535b2-106">[out] A pointer to a `CORDB_ADDRESS` value that specifies the address of the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="535b2-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="535b2-107">Requirements</span></span>  
 <span data-ttu-id="535b2-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="535b2-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="535b2-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="535b2-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="535b2-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="535b2-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="535b2-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="535b2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
