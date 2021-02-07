---
description: '자세히 알아보기: ICorDebugReferenceValue:: GetValue 메서드'
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
ms.openlocfilehash: 29e0c4997d3349b642381dcf69063de21c3f9330
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691023"
---
# <a name="icordebugreferencevaluegetvalue-method"></a><span data-ttu-id="be876-103">ICorDebugReferenceValue::GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="be876-103">ICorDebugReferenceValue::GetValue Method</span></span>

<span data-ttu-id="be876-104">참조 된 개체의 현재 메모리 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="be876-104">Gets the current memory address of the referenced object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be876-105">구문</span><span class="sxs-lookup"><span data-stu-id="be876-105">Syntax</span></span>  
  
```cpp  
HRESULT GetValue (  
    [out] CORDB_ADDRESS   *pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be876-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="be876-106">Parameters</span></span>  

 `pValue`  
 <span data-ttu-id="be876-107">제한이 `CORDB_ADDRESS` 이 ICorDebugReferenceValue 개체가 가리키는 개체의 주소를 지정 하는 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="be876-107">[out] A pointer to a `CORDB_ADDRESS` value that specifies the address of the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be876-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="be876-108">Requirements</span></span>  

 <span data-ttu-id="be876-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="be876-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be876-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="be876-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="be876-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be876-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be876-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be876-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
