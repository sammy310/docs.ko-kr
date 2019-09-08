---
title: Put 함수 (관리 되지 않는 API 참조)
description: Put 함수는 명명 된 속성에 새 값을 할당 합니다.
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
ms.openlocfilehash: 5aa629c2d07fb25db035cd80aba3c74413070e6e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798404"
---
# <a name="put-function"></a><span data-ttu-id="62f53-103">Put 함수</span><span class="sxs-lookup"><span data-stu-id="62f53-103">Put function</span></span>

<span data-ttu-id="62f53-104">명명된 속성을 새 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="62f53-104">Sets a named property to a new value.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="62f53-105">구문</span><span class="sxs-lookup"><span data-stu-id="62f53-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="62f53-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="62f53-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="62f53-107">진행 이 매개 변수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="62f53-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="62f53-108">진행 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="62f53-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="62f53-109">진행 속성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="62f53-109">[in] The name of the property.</span></span> <span data-ttu-id="62f53-110">이 매개 변수 수 없습니다 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="62f53-110">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="62f53-111">[in] 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62f53-111">[in] Reserved.</span></span> <span data-ttu-id="62f53-112">이 매개 변수는 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62f53-112">This parameter must be 0.</span></span>

`pVal`\
<span data-ttu-id="62f53-113">진행 새 속성 값이 되 `VARIANT` 는 유효한에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="62f53-113">[in] A pointer to a valid `VARIANT` that becomes the new property value.</span></span> <span data-ttu-id="62f53-114">`pVal` 가 이거나`null` 형식의 `VARIANT` 를 가리키면 속성이 로`null`설정 됩니다. `VT_NULL`</span><span class="sxs-lookup"><span data-stu-id="62f53-114">If `pVal` is `null` or points to a `VARIANT` of type `VT_NULL`, the property is set to `null`.</span></span>

`vtType`\
<span data-ttu-id="62f53-115">진행 `VARIANT` 가`pVal`가리키는의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="62f53-115">[in] The type of `VARIANT` pointed to by `pVal`.</span></span> <span data-ttu-id="62f53-116">자세한 내용은 [설명](#remarks) 부분을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="62f53-116">See the [Remarks](#remarks) section for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="62f53-117">반환 값</span><span class="sxs-lookup"><span data-stu-id="62f53-117">Return value</span></span>

<span data-ttu-id="62f53-118">이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62f53-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="62f53-119">상수</span><span class="sxs-lookup"><span data-stu-id="62f53-119">Constant</span></span>  |<span data-ttu-id="62f53-120">값</span><span class="sxs-lookup"><span data-stu-id="62f53-120">Value</span></span>  |<span data-ttu-id="62f53-121">Description</span><span class="sxs-lookup"><span data-stu-id="62f53-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="62f53-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="62f53-122">0x80041001</span></span> | <span data-ttu-id="62f53-123">일반 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="62f53-123">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="62f53-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="62f53-124">0x80041008</span></span> | <span data-ttu-id="62f53-125">하나 이상의 매개 변수가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="62f53-125">One or more parameters are not valid.</span></span> |
|`WBEM_E_INVALID_PROPERTY_TYPE` | <span data-ttu-id="62f53-126">0x8004102a</span><span class="sxs-lookup"><span data-stu-id="62f53-126">0x8004102a</span></span> | <span data-ttu-id="62f53-127">속성 형식이 인식 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="62f53-127">The property type is not recognized.</span></span> <span data-ttu-id="62f53-128">클래스가 이미 있는 경우 클래스 인스턴스를 만들 때이 값이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62f53-128">This value is returned when creating class instances if the class already exists.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="62f53-129">0x80041006</span><span class="sxs-lookup"><span data-stu-id="62f53-129">0x80041006</span></span> | <span data-ttu-id="62f53-130">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="62f53-130">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="62f53-131">0x80041005</span><span class="sxs-lookup"><span data-stu-id="62f53-131">0x80041005</span></span> | <span data-ttu-id="62f53-132">인스턴스의 경우: 가 `pVal` 속성에 대 한 `VARIANT` 잘못 된 형식의를 가리키는지 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="62f53-132">For instances: Indicates that `pVal` points to a `VARIANT` of an incorrect type for the property.</span></span> <br/> <span data-ttu-id="62f53-133">클래스 정의의 경우: 속성이 이미 부모 클래스에 있고 새 COM 형식이 이전 COM 형식과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="62f53-133">For class definitions: The property already exists in the parent class, and the new COM type is different from the old COM type.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="62f53-134">0</span><span class="sxs-lookup"><span data-stu-id="62f53-134">0</span></span> | <span data-ttu-id="62f53-135">함수 호출에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="62f53-135">The function call was successful.</span></span> |

## <a name="remarks"></a><span data-ttu-id="62f53-136">설명</span><span class="sxs-lookup"><span data-stu-id="62f53-136">Remarks</span></span>

<span data-ttu-id="62f53-137">이 함수는 [IWbemClassObject::P 세계](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="62f53-137">This function wraps a call to the [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) method.</span></span>

<span data-ttu-id="62f53-138">이 함수는 항상 현재 속성 값을 새 값으로 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="62f53-138">This function always overwrites the current property value with a new one.</span></span> <span data-ttu-id="62f53-139">[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 가 클래스 정의 `Put` 를 가리키는 경우 속성 값을 만들거나 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="62f53-139">If the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) points to a class definition, `Put` creates or updates the property value.</span></span> <span data-ttu-id="62f53-140">[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 가 CIM 인스턴스 `Put` 를 가리키면 속성 값만 업데이트 합니다. `Put` 속성 값을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="62f53-140">When [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) points to a CIM instance, `Put` updates the property value only; `Put` cannot create a property value.</span></span>

<span data-ttu-id="62f53-141">`__CLASS` 시스템 속성은 비워 둘 수 없는 경우 클래스를 만드는 동안에만 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62f53-141">The `__CLASS` system property is only writable during class creation, when it may not be left blank.</span></span> <span data-ttu-id="62f53-142">다른 모든 시스템 속성은 읽기 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="62f53-142">All other system properties are read-only.</span></span>

<span data-ttu-id="62f53-143">사용자는 이름이 밑줄 ("_")로 시작 하거나 끝나는 속성을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="62f53-143">A user cannot create properties with names that begin or end with an underscore ("_").</span></span> <span data-ttu-id="62f53-144">이는 시스템 클래스 및 속성에 대해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62f53-144">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="62f53-145">`Put` 함수에 의해 설정 된 속성이 부모 클래스에 있으면 속성 형식이 부모 클래스 형식과 일치 하지 않는 경우 속성의 기본값은 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62f53-145">If the property set by the `Put` function exists in the parent class, the default value of the property is changed unless the property type does not match the parent class type.</span></span> <span data-ttu-id="62f53-146">속성이 존재 하지 않고 형식이 일치 하지 않으면 속성이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62f53-146">If the property does not exist and it is not a type mismatch, the property is created.</span></span>

<span data-ttu-id="62f53-147">CIM 클래스 `vtType` `null` `VARIANT` `VT_NULL`정의에 새 속성을 만들고 가이거나형식의을가리키는경우에만매개변수를사용합니다.`pVal`</span><span class="sxs-lookup"><span data-stu-id="62f53-147">Use the `vtType` parameter only when creating new properties in a CIM class definition and `pVal` is `null` or points to a `VARIANT` of type `VT_NULL`.</span></span> <span data-ttu-id="62f53-148">이 경우 매개 변수는 `vType` 속성의 CIM 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="62f53-148">In this case, the `vType` parameter specifies the CIM type of the property.</span></span> <span data-ttu-id="62f53-149">다른 모든 경우는 `vtType` 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62f53-149">In every other case, `vtType` must be 0.</span></span> <span data-ttu-id="62f53-150">`vtType`속성의 형식이 고정 되어 있고 변경할 수 없으므로 기본 개체가 인스턴스인 `Val` `null`경우에도 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62f53-150">`vtType` must also be 0 if the underlying object is an instance (even if `Val` is `null`) because the type of the property is fixed and cannot be changed.</span></span>

## <a name="example"></a><span data-ttu-id="62f53-151">예제</span><span class="sxs-lookup"><span data-stu-id="62f53-151">Example</span></span>

<span data-ttu-id="62f53-152">예제를 보려면 [IWbemClassObject::P 세계](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) 메서드를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="62f53-152">For an example, see the [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="62f53-153">요구 사항</span><span class="sxs-lookup"><span data-stu-id="62f53-153">Requirements</span></span>

<span data-ttu-id="62f53-154">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="62f53-154">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="62f53-155">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="62f53-155">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="62f53-156">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="62f53-156">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="62f53-157">참고자료</span><span class="sxs-lookup"><span data-stu-id="62f53-157">See also</span></span>

- [<span data-ttu-id="62f53-158">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="62f53-158">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
