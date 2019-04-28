---
title: Put 함수 (관리 되지 않는 API 참조)
description: Put 함수는 명명 된 속성에 새 값을 할당합니다.
ms.date: 11/06/2017
api_name:
- Put
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Put
helpviewer_keywords:
- Put function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 02c8ab3aa7fcc603b76fb4b1d09e7e73d04494be
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61749022"
---
# <a name="put-function"></a><span data-ttu-id="b579e-103">Put 함수</span><span class="sxs-lookup"><span data-stu-id="b579e-103">Put function</span></span>

<span data-ttu-id="b579e-104">명명된 속성을 새 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b579e-104">Sets a named property to a new value.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="b579e-105">구문</span><span class="sxs-lookup"><span data-stu-id="b579e-105">Syntax</span></span>

```cpp
HRESULT Put (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [in] VARIANT*          pVal,
   [in] CIMTYPE           vtType
);
```

## <a name="parameters"></a><span data-ttu-id="b579e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b579e-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="b579e-107">[in] 이 매개 변수 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b579e-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="b579e-108">[in] 에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="b579e-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="b579e-109">[in] 속성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b579e-109">[in] The name of the property.</span></span> <span data-ttu-id="b579e-110">이 매개 변수 수 없습니다 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="b579e-110">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="b579e-111">[in] 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b579e-111">[in] Reserved.</span></span> <span data-ttu-id="b579e-112">이 매개 변수는 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b579e-112">This parameter must be 0.</span></span>

`pVal`\
<span data-ttu-id="b579e-113">[in] 유효한 포인터 `VARIANT` 는 새 속성 값이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b579e-113">[in] A pointer to a valid `VARIANT` that becomes the new property value.</span></span> <span data-ttu-id="b579e-114">경우 `pVal` 됩니다 `null` 가리키는 또는 `VARIANT` 형식의 `VT_NULL`, 속성이 설정 되어 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="b579e-114">If `pVal` is `null` or points to a `VARIANT` of type `VT_NULL`, the property is set to `null`.</span></span>

`vtType`\
<span data-ttu-id="b579e-115">[in] 유형의 `VARIANT` 가리키는 `pVal`합니다.</span><span class="sxs-lookup"><span data-stu-id="b579e-115">[in] The type of `VARIANT` pointed to by `pVal`.</span></span> <span data-ttu-id="b579e-116">참조 된 [주의](#remarks) 자세한 내용은 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="b579e-116">See the [Remarks](#remarks) section for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="b579e-117">반환 값</span><span class="sxs-lookup"><span data-stu-id="b579e-117">Return value</span></span>

<span data-ttu-id="b579e-118">이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="b579e-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b579e-119">상수</span><span class="sxs-lookup"><span data-stu-id="b579e-119">Constant</span></span>  |<span data-ttu-id="b579e-120">값</span><span class="sxs-lookup"><span data-stu-id="b579e-120">Value</span></span>  |<span data-ttu-id="b579e-121">설명</span><span class="sxs-lookup"><span data-stu-id="b579e-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="b579e-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="b579e-122">0x80041001</span></span> | <span data-ttu-id="b579e-123">일반 오류가 발생이 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b579e-123">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="b579e-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="b579e-124">0x80041008</span></span> | <span data-ttu-id="b579e-125">하나 이상의 매개 변수가 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b579e-125">One or more parameters are not valid.</span></span> |
|`WBEM_E_INVALID_PROPERTY_TYPE` | <span data-ttu-id="b579e-126">0x8004102a</span><span class="sxs-lookup"><span data-stu-id="b579e-126">0x8004102a</span></span> | <span data-ttu-id="b579e-127">속성 형식이 인식 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b579e-127">The property type is not recognized.</span></span> <span data-ttu-id="b579e-128">클래스가 이미 존재 하는 경우 클래스 인스턴스를 만들 때이 값이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b579e-128">This value is returned when creating class instances if the class already exists.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="b579e-129">0x80041006</span><span class="sxs-lookup"><span data-stu-id="b579e-129">0x80041006</span></span> | <span data-ttu-id="b579e-130">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b579e-130">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="b579e-131">0x80041005</span><span class="sxs-lookup"><span data-stu-id="b579e-131">0x80041005</span></span> | <span data-ttu-id="b579e-132">에 대 한 인스턴스: 함을 `pVal` 가리키는 `VARIANT` 속성에 대 한 잘못 된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b579e-132">For instances: Indicates that `pVal` points to a `VARIANT` of an incorrect type for the property.</span></span> <br/> <span data-ttu-id="b579e-133">클래스 정의: 속성이 부모 클래스에 이미 있습니다. 및 새 COM 형식은 이전 COM 유형과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b579e-133">For class definitions: The property already exists in the parent class, and the new COM type is different from the old COM type.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="b579e-134">0</span><span class="sxs-lookup"><span data-stu-id="b579e-134">0</span></span> | <span data-ttu-id="b579e-135">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b579e-135">The function call was successful.</span></span> |

## <a name="remarks"></a><span data-ttu-id="b579e-136">설명</span><span class="sxs-lookup"><span data-stu-id="b579e-136">Remarks</span></span>

<span data-ttu-id="b579e-137">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) 메서드.</span><span class="sxs-lookup"><span data-stu-id="b579e-137">This function wraps a call to the [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) method.</span></span>

<span data-ttu-id="b579e-138">이 함수는 항상 새 리소스를 사용 하 여 현재 속성 값을 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="b579e-138">This function always overwrites the current property value with a new one.</span></span> <span data-ttu-id="b579e-139">경우는 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 클래스 정의 가리키는 `Put` 만들거나 속성 값을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="b579e-139">If the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) points to a class definition, `Put` creates or updates the property value.</span></span> <span data-ttu-id="b579e-140">때 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) CIM 인스턴스를 가리키는 `Put` 만; 속성 값을 업데이트 합니다. `Put` 속성 값을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b579e-140">When [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) points to a CIM instance, `Put` updates the property value only; `Put` cannot create a property value.</span></span>

<span data-ttu-id="b579e-141">`__CLASS` 시스템 속성은 쓰기 가능한 클래스를 만드는 동안 경우에 해당 하지 비어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b579e-141">The `__CLASS` system property is only writable during class creation, when it may not be left blank.</span></span> <span data-ttu-id="b579e-142">다른 모든 시스템 속성은 읽기 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="b579e-142">All other system properties are read-only.</span></span>

<span data-ttu-id="b579e-143">사용자 이름이 밑줄 ("_")으로 시작 하거나 끝날 하는 속성을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b579e-143">A user cannot create properties with names that begin or end with an underscore ("_").</span></span> <span data-ttu-id="b579e-144">이 시스템 클래스 및 속성에 대해 예약 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b579e-144">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="b579e-145">속성으로 설정 하는 경우는 `Put` 함수가 있는 부모 클래스, 부모 클래스 유형 속성 형식에 맞지 않으면 속성의 기본 값이 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b579e-145">If the property set by the `Put` function exists in the parent class, the default value of the property is changed unless the property type does not match the parent class type.</span></span> <span data-ttu-id="b579e-146">속성이 존재 하지 않습니다 하 고 형식이 일치 하지 않습니다, 경우 속성이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="b579e-146">If the property does not exist and it is not a type mismatch, the property is created.</span></span>

<span data-ttu-id="b579e-147">사용 하 여는 `vtType` CIM 클래스 정의에 새 속성을 만드는 경우에 매개 변수 및 `pVal` 됩니다 `null` 가리키는 또는 `VARIANT` 형식의 `VT_NULL`합니다.</span><span class="sxs-lookup"><span data-stu-id="b579e-147">Use the `vtType` parameter only when creating new properties in a CIM class definition and `pVal` is `null` or points to a `VARIANT` of type `VT_NULL`.</span></span> <span data-ttu-id="b579e-148">이 경우에 `vType` 매개 변수 속성의 CIM 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b579e-148">In this case, the `vType` parameter specifies the CIM type of the property.</span></span> <span data-ttu-id="b579e-149">다른 모든 경우에서 `vtType` 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b579e-149">In every other case, `vtType` must be 0.</span></span> <span data-ttu-id="b579e-150">`vtType` 기본 개체 인스턴스이면 0 수도 있어야 합니다 (경우에 `Val` 는 `null`) 속성의 형식 고정 되어 변경할 수 없으므로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b579e-150">`vtType` must also be 0 if the underlying object is an instance (even if `Val` is `null`) because the type of the property is fixed and cannot be changed.</span></span>

## <a name="example"></a><span data-ttu-id="b579e-151">예제</span><span class="sxs-lookup"><span data-stu-id="b579e-151">Example</span></span>

<span data-ttu-id="b579e-152">예를 들어 참조 된 [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) 메서드.</span><span class="sxs-lookup"><span data-stu-id="b579e-152">For an example, see the [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="b579e-153">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b579e-153">Requirements</span></span>

<span data-ttu-id="b579e-154">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b579e-154">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="b579e-155">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b579e-155">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="b579e-156">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b579e-156">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b579e-157">참고자료</span><span class="sxs-lookup"><span data-stu-id="b579e-157">See also</span></span>

- [<span data-ttu-id="b579e-158">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="b579e-158">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)