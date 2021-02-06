---
description: '자세히 알아보기: ICorDebugType:: GetFirstTypeParameter 메서드'
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
ms.openlocfilehash: 4c37217f34f80c916d618d88e4917eab794a1d90
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658284"
---
# <a name="icordebugtypegetfirsttypeparameter-method"></a><span data-ttu-id="a38e7-103">ICorDebugType::GetFirstTypeParameter 메서드</span><span class="sxs-lookup"><span data-stu-id="a38e7-103">ICorDebugType::GetFirstTypeParameter Method</span></span>

<span data-ttu-id="a38e7-104"><xref:System.Type>이가 나타내는 형식의 첫 번째 매개 변수를 나타내는 ICorDebugType에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="a38e7-104">Gets an interface pointer to an ICorDebugType that represents the first <xref:System.Type> parameter of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a38e7-105">구문</span><span class="sxs-lookup"><span data-stu-id="a38e7-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFirstTypeParameter (  
    [out] ICorDebugType   **value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a38e7-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a38e7-106">Parameters</span></span>  

 `value`  
 <span data-ttu-id="a38e7-107">제한이 `ICorDebugType` 첫 번째 매개 변수를 나타내는 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a38e7-107">[out] A pointer to the address of an `ICorDebugType` object that represents the first parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a38e7-108">설명</span><span class="sxs-lookup"><span data-stu-id="a38e7-108">Remarks</span></span>  

 <span data-ttu-id="a38e7-109">`GetFirstTypeParameter` 형식에 대 한 추가 정보가 최대 하나의 형식 매개 변수를 포함 하는 경우를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a38e7-109">`GetFirstTypeParameter` can be called in cases where the additional information about the type involves, at most, one type parameter.</span></span> <span data-ttu-id="a38e7-110">특히 [ICorDebugType:: GetType](icordebugtype-gettype-method.md) 메서드로 표시 된 것 처럼 형식이 ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF 또는 ELEMENT_TYPE_PTR 인 경우에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a38e7-110">In particular, it can be used if the type is an ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR, as indicated by the [ICorDebugType::GetType](icordebugtype-gettype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a38e7-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a38e7-111">Requirements</span></span>  

 <span data-ttu-id="a38e7-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a38e7-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a38e7-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a38e7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a38e7-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a38e7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a38e7-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a38e7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
