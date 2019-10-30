---
title: BeginEnumeration 함수 (관리 되지 않는 API 참조)
description: BeginEnumeration 함수는 열거자를 열거형의 시작 부분으로 다시 설정 합니다.
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
ms.openlocfilehash: 9e467234a45ae702a5b77a5f0fa8b75d4ff03c52
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124139"
---
# <a name="beginenumeration-function"></a><span data-ttu-id="46082-103">BeginEnumeration 함수</span><span class="sxs-lookup"><span data-stu-id="46082-103">BeginEnumeration function</span></span>
<span data-ttu-id="46082-104">열거자를 열거형의 시작 부분으로 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="46082-104">Resets an enumerator back to the beginning of the enumeration.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="46082-105">구문</span><span class="sxs-lookup"><span data-stu-id="46082-105">Syntax</span></span>  
  
```cpp  
HRESULT BeginEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="46082-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="46082-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="46082-107">진행 이 매개 변수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46082-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="46082-108">진행 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="46082-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`\
<span data-ttu-id="46082-109">진행 [설명](#remarks) 섹션에서 설명 하는 플래그 또는 값의 비트 조합으로, 열거형에 포함 된 속성을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="46082-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that controls the properties included in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="46082-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="46082-110">Return value</span></span>

<span data-ttu-id="46082-111">이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46082-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="46082-112">상수</span><span class="sxs-lookup"><span data-stu-id="46082-112">Constant</span></span>  |<span data-ttu-id="46082-113">값</span><span class="sxs-lookup"><span data-stu-id="46082-113">Value</span></span>  |<span data-ttu-id="46082-114">설명</span><span class="sxs-lookup"><span data-stu-id="46082-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="46082-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="46082-115">0x80041008</span></span> | <span data-ttu-id="46082-116">`lEnumFlags`에서 플래그 조합이 잘못 되었거나 잘못 된 인수가 지정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="46082-116">The combination of flags in `lEnumFlags` is invalid, or an invalid argument was specified.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="46082-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="46082-117">0x8004101d</span></span> | <span data-ttu-id="46082-118">[`EndEnumeration`](endenumeration.md)를 중간에 호출 하지 않고 `BeginEnumeration`에 대 한 두 번째 호출을 수행 했습니다.</span><span class="sxs-lookup"><span data-stu-id="46082-118">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="46082-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="46082-119">0x80041006</span></span> | <span data-ttu-id="46082-120">메모리가 부족 하 여 새 열거를 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46082-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="46082-121">0</span><span class="sxs-lookup"><span data-stu-id="46082-121">0</span></span> | <span data-ttu-id="46082-122">함수 호출에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="46082-122">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="46082-123">주의</span><span class="sxs-lookup"><span data-stu-id="46082-123">Remarks</span></span>

<span data-ttu-id="46082-124">이 함수는 [IWbemClassObject:: BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="46082-124">This function wraps a call to the [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) method.</span></span>

<span data-ttu-id="46082-125">`lEnumFlags` 인수로 전달 될 수 있는 플래그는 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46082-125">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="46082-126">각 그룹의 플래그 하나를 다른 모든 그룹의 플래그와 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46082-126">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="46082-127">그러나 같은 그룹의 플래그는 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46082-127">However, flags from the same group are mutually exclusive.</span></span> 

<span data-ttu-id="46082-128">**그룹 1**</span><span class="sxs-lookup"><span data-stu-id="46082-128">**Group 1**</span></span>

|<span data-ttu-id="46082-129">상수</span><span class="sxs-lookup"><span data-stu-id="46082-129">Constant</span></span>  |<span data-ttu-id="46082-130">값</span><span class="sxs-lookup"><span data-stu-id="46082-130">Value</span></span>  |<span data-ttu-id="46082-131">설명</span><span class="sxs-lookup"><span data-stu-id="46082-131">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="46082-132">0x4</span><span class="sxs-lookup"><span data-stu-id="46082-132">0x4</span></span> | <span data-ttu-id="46082-133">키만 구성 하는 속성을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="46082-133">Include properties that constitute the key only.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="46082-134">나오는</span><span class="sxs-lookup"><span data-stu-id="46082-134">0x8</span></span> | <span data-ttu-id="46082-135">개체 참조에만 해당 하는 속성을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="46082-135">Include properties that are object references only.</span></span> |

<span data-ttu-id="46082-136">**그룹 2**</span><span class="sxs-lookup"><span data-stu-id="46082-136">**Group 2**</span></span>

<span data-ttu-id="46082-137">상수</span><span class="sxs-lookup"><span data-stu-id="46082-137">Constant</span></span>  |<span data-ttu-id="46082-138">값</span><span class="sxs-lookup"><span data-stu-id="46082-138">Value</span></span>  |<span data-ttu-id="46082-139">설명</span><span class="sxs-lookup"><span data-stu-id="46082-139">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="46082-140">0x30</span><span class="sxs-lookup"><span data-stu-id="46082-140">0x30</span></span> | <span data-ttu-id="46082-141">열거를 시스템 속성 으로만 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="46082-141">Limit the enumeration to system properties only.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="46082-142">0x40</span><span class="sxs-lookup"><span data-stu-id="46082-142">0x40</span></span> | <span data-ttu-id="46082-143">로컬 및 전파 된 속성을 포함 하지만 시스템 속성은 열거에서 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="46082-143">Include local and propagated properties but exclude system properties from the enumeration.</span></span> |

<span data-ttu-id="46082-144">클래스:</span><span class="sxs-lookup"><span data-stu-id="46082-144">For classes:</span></span>

<span data-ttu-id="46082-145">상수</span><span class="sxs-lookup"><span data-stu-id="46082-145">Constant</span></span>  |<span data-ttu-id="46082-146">값</span><span class="sxs-lookup"><span data-stu-id="46082-146">Value</span></span>  |<span data-ttu-id="46082-147">설명</span><span class="sxs-lookup"><span data-stu-id="46082-147">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | <span data-ttu-id="46082-148">0x100</span><span class="sxs-lookup"><span data-stu-id="46082-148">0x100</span></span> | <span data-ttu-id="46082-149">열거를 클래스 정의에서 재정의 된 속성으로 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="46082-149">Limit the enumeration to properties overridden in the class definition.</span></span> |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | <span data-ttu-id="46082-150">0x100</span><span class="sxs-lookup"><span data-stu-id="46082-150">0x100</span></span> | <span data-ttu-id="46082-151">열거를 현재 클래스 정의에 재정의 된 속성 및 클래스에 정의 된 새 속성으로 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="46082-151">Limit the enumeration to properties overridden in the current class definition and to new properties defined in the class.</span></span> |
| `WBEM_MASK_CLASS_CONDITION` | <span data-ttu-id="46082-152">0x300</span><span class="sxs-lookup"><span data-stu-id="46082-152">0x300</span></span> | <span data-ttu-id="46082-153">`WBEM_FLAG_CLASS_OVERRIDES_ONLY` 또는 `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` 설정 되었는지 여부를 확인 하기 위해 `lEnumFlags` 값에 대해 적용할 마스크 (플래그 아님)입니다.</span><span class="sxs-lookup"><span data-stu-id="46082-153">A mask (rather than a flag) to apply against a `lEnumFlags` value to check if either `WBEM_FLAG_CLASS_OVERRIDES_ONLY` or `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` is set.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="46082-154">0x10</span><span class="sxs-lookup"><span data-stu-id="46082-154">0x10</span></span> | <span data-ttu-id="46082-155">클래스 자체에서 정의 되거나 수정 된 속성으로 열거를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="46082-155">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="46082-156">0x20</span><span class="sxs-lookup"><span data-stu-id="46082-156">0x20</span></span> | <span data-ttu-id="46082-157">기본 클래스에서 상속 되는 속성으로 열거를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="46082-157">Limit the enumeration to properties that are inherited from base classes.</span></span> |

<span data-ttu-id="46082-158">인스턴스의 경우:</span><span class="sxs-lookup"><span data-stu-id="46082-158">For instances:</span></span>

<span data-ttu-id="46082-159">상수</span><span class="sxs-lookup"><span data-stu-id="46082-159">Constant</span></span>  |<span data-ttu-id="46082-160">값</span><span class="sxs-lookup"><span data-stu-id="46082-160">Value</span></span>  |<span data-ttu-id="46082-161">설명</span><span class="sxs-lookup"><span data-stu-id="46082-161">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="46082-162">0x10</span><span class="sxs-lookup"><span data-stu-id="46082-162">0x10</span></span> | <span data-ttu-id="46082-163">클래스 자체에서 정의 되거나 수정 된 속성으로 열거를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="46082-163">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="46082-164">0x20</span><span class="sxs-lookup"><span data-stu-id="46082-164">0x20</span></span> | <span data-ttu-id="46082-165">기본 클래스에서 상속 되는 속성으로 열거를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="46082-165">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="46082-166">요구 사항</span><span class="sxs-lookup"><span data-stu-id="46082-166">Requirements</span></span>  
 <span data-ttu-id="46082-167">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="46082-167">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46082-168">**헤더:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="46082-168">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="46082-169">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="46082-169">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46082-170">참조</span><span class="sxs-lookup"><span data-stu-id="46082-170">See also</span></span>

- [<span data-ttu-id="46082-171">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="46082-171">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
