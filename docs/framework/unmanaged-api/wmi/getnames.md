---
title: GetNames 함수(관리되지 않는 API 참조)
description: GetNames 함수는 개체의 속성 이름을 검색합니다.
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
ms.openlocfilehash: 449f0ce9c291d4bbcad4947214e56ff46f55beed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174955"
---
# <a name="getnames-function"></a><span data-ttu-id="8f12c-103">GetNames 함수</span><span class="sxs-lookup"><span data-stu-id="8f12c-103">GetNames function</span></span>
<span data-ttu-id="8f12c-104">개체 속성의 하위 집합 또는 모든 이름을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-104">Retrieves either a subset or all of the names of the properties of an object.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="8f12c-105">구문</span><span class="sxs-lookup"><span data-stu-id="8f12c-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="8f12c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8f12c-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="8f12c-107">【인】 이 매개 변수는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="8f12c-108">【인】 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszQualifierName`  
<span data-ttu-id="8f12c-109">【인】 필터의 일부로 `LPCWSTR` 작동하는 한정자 이름을 지정하는 유효한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-109">[in] A pointer to a valid `LPCWSTR` that specifies a qualifier name that operates as part of a filter.</span></span> <span data-ttu-id="8f12c-110">자세한 내용은 [비고](#remarks) 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8f12c-110">For more information, see the [Remarks](#remarks) section.</span></span> <span data-ttu-id="8f12c-111">이 매개 변수는 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-111">This parameter can be `null`.</span></span>

`lFlags`  
<span data-ttu-id="8f12c-112">【인】 비트 필드의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-112">[in] A combination of bit fields.</span></span> <span data-ttu-id="8f12c-113">자세한 내용은 [비고](#remarks) 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8f12c-113">For more information, see the [Remarks](#remarks) section.</span></span>

<span data-ttu-id="8f12c-114">`pQualifierValue`【인】 필터 값으로 `VARIANT` 초기화된 유효한 구조에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-114">`pQualifierValue` [in] A pointer to a valid `VARIANT` structure initialized to a filter value.</span></span> <span data-ttu-id="8f12c-115">이 매개 변수는 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-115">This parameter can be `null`.</span></span>

`pstrNames`  
<span data-ttu-id="8f12c-116">【아웃】 속성 `SAFEARRAY` 이름을 포함하는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-116">[out] A `SAFEARRAY` structure that contains property names.</span></span> <span data-ttu-id="8f12c-117">항목에서 이 매개 변수는 항상 `null`에 대한 포인터여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-117">On entry, this parameter must always be a pointer to `null`.</span></span> <span data-ttu-id="8f12c-118">자세한 내용은 [비고](#remarks) 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8f12c-118">See the [Remarks](#remarks) section for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="8f12c-119">반환 값</span><span class="sxs-lookup"><span data-stu-id="8f12c-119">Return value</span></span>

<span data-ttu-id="8f12c-120">이 함수에서 반환되는 다음 값은 *WbemCli.h* 헤더 파일에 정의되거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="8f12c-121">지속적임</span><span class="sxs-lookup"><span data-stu-id="8f12c-121">Constant</span></span>  |<span data-ttu-id="8f12c-122">값</span><span class="sxs-lookup"><span data-stu-id="8f12c-122">Value</span></span>  |<span data-ttu-id="8f12c-123">Description</span><span class="sxs-lookup"><span data-stu-id="8f12c-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="8f12c-124">0x80041001</span><span class="sxs-lookup"><span data-stu-id="8f12c-124">0x80041001</span></span> | <span data-ttu-id="8f12c-125">일반적인 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-125">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="8f12c-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="8f12c-126">0x80041008</span></span> | <span data-ttu-id="8f12c-127">하나 이상의 매개 변수가 유효하지 않거나 플래그와 매개 변수의 잘못된 조합이 지정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-127">One or more parameters are not valid, or an incorrect combination of flags and parameters was specified.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="8f12c-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="8f12c-128">0x80041006</span></span> | <span data-ttu-id="8f12c-129">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-129">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="8f12c-130">0</span><span class="sxs-lookup"><span data-stu-id="8f12c-130">0</span></span> | <span data-ttu-id="8f12c-131">함수 호출이 성공했습니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-131">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="8f12c-132">설명</span><span class="sxs-lookup"><span data-stu-id="8f12c-132">Remarks</span></span>

<span data-ttu-id="8f12c-133">이 함수는 [IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-133">This function wraps a call to the [IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) method.</span></span>

<span data-ttu-id="8f12c-134">반환된 명명된 플래그와 매개 변수의 조합에 의해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-134">The named returned are controlled by a combination of flags and parameters.</span></span> <span data-ttu-id="8f12c-135">예를 들어 함수는 모든 속성의 이름 또는 키 속성의 이름만 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-135">For example, the function can return the names of all properties or only the names of the key properties.</span></span>  <span data-ttu-id="8f12c-136">기본 필터는 매개 `lFlags` 변수에 지정되고 다른 매개 변수는 매개 변수에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-136">The primary filter is specified in the `lFlags` parameter, and the other parameters vary depending on it.</span></span>

<span data-ttu-id="8f12c-137">플래그 `lFlags` 값은 비트 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-137">The flag values in `lFlags` are bit fields</span></span>

<span data-ttu-id="8f12c-138">`lEnumFlags` 인수로 전달될 수 있는 플래그는 *WbemCli.h* 헤더 파일에 정의된 비트 필드이거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-138">The flags that can be passed as the `lEnumFlags` argument are bit fields that are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="8f12c-139">각 그룹의 한 플래그를 다른 그룹의 모든 플래그와 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-139">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="8f12c-140">그러나 동일한 그룹의 플래그는 상호 배타적입니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-140">However, flags from the same group are mutually exclusive.</span></span>

| <span data-ttu-id="8f12c-141">그룹 1 플래그</span><span class="sxs-lookup"><span data-stu-id="8f12c-141">Group 1 flags</span></span> |<span data-ttu-id="8f12c-142">값</span><span class="sxs-lookup"><span data-stu-id="8f12c-142">Value</span></span>  |<span data-ttu-id="8f12c-143">Description</span><span class="sxs-lookup"><span data-stu-id="8f12c-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | <span data-ttu-id="8f12c-144">0</span><span class="sxs-lookup"><span data-stu-id="8f12c-144">0</span></span> | <span data-ttu-id="8f12c-145">모든 속성 이름을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-145">Return all property names.</span></span> <span data-ttu-id="8f12c-146">`strQualifierName``pQualifierVal` 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-146">`strQualifierName` and `pQualifierVal` are unused.</span></span> |
| `WBEM_FLAG_ONLY_IF_TRUE` | <span data-ttu-id="8f12c-147">1</span><span class="sxs-lookup"><span data-stu-id="8f12c-147">1</span></span> | <span data-ttu-id="8f12c-148">매개 변수에 의해 지정된 이름의 한정자가 있는 속성만 반환합니다. `strQualifierName`</span><span class="sxs-lookup"><span data-stu-id="8f12c-148">Return only properties that have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="8f12c-149">이 플래그를 사용하는 경우 `strQualifierName`을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-149">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_FALSE` | <span data-ttu-id="8f12c-150">2</span><span class="sxs-lookup"><span data-stu-id="8f12c-150">2</span></span> |  <span data-ttu-id="8f12c-151">매개 변수에 의해 지정된 이름의 한정자가 `strQualifierName` 없는 속성만 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-151">Return only properties that do not have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="8f12c-152">이 플래그를 사용하는 경우 `strQualifierName`을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-152">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | <span data-ttu-id="8f12c-153">3</span><span class="sxs-lookup"><span data-stu-id="8f12c-153">3</span></span> | <span data-ttu-id="8f12c-154">`wszQualifierName` 매개 변수에 의해 지정된 이름의 한정자가 있고 `pQualifierVal` 구조가 지정한 값과 동일한 값을 가진 속성만 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-154">Return only properties that have a qualifier of the name specified by the `wszQualifierName` parameter and also have a value identical to that specified by the `pQualifierVal` structure.</span></span> <span data-ttu-id="8f12c-155">이 플래그를 사용하는 경우 a와 `wszQualifierName` 를 `pQualifierValue`모두 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-155">If this flag is used, you must specify both a `wszQualifierName` and a `pQualifierValue`.</span></span> |

| <span data-ttu-id="8f12c-156">그룹 2 플래그</span><span class="sxs-lookup"><span data-stu-id="8f12c-156">Group 2 flags</span></span> |<span data-ttu-id="8f12c-157">값</span><span class="sxs-lookup"><span data-stu-id="8f12c-157">Value</span></span>  |<span data-ttu-id="8f12c-158">Description</span><span class="sxs-lookup"><span data-stu-id="8f12c-158">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="8f12c-159">0x4</span><span class="sxs-lookup"><span data-stu-id="8f12c-159">0x4</span></span> | <span data-ttu-id="8f12c-160">키를 정의하는 속성 이름만 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-160">Return only the names of properties that define the keys.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="8f12c-161">0x8</span><span class="sxs-lookup"><span data-stu-id="8f12c-161">0x8</span></span> | <span data-ttu-id="8f12c-162">개체 참조인 속성 이름만 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-162">Return only property names that are object references.</span></span> |

| <span data-ttu-id="8f12c-163">그룹 3 플래그</span><span class="sxs-lookup"><span data-stu-id="8f12c-163">Group 3 flags</span></span> |<span data-ttu-id="8f12c-164">값</span><span class="sxs-lookup"><span data-stu-id="8f12c-164">Value</span></span>  |<span data-ttu-id="8f12c-165">Description</span><span class="sxs-lookup"><span data-stu-id="8f12c-165">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="8f12c-166">0x10</span><span class="sxs-lookup"><span data-stu-id="8f12c-166">0x10</span></span> | <span data-ttu-id="8f12c-167">가장 파생된 클래스에 속하는 속성 이름만 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-167">Return only property names that belong to the most derived class.</span></span> <span data-ttu-id="8f12c-168">상위 클래스에서 속성을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-168">Exclude properties from the parent classes.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="8f12c-169">0x20</span><span class="sxs-lookup"><span data-stu-id="8f12c-169">0x20</span></span> | <span data-ttu-id="8f12c-170">상위 클래스에 속하는 속성 이름만 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-170">Return only property names that belong to the parent classes.</span></span> |
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="8f12c-171">0x30</span><span class="sxs-lookup"><span data-stu-id="8f12c-171">0x30</span></span> | <span data-ttu-id="8f12c-172">시스템 속성의 이름만 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-172">Return only the names of system properties.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="8f12c-173">0x40</span><span class="sxs-lookup"><span data-stu-id="8f12c-173">0x40</span></span> | <span data-ttu-id="8f12c-174">비시스템 속성의 이름만 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-174">Return only the names of non-system properties.</span></span> |

<span data-ttu-id="8f12c-175">함수는 반환하는 경우 `SAFEARRAY` `WBEM_S_NO_ERROR`항상 새 를 `pstrNames` 할당하고 항상 가리키도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-175">The function always allocates a new `SAFEARRAY` if it returns `WBEM_S_NO_ERROR`, and `pstrNames` is always set to point to it.</span></span> <span data-ttu-id="8f12c-176">반환된 배열에는 지정된 필터와 일치하는 속성이 없는 경우 0개의 요소가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-176">The returned array can have 0 elements if no properties match the specified filters.</span></span> <span data-ttu-id="8f12c-177">함수가 `WBM_S_NO_ERROR`이외의 값을 반환하면 새 `SAFEARRAY` 구조가 반환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f12c-177">If the function returns an value other than `WBM_S_NO_ERROR`, a new `SAFEARRAY` structure is not returned.</span></span>

## <a name="requirements"></a><span data-ttu-id="8f12c-178">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8f12c-178">Requirements</span></span>  
 <span data-ttu-id="8f12c-179">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8f12c-179">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f12c-180">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="8f12c-180">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="8f12c-181">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8f12c-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f12c-182">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8f12c-182">See also</span></span>

- [<span data-ttu-id="8f12c-183">WMI 및 성능 카운터(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="8f12c-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
