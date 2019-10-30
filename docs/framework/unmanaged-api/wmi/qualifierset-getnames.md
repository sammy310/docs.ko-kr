---
title: QualifierSet_GetNames 함수 (관리 되지 않는 API 참조)
description: QualifierSet_GetNames 함수는 개체 또는 속성에서 한정자의 이름을 검색 합니다.
ms.date: 11/06/2017
api_name:
- QualifierSet_GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_GetNames
helpviewer_keywords:
- QualifierSet_GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: bd0a67987dd8ffa825114726d066249aed40cf05
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141697"
---
# <a name="qualifierset_getnames-function"></a><span data-ttu-id="5cfc6-103">QualifierSet_GetNames 함수</span><span class="sxs-lookup"><span data-stu-id="5cfc6-103">QualifierSet_GetNames function</span></span>

<span data-ttu-id="5cfc6-104">현재 개체 또는 속성에서 사용할 수 있는 모든 한정자 또는 특정 한정자의 이름을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cfc6-104">Retrieves the names of all the qualifiers or of certain qualifiers that are available from the current object or property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="5cfc6-105">구문</span><span class="sxs-lookup"><span data-stu-id="5cfc6-105">Syntax</span></span>

```cpp
HRESULT QualifierSet_GetNames (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags,
   [out] SAFEARRAY (BSTR)**  pstrNames
);
```

## <a name="parameters"></a><span data-ttu-id="5cfc6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5cfc6-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="5cfc6-107">진행 이 매개 변수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5cfc6-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="5cfc6-108">진행 [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5cfc6-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`\
<span data-ttu-id="5cfc6-109">진행 열거형에 포함할 이름을 지정 하는 다음 플래그 또는 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="5cfc6-109">[in] One of the following flags or values that specifies which names to include in the enumeration.</span></span>

|<span data-ttu-id="5cfc6-110">상수</span><span class="sxs-lookup"><span data-stu-id="5cfc6-110">Constant</span></span>  |<span data-ttu-id="5cfc6-111">값</span><span class="sxs-lookup"><span data-stu-id="5cfc6-111">Value</span></span>  |<span data-ttu-id="5cfc6-112">설명</span><span class="sxs-lookup"><span data-stu-id="5cfc6-112">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="5cfc6-113">0</span><span class="sxs-lookup"><span data-stu-id="5cfc6-113">0</span></span> | <span data-ttu-id="5cfc6-114">모든 한정자의 이름을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cfc6-114">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="5cfc6-115">0x10</span><span class="sxs-lookup"><span data-stu-id="5cfc6-115">0x10</span></span> | <span data-ttu-id="5cfc6-116">현재 속성 또는 개체와 관련 된 한정자의 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cfc6-116">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="5cfc6-117">속성의 경우: 클래스 정의에서 전파 되는 한정자가 아니라 속성 (재정의 포함)에 한정 된 한정자만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cfc6-117">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="5cfc6-118">인스턴스의 경우: 인스턴스 전용 한정자 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cfc6-118">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="5cfc6-119">클래스의 경우: 파생 되는 클래스와 관련 된 한정자만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cfc6-119">For a class: Return only qualifiers specific to the class being derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="5cfc6-120">0x20</span><span class="sxs-lookup"><span data-stu-id="5cfc6-120">0x20</span></span> | <span data-ttu-id="5cfc6-121">다른 개체에서 전파 된 한정자의 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cfc6-121">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="5cfc6-122">속성의 경우: 클래스 정의에서이 속성에 전파 된 한정자만 반환 하 고 속성 자체의 한정자는 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5cfc6-122">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="5cfc6-123">인스턴스의 경우: 클래스 정의에서 전파 된 한정자만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cfc6-123">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="5cfc6-124">클래스의 경우: 부모 클래스에서 상속 된 한정자 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cfc6-124">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

`pstrNames`\
<span data-ttu-id="5cfc6-125">제한이 요청 된 이름을 포함 하는 새 `SAFEARRAY`입니다.</span><span class="sxs-lookup"><span data-stu-id="5cfc6-125">[out] A new `SAFEARRAY` that contains the requested names.</span></span> <span data-ttu-id="5cfc6-126">배열에는 요소가 0 개 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cfc6-126">The array can have 0 elements.</span></span> <span data-ttu-id="5cfc6-127">오류가 발생 하면 새 `SAFEARRAY` 반환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5cfc6-127">If an error occurs, a new `SAFEARRAY` is not returned.</span></span>

## <a name="return-value"></a><span data-ttu-id="5cfc6-128">반환 값</span><span class="sxs-lookup"><span data-stu-id="5cfc6-128">Return value</span></span>

<span data-ttu-id="5cfc6-129">이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cfc6-129">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="5cfc6-130">상수</span><span class="sxs-lookup"><span data-stu-id="5cfc6-130">Constant</span></span>  |<span data-ttu-id="5cfc6-131">값</span><span class="sxs-lookup"><span data-stu-id="5cfc6-131">Value</span></span>  |<span data-ttu-id="5cfc6-132">설명</span><span class="sxs-lookup"><span data-stu-id="5cfc6-132">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="5cfc6-133">0x80041008</span><span class="sxs-lookup"><span data-stu-id="5cfc6-133">0x80041008</span></span> | <span data-ttu-id="5cfc6-134">매개 변수가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5cfc6-134">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="5cfc6-135">0x80041006</span><span class="sxs-lookup"><span data-stu-id="5cfc6-135">0x80041006</span></span> | <span data-ttu-id="5cfc6-136">메모리가 부족 하 여 새 열거를 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5cfc6-136">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="5cfc6-137">0</span><span class="sxs-lookup"><span data-stu-id="5cfc6-137">0</span></span> | <span data-ttu-id="5cfc6-138">함수 호출에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5cfc6-138">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="5cfc6-139">주의</span><span class="sxs-lookup"><span data-stu-id="5cfc6-139">Remarks</span></span>

<span data-ttu-id="5cfc6-140">이 함수는 [IWbemQualifierSet:: GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="5cfc6-140">This function wraps a call to the [IWbemQualifierSet::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames) method.</span></span>

<span data-ttu-id="5cfc6-141">한정자 이름을 검색 한 후에는 [QualifierSet_Get](qualifierset-get.md) 함수를 호출 하 여 이름별로 각 한정자에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cfc6-141">Once you've retrieved the qualifier names, you can access each qualifier by name by calling the [QualifierSet_Get](qualifierset-get.md) function.</span></span>

<span data-ttu-id="5cfc6-142">지정 된 개체의 한정자가 0이 아니므로 함수에서 `WBEM_S_NO_ERROR`반환 하더라도 반환 시 `pstrNames`의 문자열 수가 0이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cfc6-142">It is not an error for a given object to have zero qualifiers, so the number of strings in `pstrNames` on return can be 0, even though the function returns `WBEM_S_NO_ERROR`.</span></span>

## <a name="requirements"></a><span data-ttu-id="5cfc6-143">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5cfc6-143">Requirements</span></span>

<span data-ttu-id="5cfc6-144">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5cfc6-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="5cfc6-145">**헤더:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="5cfc6-145">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="5cfc6-146">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5cfc6-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5cfc6-147">참조</span><span class="sxs-lookup"><span data-stu-id="5cfc6-147">See also</span></span>

- [<span data-ttu-id="5cfc6-148">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="5cfc6-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
