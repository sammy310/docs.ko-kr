---
title: QualifierSet_Put 함수 (관리 되지 않는 API 참조)
description: QualifierSet_Put 함수는 명명된 된 한정자 및 값을 씁니다.
ms.date: 11/06/2017
api_name:
- QualifierSet_Put
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Put
helpviewer_keywords:
- QualifierSet_Put function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e42cf3440bef030f5c7bec71ed1b4b875b79a61
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378838"
---
# <a name="qualifiersetput-function"></a><span data-ttu-id="b631d-103">QualifierSet_Put 함수</span><span class="sxs-lookup"><span data-stu-id="b631d-103">QualifierSet_Put function</span></span>

<span data-ttu-id="b631d-104">명명된 한정자 및 값을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="b631d-104">Writes the named qualifier and value.</span></span> <span data-ttu-id="b631d-105">새 한정자는 동일한 이름의 이전 값을 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="b631d-105">The new qualifier overwrites the previous value of the same name.</span></span> <span data-ttu-id="b631d-106">한정자가 없으면 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="b631d-106">If the qualifier does not exist, it is created.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="b631d-107">구문</span><span class="sxs-lookup"><span data-stu-id="b631d-107">Syntax</span></span>

```cpp
HRESULT QualifierSet_Put (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LPCWSTR              wszName,
   [in] VARIANT*             pVal,
   [in] LONG                 lFlavor
);
```

## <a name="parameters"></a><span data-ttu-id="b631d-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b631d-108">Parameters</span></span>

`vFunc`\
<span data-ttu-id="b631d-109">[in] 이 매개 변수 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b631d-109">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="b631d-110">[in] 에 대 한 포인터를 [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="b631d-110">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`wszName`\
<span data-ttu-id="b631d-111">[in] 작성 하는 데 사용할 한정자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b631d-111">[in] The name of the qualifier to write.</span></span>

`pVal`\
<span data-ttu-id="b631d-112">[in] 유효한 포인터 `VARIANT` 작성 하는 데 사용할 한정자를 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="b631d-112">[in] A pointer to a valid `VARIANT` that contains the qualifier to write.</span></span> <span data-ttu-id="b631d-113">이 매개 변수 수 없습니다 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="b631d-113">This parameter cannot be `null`.</span></span>

`lFlavor`\
<span data-ttu-id="b631d-114">[in] 이 한정자에 대 한 원하는 한정자 특성을 정의 하는 다음 상수 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="b631d-114">[in] One of the following constants that defines the desired qualifier flavors for this qualifier.</span></span> <span data-ttu-id="b631d-115">기본값은 `WBEM_FLAVOR_OVERRIDABLE`(0)입니다.</span><span class="sxs-lookup"><span data-stu-id="b631d-115">The default value is `WBEM_FLAVOR_OVERRIDABLE` (0).</span></span>

|<span data-ttu-id="b631d-116">상수</span><span class="sxs-lookup"><span data-stu-id="b631d-116">Constant</span></span>  |<span data-ttu-id="b631d-117">값</span><span class="sxs-lookup"><span data-stu-id="b631d-117">Value</span></span>  |<span data-ttu-id="b631d-118">설명</span><span class="sxs-lookup"><span data-stu-id="b631d-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_OVERRIDABLE` | <span data-ttu-id="b631d-119">0</span><span class="sxs-lookup"><span data-stu-id="b631d-119">0</span></span> | <span data-ttu-id="b631d-120">한정자는 인스턴스나 파생된 클래스에서 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b631d-120">The qualifier can be overridden in a derived class or instance.</span></span> <span data-ttu-id="b631d-121">**이것이 기본값입니다.**</span><span class="sxs-lookup"><span data-stu-id="b631d-121">**This is the default value.**</span></span> |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_INSTANCE` | <span data-ttu-id="b631d-122">1</span><span class="sxs-lookup"><span data-stu-id="b631d-122">1</span></span> | <span data-ttu-id="b631d-123">한정자가 인스턴스로 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="b631d-123">The qualifier is propagated to instances.</span></span> |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_DERIVED_CLASS` | <span data-ttu-id="b631d-124">2</span><span class="sxs-lookup"><span data-stu-id="b631d-124">2</span></span> | <span data-ttu-id="b631d-125">한정자는 파생된 클래스에 전파 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b631d-125">The qualifier is propagated to derived classes.</span></span> |
| `WBEM_FLAVOR_NOT_OVERRIDABLE` | <span data-ttu-id="b631d-126">0x10</span><span class="sxs-lookup"><span data-stu-id="b631d-126">0x10</span></span> | <span data-ttu-id="b631d-127">한정자를 파생된 클래스 또는 인스턴스에서 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b631d-127">The qualifier cannot be overridden in a derived class or instance.</span></span> |
| `WBEM_FLAVOR_AMENDED` | <span data-ttu-id="b631d-128">0x80</span><span class="sxs-lookup"><span data-stu-id="b631d-128">0x80</span></span> | <span data-ttu-id="b631d-129">한정자 지역화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b631d-129">The qualifier is localized.</span></span> |

## <a name="return-value"></a><span data-ttu-id="b631d-130">반환 값</span><span class="sxs-lookup"><span data-stu-id="b631d-130">Return value</span></span>

<span data-ttu-id="b631d-131">이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="b631d-131">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b631d-132">상수</span><span class="sxs-lookup"><span data-stu-id="b631d-132">Constant</span></span>  |<span data-ttu-id="b631d-133">값</span><span class="sxs-lookup"><span data-stu-id="b631d-133">Value</span></span>  |<span data-ttu-id="b631d-134">설명</span><span class="sxs-lookup"><span data-stu-id="b631d-134">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_CANNOT_BE_KEY` | <span data-ttu-id="b631d-135">0x8004101f</span><span class="sxs-lookup"><span data-stu-id="b631d-135">0x8004101f</span></span> | <span data-ttu-id="b631d-136">지정 하려고 했습니다. 합니다 **키** 한정자 속성 키가 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b631d-136">There was an illegal attempt to specify the **Key** qualifier on a property that cannot be a key.</span></span> <span data-ttu-id="b631d-137">키를 지정 된 om c; 개체에 대 한 클래스 정의 인스턴스 당 단위로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b631d-137">The keys are specified om tje c;ass definition for an object and cannot be altered on a per-instance basis.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="b631d-138">0x80041008</span><span class="sxs-lookup"><span data-stu-id="b631d-138">0x80041008</span></span> | <span data-ttu-id="b631d-139">매개 변수가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b631d-139">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_QUALIFIER_TYPE` | <span data-ttu-id="b631d-140">0x80041029</span><span class="sxs-lookup"><span data-stu-id="b631d-140">0x80041029</span></span> | <span data-ttu-id="b631d-141">`pVal` 매개 변수가 올바른 한정자 형식이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b631d-141">The `pVal` parameter is not of a legal qualifier type.</span></span> |
| `WBEM_E_OVERRIDE_NOT_ALLOWED` | <span data-ttu-id="b631d-142">0x8004101a</span><span class="sxs-lookup"><span data-stu-id="b631d-142">0x8004101a</span></span> | <span data-ttu-id="b631d-143">호출 하는 것이 불가능 합니다 `QualifierSet_Put` 메서드 한정자를 소유 하는 개체는 허용 하지 않으므로 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b631d-143">It is not possible to call the `QualifierSet_Put` method on the qualifier because the owning object does not permit overrides.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="b631d-144">0</span><span class="sxs-lookup"><span data-stu-id="b631d-144">0</span></span> | <span data-ttu-id="b631d-145">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b631d-145">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="b631d-146">설명</span><span class="sxs-lookup"><span data-stu-id="b631d-146">Remarks</span></span>

<span data-ttu-id="b631d-147">이 함수에 대 한 호출을 래핑하는 [IWbemQualifierSet::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-put) 메서드.</span><span class="sxs-lookup"><span data-stu-id="b631d-147">This function wraps a call to the [IWbemQualifierSet::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-put) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="b631d-148">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b631d-148">Requirements</span></span>

<span data-ttu-id="b631d-149">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b631d-149">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="b631d-150">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b631d-150">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="b631d-151">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b631d-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b631d-152">참고자료</span><span class="sxs-lookup"><span data-stu-id="b631d-152">See also</span></span>

- [<span data-ttu-id="b631d-153">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="b631d-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)