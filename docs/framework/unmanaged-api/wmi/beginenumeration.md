---
title: BeginEnumeration 함수 (관리 되지 않는 API 참조)
description: BeginEnumeration 함수 열거형의 시작 부분에는 열거자를 다시 설정
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 07396428dafbaa76e7771a4022bb493768f9f6c1
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636798"
---
# <a name="beginenumeration-function"></a><span data-ttu-id="47ddb-103">BeginEnumeration 함수</span><span class="sxs-lookup"><span data-stu-id="47ddb-103">BeginEnumeration function</span></span>
<span data-ttu-id="47ddb-104">열거형의 시작 부분에 다시 열거자를 다시 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="47ddb-104">Resets an enumerator back to the beginning of the enumeration.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="47ddb-105">구문</span><span class="sxs-lookup"><span data-stu-id="47ddb-105">Syntax</span></span>  
  
```  
HRESULT BeginEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="47ddb-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="47ddb-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="47ddb-107">[in] 이 매개 변수 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47ddb-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="47ddb-108">[in] 에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="47ddb-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`\
<span data-ttu-id="47ddb-109">[in] 플래그를 설명 하는 값의 비트 조합 합니다 [주의](#remarks) 열거형에 포함 된 속성을 제어 하는 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="47ddb-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that controls the properties included in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="47ddb-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="47ddb-110">Return value</span></span>

<span data-ttu-id="47ddb-111">이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="47ddb-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="47ddb-112">상수</span><span class="sxs-lookup"><span data-stu-id="47ddb-112">Constant</span></span>  |<span data-ttu-id="47ddb-113">값</span><span class="sxs-lookup"><span data-stu-id="47ddb-113">Value</span></span>  |<span data-ttu-id="47ddb-114">설명</span><span class="sxs-lookup"><span data-stu-id="47ddb-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="47ddb-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="47ddb-115">0x80041008</span></span> | <span data-ttu-id="47ddb-116">플래그의 조합을 `lEnumFlags` 이 잘못 되었거나 잘못 된 인수가 지정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="47ddb-116">The combination of flags in `lEnumFlags` is invalid, or an invalid argument was specified.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="47ddb-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="47ddb-117">0x8004101d</span></span> | <span data-ttu-id="47ddb-118">두 번째 호출 `BeginEnumeration` 에 대 한 중간 호출 없이 만들어진 [ `EndEnumeration` ](endenumeration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="47ddb-118">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="47ddb-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="47ddb-119">0x80041006</span></span> | <span data-ttu-id="47ddb-120">새 열거형 시작에 사용할 있는 메모리가 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47ddb-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="47ddb-121">0</span><span class="sxs-lookup"><span data-stu-id="47ddb-121">0</span></span> | <span data-ttu-id="47ddb-122">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="47ddb-122">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="47ddb-123">설명</span><span class="sxs-lookup"><span data-stu-id="47ddb-123">Remarks</span></span>

<span data-ttu-id="47ddb-124">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 메서드.</span><span class="sxs-lookup"><span data-stu-id="47ddb-124">This function wraps a call to the [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) method.</span></span>

<span data-ttu-id="47ddb-125">로 전달 될 수 있는 플래그는 `lEnumFlags` 인수에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드.</span><span class="sxs-lookup"><span data-stu-id="47ddb-125">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="47ddb-126">다른 그룹의 모든 플래그를 사용 하 여 각 그룹에서 하나 이상의 플래그를 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47ddb-126">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="47ddb-127">그러나 동일한 그룹의 플래그는 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="47ddb-127">However, flags from the same group are mutually exclusive.</span></span> 

<span data-ttu-id="47ddb-128">**그룹 1**</span><span class="sxs-lookup"><span data-stu-id="47ddb-128">**Group 1**</span></span>

|<span data-ttu-id="47ddb-129">상수</span><span class="sxs-lookup"><span data-stu-id="47ddb-129">Constant</span></span>  |<span data-ttu-id="47ddb-130">값</span><span class="sxs-lookup"><span data-stu-id="47ddb-130">Value</span></span>  |<span data-ttu-id="47ddb-131">설명</span><span class="sxs-lookup"><span data-stu-id="47ddb-131">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="47ddb-132">0x4</span><span class="sxs-lookup"><span data-stu-id="47ddb-132">0x4</span></span> | <span data-ttu-id="47ddb-133">키에만 구성 하는 속성이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47ddb-133">Include properties that constitute the key only.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="47ddb-134">0x8</span><span class="sxs-lookup"><span data-stu-id="47ddb-134">0x8</span></span> | <span data-ttu-id="47ddb-135">개체 참조에만 해당 되는 속성이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47ddb-135">Include properties that are object references only.</span></span> |

<span data-ttu-id="47ddb-136">**그룹 2**</span><span class="sxs-lookup"><span data-stu-id="47ddb-136">**Group 2**</span></span>

<span data-ttu-id="47ddb-137">상수</span><span class="sxs-lookup"><span data-stu-id="47ddb-137">Constant</span></span>  |<span data-ttu-id="47ddb-138">값</span><span class="sxs-lookup"><span data-stu-id="47ddb-138">Value</span></span>  |<span data-ttu-id="47ddb-139">설명</span><span class="sxs-lookup"><span data-stu-id="47ddb-139">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="47ddb-140">0x30</span><span class="sxs-lookup"><span data-stu-id="47ddb-140">0x30</span></span> | <span data-ttu-id="47ddb-141">시스템 속성에 열거를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="47ddb-141">Limit the enumeration to system properties only.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="47ddb-142">0x40</span><span class="sxs-lookup"><span data-stu-id="47ddb-142">0x40</span></span> | <span data-ttu-id="47ddb-143">로컬 및 전파 속성을 포함 하지만 열거의 시스템 속성을 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="47ddb-143">Include local and propagated properties but exclude system properties from the enumeration.</span></span> |

<span data-ttu-id="47ddb-144">클래스:</span><span class="sxs-lookup"><span data-stu-id="47ddb-144">For classes:</span></span>

<span data-ttu-id="47ddb-145">상수</span><span class="sxs-lookup"><span data-stu-id="47ddb-145">Constant</span></span>  |<span data-ttu-id="47ddb-146">값</span><span class="sxs-lookup"><span data-stu-id="47ddb-146">Value</span></span>  |<span data-ttu-id="47ddb-147">설명</span><span class="sxs-lookup"><span data-stu-id="47ddb-147">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | <span data-ttu-id="47ddb-148">0x100</span><span class="sxs-lookup"><span data-stu-id="47ddb-148">0x100</span></span> | <span data-ttu-id="47ddb-149">열거형 클래스 정의에서 재정의 된 속성을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="47ddb-149">Limit the enumeration to properties overridden in the class definition.</span></span> |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | <span data-ttu-id="47ddb-150">0x100</span><span class="sxs-lookup"><span data-stu-id="47ddb-150">0x100</span></span> | <span data-ttu-id="47ddb-151">현재 클래스 정의에서 재정의 된 속성을 클래스에 정의 된 새 속성을 열거를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="47ddb-151">Limit the enumeration to properties overridden in the current class definition and to new properties defined in the class.</span></span> |
| `WBEM_MASK_CLASS_CONDITION` | <span data-ttu-id="47ddb-152">0x300</span><span class="sxs-lookup"><span data-stu-id="47ddb-152">0x300</span></span> | <span data-ttu-id="47ddb-153">A에 대해 적용할 (플래그) 대신 마스크를 `lEnumFlags` 경우 확인할 값 `WBEM_FLAG_CLASS_OVERRIDES_ONLY` 또는 `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47ddb-153">A mask (rather than a flag) to apply against a `lEnumFlags` value to check if either `WBEM_FLAG_CLASS_OVERRIDES_ONLY` or `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` is set.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="47ddb-154">0x10</span><span class="sxs-lookup"><span data-stu-id="47ddb-154">0x10</span></span> | <span data-ttu-id="47ddb-155">열거형 클래스 자체에서 수정 되거나 정의 되는 속성을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="47ddb-155">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="47ddb-156">0x20</span><span class="sxs-lookup"><span data-stu-id="47ddb-156">0x20</span></span> | <span data-ttu-id="47ddb-157">열거형 기본 클래스에서 상속 된 속성을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="47ddb-157">Limit the enumeration to properties that are inherited from base classes.</span></span> |

<span data-ttu-id="47ddb-158">에 대 한 인스턴스:</span><span class="sxs-lookup"><span data-stu-id="47ddb-158">For instances:</span></span>

<span data-ttu-id="47ddb-159">상수</span><span class="sxs-lookup"><span data-stu-id="47ddb-159">Constant</span></span>  |<span data-ttu-id="47ddb-160">값</span><span class="sxs-lookup"><span data-stu-id="47ddb-160">Value</span></span>  |<span data-ttu-id="47ddb-161">설명</span><span class="sxs-lookup"><span data-stu-id="47ddb-161">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="47ddb-162">0x10</span><span class="sxs-lookup"><span data-stu-id="47ddb-162">0x10</span></span> | <span data-ttu-id="47ddb-163">열거형 클래스 자체에서 수정 되거나 정의 되는 속성을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="47ddb-163">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="47ddb-164">0x20</span><span class="sxs-lookup"><span data-stu-id="47ddb-164">0x20</span></span> | <span data-ttu-id="47ddb-165">열거형 기본 클래스에서 상속 된 속성을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="47ddb-165">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="47ddb-166">요구 사항</span><span class="sxs-lookup"><span data-stu-id="47ddb-166">Requirements</span></span>  
 <span data-ttu-id="47ddb-167">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="47ddb-167">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47ddb-168">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="47ddb-168">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="47ddb-169">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="47ddb-169">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47ddb-170">참고자료</span><span class="sxs-lookup"><span data-stu-id="47ddb-170">See also</span></span>

- [<span data-ttu-id="47ddb-171">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="47ddb-171">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
