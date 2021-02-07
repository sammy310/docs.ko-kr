---
description: '자세히 알아보기: ICorDebugAppDomain3:: GetCachedWinRTTypesForIIDs 메서드'
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
ms.openlocfilehash: 76b93cdb8c465935a4aaf36090ee44f2b6253a3b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754175"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a><span data-ttu-id="1e467-103">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs 메서드</span><span class="sxs-lookup"><span data-stu-id="1e467-103">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs Method</span></span>

<span data-ttu-id="1e467-104">인터페이스 식별자를 기반으로 응용 프로그램 도메인의 캐시 된 Windows 런타임 형식에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1e467-104">Gets an enumerator for cached Windows Runtime types in an application domain based on their interface identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e467-105">구문</span><span class="sxs-lookup"><span data-stu-id="1e467-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypesForIIDs (
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e467-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1e467-106">Parameters</span></span>  

 `cReqTypes`  
 <span data-ttu-id="1e467-107">진행 필요한 형식의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1e467-107">[in] The number of required types.</span></span>  
  
 `iidsToResolve`  
 <span data-ttu-id="1e467-108">진행 검색할 Windows 런타임 형식의 관리 되는 표현에 해당 하는 인터페이스 식별자가 포함 된 배열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1e467-108">[in] A pointer to an array that contains the interface identifiers corresponding to the managed representations of the Windows Runtime types to be retrieved.</span></span>  
  
 `ppTypesEnum`  
 <span data-ttu-id="1e467-109">제한이 의 인터페이스 식별자를 기반으로 검색 된 Windows 런타임 형식의 캐시 된 관리 표현을 열거할 수 있도록 하는 "ICorDebugTypeEnum" 인터페이스 개체의 주소에 대 한 포인터입니다 `iidsToResolve` .</span><span class="sxs-lookup"><span data-stu-id="1e467-109">[out] A pointer to the address of an "ICorDebugTypeEnum" interface object that allows enumeration of the cached managed representations of the Windows Runtime types retrieved, based on the interface identifiers in `iidsToResolve`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1e467-110">설명</span><span class="sxs-lookup"><span data-stu-id="1e467-110">Remarks</span></span>  

 <span data-ttu-id="1e467-111">메서드가 특정 인터페이스 식별자에 대 한 정보를 검색 하지 못할 경우, "ICorDebugTypeEnum" 컬렉션의 해당 항목에는 `ELEMENT_TYPE_END` 데이터 검색 문제로 인 한 오류의 형식이 나 `ELEMENT_TYPE_VOID` 알 수 없는 인터페이스 식별자가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e467-111">If the method fails to retrieve information for a specific interface identifier, the corresponding entry in the "ICorDebugTypeEnum" collection will have a type of `ELEMENT_TYPE_END` for errors due to data retrieval issues, or `ELEMENT_TYPE_VOID` for unknown interface identifiers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e467-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1e467-112">Requirements</span></span>  

 <span data-ttu-id="1e467-113">**플랫폼:** Windows 런타임</span><span class="sxs-lookup"><span data-stu-id="1e467-113">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="1e467-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1e467-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1e467-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e467-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1e467-116">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e467-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e467-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1e467-117">See also</span></span>

- [<span data-ttu-id="1e467-118">ICorDebugAppDomain3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1e467-118">ICorDebugAppDomain3 Interface</span></span>](icordebugappdomain3-interface.md)
