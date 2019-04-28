---
title: QualifierSet_BeginEnumeration 함수 (관리 되지 않는 API 참조)
description: QualifierSet_BeginEnumeration 함수 개체의 한정자의 열거자를 다시 설정합니다.
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
ms.openlocfilehash: f663434d3e3d44dc0c406e71592651493bd8f8dc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597246"
---
# <a name="qualifiersetbeginenumeration-function"></a><span data-ttu-id="cd5a6-103">QualifierSet_BeginEnumeration 함수</span><span class="sxs-lookup"><span data-stu-id="cd5a6-103">QualifierSet_BeginEnumeration function</span></span>

<span data-ttu-id="cd5a6-104">개체 한정자의 열거자를 열거형 시작 부분으로 다시 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cd5a6-104">Resets an enumerator of the qualifiers of an object to the beginning of the enumeration.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="cd5a6-105">구문</span><span class="sxs-lookup"><span data-stu-id="cd5a6-105">Syntax</span></span>

```cpp
HRESULT QualifierSet_BeginEnumeration (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags
);
```

## <a name="parameters"></a><span data-ttu-id="cd5a6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cd5a6-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="cd5a6-107">[in] 이 매개 변수 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd5a6-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="cd5a6-108">[in] 에 대 한 포인터를 [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="cd5a6-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`\
<span data-ttu-id="cd5a6-109">[in] 플래그를 설명 하는 값의 비트 조합 합니다 [주의](#remarks) 열거형에 포함 하려면 한정자를 지정 하는 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="cd5a6-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that specifies the qualifiers to include in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="cd5a6-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="cd5a6-110">Return value</span></span>

<span data-ttu-id="cd5a6-111">이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="cd5a6-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="cd5a6-112">상수</span><span class="sxs-lookup"><span data-stu-id="cd5a6-112">Constant</span></span>  |<span data-ttu-id="cd5a6-113">값</span><span class="sxs-lookup"><span data-stu-id="cd5a6-113">Value</span></span>  |<span data-ttu-id="cd5a6-114">설명</span><span class="sxs-lookup"><span data-stu-id="cd5a6-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="cd5a6-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="cd5a6-115">0x80041008</span></span> | <span data-ttu-id="cd5a6-116">`lFlags` 매개 변수가 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cd5a6-116">The `lFlags` parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="cd5a6-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="cd5a6-117">0x8004101d</span></span> | <span data-ttu-id="cd5a6-118">두 번째 호출 `QualifierSet_BeginEnumeration` 에 대 한 중간 호출 없이 만들어진 [ `QualifierSet_EndEnumeration` ](qualifierset-endenumeration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cd5a6-118">A second call to `QualifierSet_BeginEnumeration` was made without an intervening call to [`QualifierSet_EndEnumeration`](qualifierset-endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="cd5a6-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="cd5a6-119">0x80041006</span></span> | <span data-ttu-id="cd5a6-120">새 열거형 시작에 사용할 있는 메모리가 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd5a6-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="cd5a6-121">0</span><span class="sxs-lookup"><span data-stu-id="cd5a6-121">0</span></span> | <span data-ttu-id="cd5a6-122">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="cd5a6-122">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="cd5a6-123">설명</span><span class="sxs-lookup"><span data-stu-id="cd5a6-123">Remarks</span></span>

<span data-ttu-id="cd5a6-124">이 함수에 대 한 호출을 래핑하는 [IWbemQualifierSet::BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) 메서드.</span><span class="sxs-lookup"><span data-stu-id="cd5a6-124">This function wraps a call to the [IWbemQualifierSet::BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) method.</span></span>

<span data-ttu-id="cd5a6-125">모든 개체에 한정자를 열거 하려면이 메서드를 처음 호출 하기 전에 호출 해야 [QualifierSet_Next](qualifierset-next.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cd5a6-125">To enumerate all of the qualifiers on an object, this method must be called before the first call to [QualifierSet_Next](qualifierset-next.md).</span></span> <span data-ttu-id="cd5a6-126">한정자를 열거 하는 순서를 지정 된 열거형에 대 한 변형 보장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd5a6-126">The order in which qualifiers are enumerated is guaranteed to be invariant for a given enumeration.</span></span>

<span data-ttu-id="cd5a6-127">로 전달 될 수 있는 플래그는 `lEnumFlags` 인수에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드.</span><span class="sxs-lookup"><span data-stu-id="cd5a6-127">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>

|<span data-ttu-id="cd5a6-128">상수</span><span class="sxs-lookup"><span data-stu-id="cd5a6-128">Constant</span></span>  |<span data-ttu-id="cd5a6-129">값</span><span class="sxs-lookup"><span data-stu-id="cd5a6-129">Value</span></span>  |<span data-ttu-id="cd5a6-130">설명</span><span class="sxs-lookup"><span data-stu-id="cd5a6-130">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="cd5a6-131">0</span><span class="sxs-lookup"><span data-stu-id="cd5a6-131">0</span></span> | <span data-ttu-id="cd5a6-132">모든 한정자의 이름을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd5a6-132">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="cd5a6-133">0x10</span><span class="sxs-lookup"><span data-stu-id="cd5a6-133">0x10</span></span> | <span data-ttu-id="cd5a6-134">현재 속성 또는 개체에 특정 한정자의 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd5a6-134">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="cd5a6-135">속성: (재정의 포함), 속성에 특정 한정자만 및 클래스 정의에서 전파 하는 한정자에 하지를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd5a6-135">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="cd5a6-136">인스턴스: 인스턴스별 한정자 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd5a6-136">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="cd5a6-137">클래스: 파생 클래스에 특정 한정자만를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd5a6-137">For a class: Return only qualifiers specific to the class being derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="cd5a6-138">0x20</span><span class="sxs-lookup"><span data-stu-id="cd5a6-138">0x20</span></span> | <span data-ttu-id="cd5a6-139">반환이 한정자의 이름에만 전파 다른 개체에서입니다.</span><span class="sxs-lookup"><span data-stu-id="cd5a6-139">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="cd5a6-140">속성: 한정자만 전파이 속성에서 반환 클래스 정의와 속성 자체에서 해당 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd5a6-140">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="cd5a6-141">인스턴스: 클래스 정의에서 이러한 한정자만 전파 반환 이면입니다.</span><span class="sxs-lookup"><span data-stu-id="cd5a6-141">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="cd5a6-142">클래스: 부모 클래스에서 상속 한정자 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd5a6-142">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="cd5a6-143">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cd5a6-143">Requirements</span></span>

<span data-ttu-id="cd5a6-144">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cd5a6-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="cd5a6-145">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="cd5a6-145">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="cd5a6-146">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="cd5a6-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="cd5a6-147">참고자료</span><span class="sxs-lookup"><span data-stu-id="cd5a6-147">See also</span></span>

- [<span data-ttu-id="cd5a6-148">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="cd5a6-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)