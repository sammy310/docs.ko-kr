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
ms.openlocfilehash: f8e92ec4f813e8810273a1514298d0739a3d2406
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179059"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a><span data-ttu-id="44243-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs 메서드</span><span class="sxs-lookup"><span data-stu-id="44243-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs Method</span></span>
<span data-ttu-id="44243-103">인터페이스 식별자를 기반으로 응용 프로그램 도메인에서 캐시된 Windows 런타임 형식에 대한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="44243-103">Gets an enumerator for cached Windows Runtime types in an application domain based on their interface identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44243-104">구문</span><span class="sxs-lookup"><span data-stu-id="44243-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypesForIIDs (
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44243-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="44243-105">Parameters</span></span>  
 `cReqTypes`  
 <span data-ttu-id="44243-106">【인】 필수 형식의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="44243-106">[in] The number of required types.</span></span>  
  
 `iidsToResolve`  
 <span data-ttu-id="44243-107">【인】 검색할 Windows 런타임 형식의 관리되는 표현에 해당하는 인터페이스 식별자가 포함된 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="44243-107">[in] A pointer to an array that contains the interface identifiers corresponding to the managed representations of the Windows Runtime types to be retrieved.</span></span>  
  
 `ppTypesEnum`  
 <span data-ttu-id="44243-108">【아웃】 `iidsToResolve`의 인터페이스 식별자를 기반으로 검색된 Windows 런타임 형식의 캐시된 관리되는 표현을 열거할 수 있는 "ICorDebugTypeEnum" 인터페이스 개체의 주소에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="44243-108">[out] A pointer to the address of an "ICorDebugTypeEnum" interface object that allows enumeration of the cached managed representations of the Windows Runtime types retrieved, based on the interface identifiers in `iidsToResolve`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44243-109">설명</span><span class="sxs-lookup"><span data-stu-id="44243-109">Remarks</span></span>  
 <span data-ttu-id="44243-110">메서드가 특정 인터페이스 식별자에 대한 정보를 검색하지 못하면 "ICorDebugTypeEnum" 컬렉션의 해당 `ELEMENT_TYPE_END` 항목에는 데이터 검색 문제 또는 `ELEMENT_TYPE_VOID` 알 수 없는 인터페이스 식별자로 인한 오류 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44243-110">If the method fails to retrieve information for a specific interface identifier, the corresponding entry in the "ICorDebugTypeEnum" collection will have a type of `ELEMENT_TYPE_END` for errors due to data retrieval issues, or `ELEMENT_TYPE_VOID` for unknown interface identifiers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44243-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="44243-111">Requirements</span></span>  
 <span data-ttu-id="44243-112">**플랫폼:** 윈도우 런타임</span><span class="sxs-lookup"><span data-stu-id="44243-112">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="44243-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="44243-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="44243-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44243-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44243-115">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44243-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44243-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="44243-116">See also</span></span>

- [<span data-ttu-id="44243-117">ICorDebugAppDomain3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="44243-117">ICorDebugAppDomain3 Interface</span></span>](icordebugappdomain3-interface.md)
