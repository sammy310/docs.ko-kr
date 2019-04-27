---
title: ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3.GetCachedWinRTTypesForIIDs
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs method, [.NET Framework debugging]
- GetCachedWinRTTypesForIIDs method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 23682ca0-1bcf-48e6-996e-69f7ba337682
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed1d7ad95b7c8474121994d0f54557c1c36cb531
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61917378"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a><span data-ttu-id="42c7c-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs 메서드</span><span class="sxs-lookup"><span data-stu-id="42c7c-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs Method</span></span>
<span data-ttu-id="42c7c-103">캐시에 대 한 열거자를 가져옵니다 [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 형식은 응용 프로그램 도메인에서 해당 인터페이스 식별자 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="42c7c-103">Gets an enumerator for cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain based on their interface identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42c7c-104">구문</span><span class="sxs-lookup"><span data-stu-id="42c7c-104">Syntax</span></span>  
  
```  
HRESULT GetCachedWinRTTypesForIIDs (   
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42c7c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="42c7c-105">Parameters</span></span>  
 `cReqTypes`  
 <span data-ttu-id="42c7c-106">[in] 필요한 형식의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="42c7c-106">[in] The number of required types.</span></span>  
  
 `iidsToResolve`  
 <span data-ttu-id="42c7c-107">[in] 관리 되는 표현에 해당 하는 인터페이스 식별자를 포함 하는 배열에 대 한 포인터를 [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 검색할 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="42c7c-107">[in] A pointer to an array that contains the interface identifiers corresponding to the managed representations of the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types to be retrieved.</span></span>  
  
 `ppTypesEnum`  
 <span data-ttu-id="42c7c-108">[out] 캐시 된 열거 수 있도록 "ICorDebugTypeEnum" 인터페이스 개체의 주소에 대 한 포인터의 표현을 관리 합니다 [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 의 인터페이스 식별자에 따라 형식 검색 `iidsToResolve`합니다.</span><span class="sxs-lookup"><span data-stu-id="42c7c-108">[out] A pointer to the address of an "ICorDebugTypeEnum" interface object that allows enumeration of the cached managed representations of the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types retrieved, based on the interface identifiers in `iidsToResolve`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42c7c-109">설명</span><span class="sxs-lookup"><span data-stu-id="42c7c-109">Remarks</span></span>  
 <span data-ttu-id="42c7c-110">메서드를 특정 인터페이스 식별자에 대 한 정보를 검색 하지 못하는 경우 "ICorDebugTypeEnum" 컬렉션의 해당 항목은 형식이 `ELEMENT_TYPE_END` 데이터 검색 문제로 인해 오류 또는 `ELEMENT_TYPE_VOID` 알 수 없는 인터페이스에 대 한 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="42c7c-110">If the method fails to retrieve information for a specific interface identifier, the corresponding entry in the "ICorDebugTypeEnum" collection will have a type of `ELEMENT_TYPE_END` for errors due to data retrieval issues, or `ELEMENT_TYPE_VOID` for unknown interface identifiers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42c7c-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="42c7c-111">Requirements</span></span>  
 <span data-ttu-id="42c7c-112">**플랫폼:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42c7c-112">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="42c7c-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="42c7c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="42c7c-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42c7c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42c7c-115">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42c7c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42c7c-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="42c7c-116">See also</span></span>

- [<span data-ttu-id="42c7c-117">ICorDebugAppDomain3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="42c7c-117">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
