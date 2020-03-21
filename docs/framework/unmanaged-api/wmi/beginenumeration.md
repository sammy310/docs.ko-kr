---
title: 시작 열거 함수(관리되지 않는 API 참조)
description: BeginEnumeration 함수는 열거형의 시작 부분으로 열거기를 재설정합니다.
ms.date: 11/06/2017
api_name:
- BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BeginEnumeration
helpviewer_keywords:
- BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: eac23916bd78ec3970a87566e2d2f4d79b379824
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176879"
---
# <a name="beginenumeration-function"></a><span data-ttu-id="ab18c-103">BeginEnumeration 함수</span><span class="sxs-lookup"><span data-stu-id="ab18c-103">BeginEnumeration function</span></span>
<span data-ttu-id="ab18c-104">열거체를 열거시작부분으로 재설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ab18c-104">Resets an enumerator back to the beginning of the enumeration.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="ab18c-105">구문</span><span class="sxs-lookup"><span data-stu-id="ab18c-105">Syntax</span></span>  
  
```cpp  
HRESULT BeginEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              lEnumFlags
);
```  

## <a name="parameters"></a><span data-ttu-id="ab18c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ab18c-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="ab18c-107">【인】 이 매개 변수는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab18c-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="ab18c-108">【인】 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ab18c-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`\
<span data-ttu-id="ab18c-109">【인】 설명 [섹션에](#remarks) 설명된 플래그 또는 값의 비트 조합으로 열거형에 포함된 속성을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="ab18c-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that controls the properties included in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="ab18c-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="ab18c-110">Return value</span></span>

<span data-ttu-id="ab18c-111">이 함수에서 반환되는 다음 값은 *WbemCli.h* 헤더 파일에 정의되거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab18c-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ab18c-112">지속적임</span><span class="sxs-lookup"><span data-stu-id="ab18c-112">Constant</span></span>  |<span data-ttu-id="ab18c-113">값</span><span class="sxs-lookup"><span data-stu-id="ab18c-113">Value</span></span>  |<span data-ttu-id="ab18c-114">Description</span><span class="sxs-lookup"><span data-stu-id="ab18c-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="ab18c-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="ab18c-115">0x80041008</span></span> | <span data-ttu-id="ab18c-116">의 `lEnumFlags` 플래그 조합이 잘못되었거나 잘못된 인수가 지정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ab18c-116">The combination of flags in `lEnumFlags` is invalid, or an invalid argument was specified.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="ab18c-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="ab18c-117">0x8004101d</span></span> | <span data-ttu-id="ab18c-118">에 대한 `BeginEnumeration` 두 번째 호출은 에 [`EndEnumeration`](endenumeration.md)대한 중간 호출 없이 이루어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="ab18c-118">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="ab18c-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="ab18c-119">0x80041006</span></span> | <span data-ttu-id="ab18c-120">새 열거를 시작하기에 사용할 수 있는 메모리가 부족합니다.</span><span class="sxs-lookup"><span data-stu-id="ab18c-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="ab18c-121">0</span><span class="sxs-lookup"><span data-stu-id="ab18c-121">0</span></span> | <span data-ttu-id="ab18c-122">함수 호출이 성공했습니다.</span><span class="sxs-lookup"><span data-stu-id="ab18c-122">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="ab18c-123">설명</span><span class="sxs-lookup"><span data-stu-id="ab18c-123">Remarks</span></span>

<span data-ttu-id="ab18c-124">이 함수는 [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 메서드에 대한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="ab18c-124">This function wraps a call to the [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) method.</span></span>

<span data-ttu-id="ab18c-125">`lEnumFlags` 인수로 전달할 수 있는 플래그는 *WbemCli.h* 헤더 파일에 정의되거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab18c-125">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="ab18c-126">각 그룹의 한 플래그를 다른 그룹의 모든 플래그와 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab18c-126">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="ab18c-127">그러나 동일한 그룹의 플래그는 상호 배타적입니다.</span><span class="sxs-lookup"><span data-stu-id="ab18c-127">However, flags from the same group are mutually exclusive.</span></span>

<span data-ttu-id="ab18c-128">**그룹 1**</span><span class="sxs-lookup"><span data-stu-id="ab18c-128">**Group 1**</span></span>

|<span data-ttu-id="ab18c-129">지속적임</span><span class="sxs-lookup"><span data-stu-id="ab18c-129">Constant</span></span>  |<span data-ttu-id="ab18c-130">값</span><span class="sxs-lookup"><span data-stu-id="ab18c-130">Value</span></span>  |<span data-ttu-id="ab18c-131">Description</span><span class="sxs-lookup"><span data-stu-id="ab18c-131">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="ab18c-132">0x4</span><span class="sxs-lookup"><span data-stu-id="ab18c-132">0x4</span></span> | <span data-ttu-id="ab18c-133">키만 을 구성하는 속성을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ab18c-133">Include properties that constitute the key only.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="ab18c-134">0x8</span><span class="sxs-lookup"><span data-stu-id="ab18c-134">0x8</span></span> | <span data-ttu-id="ab18c-135">개체 참조인 속성만 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ab18c-135">Include properties that are object references only.</span></span> |

<span data-ttu-id="ab18c-136">**그룹 2**</span><span class="sxs-lookup"><span data-stu-id="ab18c-136">**Group 2**</span></span>

<span data-ttu-id="ab18c-137">지속적임</span><span class="sxs-lookup"><span data-stu-id="ab18c-137">Constant</span></span>  |<span data-ttu-id="ab18c-138">값</span><span class="sxs-lookup"><span data-stu-id="ab18c-138">Value</span></span>  |<span data-ttu-id="ab18c-139">Description</span><span class="sxs-lookup"><span data-stu-id="ab18c-139">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="ab18c-140">0x30</span><span class="sxs-lookup"><span data-stu-id="ab18c-140">0x30</span></span> | <span data-ttu-id="ab18c-141">열거형은 시스템 속성으로만 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="ab18c-141">Limit the enumeration to system properties only.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="ab18c-142">0x40</span><span class="sxs-lookup"><span data-stu-id="ab18c-142">0x40</span></span> | <span data-ttu-id="ab18c-143">로컬 및 전파 속성을 포함하지만 열거형에서 시스템 속성을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="ab18c-143">Include local and propagated properties but exclude system properties from the enumeration.</span></span> |

<span data-ttu-id="ab18c-144">수업의 경우:</span><span class="sxs-lookup"><span data-stu-id="ab18c-144">For classes:</span></span>

<span data-ttu-id="ab18c-145">지속적임</span><span class="sxs-lookup"><span data-stu-id="ab18c-145">Constant</span></span>  |<span data-ttu-id="ab18c-146">값</span><span class="sxs-lookup"><span data-stu-id="ab18c-146">Value</span></span>  |<span data-ttu-id="ab18c-147">Description</span><span class="sxs-lookup"><span data-stu-id="ab18c-147">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | <span data-ttu-id="ab18c-148">0x100</span><span class="sxs-lookup"><span data-stu-id="ab18c-148">0x100</span></span> | <span data-ttu-id="ab18c-149">열거형이 클래스 정의에서 재정의된 속성으로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="ab18c-149">Limit the enumeration to properties overridden in the class definition.</span></span> |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | <span data-ttu-id="ab18c-150">0x100</span><span class="sxs-lookup"><span data-stu-id="ab18c-150">0x100</span></span> | <span data-ttu-id="ab18c-151">열거형 속성을 현재 클래스 정의에서 재정의하고 클래스에 정의된 새 속성으로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="ab18c-151">Limit the enumeration to properties overridden in the current class definition and to new properties defined in the class.</span></span> |
| `WBEM_MASK_CLASS_CONDITION` | <span data-ttu-id="ab18c-152">0x300</span><span class="sxs-lookup"><span data-stu-id="ab18c-152">0x300</span></span> | <span data-ttu-id="ab18c-153">플래그가 아닌 `lEnumFlags` 마스크로 값에 적용하여 둘 중 `WBEM_FLAG_CLASS_OVERRIDES_ONLY` `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` 하나 또는 설정된지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ab18c-153">A mask (rather than a flag) to apply against a `lEnumFlags` value to check if either `WBEM_FLAG_CLASS_OVERRIDES_ONLY` or `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` is set.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="ab18c-154">0x10</span><span class="sxs-lookup"><span data-stu-id="ab18c-154">0x10</span></span> | <span data-ttu-id="ab18c-155">열거형은 클래스 자체에서 정의되거나 수정된 속성으로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="ab18c-155">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="ab18c-156">0x20</span><span class="sxs-lookup"><span data-stu-id="ab18c-156">0x20</span></span> | <span data-ttu-id="ab18c-157">열거형은 기본 클래스에서 상속되는 속성으로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="ab18c-157">Limit the enumeration to properties that are inherited from base classes.</span></span> |

<span data-ttu-id="ab18c-158">인스턴스의 경우:</span><span class="sxs-lookup"><span data-stu-id="ab18c-158">For instances:</span></span>

<span data-ttu-id="ab18c-159">지속적임</span><span class="sxs-lookup"><span data-stu-id="ab18c-159">Constant</span></span>  |<span data-ttu-id="ab18c-160">값</span><span class="sxs-lookup"><span data-stu-id="ab18c-160">Value</span></span>  |<span data-ttu-id="ab18c-161">Description</span><span class="sxs-lookup"><span data-stu-id="ab18c-161">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="ab18c-162">0x10</span><span class="sxs-lookup"><span data-stu-id="ab18c-162">0x10</span></span> | <span data-ttu-id="ab18c-163">열거형은 클래스 자체에서 정의되거나 수정된 속성으로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="ab18c-163">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="ab18c-164">0x20</span><span class="sxs-lookup"><span data-stu-id="ab18c-164">0x20</span></span> | <span data-ttu-id="ab18c-165">열거형은 기본 클래스에서 상속되는 속성으로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="ab18c-165">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="ab18c-166">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ab18c-166">Requirements</span></span>  
 <span data-ttu-id="ab18c-167">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ab18c-167">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab18c-168">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ab18c-168">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="ab18c-169">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ab18c-169">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab18c-170">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ab18c-170">See also</span></span>

- [<span data-ttu-id="ab18c-171">WMI 및 성능 카운터(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="ab18c-171">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
