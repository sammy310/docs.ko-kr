---
title: GetNames 함수 (관리 되지 않는 API 참조)
description: GetNames 함수는 개체의 속성 이름을 검색 합니다.
ms.date: 11/06/2017
api_name:
- GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetNames
helpviewer_keywords:
- GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 748767596a8f4680a2d7b63cb0579acaed5f53f8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798519"
---
# <a name="getnames-function"></a><span data-ttu-id="59324-103">GetNames 함수</span><span class="sxs-lookup"><span data-stu-id="59324-103">GetNames function</span></span>
<span data-ttu-id="59324-104">개체 속성의 하위 집합 또는 모든 이름을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="59324-104">Retrieves either a subset or all of the names of the properties of an object.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="59324-105">구문</span><span class="sxs-lookup"><span data-stu-id="59324-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNames (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszQualifierName,
   [in] LONG                lFlags,
   [in] VARIANT*            pQualifierValue,
   [out] SAFEARRAY (BSTR)** pstrNames
); 
```  

## <a name="parameters"></a><span data-ttu-id="59324-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="59324-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="59324-107">진행 이 매개 변수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59324-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="59324-108">진행 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="59324-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszQualifierName`  
<span data-ttu-id="59324-109">진행 필터의 일부로 작동 하 `LPCWSTR` 는 한정자 이름을 지정 하는 유효한에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="59324-109">[in] A pointer to a valid `LPCWSTR` that specifies a qualifier name that operates as part of a filter.</span></span> <span data-ttu-id="59324-110">자세한 내용은 [설명](#remarks) 부분을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="59324-110">For more information, see the [Remarks](#remarks) section.</span></span> <span data-ttu-id="59324-111">이 매개 변수는 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59324-111">This parameter can be `null`.</span></span> 

`lFlags`  
<span data-ttu-id="59324-112">진행 비트 필드의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="59324-112">[in] A combination of bit fields.</span></span> <span data-ttu-id="59324-113">자세한 내용은 [설명](#remarks) 부분을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="59324-113">For more information, see the [Remarks](#remarks) section.</span></span>

`pQualifierValue`   
<span data-ttu-id="59324-114">진행 필터 값으로 초기화 된 `VARIANT` 유효한 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="59324-114">[in] A pointer to a valid `VARIANT` structure initialized to a filter value.</span></span> <span data-ttu-id="59324-115">이 매개 변수는 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59324-115">This parameter can be `null`.</span></span> 

`pstrNames`  
<span data-ttu-id="59324-116">제한이 속성 이름을 포함 하는 구조체입니다.`SAFEARRAY`</span><span class="sxs-lookup"><span data-stu-id="59324-116">[out] A `SAFEARRAY` structure that contains property names.</span></span> <span data-ttu-id="59324-117">항목에서이 매개 변수는 항상에 대 `null`한 포인터 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59324-117">On entry, this parameter must always be a pointer to `null`.</span></span> <span data-ttu-id="59324-118">자세한 내용은 [설명](#remarks) 부분을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="59324-118">See the [Remarks](#remarks) section for more information.</span></span> 

## <a name="return-value"></a><span data-ttu-id="59324-119">반환 값</span><span class="sxs-lookup"><span data-stu-id="59324-119">Return value</span></span>

<span data-ttu-id="59324-120">이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59324-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="59324-121">상수</span><span class="sxs-lookup"><span data-stu-id="59324-121">Constant</span></span>  |<span data-ttu-id="59324-122">값</span><span class="sxs-lookup"><span data-stu-id="59324-122">Value</span></span>  |<span data-ttu-id="59324-123">설명</span><span class="sxs-lookup"><span data-stu-id="59324-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="59324-124">0x80041001</span><span class="sxs-lookup"><span data-stu-id="59324-124">0x80041001</span></span> | <span data-ttu-id="59324-125">일반 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="59324-125">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="59324-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="59324-126">0x80041008</span></span> | <span data-ttu-id="59324-127">하나 이상의 매개 변수가 유효 하지 않거나 잘못 된 플래그와 매개 변수 조합이 지정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="59324-127">One or more parameters are not valid, or an incorrect combination of flags and parameters was specified.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="59324-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="59324-128">0x80041006</span></span> | <span data-ttu-id="59324-129">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="59324-129">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="59324-130">0</span><span class="sxs-lookup"><span data-stu-id="59324-130">0</span></span> | <span data-ttu-id="59324-131">함수 호출에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="59324-131">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="59324-132">설명</span><span class="sxs-lookup"><span data-stu-id="59324-132">Remarks</span></span>

<span data-ttu-id="59324-133">이 함수는 [IWbemClassObject:: GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="59324-133">This function wraps a call to the [IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) method.</span></span>

<span data-ttu-id="59324-134">반환 된 이름은 플래그와 매개 변수를 조합 하 여 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59324-134">The named returned are controlled by a combination of flags and parameters.</span></span> <span data-ttu-id="59324-135">예를 들어 함수는 모든 속성의 이름이 나 키 속성의 이름만 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59324-135">For example, the function can return the names of all properties or only the names of the key properties.</span></span>  <span data-ttu-id="59324-136">기본 필터는 `lFlags` 매개 변수에서 지정 되 고 다른 매개 변수는이에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="59324-136">The primary filter is specified in the `lFlags` parameter, and the other parameters vary depending on it.</span></span>

<span data-ttu-id="59324-137">의 `lFlags` 플래그 값은 비트 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="59324-137">The flag values in `lFlags` are bit fields</span></span>

<span data-ttu-id="59324-138">`lEnumFlags` 인수로 전달 될 수 있는 플래그는 *WbemCli* 헤더 파일에 정의 된 비트 필드 이거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59324-138">The flags that can be passed as the `lEnumFlags` argument are bit fields that are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="59324-139">각 그룹의 플래그 하나를 다른 모든 그룹의 플래그와 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59324-139">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="59324-140">그러나 같은 그룹의 플래그는 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="59324-140">However, flags from the same group are mutually exclusive.</span></span> 

| <span data-ttu-id="59324-141">그룹 1 플래그</span><span class="sxs-lookup"><span data-stu-id="59324-141">Group 1 flags</span></span> |<span data-ttu-id="59324-142">값</span><span class="sxs-lookup"><span data-stu-id="59324-142">Value</span></span>  |<span data-ttu-id="59324-143">설명</span><span class="sxs-lookup"><span data-stu-id="59324-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | <span data-ttu-id="59324-144">0</span><span class="sxs-lookup"><span data-stu-id="59324-144">0</span></span> | <span data-ttu-id="59324-145">모든 속성 이름을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="59324-145">Return all property names.</span></span> <span data-ttu-id="59324-146">`strQualifierName`및 `pQualifierVal` 는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59324-146">`strQualifierName` and `pQualifierVal` are unused.</span></span> |
| `WBEM_FLAG_ONLY_IF_TRUE` | <span data-ttu-id="59324-147">1</span><span class="sxs-lookup"><span data-stu-id="59324-147">1</span></span> | <span data-ttu-id="59324-148">`strQualifierName` 매개 변수로 지정 된 이름의 한정자가 있는 속성만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="59324-148">Return only properties that have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="59324-149">이 플래그를 사용 하는 경우를 지정 `strQualifierName`해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59324-149">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_FALSE` | <span data-ttu-id="59324-150">2</span><span class="sxs-lookup"><span data-stu-id="59324-150">2</span></span> |  <span data-ttu-id="59324-151">`strQualifierName` 매개 변수로 지정 된 이름의 한정자가 없는 속성만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="59324-151">Return only properties that do not have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="59324-152">이 플래그를 사용 하는 경우를 지정 `strQualifierName`해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59324-152">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | <span data-ttu-id="59324-153">3</span><span class="sxs-lookup"><span data-stu-id="59324-153">3</span></span> | <span data-ttu-id="59324-154">매개 변수로 지정 된 이름의 한정자가 있고 `wszQualifierName` `pQualifierVal` 구조체에 지정 된 값과 동일한 속성만 반환 하는 속성을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="59324-154">Return only properties that have a qualifier of the name specified by the `wszQualifierName` parameter and also have a value identical to that specified by the `pQualifierVal` structure.</span></span> <span data-ttu-id="59324-155">이 플래그를 사용 하는 경우 `wszQualifierName` `pQualifierValue`및를 모두 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59324-155">If this flag is used, you must specify both a `wszQualifierName` and a `pQualifierValue`.</span></span> |

| <span data-ttu-id="59324-156">그룹 2 플래그</span><span class="sxs-lookup"><span data-stu-id="59324-156">Group 2 flags</span></span> |<span data-ttu-id="59324-157">값</span><span class="sxs-lookup"><span data-stu-id="59324-157">Value</span></span>  |<span data-ttu-id="59324-158">설명</span><span class="sxs-lookup"><span data-stu-id="59324-158">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="59324-159">0x4</span><span class="sxs-lookup"><span data-stu-id="59324-159">0x4</span></span> | <span data-ttu-id="59324-160">키를 정의 하는 속성의 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="59324-160">Return only the names of properties that define the keys.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="59324-161">0x8</span><span class="sxs-lookup"><span data-stu-id="59324-161">0x8</span></span> | <span data-ttu-id="59324-162">개체 참조 인 속성 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="59324-162">Return only property names that are object references.</span></span> |

| <span data-ttu-id="59324-163">그룹 3 플래그</span><span class="sxs-lookup"><span data-stu-id="59324-163">Group 3 flags</span></span> |<span data-ttu-id="59324-164">값</span><span class="sxs-lookup"><span data-stu-id="59324-164">Value</span></span>  |<span data-ttu-id="59324-165">Description</span><span class="sxs-lookup"><span data-stu-id="59324-165">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="59324-166">0x10</span><span class="sxs-lookup"><span data-stu-id="59324-166">0x10</span></span> | <span data-ttu-id="59324-167">가장 많이 파생 된 클래스에 속하는 속성 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="59324-167">Return only property names that belong to the most derived class.</span></span> <span data-ttu-id="59324-168">부모 클래스에서 속성을 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="59324-168">Exclude properties from the parent classes.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="59324-169">0x20</span><span class="sxs-lookup"><span data-stu-id="59324-169">0x20</span></span> | <span data-ttu-id="59324-170">부모 클래스에 속하는 속성 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="59324-170">Return only property names that belong to the parent classes.</span></span> |
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="59324-171">0x30</span><span class="sxs-lookup"><span data-stu-id="59324-171">0x30</span></span> | <span data-ttu-id="59324-172">시스템 속성의 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="59324-172">Return only the names of system properties.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="59324-173">0x40</span><span class="sxs-lookup"><span data-stu-id="59324-173">0x40</span></span> | <span data-ttu-id="59324-174">비시스템 속성의 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="59324-174">Return only the names of non-system properties.</span></span> |

<span data-ttu-id="59324-175">함수는를 반환 `SAFEARRAY` `WBEM_S_NO_ERROR`하는 경우 항상 새를 할당 `pstrNames` 하 고 항상이를 가리키도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="59324-175">The function always allocates a new `SAFEARRAY` if it returns `WBEM_S_NO_ERROR`, and `pstrNames` is always set to point to it.</span></span> <span data-ttu-id="59324-176">지정 된 필터와 일치 하는 속성이 없을 경우 반환 된 배열의 요소는 0이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59324-176">The returned array can have 0 elements if no properties match the specified filters.</span></span> <span data-ttu-id="59324-177">함수가 이외의 `WBM_S_NO_ERROR`값을 반환 하는 경우에는 새 `SAFEARRAY` 구조체가 반환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59324-177">If the function returns an value other than `WBM_S_NO_ERROR`, a new `SAFEARRAY` structure is not returned.</span></span>
 
## <a name="requirements"></a><span data-ttu-id="59324-178">요구 사항</span><span class="sxs-lookup"><span data-stu-id="59324-178">Requirements</span></span>  
 <span data-ttu-id="59324-179">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="59324-179">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59324-180">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="59324-180">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="59324-181">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="59324-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59324-182">참고자료</span><span class="sxs-lookup"><span data-stu-id="59324-182">See also</span></span>

- [<span data-ttu-id="59324-183">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="59324-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
