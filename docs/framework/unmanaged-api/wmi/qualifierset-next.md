---
title: QualifierSet_Next 함수 (관리 되지 않는 API 참조)
description: QualifierSet_Next 함수 열거형의 다음 한정자를 검색합니다.
ms.date: 11/06/2017
api_name:
- QualifierSet_Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Next
helpviewer_keywords:
- QualifierSet_Next function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e8b96957467b0acb100f7eea137b3294a60e208a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000196"
---
# <a name="qualifiersetnext-function"></a><span data-ttu-id="a4111-103">QualifierSet_Next 함수</span><span class="sxs-lookup"><span data-stu-id="a4111-103">QualifierSet_Next function</span></span>
<span data-ttu-id="a4111-104">[QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) 함수를 호출하여 시작된 열거형의 다음 한정자를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="a4111-104">Retrieves the next qualifier in an enumeration that started with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>   

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="a4111-105">구문</span><span class="sxs-lookup"><span data-stu-id="a4111-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_Next (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags,
   [out] BSTR*               pstrName,        
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor                 
); 
```  

## <a name="parameters"></a><span data-ttu-id="a4111-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a4111-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="a4111-107">[in] 이 매개 변수 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4111-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="a4111-108">[in] 에 대 한 포인터를 [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="a4111-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`   
<span data-ttu-id="a4111-109">[in] 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4111-109">[in] Reserved.</span></span> <span data-ttu-id="a4111-110">이 매개 변수는 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4111-110">This parameter must be 0.</span></span>

`pstrName`   
<span data-ttu-id="a4111-111">[out] 한정자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a4111-111">[out] The name of the qualifier.</span></span> <span data-ttu-id="a4111-112">하는 경우 `null`,이 매개 변수는 무시 되 고, 그렇지 않으면 `pstrName` 유효한 가리키지 해야 `BSTR` 또는 메모리 누수가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4111-112">If `null`, this parameter is ignored; otherwise, `pstrName` should not point to a valid `BSTR` or a memory leak occurs.</span></span> <span data-ttu-id="a4111-113">Null이 아닌 함수 항상 할당 하는 새 `BSTR` 반환 하는 경우 `WBEM_S_NO_ERROR`합니다.</span><span class="sxs-lookup"><span data-stu-id="a4111-113">If not null, the function always allocates a new `BSTR` when it returns `WBEM_S_NO_ERROR`.</span></span>

`pVal`   
<span data-ttu-id="a4111-114">[out] 성공 하면 한정자의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a4111-114">[out] When successful, the value for the qualifier.</span></span> <span data-ttu-id="a4111-115">함수가 실패 한 경우는 `VARIANT` 가리키는 `pVal` 수정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4111-115">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="a4111-116">이 매개 변수가 `null`, 매개 변수는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4111-116">If this parameter is `null`, the parameter is ignored.</span></span>

`plFlavor`   
<span data-ttu-id="a4111-117">[out] 긴 한정자 버전을 수신 하는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a4111-117">[out] A pointer to a LONG that receives the qualifier flavor.</span></span> <span data-ttu-id="a4111-118">버전 정보는 적절 하지 않으면이 매개 변수 수 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="a4111-118">If flavor information is not desired, this parameter can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="a4111-119">반환 값</span><span class="sxs-lookup"><span data-stu-id="a4111-119">Return value</span></span>

<span data-ttu-id="a4111-120">이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="a4111-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="a4111-121">상수</span><span class="sxs-lookup"><span data-stu-id="a4111-121">Constant</span></span>  |<span data-ttu-id="a4111-122">값</span><span class="sxs-lookup"><span data-stu-id="a4111-122">Value</span></span>  |<span data-ttu-id="a4111-123">설명</span><span class="sxs-lookup"><span data-stu-id="a4111-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="a4111-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="a4111-124">0x80041008</span></span> | <span data-ttu-id="a4111-125">매개 변수가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a4111-125">A parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="a4111-126">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="a4111-126">0x8004101d</span></span> | <span data-ttu-id="a4111-127">호출자에 게 호출 하지 않았습니다 [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a4111-127">The caller did not call [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="a4111-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="a4111-128">0x80041006</span></span> | <span data-ttu-id="a4111-129">새 열거형 시작에 사용할 있는 메모리가 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4111-129">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="a4111-130">0x40005</span><span class="sxs-lookup"><span data-stu-id="a4111-130">0x40005</span></span> | <span data-ttu-id="a4111-131">한정자가 자세한 열거형에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4111-131">No more qualifiers are left in the enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="a4111-132">0</span><span class="sxs-lookup"><span data-stu-id="a4111-132">0</span></span> | <span data-ttu-id="a4111-133">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a4111-133">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="a4111-134">설명</span><span class="sxs-lookup"><span data-stu-id="a4111-134">Remarks</span></span>

<span data-ttu-id="a4111-135">이 함수에 대 한 호출을 래핑하는 [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) 메서드.</span><span class="sxs-lookup"><span data-stu-id="a4111-135">This function wraps a call to the [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) method.</span></span>

<span data-ttu-id="a4111-136">호출 된 `QualifierSet_Next` 함수는 반환 될 때까지 모든 한정자 열거를 반복적으로 `WBEM_S_NO_MORE_DATA`입니다.</span><span class="sxs-lookup"><span data-stu-id="a4111-136">You call the `QualifierSet_Next` function repeatedly to enumerate all the qualifiers until the function return `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="a4111-137">열거형을 조기에 종료를 호출 합니다 [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="a4111-137">To terminate the enumeration early, call the [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) function.</span></span>

<span data-ttu-id="a4111-138">열거 동안 반환 되는 한정자가 순서 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4111-138">The order of the qualifiers returned during the enumeration is undefined.</span></span>

## <a name="requirements"></a><span data-ttu-id="a4111-139">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a4111-139">Requirements</span></span>  
 <span data-ttu-id="a4111-140">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a4111-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4111-141">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="a4111-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="a4111-142">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a4111-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4111-143">참고자료</span><span class="sxs-lookup"><span data-stu-id="a4111-143">See also</span></span>

- [<span data-ttu-id="a4111-144">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="a4111-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
