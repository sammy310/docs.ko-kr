---
title: 복제 함수 (관리 되지 않는 API 참조)
description: 복제 함수는 현재 전체 복제본 인 새 개체를 반환 합니다.
ms.date: 11/06/2017
api_name:
- Clone
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Clone
helpviewer_keywords:
- Clone function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf9cca10a580af7991889de6993e931347fc27ea
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61968157"
---
# <a name="clone-function"></a><span data-ttu-id="a53ec-103">Clone 함수</span><span class="sxs-lookup"><span data-stu-id="a53ec-103">Clone function</span></span>
<span data-ttu-id="a53ec-104">현재 개체의 전체 복제본인 새 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a53ec-104">Returns a new object that is a complete clone of the current object.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="a53ec-105">구문</span><span class="sxs-lookup"><span data-stu-id="a53ec-105">Syntax</span></span>  
  
```  
HRESULT Clone (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [out] IWbemClassObject**  ppCopy
); 
```  

## <a name="parameters"></a><span data-ttu-id="a53ec-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a53ec-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="a53ec-107">[in] 이 매개 변수 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a53ec-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="a53ec-108">[in] 에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="a53ec-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppCopy`  
<span data-ttu-id="a53ec-109">[out] 완료 된 새 개체의 유일한 `ptr`합니다.</span><span class="sxs-lookup"><span data-stu-id="a53ec-109">[out] A new object that is a complete lone of `ptr`.</span></span> <span data-ttu-id="a53ec-110">두이 일 수 없습니다 `null` 현재 개체의 복사본을 수신 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="a53ec-110">This argument cannot be `null` if it receives the copy of the current object.</span></span>

## <a name="return-value"></a><span data-ttu-id="a53ec-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="a53ec-111">Return value</span></span>

<span data-ttu-id="a53ec-112">이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="a53ec-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="a53ec-113">상수</span><span class="sxs-lookup"><span data-stu-id="a53ec-113">Constant</span></span>  |<span data-ttu-id="a53ec-114">값</span><span class="sxs-lookup"><span data-stu-id="a53ec-114">Value</span></span>  |<span data-ttu-id="a53ec-115">설명</span><span class="sxs-lookup"><span data-stu-id="a53ec-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="a53ec-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="a53ec-116">0x80041001</span></span> | <span data-ttu-id="a53ec-117">일반 오류가 발생이 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a53ec-117">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="a53ec-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="a53ec-118">0x80041008</span></span> | <span data-ttu-id="a53ec-119">`null` 매개 변수로 지정 된이 사용이 적합 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a53ec-119">`null` was specified as a parameter, and it is not legal in this usage.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="a53ec-120">0x80041006</span><span class="sxs-lookup"><span data-stu-id="a53ec-120">0x80041006</span></span> | <span data-ttu-id="a53ec-121">개체를 복제에 사용할 있는 메모리가 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a53ec-121">Not enough memory is available to clone the object.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="a53ec-122">0</span><span class="sxs-lookup"><span data-stu-id="a53ec-122">0</span></span> | <span data-ttu-id="a53ec-123">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a53ec-123">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="a53ec-124">설명</span><span class="sxs-lookup"><span data-stu-id="a53ec-124">Remarks</span></span>

<span data-ttu-id="a53ec-125">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) 메서드.</span><span class="sxs-lookup"><span data-stu-id="a53ec-125">This function wraps a call to the [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="a53ec-126">복제 된 개체는는 COM 개체에는 참조 횟수가 1입니다.</span><span class="sxs-lookup"><span data-stu-id="a53ec-126">The cloned object is a COM object that has a reference count of 1.</span></span>

## <a name="requirements"></a><span data-ttu-id="a53ec-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a53ec-127">Requirements</span></span>  
 <span data-ttu-id="a53ec-128">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a53ec-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a53ec-129">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="a53ec-129">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="a53ec-130">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a53ec-130">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a53ec-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="a53ec-131">See also</span></span>

- [<span data-ttu-id="a53ec-132">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="a53ec-132">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
