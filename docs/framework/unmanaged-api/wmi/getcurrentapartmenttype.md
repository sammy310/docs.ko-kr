---
title: GetCurrentApartmentType 함수 (관리 되지 않는 API 참조)
description: GetCurrentApartmentType 함수 호출자가 실행 하는 아파트의 형식을 검색 합니다.
ms.date: 11/06/2017
api_name:
- GetCurrentApartmentType
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetCurrentApartmentType
helpviewer_keywords:
- GetCurrentApartmentType function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ead1c1a91b910e7cfbb09f17ba823fc7a77ce0f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609011"
---
# <a name="getcurrentapartmenttype-function"></a><span data-ttu-id="c487b-103">GetCurrentApartmentType 함수</span><span class="sxs-lookup"><span data-stu-id="c487b-103">GetCurrentApartmentType function</span></span>
<span data-ttu-id="c487b-104">호출자가 실행 중인 아파트의 유형을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="c487b-104">Retrieves the type of apartment in which the caller is executing.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="c487b-105">구문</span><span class="sxs-lookup"><span data-stu-id="c487b-105">Syntax</span></span>  
  
```  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc, 
   [in] IComThreadingInfo*    ptr, 
   [out] APTTYPE*             aptType
); 
```  

## <a name="parameters"></a><span data-ttu-id="c487b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c487b-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="c487b-107">[in] 이 매개 변수 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c487b-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="c487b-108">[in] 에 대 한 포인터를 [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="c487b-108">[in] A pointer to an [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) instance.</span></span>

`aptType`  
<span data-ttu-id="c487b-109">[out] 에 대 한 포인터를 [APTTYPE](/windows/desktop/api/objidlbase/ne-objidlbase-_apttype) 호출자의 아파트를 나타내는 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c487b-109">[out] A pointer to an [APTTYPE](/windows/desktop/api/objidlbase/ne-objidlbase-_apttype) enumeration value that indicates the caller's apartment.</span></span>

## <a name="return-value"></a><span data-ttu-id="c487b-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="c487b-110">Return value</span></span>

|<span data-ttu-id="c487b-111">상수</span><span class="sxs-lookup"><span data-stu-id="c487b-111">Constant</span></span>  |<span data-ttu-id="c487b-112">값</span><span class="sxs-lookup"><span data-stu-id="c487b-112">Value</span></span>  |<span data-ttu-id="c487b-113">설명</span><span class="sxs-lookup"><span data-stu-id="c487b-113">Description</span></span>  |
|---------|---------|---------|
| `S_OK` | <span data-ttu-id="c487b-114">0</span><span class="sxs-lookup"><span data-stu-id="c487b-114">0</span></span> | <span data-ttu-id="c487b-115">함수는 성공적으로 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c487b-115">The function completed successfully.</span></span> |
| `E_FAIL` | <span data-ttu-id="c487b-116">0x80000008</span><span class="sxs-lookup"><span data-stu-id="c487b-116">0x80000008</span></span> | <span data-ttu-id="c487b-117">호출자는 아파트에서 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c487b-117">The caller is not executing in an apartment.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="c487b-118">설명</span><span class="sxs-lookup"><span data-stu-id="c487b-118">Remarks</span></span>

<span data-ttu-id="c487b-119">이 함수에 대 한 호출을 래핑하는 [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) 메서드.</span><span class="sxs-lookup"><span data-stu-id="c487b-119">This function wraps a call to the [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="c487b-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c487b-120">Requirements</span></span>  
 <span data-ttu-id="c487b-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c487b-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c487b-122">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="c487b-122">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="c487b-123">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c487b-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c487b-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="c487b-124">See also</span></span>

- [<span data-ttu-id="c487b-125">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="c487b-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
