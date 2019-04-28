---
title: Get 함수 (관리 되지 않는 API 참조)
description: Get 함수는 지정된 된 속성 값을 검색합니다.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7534d760f902f80d42c6c20c57a34d52012997a7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61608998"
---
# <a name="get-function"></a><span data-ttu-id="3f0b4-103">Get 함수</span><span class="sxs-lookup"><span data-stu-id="3f0b4-103">Get function</span></span>

<span data-ttu-id="3f0b4-104">존재 하는 경우 지정된 된 속성 값을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b4-104">Retrieves the specified property value if it exists.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="3f0b4-105">구문</span><span class="sxs-lookup"><span data-stu-id="3f0b4-105">Syntax</span></span>

```
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

## <a name="parameters"></a><span data-ttu-id="3f0b4-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3f0b4-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="3f0b4-107">[in] 이 매개 변수 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b4-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="3f0b4-108">[in] 에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="3f0b4-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="3f0b4-109">[in] 속성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b4-109">[in] The name of the property.</span></span>

`lFlags`\
<span data-ttu-id="3f0b4-110">[in] 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b4-110">[in] Reserved.</span></span> <span data-ttu-id="3f0b4-111">이 매개 변수는 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b4-111">This parameter must be 0.</span></span>

`pVal`\
<span data-ttu-id="3f0b4-112">[out] 함수가 성공적으로 반환 하는 경우의 값이 포함 된 `wszName` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b4-112">[out] If the function returns successfully, contains the value of the `wszName` property.</span></span> <span data-ttu-id="3f0b4-113">`pval` 인수는 올바른 형식 및 한정자의 값에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b4-113">The `pval` argument is assigned the correct type and value for the qualifier.</span></span>

`pvtType`\
<span data-ttu-id="3f0b4-114">[out] 함수가 성공적으로 반환 하는 경우 포함 된 [CIM 형식 상수](/windows/desktop/api/wbemcli/ne-wbemcli-tag_cimtype_enumeration) 속성 형식을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b4-114">[out] If the function returns successfully, contains a [CIM-type constant](/windows/desktop/api/wbemcli/ne-wbemcli-tag_cimtype_enumeration) that indicates the property type.</span></span> <span data-ttu-id="3f0b4-115">해당 값을 수도 있습니다 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b4-115">Its value can also be `null`.</span></span> 

`plFlavor`\
<span data-ttu-id="3f0b4-116">[out] 함수가 성공적으로 반환 하는 경우 속성의 원본에 대 한 정보를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b4-116">[out] If the function returns successfully, receives information about the origin of the property.</span></span> <span data-ttu-id="3f0b4-117">해당 값이 될 수 있습니다 `null`, 또는에 정의 된 다음 WBEM_FLAVOR_TYPE 상수 중 하나는 *WbemCli.h* 헤더 파일:</span><span class="sxs-lookup"><span data-stu-id="3f0b4-117">Its value can be `null`, or one of the following WBEM_FLAVOR_TYPE constants defined in the *WbemCli.h* header file:</span></span> 

|<span data-ttu-id="3f0b4-118">상수</span><span class="sxs-lookup"><span data-stu-id="3f0b4-118">Constant</span></span>  |<span data-ttu-id="3f0b4-119">값</span><span class="sxs-lookup"><span data-stu-id="3f0b4-119">Value</span></span>  |<span data-ttu-id="3f0b4-120">설명</span><span class="sxs-lookup"><span data-stu-id="3f0b4-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="3f0b4-121">0x40</span><span class="sxs-lookup"><span data-stu-id="3f0b4-121">0x40</span></span> | <span data-ttu-id="3f0b4-122">속성에는 표준 시스템 속성이입니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b4-122">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="3f0b4-123">0x20</span><span class="sxs-lookup"><span data-stu-id="3f0b4-123">0x20</span></span> | <span data-ttu-id="3f0b4-124">클래스: 속성은 부모 클래스에서 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b4-124">For a class: The property is inherited from the parent class.</span></span> <br> <span data-ttu-id="3f0b4-125">인스턴스: 속성을 부모 클래스에서 상속 하는 동안에 의해 수정 되지 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="3f0b4-125">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="3f0b4-126">0</span><span class="sxs-lookup"><span data-stu-id="3f0b4-126">0</span></span> | <span data-ttu-id="3f0b4-127">클래스: 속성은 파생된 클래스에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b4-127">For a class: The property belongs to the derived class.</span></span> <br> <span data-ttu-id="3f0b4-128">인스턴스: 인스턴스에서; 속성이 수정 됩니다. 즉, 값이 제공 된 또는 한정자를 추가 또는 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b4-128">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="return-value"></a><span data-ttu-id="3f0b4-129">반환 값</span><span class="sxs-lookup"><span data-stu-id="3f0b4-129">Return value</span></span>

<span data-ttu-id="3f0b4-130">이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="3f0b4-130">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="3f0b4-131">상수</span><span class="sxs-lookup"><span data-stu-id="3f0b4-131">Constant</span></span>  |<span data-ttu-id="3f0b4-132">값</span><span class="sxs-lookup"><span data-stu-id="3f0b4-132">Value</span></span>  |<span data-ttu-id="3f0b4-133">설명</span><span class="sxs-lookup"><span data-stu-id="3f0b4-133">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="3f0b4-134">0x80041001</span><span class="sxs-lookup"><span data-stu-id="3f0b4-134">0x80041001</span></span> | <span data-ttu-id="3f0b4-135">일반 오류가 발생이 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b4-135">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="3f0b4-136">0x80041008</span><span class="sxs-lookup"><span data-stu-id="3f0b4-136">0x80041008</span></span> | <span data-ttu-id="3f0b4-137">하나 이상의 매개 변수가 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b4-137">One or more parameters are not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="3f0b4-138">0x80041002</span><span class="sxs-lookup"><span data-stu-id="3f0b4-138">0x80041002</span></span> | <span data-ttu-id="3f0b4-139">지정된 된 속성을 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b4-139">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="3f0b4-140">0x80041006</span><span class="sxs-lookup"><span data-stu-id="3f0b4-140">0x80041006</span></span> | <span data-ttu-id="3f0b4-141">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b4-141">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="3f0b4-142">0</span><span class="sxs-lookup"><span data-stu-id="3f0b4-142">0</span></span> | <span data-ttu-id="3f0b4-143">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b4-143">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="3f0b4-144">설명</span><span class="sxs-lookup"><span data-stu-id="3f0b4-144">Remarks</span></span>

<span data-ttu-id="3f0b4-145">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) 메서드.</span><span class="sxs-lookup"><span data-stu-id="3f0b4-145">This function wraps a call to the [IWbemClassObject::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) method.</span></span>

<span data-ttu-id="3f0b4-146">`Get` 함수 시스템 속성을 반환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b4-146">The `Get` function can also return system properties.</span></span>

<span data-ttu-id="3f0b4-147">합니다 `pVal` 인수는 올바른 형식 및 한정자 및 COM에 대 한 값에 할당 됩니다 [VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) 함수</span><span class="sxs-lookup"><span data-stu-id="3f0b4-147">The `pVal` argument is assigned the correct type and value for the qualifier and the COM [VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) function</span></span>

## <a name="requirements"></a><span data-ttu-id="3f0b4-148">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3f0b4-148">Requirements</span></span>

 <span data-ttu-id="3f0b4-149">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3f0b4-149">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="3f0b4-150">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="3f0b4-150">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="3f0b4-151">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3f0b4-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="3f0b4-152">참고자료</span><span class="sxs-lookup"><span data-stu-id="3f0b4-152">See also</span></span>

- [<span data-ttu-id="3f0b4-153">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="3f0b4-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)