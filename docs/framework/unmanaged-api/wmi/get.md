---
title: Get 함수 (관리 되지 않는 API 참조)
description: Get 함수는 지정 된 속성 값을 검색 합니다.
ms.date: 11/06/2017
api_name:
- Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Get
helpviewer_keywords:
- Get function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 7cc0c285f79b2791863fce251e4683aa7b55341b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553690"
---
# <a name="get-function"></a><span data-ttu-id="86695-103">Get 함수</span><span class="sxs-lookup"><span data-stu-id="86695-103">Get function</span></span>

<span data-ttu-id="86695-104">지정 된 속성 값이 있는 경우 해당 값을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="86695-104">Retrieves the specified property value if it exists.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="86695-105">구문</span><span class="sxs-lookup"><span data-stu-id="86695-105">Syntax</span></span>

```cpp
HRESULT Get (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor
);
```

## <a name="parameters"></a><span data-ttu-id="86695-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="86695-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="86695-107">진행 이 매개 변수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86695-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="86695-108">진행 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="86695-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="86695-109">진행 속성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="86695-109">[in] The name of the property.</span></span>

`lFlags`\
<span data-ttu-id="86695-110">[in] 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86695-110">[in] Reserved.</span></span> <span data-ttu-id="86695-111">이 매개 변수는 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86695-111">This parameter must be 0.</span></span>

`pVal`\
<span data-ttu-id="86695-112">제한이 함수가 성공적으로 반환 되 면에는 속성 값이 포함 `wszName` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86695-112">[out] If the function returns successfully, contains the value of the `wszName` property.</span></span> <span data-ttu-id="86695-113">`pval`인수에 올바른 형식과 한정자의 값이 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86695-113">The `pval` argument is assigned the correct type and value for the qualifier.</span></span>

`pvtType`\
<span data-ttu-id="86695-114">제한이 함수가 성공적으로 반환 되 면에는 속성 형식을 나타내는 [CIM 형식 상수가](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86695-114">[out] If the function returns successfully, contains a [CIM-type constant](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) that indicates the property type.</span></span> <span data-ttu-id="86695-115">값은 일 수도 있습니다 `null` .</span><span class="sxs-lookup"><span data-stu-id="86695-115">Its value can also be `null`.</span></span>

`plFlavor`\
<span data-ttu-id="86695-116">제한이 함수가 성공적으로 반환 되 면는 속성의 원본에 대 한 정보를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="86695-116">[out] If the function returns successfully, receives information about the origin of the property.</span></span> <span data-ttu-id="86695-117">해당 값은 `null` *WbemCli* 헤더 파일에 정의 된 다음 WBEM_FLAVOR_TYPE 상수 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86695-117">Its value can be `null`, or one of the following WBEM_FLAVOR_TYPE constants defined in the *WbemCli.h* header file:</span></span>

|<span data-ttu-id="86695-118">상수</span><span class="sxs-lookup"><span data-stu-id="86695-118">Constant</span></span>  |<span data-ttu-id="86695-119">값</span><span class="sxs-lookup"><span data-stu-id="86695-119">Value</span></span>  |<span data-ttu-id="86695-120">Description</span><span class="sxs-lookup"><span data-stu-id="86695-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="86695-121">0x40</span><span class="sxs-lookup"><span data-stu-id="86695-121">0x40</span></span> | <span data-ttu-id="86695-122">속성은 표준 시스템 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="86695-122">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="86695-123">0x20</span><span class="sxs-lookup"><span data-stu-id="86695-123">0x20</span></span> | <span data-ttu-id="86695-124">클래스의 경우: 속성은 부모 클래스에서 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86695-124">For a class: The property is inherited from the parent class.</span></span> <br> <span data-ttu-id="86695-125">인스턴스의 경우: 부모 클래스에서 상속 된 속성은 인스턴스에 의해 수정 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="86695-125">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="86695-126">0</span><span class="sxs-lookup"><span data-stu-id="86695-126">0</span></span> | <span data-ttu-id="86695-127">클래스의 경우: 속성이 파생 클래스에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="86695-127">For a class: The property belongs to the derived class.</span></span> <br> <span data-ttu-id="86695-128">인스턴스의 경우: 속성은 인스턴스에 의해 수정 됩니다. 즉, 값을 제공 했거나 한정자를 추가 하거나 수정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="86695-128">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="return-value"></a><span data-ttu-id="86695-129">반환 값</span><span class="sxs-lookup"><span data-stu-id="86695-129">Return value</span></span>

<span data-ttu-id="86695-130">이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86695-130">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="86695-131">상수</span><span class="sxs-lookup"><span data-stu-id="86695-131">Constant</span></span>  |<span data-ttu-id="86695-132">값</span><span class="sxs-lookup"><span data-stu-id="86695-132">Value</span></span>  |<span data-ttu-id="86695-133">Description</span><span class="sxs-lookup"><span data-stu-id="86695-133">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="86695-134">0x80041001</span><span class="sxs-lookup"><span data-stu-id="86695-134">0x80041001</span></span> | <span data-ttu-id="86695-135">일반 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="86695-135">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="86695-136">0x80041008</span><span class="sxs-lookup"><span data-stu-id="86695-136">0x80041008</span></span> | <span data-ttu-id="86695-137">하나 이상의 매개 변수가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86695-137">One or more parameters are not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="86695-138">0x80041002</span><span class="sxs-lookup"><span data-stu-id="86695-138">0x80041002</span></span> | <span data-ttu-id="86695-139">지정 된 속성을 찾을 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="86695-139">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="86695-140">0x80041006</span><span class="sxs-lookup"><span data-stu-id="86695-140">0x80041006</span></span> | <span data-ttu-id="86695-141">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="86695-141">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="86695-142">0</span><span class="sxs-lookup"><span data-stu-id="86695-142">0</span></span> | <span data-ttu-id="86695-143">함수 호출에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="86695-143">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="86695-144">설명</span><span class="sxs-lookup"><span data-stu-id="86695-144">Remarks</span></span>

<span data-ttu-id="86695-145">이 함수는 [IWbemClassObject:: Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="86695-145">This function wraps a call to the [IWbemClassObject::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) method.</span></span>

<span data-ttu-id="86695-146">`Get`함수는 시스템 속성을 반환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86695-146">The `Get` function can also return system properties.</span></span>

<span data-ttu-id="86695-147">`pVal`인수에는 한정자와 COM [VariantInit](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) 함수에 대 한 올바른 형식 및 값이 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86695-147">The `pVal` argument is assigned the correct type and value for the qualifier and the COM [VariantInit](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) function</span></span>

## <a name="requirements"></a><span data-ttu-id="86695-148">요구 사항</span><span class="sxs-lookup"><span data-stu-id="86695-148">Requirements</span></span>

 <span data-ttu-id="86695-149">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="86695-149">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="86695-150">**헤더:** WMINet_Utils idl</span><span class="sxs-lookup"><span data-stu-id="86695-150">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="86695-151">**.NET Framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="86695-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="86695-152">참조</span><span class="sxs-lookup"><span data-stu-id="86695-152">See also</span></span>

- [<span data-ttu-id="86695-153">WMI 및 성능 카운터(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="86695-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
