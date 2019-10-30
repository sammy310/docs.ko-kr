---
title: QualifierSet_Put 함수 (관리 되지 않는 API 참조)
description: QualifierSet_Put 함수는 명명 된 한정자와 해당 값을 씁니다.
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
ms.openlocfilehash: a35025c6d16455a51b7b22d822ba77337ddd894a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120228"
---
# <a name="qualifierset_put-function"></a><span data-ttu-id="5173e-103">QualifierSet_Put 함수</span><span class="sxs-lookup"><span data-stu-id="5173e-103">QualifierSet_Put function</span></span>

<span data-ttu-id="5173e-104">명명된 한정자 및 값을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="5173e-104">Writes the named qualifier and value.</span></span> <span data-ttu-id="5173e-105">새 한정자는 동일한 이름의 이전 값을 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="5173e-105">The new qualifier overwrites the previous value of the same name.</span></span> <span data-ttu-id="5173e-106">한정자가 없으면 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5173e-106">If the qualifier does not exist, it is created.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="5173e-107">구문</span><span class="sxs-lookup"><span data-stu-id="5173e-107">Syntax</span></span>

```cpp
HRESULT QualifierSet_Put (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LPCWSTR              wszName,
   [in] VARIANT*             pVal,
   [in] LONG                 lFlavor
);
```

## <a name="parameters"></a><span data-ttu-id="5173e-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5173e-108">Parameters</span></span>

`vFunc`\
<span data-ttu-id="5173e-109">진행 이 매개 변수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5173e-109">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="5173e-110">진행 [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5173e-110">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`wszName`\
<span data-ttu-id="5173e-111">진행 쓸 한정자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5173e-111">[in] The name of the qualifier to write.</span></span>

`pVal`\
<span data-ttu-id="5173e-112">진행 쓸 한정자를 포함 하는 유효한 `VARIANT`에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5173e-112">[in] A pointer to a valid `VARIANT` that contains the qualifier to write.</span></span> <span data-ttu-id="5173e-113">이 매개 변수를 `null`수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5173e-113">This parameter cannot be `null`.</span></span>

`lFlavor`\
<span data-ttu-id="5173e-114">진행 이 한정자에 대 한 원하는 한정자 특색을 정의 하는 다음 상수 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="5173e-114">[in] One of the following constants that defines the desired qualifier flavors for this qualifier.</span></span> <span data-ttu-id="5173e-115">기본값은 `WBEM_FLAVOR_OVERRIDABLE` (0)입니다.</span><span class="sxs-lookup"><span data-stu-id="5173e-115">The default value is `WBEM_FLAVOR_OVERRIDABLE` (0).</span></span>

|<span data-ttu-id="5173e-116">상수</span><span class="sxs-lookup"><span data-stu-id="5173e-116">Constant</span></span>  |<span data-ttu-id="5173e-117">값</span><span class="sxs-lookup"><span data-stu-id="5173e-117">Value</span></span>  |<span data-ttu-id="5173e-118">설명</span><span class="sxs-lookup"><span data-stu-id="5173e-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_OVERRIDABLE` | <span data-ttu-id="5173e-119">0</span><span class="sxs-lookup"><span data-stu-id="5173e-119">0</span></span> | <span data-ttu-id="5173e-120">한정자는 파생 된 클래스 또는 인스턴스에서 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5173e-120">The qualifier can be overridden in a derived class or instance.</span></span> <span data-ttu-id="5173e-121">**이 값은 기본값입니다.**</span><span class="sxs-lookup"><span data-stu-id="5173e-121">**This is the default value.**</span></span> |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_INSTANCE` | <span data-ttu-id="5173e-122">1</span><span class="sxs-lookup"><span data-stu-id="5173e-122">1</span></span> | <span data-ttu-id="5173e-123">한정자가 인스턴스로 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="5173e-123">The qualifier is propagated to instances.</span></span> |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_DERIVED_CLASS` | <span data-ttu-id="5173e-124">2</span><span class="sxs-lookup"><span data-stu-id="5173e-124">2</span></span> | <span data-ttu-id="5173e-125">한정자는 파생 클래스에 전파 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5173e-125">The qualifier is propagated to derived classes.</span></span> |
| `WBEM_FLAVOR_NOT_OVERRIDABLE` | <span data-ttu-id="5173e-126">0x10</span><span class="sxs-lookup"><span data-stu-id="5173e-126">0x10</span></span> | <span data-ttu-id="5173e-127">한정자를 파생된 클래스 또는 인스턴스에서 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5173e-127">The qualifier cannot be overridden in a derived class or instance.</span></span> |
| `WBEM_FLAVOR_AMENDED` | <span data-ttu-id="5173e-128">0x80</span><span class="sxs-lookup"><span data-stu-id="5173e-128">0x80</span></span> | <span data-ttu-id="5173e-129">한정자는 지역화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5173e-129">The qualifier is localized.</span></span> |

## <a name="return-value"></a><span data-ttu-id="5173e-130">반환 값</span><span class="sxs-lookup"><span data-stu-id="5173e-130">Return value</span></span>

<span data-ttu-id="5173e-131">이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5173e-131">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="5173e-132">상수</span><span class="sxs-lookup"><span data-stu-id="5173e-132">Constant</span></span>  |<span data-ttu-id="5173e-133">값</span><span class="sxs-lookup"><span data-stu-id="5173e-133">Value</span></span>  |<span data-ttu-id="5173e-134">설명</span><span class="sxs-lookup"><span data-stu-id="5173e-134">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_CANNOT_BE_KEY` | <span data-ttu-id="5173e-135">0x8004101f</span><span class="sxs-lookup"><span data-stu-id="5173e-135">0x8004101f</span></span> | <span data-ttu-id="5173e-136">키가 될 수 없는 속성에 **키** 한정자를 지정 하는 잘못 된 시도가 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="5173e-136">There was an illegal attempt to specify the **Key** qualifier on a property that cannot be a key.</span></span> <span data-ttu-id="5173e-137">키는 개체에 대 한 클래스 정의에 지정 되며 인스턴스별 으로만 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5173e-137">The keys are specified in the class definition for an object and cannot be altered on a per-instance basis.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="5173e-138">0x80041008</span><span class="sxs-lookup"><span data-stu-id="5173e-138">0x80041008</span></span> | <span data-ttu-id="5173e-139">매개 변수가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5173e-139">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_QUALIFIER_TYPE` | <span data-ttu-id="5173e-140">0x80041029</span><span class="sxs-lookup"><span data-stu-id="5173e-140">0x80041029</span></span> | <span data-ttu-id="5173e-141">`pVal` 매개 변수가 올바른 한정자 형식이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="5173e-141">The `pVal` parameter is not of a legal qualifier type.</span></span> |
| `WBEM_E_OVERRIDE_NOT_ALLOWED` | <span data-ttu-id="5173e-142">0x8004101a</span><span class="sxs-lookup"><span data-stu-id="5173e-142">0x8004101a</span></span> | <span data-ttu-id="5173e-143">소유 하는 개체가 재정의를 허용 하지 않으므로 한정자에서 `QualifierSet_Put` 메서드를 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5173e-143">It is not possible to call the `QualifierSet_Put` method on the qualifier because the owning object does not permit overrides.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="5173e-144">0</span><span class="sxs-lookup"><span data-stu-id="5173e-144">0</span></span> | <span data-ttu-id="5173e-145">함수 호출에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5173e-145">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="5173e-146">주의</span><span class="sxs-lookup"><span data-stu-id="5173e-146">Remarks</span></span>

<span data-ttu-id="5173e-147">이 함수는 [IWbemQualifierSet::P 세계](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-put) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="5173e-147">This function wraps a call to the [IWbemQualifierSet::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-put) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="5173e-148">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5173e-148">Requirements</span></span>

<span data-ttu-id="5173e-149">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5173e-149">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="5173e-150">**헤더:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="5173e-150">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="5173e-151">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5173e-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5173e-152">참조</span><span class="sxs-lookup"><span data-stu-id="5173e-152">See also</span></span>

- [<span data-ttu-id="5173e-153">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="5173e-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
