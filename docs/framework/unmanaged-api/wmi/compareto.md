---
title: CompareTo 함수 (관리 되지 않는 API 참조)
description: CompareTo 함수는 개체를 다른 WMI 개체를 비교합니다.
ms.date: 11/06/2017
api_name:
- CompareTo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CompareTo
helpviewer_keywords:
- CompareTo function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb5a26fccf7ceb56089aae4bd4f0732b8a405ba0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049273"
---
# <a name="compareto-function"></a><span data-ttu-id="7ad5b-103">CompareTo 함수</span><span class="sxs-lookup"><span data-stu-id="7ad5b-103">CompareTo function</span></span>

<span data-ttu-id="7ad5b-104">개체를 다른 Windows 관리 개체와 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad5b-104">Compares an object to another Windows management object.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="7ad5b-105">구문</span><span class="sxs-lookup"><span data-stu-id="7ad5b-105">Syntax</span></span>

```cpp
HRESULT CompareTo (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              flags,
   [in] IWbemClassObject* pCompareTo
);
```

## <a name="parameters"></a><span data-ttu-id="7ad5b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7ad5b-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="7ad5b-107">[in] 이 매개 변수 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad5b-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="7ad5b-108">[in] 에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="7ad5b-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`flags`\
<span data-ttu-id="7ad5b-109">[in] 비교에 대해 고려할 개체 특징을 지정 하는 플래그의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="7ad5b-109">[in] A bitwise combination of the flags that specify the object characteristics to consider for the comparison.</span></span> <span data-ttu-id="7ad5b-110">참조 된 [주의](#remarks) 자세한 내용은 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="7ad5b-110">See the [Remarks](#remarks) section for more information.</span></span>

`pCompareTo`\
<span data-ttu-id="7ad5b-111">[in] 비교할 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="7ad5b-111">[in] The object for comparison.</span></span> <span data-ttu-id="7ad5b-112">`pCompareTo` 올바른 이어야 합니다 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스; 일 수 없습니다 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad5b-112">`pCompareTo` must be a valid [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance; it cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="7ad5b-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="7ad5b-113">Return value</span></span>

<span data-ttu-id="7ad5b-114">이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="7ad5b-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="7ad5b-115">상수</span><span class="sxs-lookup"><span data-stu-id="7ad5b-115">Constant</span></span>  |<span data-ttu-id="7ad5b-116">값</span><span class="sxs-lookup"><span data-stu-id="7ad5b-116">Value</span></span>  |<span data-ttu-id="7ad5b-117">설명</span><span class="sxs-lookup"><span data-stu-id="7ad5b-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="7ad5b-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="7ad5b-118">0x80041001</span></span> | <span data-ttu-id="7ad5b-119">지정 되지 않은 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad5b-119">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="7ad5b-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="7ad5b-120">0x80041008</span></span> | <span data-ttu-id="7ad5b-121">매개 변수가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad5b-121">A parameter is invalid.</span></span> |
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="7ad5b-122">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="7ad5b-122">0x8004101d</span></span> | <span data-ttu-id="7ad5b-123">두 번째 호출 `BeginEnumeration` 에 대 한 중간 호출 없이 만들어진 [ `EndEnumeration` ](endenumeration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad5b-123">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="7ad5b-124">0</span><span class="sxs-lookup"><span data-stu-id="7ad5b-124">0</span></span> | <span data-ttu-id="7ad5b-125">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad5b-125">The function call was successful.</span></span>  |
| `WBEM_S_DIFFERENT` | <span data-ttu-id="7ad5b-126">0x40003</span><span class="sxs-lookup"><span data-stu-id="7ad5b-126">0x40003</span></span> | <span data-ttu-id="7ad5b-127">개체가 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="7ad5b-127">The objects are different.</span></span> |
| `WBEM_S_SAME` | <span data-ttu-id="7ad5b-128">0</span><span class="sxs-lookup"><span data-stu-id="7ad5b-128">0</span></span> | <span data-ttu-id="7ad5b-129">개체는 비교 플래그에 따라 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad5b-129">The objects are the same based on the comparison flags.</span></span> |

## <a name="remarks"></a><span data-ttu-id="7ad5b-130">설명</span><span class="sxs-lookup"><span data-stu-id="7ad5b-130">Remarks</span></span>

<span data-ttu-id="7ad5b-131">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto) 메서드.</span><span class="sxs-lookup"><span data-stu-id="7ad5b-131">This function wraps a call to the [IWbemClassObject::CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto) method.</span></span>

<span data-ttu-id="7ad5b-132">로 전달 될 수 있는 플래그는 `lEnumFlags` 인수에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드.</span><span class="sxs-lookup"><span data-stu-id="7ad5b-132">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span> <span data-ttu-id="7ad5b-133">다음 플래그의 비트 조합 지정 하 여 비교에 사용 되는 개별 특성을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad5b-133">You can specify the individual characteristics involved in the comparison by specifying a bitwise combination of the following flags:</span></span>

|<span data-ttu-id="7ad5b-134">상수</span><span class="sxs-lookup"><span data-stu-id="7ad5b-134">Constant</span></span>  |<span data-ttu-id="7ad5b-135">값</span><span class="sxs-lookup"><span data-stu-id="7ad5b-135">Value</span></span>  |<span data-ttu-id="7ad5b-136">설명</span><span class="sxs-lookup"><span data-stu-id="7ad5b-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_IGNORE_OBJECT_SOURCE` | <span data-ttu-id="7ad5b-137">2</span><span class="sxs-lookup"><span data-stu-id="7ad5b-137">2</span></span> | <span data-ttu-id="7ad5b-138">(서버 및 네임 스페이스에서 미끄러져) 소스를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad5b-138">Ignore the source (the server and the namespace they came from).</span></span> |
| `WBEM_FLAG_IGNORE_QUALIFIERS` | <span data-ttu-id="7ad5b-139">1</span><span class="sxs-lookup"><span data-stu-id="7ad5b-139">1</span></span> | <span data-ttu-id="7ad5b-140">모든 한정자를 무시 (포함 **키** 하 고 **동적**)</span><span class="sxs-lookup"><span data-stu-id="7ad5b-140">Ignore all qualifiers (including **Key** and **Dynamic**)</span></span> |
| `WBEM_FLAG_IGNORE_DEFAULT_VALUES` | <span data-ttu-id="7ad5b-141">4</span><span class="sxs-lookup"><span data-stu-id="7ad5b-141">4</span></span> | <span data-ttu-id="7ad5b-142">속성의 기본값을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad5b-142">Ignore default values of properties.</span></span> <span data-ttu-id="7ad5b-143">이 플래그는 클래스의 비교에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ad5b-143">This flag only applies to comparison of classes.</span></span> |
| `WBEM_FLAG_IGNORE_FLAVOR` | <span data-ttu-id="7ad5b-144">0x20</span><span class="sxs-lookup"><span data-stu-id="7ad5b-144">0x20</span></span> | <span data-ttu-id="7ad5b-145">한정자 특성을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad5b-145">Ignore qualifier flavors.</span></span> <span data-ttu-id="7ad5b-146">이 플래그 여전히 한정자 고려 하지만 전파 규칙과 같은 특색의 차이 무시 및 제한 사항을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad5b-146">This flag still takes qualifiers into account, but ignores flavor distinctions such as propagation rules and override restrictions.</span></span> |
| `WBEM_FLAG_IGNORE_CASE` | <span data-ttu-id="7ad5b-147">0x10</span><span class="sxs-lookup"><span data-stu-id="7ad5b-147">0x10</span></span> | <span data-ttu-id="7ad5b-148">문자열 값 비교에서 대/소문자를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad5b-148">Ignore case in comparing string values.</span></span> <span data-ttu-id="7ad5b-149">문자열과 한정자 값에 모두 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ad5b-149">This applies both to strings and qualifier values.</span></span> <span data-ttu-id="7ad5b-150">속성과 한정자 이름은의 비교는 항상이 플래그가 설정 되어 있는지 여부에 관계 없이 대/소문자 구분.</span><span class="sxs-lookup"><span data-stu-id="7ad5b-150">The comparison of property and qualifier names is always case-sensitive regardless of whether this flag is set.</span></span> |
| `WBEM_FLAG_IGNORE_CLASS` | <span data-ttu-id="7ad5b-151">0x8</span><span class="sxs-lookup"><span data-stu-id="7ad5b-151">0x8</span></span> | <span data-ttu-id="7ad5b-152">비교 되는 개체에 동일한 클래스의 인스턴스에 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad5b-152">Assume that the objects being compared are instances of the same class.</span></span> <span data-ttu-id="7ad5b-153">따라서이 플래그는 인스턴스와 관련 된 정보만을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad5b-153">Consequently, this flag compares instance-related information only.</span></span> <span data-ttu-id="7ad5b-154">성능을 최적화 하려면이 플래그를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad5b-154">Use this flags to optimize performance.</span></span> <span data-ttu-id="7ad5b-155">동일한 클래스의 개체가 없으면 결과가 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad5b-155">If the objects are not of the same class, the results are undefined.</span></span> |

<span data-ttu-id="7ad5b-156">또는 다음과 같이 단일 복합 플래그를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad5b-156">Or you can specify a single composite flag as follows:</span></span>

|<span data-ttu-id="7ad5b-157">상수</span><span class="sxs-lookup"><span data-stu-id="7ad5b-157">Constant</span></span>  |<span data-ttu-id="7ad5b-158">값</span><span class="sxs-lookup"><span data-stu-id="7ad5b-158">Value</span></span>  |<span data-ttu-id="7ad5b-159">설명</span><span class="sxs-lookup"><span data-stu-id="7ad5b-159">Description</span></span>  |
|---------|---------|---------|
|`WBEM_COMPARISON_INCLUDE_ALL` | <span data-ttu-id="7ad5b-160">0</span><span class="sxs-lookup"><span data-stu-id="7ad5b-160">0</span></span> | <span data-ttu-id="7ad5b-161">비교의 모든 기능을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad5b-161">Consider all features in the comparison.</span></span> |

## <a name="requirements"></a><span data-ttu-id="7ad5b-162">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7ad5b-162">Requirements</span></span>

<span data-ttu-id="7ad5b-163">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7ad5b-163">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="7ad5b-164">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="7ad5b-164">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="7ad5b-165">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7ad5b-165">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="7ad5b-166">참고자료</span><span class="sxs-lookup"><span data-stu-id="7ad5b-166">See also</span></span>

- [<span data-ttu-id="7ad5b-167">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="7ad5b-167">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)