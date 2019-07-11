---
title: GetNames 함수 (관리 되지 않는 API 참조)
description: GetNames 함수 개체의 속성 이름을 검색합니다.
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
ms.openlocfilehash: e75bf9aab820216373f2f33fe8aa567f10befcb1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746523"
---
# <a name="getnames-function"></a><span data-ttu-id="6ef64-103">GetNames 함수</span><span class="sxs-lookup"><span data-stu-id="6ef64-103">GetNames function</span></span>
<span data-ttu-id="6ef64-104">개체 속성의 하위 집합 또는 모든 이름을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-104">Retrieves either a subset or all of the names of the properties of an object.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="6ef64-105">구문</span><span class="sxs-lookup"><span data-stu-id="6ef64-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="6ef64-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6ef64-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="6ef64-107">[in] 이 매개 변수 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="6ef64-108">[in] 에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="6ef64-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszQualifierName`  
<span data-ttu-id="6ef64-109">[in] 유효한 포인터 `LPCWSTR` 필터의 일부로 작동 하는 한정자 이름을 지정 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-109">[in] A pointer to a valid `LPCWSTR` that specifies a qualifier name that operates as part of a filter.</span></span> <span data-ttu-id="6ef64-110">자세한 내용은 참조는 [주의](#remarks) 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-110">For more information, see the [Remarks](#remarks) section.</span></span> <span data-ttu-id="6ef64-111">이 매개 변수는 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-111">This parameter can be `null`.</span></span> 

`lFlags`  
<span data-ttu-id="6ef64-112">[in] 비트 필드의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-112">[in] A combination of bit fields.</span></span> <span data-ttu-id="6ef64-113">자세한 내용은 참조는 [주의](#remarks) 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-113">For more information, see the [Remarks](#remarks) section.</span></span>

`pQualifierValue`   
<span data-ttu-id="6ef64-114">[in] 유효한 포인터 `VARIANT` 구조 필터 값으로 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-114">[in] A pointer to a valid `VARIANT` structure initialized to a filter value.</span></span> <span data-ttu-id="6ef64-115">이 매개 변수는 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-115">This parameter can be `null`.</span></span> 

`pstrNames`  
<span data-ttu-id="6ef64-116">[out] `SAFEARRAY` 속성 이름이 포함 된 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-116">[out] A `SAFEARRAY` structure that contains property names.</span></span> <span data-ttu-id="6ef64-117">항목에서이 매개 변수 여야에 대 한 포인터 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-117">On entry, this parameter must always be a pointer to `null`.</span></span> <span data-ttu-id="6ef64-118">참조 된 [주의](#remarks) 자세한 내용은 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-118">See the [Remarks](#remarks) section for more information.</span></span> 

## <a name="return-value"></a><span data-ttu-id="6ef64-119">반환 값</span><span class="sxs-lookup"><span data-stu-id="6ef64-119">Return value</span></span>

<span data-ttu-id="6ef64-120">이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="6ef64-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="6ef64-121">상수</span><span class="sxs-lookup"><span data-stu-id="6ef64-121">Constant</span></span>  |<span data-ttu-id="6ef64-122">값</span><span class="sxs-lookup"><span data-stu-id="6ef64-122">Value</span></span>  |<span data-ttu-id="6ef64-123">Description</span><span class="sxs-lookup"><span data-stu-id="6ef64-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="6ef64-124">0x80041001</span><span class="sxs-lookup"><span data-stu-id="6ef64-124">0x80041001</span></span> | <span data-ttu-id="6ef64-125">일반 오류가 발생이 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-125">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="6ef64-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="6ef64-126">0x80041008</span></span> | <span data-ttu-id="6ef64-127">하나 이상의 매개 변수가 잘못 된 경우 또는 플래그 및 매개 변수는 잘못 된 조합이 지정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-127">One or more parameters are not valid, or an incorrect combination of flags and parameters was specified.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="6ef64-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="6ef64-128">0x80041006</span></span> | <span data-ttu-id="6ef64-129">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-129">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="6ef64-130">0</span><span class="sxs-lookup"><span data-stu-id="6ef64-130">0</span></span> | <span data-ttu-id="6ef64-131">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-131">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="6ef64-132">설명</span><span class="sxs-lookup"><span data-stu-id="6ef64-132">Remarks</span></span>

<span data-ttu-id="6ef64-133">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) 메서드.</span><span class="sxs-lookup"><span data-stu-id="6ef64-133">This function wraps a call to the [IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) method.</span></span>

<span data-ttu-id="6ef64-134">명명 된 반환 매개 변수 및 플래그의 조합으로 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-134">The named returned are controlled by a combination of flags and parameters.</span></span> <span data-ttu-id="6ef64-135">예를 들어, 모든 속성의 이름 또는 키 속성의 이름만 함수가 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-135">For example, the function can return the names of all properties or only the names of the key properties.</span></span>  <span data-ttu-id="6ef64-136">기본 필터에 지정 된 된 `lFlags` 매개 변수 및 다른 매개 변수를 그에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-136">The primary filter is specified in the `lFlags` parameter, and the other parameters vary depending on it.</span></span>

<span data-ttu-id="6ef64-137">플래그 값 `lFlags` 는 비트 필드</span><span class="sxs-lookup"><span data-stu-id="6ef64-137">The flag values in `lFlags` are bit fields</span></span>

<span data-ttu-id="6ef64-138">로 전달 될 수 있는 플래그는 `lEnumFlags` 인수에 정의 된 비트 필드는 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드.</span><span class="sxs-lookup"><span data-stu-id="6ef64-138">The flags that can be passed as the `lEnumFlags` argument are bit fields that are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="6ef64-139">다른 그룹의 모든 플래그를 사용 하 여 각 그룹에서 하나 이상의 플래그를 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-139">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="6ef64-140">그러나 동일한 그룹의 플래그는 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-140">However, flags from the same group are mutually exclusive.</span></span> 

| <span data-ttu-id="6ef64-141">그룹 1 플래그</span><span class="sxs-lookup"><span data-stu-id="6ef64-141">Group 1 flags</span></span> |<span data-ttu-id="6ef64-142">값</span><span class="sxs-lookup"><span data-stu-id="6ef64-142">Value</span></span>  |<span data-ttu-id="6ef64-143">설명</span><span class="sxs-lookup"><span data-stu-id="6ef64-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | <span data-ttu-id="6ef64-144">0</span><span class="sxs-lookup"><span data-stu-id="6ef64-144">0</span></span> | <span data-ttu-id="6ef64-145">모든 속성 이름을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-145">Return all property names.</span></span> <span data-ttu-id="6ef64-146">`strQualifierName` 및 `pQualifierVal` 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-146">`strQualifierName` and `pQualifierVal` are unused.</span></span> |
| `WBEM_FLAG_ONLY_IF_TRUE` | <span data-ttu-id="6ef64-147">1</span><span class="sxs-lookup"><span data-stu-id="6ef64-147">1</span></span> | <span data-ttu-id="6ef64-148">지정 된 이름의 한정자가 있는 속성만 반환 합니다 `strQualifierName` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-148">Return only properties that have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="6ef64-149">이 플래그를 사용 하는 경우를 지정 해야 `strQualifierName`합니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-149">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_FALSE` | <span data-ttu-id="6ef64-150">2</span><span class="sxs-lookup"><span data-stu-id="6ef64-150">2</span></span> |  <span data-ttu-id="6ef64-151">지정 된 이름의 한정자를 갖지 않는 속성만 반환 합니다 `strQualifierName` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-151">Return only properties that do not have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="6ef64-152">이 플래그를 사용 하는 경우를 지정 해야 `strQualifierName`합니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-152">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | <span data-ttu-id="6ef64-153">3</span><span class="sxs-lookup"><span data-stu-id="6ef64-153">3</span></span> | <span data-ttu-id="6ef64-154">하 여 지정 된 이름의 한정자가 하는 속성만 반환 합니다 `wszQualifierName` 매개 변수 값에 지정 된 동일한 수도 있고는 `pQualifierVal` 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-154">Return only properties that have a qualifier of the name specified by the `wszQualifierName` parameter and also have a value identical to that specified by the `pQualifierVal` structure.</span></span> <span data-ttu-id="6ef64-155">이 플래그를 사용 하는 경우 둘 다 지정 해야 하는 `wszQualifierName` 및 `pQualifierValue`합니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-155">If this flag is used, you must specify both a `wszQualifierName` and a `pQualifierValue`.</span></span> |

| <span data-ttu-id="6ef64-156">그룹 2 플래그</span><span class="sxs-lookup"><span data-stu-id="6ef64-156">Group 2 flags</span></span> |<span data-ttu-id="6ef64-157">값</span><span class="sxs-lookup"><span data-stu-id="6ef64-157">Value</span></span>  |<span data-ttu-id="6ef64-158">설명</span><span class="sxs-lookup"><span data-stu-id="6ef64-158">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="6ef64-159">0x4</span><span class="sxs-lookup"><span data-stu-id="6ef64-159">0x4</span></span> | <span data-ttu-id="6ef64-160">키를 정의 하는 속성의 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-160">Return only the names of properties that define the keys.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="6ef64-161">0x8</span><span class="sxs-lookup"><span data-stu-id="6ef64-161">0x8</span></span> | <span data-ttu-id="6ef64-162">반환 속성 이름만 개체 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-162">Return only property names that are object references.</span></span> |

| <span data-ttu-id="6ef64-163">그룹 3 플래그</span><span class="sxs-lookup"><span data-stu-id="6ef64-163">Group 3 flags</span></span> |<span data-ttu-id="6ef64-164">값</span><span class="sxs-lookup"><span data-stu-id="6ef64-164">Value</span></span>  |<span data-ttu-id="6ef64-165">Description</span><span class="sxs-lookup"><span data-stu-id="6ef64-165">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="6ef64-166">0x10</span><span class="sxs-lookup"><span data-stu-id="6ef64-166">0x10</span></span> | <span data-ttu-id="6ef64-167">가장 많이 파생 된 클래스에 속하는 속성 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-167">Return only property names that belong to the most derived class.</span></span> <span data-ttu-id="6ef64-168">부모 클래스에서 속성을 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-168">Exclude properties from the parent classes.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="6ef64-169">0x20</span><span class="sxs-lookup"><span data-stu-id="6ef64-169">0x20</span></span> | <span data-ttu-id="6ef64-170">부모 클래스에 속하는 속성 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-170">Return only property names that belong to the parent classes.</span></span> |
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="6ef64-171">0x30</span><span class="sxs-lookup"><span data-stu-id="6ef64-171">0x30</span></span> | <span data-ttu-id="6ef64-172">시스템 속성의 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-172">Return only the names of system properties.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="6ef64-173">0x40</span><span class="sxs-lookup"><span data-stu-id="6ef64-173">0x40</span></span> | <span data-ttu-id="6ef64-174">비 시스템 속성의 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-174">Return only the names of non-system properties.</span></span> |

<span data-ttu-id="6ef64-175">함수는 항상 새 할당 `SAFEARRAY` 반환 `WBEM_S_NO_ERROR`, 및 `pstrNames` 항상 가리키도록로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-175">The function always allocates a new `SAFEARRAY` if it returns `WBEM_S_NO_ERROR`, and `pstrNames` is always set to point to it.</span></span> <span data-ttu-id="6ef64-176">속성이 지정 된 필터와 일치 하는 경우 반환된 된 배열의 0 요소를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-176">The returned array can have 0 elements if no properties match the specified filters.</span></span> <span data-ttu-id="6ef64-177">함수가 아닌 다른 값을 반환 하는 경우 `WBM_S_NO_ERROR`, 새 `SAFEARRAY` 구조 반환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ef64-177">If the function returns an value other than `WBM_S_NO_ERROR`, a new `SAFEARRAY` structure is not returned.</span></span>
 
## <a name="requirements"></a><span data-ttu-id="6ef64-178">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6ef64-178">Requirements</span></span>  
 <span data-ttu-id="6ef64-179">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6ef64-179">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ef64-180">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="6ef64-180">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="6ef64-181">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6ef64-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ef64-182">참고자료</span><span class="sxs-lookup"><span data-stu-id="6ef64-182">See also</span></span>

- [<span data-ttu-id="6ef64-183">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="6ef64-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
