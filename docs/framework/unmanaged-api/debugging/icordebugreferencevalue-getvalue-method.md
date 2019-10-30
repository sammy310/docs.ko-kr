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
ms.openlocfilehash: 7a2288eb84bd51795995032954e41525c2ce605a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137721"
---
# <a name="icordebugreferencevaluegetvalue-method"></a><span data-ttu-id="a13a0-102">ICorDebugReferenceValue::GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="a13a0-102">ICorDebugReferenceValue::GetValue Method</span></span>
<span data-ttu-id="a13a0-103">참조 된 개체의 현재 메모리 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a13a0-103">Gets the current memory address of the referenced object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a13a0-104">구문</span><span class="sxs-lookup"><span data-stu-id="a13a0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue (  
    [out] CORDB_ADDRESS   *pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a13a0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a13a0-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="a13a0-106">제한이 이 ICorDebugReferenceValue 개체가 가리키는 개체의 주소를 지정 하는 `CORDB_ADDRESS` 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a13a0-106">[out] A pointer to a `CORDB_ADDRESS` value that specifies the address of the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a13a0-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a13a0-107">Requirements</span></span>  
 <span data-ttu-id="a13a0-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a13a0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a13a0-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a13a0-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a13a0-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a13a0-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a13a0-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a13a0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
