---
title: QualifierSet_BeginEnumeration 함수 (관리 되지 않는 API 참조)
description: QualifierSet_BeginEnumeration 함수는 개체 한정자의 열거자를 다시 설정 합니다.
ms.date: 11/06/2017
api_name:
- QualifierSet_BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_BeginEnumeration
helpviewer_keywords:
- QualifierSet_BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3b75c51ebddd78e447fed57b22a96c2d5c35004e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798353"
---
# <a name="qualifierset_beginenumeration-function"></a><span data-ttu-id="4a08d-103">QualifierSet_BeginEnumeration 함수</span><span class="sxs-lookup"><span data-stu-id="4a08d-103">QualifierSet_BeginEnumeration function</span></span>

<span data-ttu-id="4a08d-104">개체 한정자의 열거자를 열거형 시작 부분으로 다시 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4a08d-104">Resets an enumerator of the qualifiers of an object to the beginning of the enumeration.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="4a08d-105">구문</span><span class="sxs-lookup"><span data-stu-id="4a08d-105">Syntax</span></span>

```cpp
HRESULT QualifierSet_BeginEnumeration (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags
);
```

## <a name="parameters"></a><span data-ttu-id="4a08d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4a08d-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="4a08d-107">진행 이 매개 변수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4a08d-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="4a08d-108">진행 [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4a08d-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`\
<span data-ttu-id="4a08d-109">진행 [설명](#remarks) 섹션에서 설명 하는 플래그 또는 값의 비트 조합으로, 열거형에 포함할 한정자를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a08d-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that specifies the qualifiers to include in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="4a08d-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="4a08d-110">Return value</span></span>

<span data-ttu-id="4a08d-111">이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a08d-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="4a08d-112">상수</span><span class="sxs-lookup"><span data-stu-id="4a08d-112">Constant</span></span>  |<span data-ttu-id="4a08d-113">값</span><span class="sxs-lookup"><span data-stu-id="4a08d-113">Value</span></span>  |<span data-ttu-id="4a08d-114">Description</span><span class="sxs-lookup"><span data-stu-id="4a08d-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="4a08d-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="4a08d-115">0x80041008</span></span> | <span data-ttu-id="4a08d-116">`lFlags` 매개 변수가 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4a08d-116">The `lFlags` parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="4a08d-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="4a08d-117">0x8004101d</span></span> | <span data-ttu-id="4a08d-118">`QualifierSet_BeginEnumeration` [를`QualifierSet_EndEnumeration`](qualifierset-endenumeration.md)호출 하지 않고에 대 한 두 번째 호출을 수행 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4a08d-118">A second call to `QualifierSet_BeginEnumeration` was made without an intervening call to [`QualifierSet_EndEnumeration`](qualifierset-endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="4a08d-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="4a08d-119">0x80041006</span></span> | <span data-ttu-id="4a08d-120">메모리가 부족 하 여 새 열거를 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4a08d-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="4a08d-121">0</span><span class="sxs-lookup"><span data-stu-id="4a08d-121">0</span></span> | <span data-ttu-id="4a08d-122">함수 호출에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4a08d-122">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="4a08d-123">설명</span><span class="sxs-lookup"><span data-stu-id="4a08d-123">Remarks</span></span>

<span data-ttu-id="4a08d-124">이 함수는 [IWbemQualifierSet:: BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="4a08d-124">This function wraps a call to the [IWbemQualifierSet::BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) method.</span></span>

<span data-ttu-id="4a08d-125">개체에 대 한 모든 한정자를 열거 하려면 [QualifierSet_Next](qualifierset-next.md)에 대 한 첫 번째 호출 전에이 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a08d-125">To enumerate all of the qualifiers on an object, this method must be called before the first call to [QualifierSet_Next](qualifierset-next.md).</span></span> <span data-ttu-id="4a08d-126">한정자를 열거 하는 순서는 지정 된 열거형에 대해 고정이 되도록 보장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a08d-126">The order in which qualifiers are enumerated is guaranteed to be invariant for a given enumeration.</span></span>

<span data-ttu-id="4a08d-127">`lEnumFlags` 인수로 전달 될 수 있는 플래그는 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a08d-127">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>

|<span data-ttu-id="4a08d-128">상수</span><span class="sxs-lookup"><span data-stu-id="4a08d-128">Constant</span></span>  |<span data-ttu-id="4a08d-129">값</span><span class="sxs-lookup"><span data-stu-id="4a08d-129">Value</span></span>  |<span data-ttu-id="4a08d-130">설명</span><span class="sxs-lookup"><span data-stu-id="4a08d-130">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="4a08d-131">0</span><span class="sxs-lookup"><span data-stu-id="4a08d-131">0</span></span> | <span data-ttu-id="4a08d-132">모든 한정자의 이름을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a08d-132">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="4a08d-133">0x10</span><span class="sxs-lookup"><span data-stu-id="4a08d-133">0x10</span></span> | <span data-ttu-id="4a08d-134">현재 속성 또는 개체와 관련 된 한정자의 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a08d-134">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="4a08d-135">속성의 경우: 클래스 정의에서 전파 되는 한정자가 아니라 속성 (재정의 포함)에 한정 된 한정자만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a08d-135">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="4a08d-136">인스턴스의 경우: 인스턴스별 한정자 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a08d-136">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="4a08d-137">클래스의 경우: 파생 되는 클래스와 관련 된 한정자만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a08d-137">For a class: Return only qualifiers specific to the class being derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="4a08d-138">0x20</span><span class="sxs-lookup"><span data-stu-id="4a08d-138">0x20</span></span> | <span data-ttu-id="4a08d-139">다른 개체에서 전파 된 한정자의 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a08d-139">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="4a08d-140">속성의 경우: 클래스 정의에서이 속성에 전파 된 한정자만 반환 하 고 속성 자체의 한정자는 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4a08d-140">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="4a08d-141">인스턴스의 경우: 클래스 정의에서 전파 된 한정자만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a08d-141">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="4a08d-142">클래스의 경우: 부모 클래스에서 상속 된 한정자 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a08d-142">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="4a08d-143">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4a08d-143">Requirements</span></span>

<span data-ttu-id="4a08d-144">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4a08d-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="4a08d-145">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="4a08d-145">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="4a08d-146">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4a08d-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="4a08d-147">참고자료</span><span class="sxs-lookup"><span data-stu-id="4a08d-147">See also</span></span>

- [<span data-ttu-id="4a08d-148">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="4a08d-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
