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
ms.openlocfilehash: fd889158e61b86f42d88bcf86eda7d816277e6ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687660"
---
# <a name="getnames-function"></a><span data-ttu-id="fc2c2-103">GetNames 함수</span><span class="sxs-lookup"><span data-stu-id="fc2c2-103">GetNames function</span></span>

<span data-ttu-id="fc2c2-104">개체 속성의 하위 집합 또는 모든 이름을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-104">Retrieves either a subset or all of the names of the properties of an object.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="fc2c2-105">구문</span><span class="sxs-lookup"><span data-stu-id="fc2c2-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="fc2c2-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fc2c2-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="fc2c2-107">진행 이 매개 변수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="fc2c2-108">진행 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszQualifierName`  
<span data-ttu-id="fc2c2-109">진행 `LPCWSTR` 필터의 일부로 작동 하는 한정자 이름을 지정 하는 유효한에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-109">[in] A pointer to a valid `LPCWSTR` that specifies a qualifier name that operates as part of a filter.</span></span> <span data-ttu-id="fc2c2-110">자세한 내용은 [설명](#remarks) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-110">For more information, see the [Remarks](#remarks) section.</span></span> <span data-ttu-id="fc2c2-111">이 매개 변수는 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-111">This parameter can be `null`.</span></span>

`lFlags`  
<span data-ttu-id="fc2c2-112">진행 비트 필드의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-112">[in] A combination of bit fields.</span></span> <span data-ttu-id="fc2c2-113">자세한 내용은 [설명](#remarks) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-113">For more information, see the [Remarks](#remarks) section.</span></span>

<span data-ttu-id="fc2c2-114">`pQualifierValue` 진행 필터 값으로 초기화 된 유효한 구조체에 대 한 포인터 `VARIANT` 입니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-114">`pQualifierValue` [in] A pointer to a valid `VARIANT` structure initialized to a filter value.</span></span> <span data-ttu-id="fc2c2-115">이 매개 변수는 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-115">This parameter can be `null`.</span></span>

`pstrNames`  
<span data-ttu-id="fc2c2-116">제한이 `SAFEARRAY` 속성 이름을 포함 하는 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-116">[out] A `SAFEARRAY` structure that contains property names.</span></span> <span data-ttu-id="fc2c2-117">항목에서이 매개 변수는 항상에 대 한 포인터 여야 합니다 `null` .</span><span class="sxs-lookup"><span data-stu-id="fc2c2-117">On entry, this parameter must always be a pointer to `null`.</span></span> <span data-ttu-id="fc2c2-118">자세한 내용은 [설명](#remarks) 부분을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-118">See the [Remarks](#remarks) section for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="fc2c2-119">반환 값</span><span class="sxs-lookup"><span data-stu-id="fc2c2-119">Return value</span></span>

<span data-ttu-id="fc2c2-120">이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="fc2c2-121">상수</span><span class="sxs-lookup"><span data-stu-id="fc2c2-121">Constant</span></span>  |<span data-ttu-id="fc2c2-122">값</span><span class="sxs-lookup"><span data-stu-id="fc2c2-122">Value</span></span>  |<span data-ttu-id="fc2c2-123">설명</span><span class="sxs-lookup"><span data-stu-id="fc2c2-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="fc2c2-124">0x80041001</span><span class="sxs-lookup"><span data-stu-id="fc2c2-124">0x80041001</span></span> | <span data-ttu-id="fc2c2-125">일반 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-125">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="fc2c2-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="fc2c2-126">0x80041008</span></span> | <span data-ttu-id="fc2c2-127">하나 이상의 매개 변수가 유효 하지 않거나 잘못 된 플래그와 매개 변수 조합이 지정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-127">One or more parameters are not valid, or an incorrect combination of flags and parameters was specified.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="fc2c2-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="fc2c2-128">0x80041006</span></span> | <span data-ttu-id="fc2c2-129">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-129">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="fc2c2-130">0</span><span class="sxs-lookup"><span data-stu-id="fc2c2-130">0</span></span> | <span data-ttu-id="fc2c2-131">함수 호출에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-131">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="fc2c2-132">설명</span><span class="sxs-lookup"><span data-stu-id="fc2c2-132">Remarks</span></span>

<span data-ttu-id="fc2c2-133">이 함수는 [IWbemClassObject:: GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-133">This function wraps a call to the [IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) method.</span></span>

<span data-ttu-id="fc2c2-134">반환 된 이름은 플래그와 매개 변수를 조합 하 여 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-134">The named returned are controlled by a combination of flags and parameters.</span></span> <span data-ttu-id="fc2c2-135">예를 들어 함수는 모든 속성의 이름이 나 키 속성의 이름만 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-135">For example, the function can return the names of all properties or only the names of the key properties.</span></span>  <span data-ttu-id="fc2c2-136">기본 필터는 매개 변수에서 지정 되 `lFlags` 고 다른 매개 변수는이에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-136">The primary filter is specified in the `lFlags` parameter, and the other parameters vary depending on it.</span></span>

<span data-ttu-id="fc2c2-137">의 플래그 값은 `lFlags` 비트 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-137">The flag values in `lFlags` are bit fields</span></span>

<span data-ttu-id="fc2c2-138">인수로 전달 될 수 있는 플래그는 `lEnumFlags` *WbemCli* 헤더 파일에 정의 된 비트 필드 이거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-138">The flags that can be passed as the `lEnumFlags` argument are bit fields that are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="fc2c2-139">각 그룹의 플래그 하나를 다른 모든 그룹의 플래그와 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-139">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="fc2c2-140">그러나 같은 그룹의 플래그는 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-140">However, flags from the same group are mutually exclusive.</span></span>

| <span data-ttu-id="fc2c2-141">그룹 1 플래그</span><span class="sxs-lookup"><span data-stu-id="fc2c2-141">Group 1 flags</span></span> |<span data-ttu-id="fc2c2-142">값</span><span class="sxs-lookup"><span data-stu-id="fc2c2-142">Value</span></span>  |<span data-ttu-id="fc2c2-143">설명</span><span class="sxs-lookup"><span data-stu-id="fc2c2-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | <span data-ttu-id="fc2c2-144">0</span><span class="sxs-lookup"><span data-stu-id="fc2c2-144">0</span></span> | <span data-ttu-id="fc2c2-145">모든 속성 이름을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-145">Return all property names.</span></span> <span data-ttu-id="fc2c2-146">`strQualifierName` 및 `pQualifierVal` 는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-146">`strQualifierName` and `pQualifierVal` are unused.</span></span> |
| `WBEM_FLAG_ONLY_IF_TRUE` | <span data-ttu-id="fc2c2-147">1</span><span class="sxs-lookup"><span data-stu-id="fc2c2-147">1</span></span> | <span data-ttu-id="fc2c2-148">매개 변수로 지정 된 이름의 한정자가 있는 속성만 반환 `strQualifierName` 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-148">Return only properties that have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="fc2c2-149">이 플래그를 사용 하는 경우를 지정 해야 `strQualifierName` 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-149">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_FALSE` | <span data-ttu-id="fc2c2-150">2</span><span class="sxs-lookup"><span data-stu-id="fc2c2-150">2</span></span> |  <span data-ttu-id="fc2c2-151">매개 변수로 지정 된 이름의 한정자가 없는 속성만 반환 `strQualifierName` 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-151">Return only properties that do not have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="fc2c2-152">이 플래그를 사용 하는 경우를 지정 해야 `strQualifierName` 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-152">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | <span data-ttu-id="fc2c2-153">3</span><span class="sxs-lookup"><span data-stu-id="fc2c2-153">3</span></span> | <span data-ttu-id="fc2c2-154">매개 변수로 지정 된 이름의 한정자가 있고 구조체에 지정 된 값과 동일한 속성만 반환 하는 속성을 반환 합니다 `wszQualifierName` `pQualifierVal` .</span><span class="sxs-lookup"><span data-stu-id="fc2c2-154">Return only properties that have a qualifier of the name specified by the `wszQualifierName` parameter and also have a value identical to that specified by the `pQualifierVal` structure.</span></span> <span data-ttu-id="fc2c2-155">이 플래그를 사용 하는 경우 및를 모두 지정 해야 합니다 `wszQualifierName` `pQualifierValue` .</span><span class="sxs-lookup"><span data-stu-id="fc2c2-155">If this flag is used, you must specify both a `wszQualifierName` and a `pQualifierValue`.</span></span> |

| <span data-ttu-id="fc2c2-156">그룹 2 플래그</span><span class="sxs-lookup"><span data-stu-id="fc2c2-156">Group 2 flags</span></span> |<span data-ttu-id="fc2c2-157">값</span><span class="sxs-lookup"><span data-stu-id="fc2c2-157">Value</span></span>  |<span data-ttu-id="fc2c2-158">설명</span><span class="sxs-lookup"><span data-stu-id="fc2c2-158">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="fc2c2-159">0x4</span><span class="sxs-lookup"><span data-stu-id="fc2c2-159">0x4</span></span> | <span data-ttu-id="fc2c2-160">키를 정의 하는 속성의 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-160">Return only the names of properties that define the keys.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="fc2c2-161">0x8</span><span class="sxs-lookup"><span data-stu-id="fc2c2-161">0x8</span></span> | <span data-ttu-id="fc2c2-162">개체 참조 인 속성 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-162">Return only property names that are object references.</span></span> |

| <span data-ttu-id="fc2c2-163">그룹 3 플래그</span><span class="sxs-lookup"><span data-stu-id="fc2c2-163">Group 3 flags</span></span> |<span data-ttu-id="fc2c2-164">값</span><span class="sxs-lookup"><span data-stu-id="fc2c2-164">Value</span></span>  |<span data-ttu-id="fc2c2-165">설명</span><span class="sxs-lookup"><span data-stu-id="fc2c2-165">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="fc2c2-166">0x10</span><span class="sxs-lookup"><span data-stu-id="fc2c2-166">0x10</span></span> | <span data-ttu-id="fc2c2-167">가장 많이 파생 된 클래스에 속하는 속성 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-167">Return only property names that belong to the most derived class.</span></span> <span data-ttu-id="fc2c2-168">부모 클래스에서 속성을 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-168">Exclude properties from the parent classes.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="fc2c2-169">0x20</span><span class="sxs-lookup"><span data-stu-id="fc2c2-169">0x20</span></span> | <span data-ttu-id="fc2c2-170">부모 클래스에 속하는 속성 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-170">Return only property names that belong to the parent classes.</span></span> |
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="fc2c2-171">0x30</span><span class="sxs-lookup"><span data-stu-id="fc2c2-171">0x30</span></span> | <span data-ttu-id="fc2c2-172">시스템 속성의 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-172">Return only the names of system properties.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="fc2c2-173">0x40</span><span class="sxs-lookup"><span data-stu-id="fc2c2-173">0x40</span></span> | <span data-ttu-id="fc2c2-174">비시스템 속성의 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-174">Return only the names of non-system properties.</span></span> |

<span data-ttu-id="fc2c2-175">함수는를 반환 하는 경우 항상 새를 할당 하 `SAFEARRAY` `WBEM_S_NO_ERROR` 고 `pstrNames` 항상이를 가리키도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-175">The function always allocates a new `SAFEARRAY` if it returns `WBEM_S_NO_ERROR`, and `pstrNames` is always set to point to it.</span></span> <span data-ttu-id="fc2c2-176">지정 된 필터와 일치 하는 속성이 없을 경우 반환 된 배열의 요소는 0이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-176">The returned array can have 0 elements if no properties match the specified filters.</span></span> <span data-ttu-id="fc2c2-177">함수가 이외의 값을 반환 하는 경우에는 `WBM_S_NO_ERROR` 새 `SAFEARRAY` 구조체가 반환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-177">If the function returns an value other than `WBM_S_NO_ERROR`, a new `SAFEARRAY` structure is not returned.</span></span>

## <a name="requirements"></a><span data-ttu-id="fc2c2-178">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fc2c2-178">Requirements</span></span>  

 <span data-ttu-id="fc2c2-179">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fc2c2-179">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc2c2-180">**헤더:** WMINet_Utils idl</span><span class="sxs-lookup"><span data-stu-id="fc2c2-180">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="fc2c2-181">**.NET Framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fc2c2-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc2c2-182">참조</span><span class="sxs-lookup"><span data-stu-id="fc2c2-182">See also</span></span>

- [<span data-ttu-id="fc2c2-183">WMI 및 성능 카운터(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="fc2c2-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
