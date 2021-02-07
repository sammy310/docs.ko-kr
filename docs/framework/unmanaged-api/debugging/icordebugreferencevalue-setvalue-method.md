---
description: '자세히 알아보기: ICorDebugReferenceValue:: SetValue 메서드'
title: ICorDebugReferenceValue::SetValue 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.SetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::SetValue
helpviewer_keywords:
- SetValue method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::SetValue method [.NET Framework debugging]
ms.assetid: 3d3f6eec-d772-401f-a028-1a2ecdc31e95
topic_type:
- apiref
ms.openlocfilehash: 44909962d2716ddb606d98a2f6b3804247c581cd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690914"
---
# <a name="icordebugreferencevaluesetvalue-method"></a><span data-ttu-id="6a6cf-103">ICorDebugReferenceValue::SetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="6a6cf-103">ICorDebugReferenceValue::SetValue Method</span></span>

<span data-ttu-id="6a6cf-104">지정 된 메모리 주소를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a6cf-104">Sets the specified memory address.</span></span> <span data-ttu-id="6a6cf-105">즉,이 메서드는 개체를 가리키도록이 ICorDebugReferenceValue를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a6cf-105">That is, this method sets this ICorDebugReferenceValue to point to an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a6cf-106">구문</span><span class="sxs-lookup"><span data-stu-id="6a6cf-106">Syntax</span></span>  
  
```cpp  
HRESULT SetValue (  
    [in] CORDB_ADDRESS    value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a6cf-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6a6cf-107">Parameters</span></span>  

 `value`  
 <span data-ttu-id="6a6cf-108">진행 `CORDB_ADDRESS` 이가 가리키는 개체의 주소를 지정 하는 값입니다 `ICorDebugReferenceValue` .</span><span class="sxs-lookup"><span data-stu-id="6a6cf-108">[in] A `CORDB_ADDRESS` value that specifies the address of the object to which this `ICorDebugReferenceValue` points.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a6cf-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6a6cf-109">Requirements</span></span>  

 <span data-ttu-id="6a6cf-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6a6cf-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a6cf-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6a6cf-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6a6cf-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a6cf-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a6cf-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a6cf-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
