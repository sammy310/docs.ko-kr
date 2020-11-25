---
title: QualifierSet_Next 함수 (관리 되지 않는 API 참조)
description: QualifierSet_Next 함수는 열거형의 다음 한정자를 검색 합니다.
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
ms.openlocfilehash: 54d79a3dc081e9cdcb42153b6f7aa457557e3399
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721129"
---
# <a name="qualifierset_next-function"></a><span data-ttu-id="704d6-103">QualifierSet_Next 함수</span><span class="sxs-lookup"><span data-stu-id="704d6-103">QualifierSet_Next function</span></span>

<span data-ttu-id="704d6-104">[QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) 함수를 호출하여 시작된 열거형의 다음 한정자를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="704d6-104">Retrieves the next qualifier in an enumeration that started with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="704d6-105">구문</span><span class="sxs-lookup"><span data-stu-id="704d6-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_Next (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags,
   [out] BSTR*               pstrName,
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor
);
```  

## <a name="parameters"></a><span data-ttu-id="704d6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="704d6-106">Parameters</span></span>

<span data-ttu-id="704d6-107">`vFunc` 진행 이 매개 변수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="704d6-107">`vFunc` [in] This parameter is unused.</span></span>

<span data-ttu-id="704d6-108">`ptr` 진행 [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="704d6-108">`ptr` [in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

<span data-ttu-id="704d6-109">`lFlags` 진행 쓰이는.</span><span class="sxs-lookup"><span data-stu-id="704d6-109">`lFlags` [in] Reserved.</span></span> <span data-ttu-id="704d6-110">이 매개 변수는 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="704d6-110">This parameter must be 0.</span></span>

<span data-ttu-id="704d6-111">`pstrName` 제한이 한정자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="704d6-111">`pstrName` [out] The name of the qualifier.</span></span> <span data-ttu-id="704d6-112">이면 `null` 이 매개 변수는 무시 되 고, 그렇지 않으면 `pstrName` 유효한를 가리키지 않거나 `BSTR` 메모리 누수가 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="704d6-112">If `null`, this parameter is ignored; otherwise, `pstrName` should not point to a valid `BSTR` or a memory leak occurs.</span></span> <span data-ttu-id="704d6-113">Null이 아닌 경우 함수는 `BSTR` 반환 될 때 항상 새를 할당 `WBEM_S_NO_ERROR` 합니다.</span><span class="sxs-lookup"><span data-stu-id="704d6-113">If not null, the function always allocates a new `BSTR` when it returns `WBEM_S_NO_ERROR`.</span></span>

<span data-ttu-id="704d6-114">`pVal` 제한이 성공 하면 한정자의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="704d6-114">`pVal` [out] When successful, the value for the qualifier.</span></span> <span data-ttu-id="704d6-115">함수가 실패 하면 `VARIANT` 에서 가리키는가 `pVal` 수정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="704d6-115">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="704d6-116">이 매개 변수가 이면 `null` 매개 변수는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="704d6-116">If this parameter is `null`, the parameter is ignored.</span></span>

<span data-ttu-id="704d6-117">`plFlavor` 제한이 한정자 버전을 받는 LONG에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="704d6-117">`plFlavor` [out] A pointer to a LONG that receives the qualifier flavor.</span></span> <span data-ttu-id="704d6-118">버전 정보를 원하지 않는 경우이 매개 변수는 일 수 있습니다 `null` .</span><span class="sxs-lookup"><span data-stu-id="704d6-118">If flavor information is not desired, this parameter can be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="704d6-119">반환 값</span><span class="sxs-lookup"><span data-stu-id="704d6-119">Return value</span></span>

<span data-ttu-id="704d6-120">이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="704d6-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="704d6-121">상수</span><span class="sxs-lookup"><span data-stu-id="704d6-121">Constant</span></span>  |<span data-ttu-id="704d6-122">값</span><span class="sxs-lookup"><span data-stu-id="704d6-122">Value</span></span>  |<span data-ttu-id="704d6-123">설명</span><span class="sxs-lookup"><span data-stu-id="704d6-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="704d6-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="704d6-124">0x80041008</span></span> | <span data-ttu-id="704d6-125">매개 변수가 잘못된 경우</span><span class="sxs-lookup"><span data-stu-id="704d6-125">A parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="704d6-126">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="704d6-126">0x8004101d</span></span> | <span data-ttu-id="704d6-127">호출자가 [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)를 호출 하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="704d6-127">The caller did not call [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="704d6-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="704d6-128">0x80041006</span></span> | <span data-ttu-id="704d6-129">메모리가 부족 하 여 새 열거를 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="704d6-129">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="704d6-130">0x40005</span><span class="sxs-lookup"><span data-stu-id="704d6-130">0x40005</span></span> | <span data-ttu-id="704d6-131">더 이상 한정자가 열거에 남아 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="704d6-131">No more qualifiers are left in the enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="704d6-132">0</span><span class="sxs-lookup"><span data-stu-id="704d6-132">0</span></span> | <span data-ttu-id="704d6-133">함수 호출에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="704d6-133">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="704d6-134">설명</span><span class="sxs-lookup"><span data-stu-id="704d6-134">Remarks</span></span>

<span data-ttu-id="704d6-135">이 함수는 [IWbemQualifierSet:: Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="704d6-135">This function wraps a call to the [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) method.</span></span>

<span data-ttu-id="704d6-136">함수가 `QualifierSet_Next` 반환 될 때까지 함수를 반복적으로 호출 하 여 모든 한정자를 열거 합니다 `WBEM_S_NO_MORE_DATA` .</span><span class="sxs-lookup"><span data-stu-id="704d6-136">You call the `QualifierSet_Next` function repeatedly to enumerate all the qualifiers until the function return `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="704d6-137">열거를 조기에 종료 하려면 [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="704d6-137">To terminate the enumeration early, call the [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) function.</span></span>

<span data-ttu-id="704d6-138">열거 하는 동안 반환 되는 한정자의 순서는 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="704d6-138">The order of the qualifiers returned during the enumeration is undefined.</span></span>

## <a name="requirements"></a><span data-ttu-id="704d6-139">요구 사항</span><span class="sxs-lookup"><span data-stu-id="704d6-139">Requirements</span></span>  

 <span data-ttu-id="704d6-140">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="704d6-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="704d6-141">**헤더:** WMINet_Utils idl</span><span class="sxs-lookup"><span data-stu-id="704d6-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="704d6-142">**.NET Framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="704d6-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="704d6-143">참조</span><span class="sxs-lookup"><span data-stu-id="704d6-143">See also</span></span>

- [<span data-ttu-id="704d6-144">WMI 및 성능 카운터(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="704d6-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
