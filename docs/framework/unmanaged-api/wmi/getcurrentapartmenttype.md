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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59181443"
---
# <a name="getcurrentapartmenttype-function"></a><span data-ttu-id="3dbfd-103">GetCurrentApartmentType 함수</span><span class="sxs-lookup"><span data-stu-id="3dbfd-103">GetCurrentApartmentType function</span></span>
<span data-ttu-id="3dbfd-104">호출자가 실행 중인 아파트의 유형을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbfd-104">Retrieves the type of apartment in which the caller is executing.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="3dbfd-105">구문</span><span class="sxs-lookup"><span data-stu-id="3dbfd-105">Syntax</span></span>  
  
```  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc, 
   [in] IComThreadingInfo*    ptr, 
   [out] APTTYPE*             aptType
); 
```  

## <a name="parameters"></a><span data-ttu-id="3dbfd-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3dbfd-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="3dbfd-107">[in] 이 매개 변수 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3dbfd-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="3dbfd-108">[in] 에 대 한 포인터를 [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="3dbfd-108">[in] A pointer to an [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) instance.</span></span>

`aptType`  
<span data-ttu-id="3dbfd-109">[out] 에 대 한 포인터를 [APTTYPE](/windows/desktop/api/objidlbase/ne-objidlbase-_apttype) 호출자의 아파트를 나타내는 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3dbfd-109">[out] A pointer to an [APTTYPE](/windows/desktop/api/objidlbase/ne-objidlbase-_apttype) enumeration value that indicates the caller's apartment.</span></span>

## <a name="return-value"></a><span data-ttu-id="3dbfd-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="3dbfd-110">Return value</span></span>

|<span data-ttu-id="3dbfd-111">상수</span><span class="sxs-lookup"><span data-stu-id="3dbfd-111">Constant</span></span>  |<span data-ttu-id="3dbfd-112">값</span><span class="sxs-lookup"><span data-stu-id="3dbfd-112">Value</span></span>  |<span data-ttu-id="3dbfd-113">설명</span><span class="sxs-lookup"><span data-stu-id="3dbfd-113">Description</span></span>  |
|---------|---------|---------|
| `S_OK` | <span data-ttu-id="3dbfd-114">0</span><span class="sxs-lookup"><span data-stu-id="3dbfd-114">0</span></span> | <span data-ttu-id="3dbfd-115">함수는 성공적으로 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3dbfd-115">The function completed successfully.</span></span> |
| `E_FAIL` | <span data-ttu-id="3dbfd-116">0x80000008</span><span class="sxs-lookup"><span data-stu-id="3dbfd-116">0x80000008</span></span> | <span data-ttu-id="3dbfd-117">호출자는 아파트에서 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3dbfd-117">The caller is not executing in an apartment.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="3dbfd-118">설명</span><span class="sxs-lookup"><span data-stu-id="3dbfd-118">Remarks</span></span>

<span data-ttu-id="3dbfd-119">이 함수에 대 한 호출을 래핑하는 [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) 메서드.</span><span class="sxs-lookup"><span data-stu-id="3dbfd-119">This function wraps a call to the [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="3dbfd-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3dbfd-120">Requirements</span></span>  
 <span data-ttu-id="3dbfd-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3dbfd-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3dbfd-122">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="3dbfd-122">**Header:** WMINet_Utils.idl</span></span>  
  
 **<span data-ttu-id="3dbfd-123">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="3dbfd-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3dbfd-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="3dbfd-124">See also</span></span>

- [<span data-ttu-id="3dbfd-125">WMI 및 성능 카운터(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="3dbfd-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
